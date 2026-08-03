AI Builders Digest — 2026 年 5 月 29 日

数据说明：本期使用 `prepare-digest.js` 拉取的最新中心 feed，来源均为 `origin_main`。`feed-x.json` 生成于 `2026-05-28T07:41:35.372Z`，本批次 X builders 为 0；`feed-blogs.json` 包含 4 篇官方博客；`feed-podcasts.json` 包含 1 期播客。

## X / TWITTER

本批次没有新的 X 动态。

## OFFICIAL BLOGS

### Anthropic Engineering：An update on recent Claude Code quality reports

Anthropic 解释了过去一个月部分用户感到 Claude Code 质量下降的原因。结论不是模型 API 或 inference layer 出问题，而是三个产品层变化分别影响了 Claude Code、Claude Agent SDK 和 Claude Cowork；所有问题已在 4 月 20 日的 `v2.1.116` 解决。

第一个问题是 Claude Code 默认 reasoning effort 的调整。Anthropic 在 3 月 4 日把 Claude Code 默认 effort 从 high 改成 medium，目的是降低高 effort 模式下过长思考导致 UI 像冻结一样的延迟和 token 消耗。但用户反馈说 Claude Code 变得“不够聪明”。Anthropic 最终认为这是错误取舍，并在 4 月 7 日回滚。现在 Opus 4.7 默认 `xhigh` effort，其他模型默认 high effort。

第二个问题是一个缓存优化 bug。Claude 的 reasoning 通常会保留在对话历史里，帮助后续 turn 理解此前为什么做了某些编辑和工具调用。3 月 26 日，Anthropic 试图在 session 空闲超过 1 小时后清理旧 thinking，以降低恢复 session 的 uncached token 成本。设计本应只清一次，但 bug 导致清理在后续每一轮持续发生，使 Claude 逐渐失去此前推理上下文，表现为健忘、重复、奇怪的工具选择，也可能导致 usage limits 更快消耗。这个 bug 在 4 月 10 日的 `v2.1.101` 修复。

第三个问题是 4 月 16 日的一条 system prompt 变更，目的是降低 Opus 4.7 的冗长输出。相关指令要求 tool calls 之间的文本不超过 25 个词，最终回复不超过 100 个词，除非任务需要更多细节。内部测试没有捕捉到回归，但后续更广泛 ablation 发现它让 Opus 4.6 和 4.7 在一个 eval 上下降约 3%，因此 Anthropic 在 4 月 20 日回滚。

后续改进包括：让更多内部员工使用和用户相同的 public build；改进内部 Code Review，让它能跨多个 repo 获取上下文；对 Claude Code 的 system prompt 变更增加更广泛的 per-model eval、逐行 ablation、review/audit 工具、soak period 和 gradual rollout；并通过 ClaudeDevs on X 和 GitHub threads 更集中地解释产品决策。

这篇 postmortem 的重点是：AI 编程产品的质量不只取决于底层模型，还取决于 effort 默认值、缓存策略、context 管理、prompt harness 和发布流程。对 builder 来说，这是一份很实用的 agent 产品运维清单。

链接：https://www.anthropic.com/engineering/april-23-postmortem

### Anthropic Engineering：Scaling Managed Agents: Decoupling the brain from the hands

Anthropic 解释了 Claude Managed Agents 的架构设计：把 agent 拆成 session、harness 和 sandbox 三个相对稳定的接口，让 agent 能在长任务里更可靠地运行，并且适应未来还没出现的 harness 和 sandbox。

他们最初把所有组件都放进一个 container：session、agent harness 和 sandbox 共享同一环境。这样做简单，但会把 container 变成“pet”而不是“cattle”：container 失败时 session 会丢；container 无响应时需要人工排查；工程师要进入 container 调试，但 container 里可能有用户数据。另一个问题是 harness 默认 Claude 要处理的东西就在 container 里，这让连接客户 VPC 或外部基础设施变困难。

最终方案是把“brain”（Claude 和 harness）与“hands”（sandbox 和工具）以及“session”（append-only 事件日志）解耦。harness 不再住在 container 里，而是像调用普通工具一样调用 container：`execute(name, input) -> string`。container 死掉时，harness 把失败作为 tool-call error 交回 Claude；如果 Claude 决定重试，就用标准 recipe 重新 provision 一个 container。harness 自身也可以崩溃后重启，因为 session log 独立存在，新 harness 可以 `wake(sessionId)`、读取事件日志并从最后事件恢复。

安全边界也因此更清楚。在耦合设计里，Claude 生成的不可信代码和 credentials 在同一个 container 里，prompt injection 只要说服 Claude 读取环境变量就可能拿到 token。解耦后，token 不进入 sandbox：Git token 用于初始化 repo 和 remote，但 agent 本身不接触 token；MCP OAuth token 放在 vault，由 proxy 代为调用外部服务。

文章还强调 session 不是 Claude 的 context window。长任务会超过上下文长度，传统 compaction 和 trimming 都会做不可逆取舍；Managed Agents 把 session log 做成 durable context object，让 brain 通过 `getEvents()` 读取事件切片、回看某个动作之前的上下文，harness 再决定怎样整理进模型上下文。

性能收益也很明显。把 brain 和 hands 解耦后，session 不需要一开始就 provision container；只有需要执行时才通过 tool call 创建 sandbox。Anthropic 表示，这让 p50 time-to-first-token 降低约 60%，p95 降低超过 90%。同时，一个 brain 可以连接多个 hands，多个 brain 也可以更容易扩展。

这篇文章的核心判断是：agent infra 会越来越像操作系统设计。好的接口要能承接未来“还没被想出来”的 agent 程序，而不是围绕当前模型能力写死。

链接：https://www.anthropic.com/engineering/managed-agents

### Claude Blog：New in Claude Managed Agents: self-hosted sandboxes and MCP tunnels

Claude Managed Agents 新增两个企业能力：self-hosted sandboxes 和 MCP tunnels。前者让 agent 的工具执行环境运行在客户自己的基础设施或托管 sandbox provider 上；后者让 agent 连接私有网络中的 MCP servers，而不需要把这些服务暴露到公网。

在 self-hosted sandboxes 模式下，agent loop 仍由 Anthropic 基础设施负责 orchestration、context management 和 error recovery，但工具执行移动到企业自己控制的环境里。敏感文件、packages、repositories 和内部服务可以留在企业边界内，网络策略、audit logging、安全工具和 compute sizing 也由企业控制。

Claude 支持的 sandbox provider 包括 Cloudflare、Daytona、Modal 和 Vercel。Cloudflare 提供 microVMs 和 lighter-weight isolates，以及 outbound network control、zero-trust secrets injection、customizable proxies 和内部网络连接能力。Daytona 提供 long-running、stateful、可暂停恢复的 composable computers。Modal 面向 AI workloads，强调 sub-second startup、可扩到几十万并发 sandboxes、按需 CPU/GPU。Vercel sandboxes 强调 VM security、VPC peering、bring your own cloud 和 millisecond startup，并在网络边界注入 credentials，使其不进入 sandbox。

MCP tunnels 则面向私有网络工具连接。企业部署一个 lightweight gateway，建立单个 outbound connection，无需 inbound firewall rules 或公开 endpoint，流量端到端加密。这样内部数据库、私有 API、知识库和 ticketing systems 可以成为 agent 可调用的工具。MCP tunnels 支持 Managed Agents 和 Messages API，并由组织管理员在 Claude Console 的 workspace settings 管理。

这次更新和前一篇 Managed Agents 架构文章是同一条线：agent 的模型循环可以托管，但执行环境、数据边界和私有工具连接越来越需要企业自己控制。

链接：https://claude.com/blog/claude-managed-agents-updates

### Claude Blog：New connectors in Claude for everyday life

Claude 扩展了 connectors：除了工作工具，现在还可以连接 AllTrails、Instacart、Audible、Tripadvisor、Intuit TurboTax 等日常生活应用。Claude directory 自 2025 年 7 月上线以来已经超过 200 个 connectors，覆盖设计、金融、生产力、健康等常用 app。

Claude 的 connectors 不只是“可安装插件”，还开始在对话中动态出现。用户问周末徒步建议时，AllTrails 会浮现并按偏好推荐附近路线；用户可以继续要求更短、更 scenic 或 dog-friendly 的路线，而不用离开对话。当多个 app 都可能有帮助时，Claude 会展示多个选项让用户选择。

这次新增的生活类服务包括 AllTrails、Audible、Booking.com、Instacart、Intuit Credit Karma、Intuit TurboTax、Resy、Spotify、StubHub、Taskrabbit、Thumbtack、Tripadvisor、Uber、Uber Eats 和 Viator。

Anthropic 同时强调，Claude 是 ad-free，没有 paid placements 或 sponsored answers。连接服务后，Claude 代表用户访问该服务；该 app 的数据不会用于训练模型，app 也看不到用户在 Claude 里的其他对话。执行预订或购买前，Claude 设计上会先向用户确认。

这条更新的意义在于：Claude 正在从工作 assistant 扩展成跨生活服务的 conversation router。它不只回答问题，而是在对话里识别任务、推荐合适 connector、再把用户引到具体行动。

链接：https://claude.com/blog/connectors-for-everyday-life

## PODCASTS

### AI & I by Every：We Automated Everything With AI and Tripled Our Headcount

这期是 Every COO Brandon 采访 Every CEO Dan Shipper，讨论 Dan 的文章《After Automation》。核心观点很清楚：Every 是一个高度 AI-native、agent-native 的组织，Slack 里 human 和 agent 都很多，Claude Code、Codex 等工具每天都在用；但从 GPT-3 时代到现在，Every 反而从 4 人增长到 30 人，并且还在继续招聘。

Dan 的解释是：AI 让“昨天的专家能力”变得便宜。代码、写作、设计、决策等过去需要专家才能产出的东西，现在很多人通过 prompt 就能生成。于是组织里会涌出大量“看起来差不多对，但还不完全对”的工作产物：非工程师可以提 PR，工程师可以写文章，运营可以做以前做不了的东西。

这并不会简单消灭专家需求，反而会改变专家工作。专家会更需要搭系统：repo rules、review guidelines、editorial process、agent workflow，把大量半成品推到可用质量。专家也会用 AI 做过去不可能做的东西。Dan 举例说 Every 内部有人在一两个月里做出了完整 inbox，这在过去几乎不可想象。

Dan 反复强调一句话：agent 离人越远，价值越低。AI 很强，但它常常会在完成一段工作后回头问“下一步做什么”。他把 agent 和 agency 区分开：agent 是代表某人行动的系统，可以越来越 autonomous 地完成指定任务；但 agency 是人类甚至小孩拥有的自发欲望、拒绝、玩耍和自我驱动。现在产业激励整体上也在把 AI 做得更 compliant，而不是做成会拒绝用户目标的自主主体。

他们还讨论了 AGI 的一个操作性定义：如果一个 agent 经济上值得一直运行、不需要反复重新 prompt、持续为你生成 token 和完成任务，那可以算一种 AGI。Dan 认为这会发生，但即便发生，也不能假设组织会立刻全面替换人。新技术的吸收速度比人们想象得慢，尤其像客服这种看似最容易被自动化的工作，用户往往明确想找真人；企业如果粗暴自动化，可能很快发现效果不好又把人请回来。

对裁员叙事，Dan 和 Brandon 都比较警惕。他们认为有些公司本来战略、组织或经营就有问题，裁员时会把 AI 当作解释。AI 确实会重组 workflow 和公司结构，但不等于所有工作都原样保留、只是换 agent 做。真正的问题是如何让过渡对人更好，而不是把裁员包装成技术胜利。

后半段还讨论了数据和就业关系。Dan 提到，未来如果员工的工作数据被模型学习，雇佣关系和报酬方式可能也要改变；他提到一种想法：根据某个发布者或人的数据对训练语料的独特贡献来付费，越 generic 的内容越不值钱，越独特、越有贡献的内容越值钱。但他也提醒，数据价值会快速折旧，很多东西几周内就可能过时。

最后，Dan 给出的行动建议很直接：ride the models。每次新模型出来，就学习怎么把它用于自己正在做的工作。你不一定非要参与，但如果你想过更 ambitious 的生活、构建公司或做更好的作品，持续跟上模型会让更多人拥有这种可能性。

链接：https://www.youtube.com/watch?v=dCmOTURRf1Y

## Sources & Metadata

- Markdown export path: `data/2026-05-29/digest.md`
- Generated at: `2026-05-28T21:31:10.931Z`
- Feed source: `origin_main`
- `feed-x.json`: `2026-05-28T07:41:35.372Z`，0 builders，0 tweets
- `feed-blogs.json`: 4 posts
- `feed-podcasts.json`: 1 episode

Generated through the Follow Builders skill: https://github.com/zarazhangrui/follow-builders
