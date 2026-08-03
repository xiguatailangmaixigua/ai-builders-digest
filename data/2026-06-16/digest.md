# AI Builders Digest — 2026-06-16

## Brief

### 今日关键信号

- 今天最贴近你账号定位的是 Codex/Claude Code/Agent workflow：Codex 现在能看到并设置自己的 `/goal`，这不是小功能，而是在把“用户意图”变成 agent 可自我维护的任务目标。
- Anthropic 新文章 “How we contain Claude across products” 很值得写公众号：它明确说 human-in-the-loop 并不可靠，因为用户会批准大约 93% 的权限提示。真正的安全思路不是多弹窗，而是限制 blast radius。
- Swyx 提到 Anthropic ultracode：这类 subagent fanout 很会烧 token，但前提是 repo 要能并行化。这个判断和你之前的“长任务怎么跑几个小时不失控”可以接成一组。
- Zara Zhang 的 skill 观点非常适合沉淀到你的项目 memory：不是先写 skill，而是先把事做完、修 20 次，再把经验封装成 skill。
- 企业 AI 主线从“选哪个模型”转向“谁拥有学习闭环”：Satya/Aaron/Swyx 都在强调 learning loop、institutional knowledge、人力资本和 token capital 的复合。
- Jensen Huang 播客把 AI factory 讲成“用电生产 token/intelligence 的工厂”，适合做宏观背景，但不如 Codex `/goal` 和 Claude containment 贴近公众号主线。

### 适合谁读

适合正在用 Codex、Claude Code、Claude Managed Agents、OpenClaw、AI SDK、内部 agent 平台，或者在团队里设计长任务 agent 工作流的工程师、产品负责人和 AI operator。

## 今日公众号候选

| 优先级 | 选题 | 来源 | 为什么适合公众号 |
| --- | --- | --- | --- |
| 高 | Codex 开始自己设 `/goal`：长任务 agent 真正需要的是“目标可维护” | Thibault Sottiaux | 很贴合 Codex 工作流。可以从“你一句话给任务，agent 跑到一半为什么会偏”切入，再讲 `/goal` 是把用户意图变成 agent 自己能读取、更新、校验的目标。 |
| 高 | Claude 为什么不能只靠确认弹窗：用户会批准 93% 的权限请求 | Anthropic Engineering | 痛点强、细节硬、有反直觉。适合写成 agent 安全/权限管理文章，重点是 blast radius，不是泛泛 AI safety。 |
| 高 | Subagent 很强，但前提是你的 repo 能并行化 | Swyx | 和你之前的长任务、MEMORY.md、Fable 5 工作流连续。能落到具体方法：测试、任务拆分、工作树、验证闭环、上下文隔离。 |
| 中高 | 好 skill 不是写出来的，是修出来的 | Zara Zhang | 很适合项目 memory 和公众号短文。可以写成“为什么 skill 管理成本高，因为很多 skill 还没被真实流程打磨过”。 |
| 中高 | 企业真正要买的不是模型，而是自己的 learning loop | Swyx + Aaron Levie + Amjad Masad | 更偏战略，但可以和你之前“不要 token 排行榜，要 outcomes”合并，讲公司怎么把 institutional knowledge 编码进 agent 系统。 |
| 中 | Agentic systems 会把互联网从十亿用户变成千亿 agent | Jensen Huang / Training Data | 宏观叙事强，但离你账号的 Claude/Codex 实操稍远。适合作为开篇背景或次条，不建议单独优先。 |
| 中 | Open weights 会成为企业的 escape hatch | Aaron Levie + Garry Tan | 有热点延续，适合写模型访问限制后的供应风险，但容易变成泛行业评论。 |

## 今日最建议写

**Codex 开始自己设 `/goal`：长任务 agent 真正需要的是“目标可维护”**

这篇最适合接你之前的内容诊断和选题主线。开头可以直接写：

> 很多人用 Codex 跑长任务，失败不是因为模型不会写代码，而是它跑着跑着就忘了“到底要完成什么”。所以 Codex 现在能看到并设置自己的 `/goal`，这不是一个 UI 小功能，而是长任务 agent 的核心能力。

正文建议拆成三段：

1. `/goal` 解决的不是 prompt，而是任务目标在长上下文里的可见性。
2. 让 agent 自己读写 `/goal`，本质是 meta prompting 的泛化：agent 可以基于用户意图整理自己的任务。
3. 这要和验证闭环一起用：目标写得清楚，但没有测试、e2e、review，仍然会变成“认真地跑偏”。

备选第二篇：

**Claude 为什么不能只靠确认弹窗：用户会批准 93% 的权限请求**

这篇更容易有点击，因为它有一个非常具体的数字和反直觉结论。适合从 Claude Code 的权限提示切入，再讲 agent 安全的核心是控制环境、限制损害范围，而不是让用户每一步都点确认。

## X 动态

### Thibault Sottiaux：Codex can see and set its own `/goal`

OpenAI Codex/ChatGPT 团队的 Thibault Sottiaux 说，Codex 现在可以看到并设置自己的 `/goal`。他把这称为 meta prompting 的泛化：让 agent 基于用户意图设置自己的任务。他还补了一句很关键的话：他们构建的每个东西，也会作为 agent 自己能用的工具。

为什么重要：这条非常适合写公众号。长任务 agent 的问题不是“prompt 写长一点”就能解决，而是 agent 需要在执行中持续维护目标、检查目标、必要时重述目标。`/goal` 变成工具后，用户意图开始从一次性输入变成 agent 的运行时状态。

链接：https://x.com/thsottiaux/status/2066270561081454989

### Swyx：ultracode/subagents 很强，但 repo 要先能并行化

Swyx 说，Anthropic ultracode 很会烧 token，但要用好 subagent fanout，前提是 repo 设置得足够适合并行化。他把 subagents 形容成 “subroutines but intelligent”。他的判断是，很多知识工作其实是一层层 yak shave，需要判断力和智能，所以 dynamic workflows 不只是 coding task 的工具。

为什么重要：这条能直接补充你之前的 agent 长任务文章。subagent 不是魔法，真正的问题是：任务能不能拆、状态能不能隔离、验证能不能并行、结果能不能合并。

链接：https://x.com/swyx/status/2066415484149633329

### Zara Zhang：你不是先写 skill，而是最后才把它封装成 skill

Zara Zhang 的两条动态很适合项目方法论：好的 skill 不是一开始写出来的，而是先真的做一件事，修 20 次，然后再把刚刚积累出来的流程和判断封装给 AI。

为什么重要：这和你前面说“skill 管理成本太高”完全对上。不是每个想法都要做成 skill，只有经过真实任务反复修正的流程，才值得固化。

链接：

- https://x.com/zarazhangrui/status/2066394505037926426
- https://x.com/zarazhangrui/status/2066388749244854771

### Aaron Levie：企业机会不在选模型，而在构建 learning loop

Box CEO Aaron Levie 转述并强化了一个观点：真正的机会不是选最好的模型，而是在模型之上构建 learning loop，让人力资本和 token capital 一起复合。企业需要把自己的 unique IP、institutional knowledge 和数据放进能持续学习的架构里，这样即使换掉通用模型，也不会丢掉自己的 “company veteran” 能力。

为什么重要：这可以和 Codex `/goal`、Managed Agents memory、Zara 的 skill 方法论合并成一个更大的主题：agent 系统真正沉淀的是组织学习，而不是某次输出。

链接：https://x.com/levie/status/2066237607244427761

### Aaron Levie / Garry Tan：open weights 可能成为企业的 escape hatch

Aaron Levie 认为，如果某个模型能突然对某些国家、用户或企业不可用，就会逼迫更多国家和企业发展 sovereign AI 或依赖 open weights。Garry Tan 也说，open source 是企业长期控制自己命运的 escape hatch。

为什么重要：这条有行业意义，但公众号最好不要写成泛监管评论。更适合落到“AI 产品架构不能把单一闭源模型当永久基础设施”，也就是模型切换、open weights、私有部署、fallback 都要进入产品设计。

链接：

- https://x.com/levie/status/2066167615618466060
- https://x.com/garrytan/status/2066307697574862905

### Garry Tan：下一代强者会擅长让 long-running multi-stage multi-team agent tasks 工作

YC CEO Garry Tan 说，下一代能改变世界的年轻人，很可能是最擅长让 long-running、multi-stage、multi-team agent tasks 大规模稳定工作的人。

为什么重要：这句话适合放到长任务 agent 系列文章里做结尾。它不是说“会用 AI 的人赢”，而是说能把长流程、多阶段、多团队的 agent 任务跑稳定的人会赢。

链接：https://x.com/garrytan/status/2066269412391637050

### Guillermo Rauch：v0 社区已超过 700,000 skills

Vercel CEO Guillermo Rauch 说，v0 已经超过 700,000 skills，且是社区自然增长。

为什么重要：这说明 skill/ecosystem 正在变成产品竞争的一部分。不过单条信息偏短，适合放在 skill 方法论文章里，不建议单独写。

链接：https://x.com/rauchg/status/2066299732277031042

## 官方博客

### Anthropic Engineering：How we contain Claude across products

Anthropic 这篇文章是今天最值得关注的官方博客。核心结论很直接：随着 Claude 被赋予更高权限，风险不只来自模型犯错概率，也来自它能造成多大 damage。模型越强、访问越多，理论 blast radius 越大，所以工程问题变成：如何限制 agent 的损害范围。

文章里最适合公众号的细节是 human-in-the-loop 的失效。Claude Code 过去通过每一步权限确认来防止 agent 做错事，但 Anthropic 的 telemetry 显示，用户批准了大约 93% 的 permission prompts。提示越多，用户越不认真看。这意味着“让用户每次点确认”不是可靠安全机制。

更好的方向是控制环境和权限边界：给 agent 能完成任务所需的能力，但把它可能造成的损害限制在可接受范围内。文章还提到 Claude Mythos Preview 在 2026 年 4 月因为 blast radius 被认为过高而没有发布，但 Anthropic 预计随着防御者加固系统和 safeguards 成熟，类似能力会逐步适合更广泛发布。

公众号角度：这篇不要写成 “Anthropic 如何做 AI safety”。应该写成“为什么 Claude Code 不能只靠确认弹窗”。读者会更有体感。

链接：https://www.anthropic.com/engineering/how-we-contain-claude

### Anthropic Engineering：Scaling Managed Agents: Decoupling the brain from the hands

Managed Agents 的核心仍然是把 agent runtime 拆成 brain、hands、session。brain 是 Claude 和 harness，hands 是 sandbox 和工具执行环境，session 是 append-only event log。这样容器可以失败，工具环境可以重建，session 仍然保持连续。

今天这篇和 containment 可以放在一起看：一个回答“怎么让 agent 长期运行”，一个回答“怎么让高权限 agent 不把损害扩大”。长任务、工具执行、权限边界，本质上是同一套 agent 操作系统问题。

链接：https://www.anthropic.com/engineering/managed-agents

### Anthropic Engineering：An update on recent Claude Code quality reports

这篇复盘 Claude Code、Claude Agent SDK、Claude Cowork 的质量波动：默认 reasoning effort 调低、idle session old thinking 清理 bug、减少 verbosity 的 system prompt 变化，分别让用户感觉 Claude “变笨、健忘、重复或代码质量下降”。

今天不建议再单独写它，但它可以作为补充证据：agent 体验不是只由底层模型决定，默认参数、session 管理、system prompt、harness 都会改变用户感知。

链接：https://www.anthropic.com/engineering/april-23-postmortem

### Claude Blog：Managed Agents updates / dreaming / Foundation Models

本地补抓里还包含三篇 Claude Blog：self-hosted sandboxes and MCP tunnels、dreaming/outcomes/multiagent orchestration，以及 Claude 接入 Apple Foundation Models framework。

今天这些不是第一优先，但可以分别归入已有主题：

- self-hosted sandboxes and MCP tunnels：企业 agent 的 hands 要留在自己的 perimeter。
- dreaming/outcomes/multiagent orchestration：memory 不是越多越好，需要睡后整理和 rubric 评估。
- Foundation Models framework：端侧小模型和云端 Claude 分工，适合 Apple 开发者向。

链接：

- https://claude.com/blog/claude-managed-agents-updates
- https://claude.com/blog/new-in-claude-managed-agents
- https://claude.com/blog/claude-for-foundation-models

## 播客

### Training Data：LIVE: Jensen Huang on Building the Dynamo of the Intelligence Age

Jensen Huang 把 AI factory 讲成新的工业基础设施：传统 dynamo 把 atoms/motion 转成 electrons，而 AI factory 把 electrons 转成 numbers/tokens/intelligence。他强调 token 不只是文字片段，而是可以重组为语言、数学、蛋白质、物理世界、机器人和自动驾驶控制的 intelligence。

最适合公众号引用的一段是 agentic systems：两年前大家看到的是 ChatGPT 这类输入输出系统，现在 AI 能生成“控制其他工具的智能”，比如控制浏览器、表格、Photoshop、PowerPoint、AutoCAD，未来也会控制机器人和自动驾驶。他还预测未来互联网不只是十亿人使用，而可能会有海量 agents 24 小时工作、彼此交流、代表员工和公司执行任务。

公众号角度：这期适合做宏观背景，不适合今天单独优先写。它可以放进 “为什么 agent workflow 会变成新基础设施” 的开头，用来解释为什么 Codex `/goal`、subagents、containment 都不是小功能，而是 AI factory 之上的操作系统层。

链接：https://www.youtube.com/watch?v=2UpQbeAZuqA

## 今日建议

如果今天只写一篇，我建议写：

**Codex 开始自己设 `/goal`：长任务 agent 真正需要的是“目标可维护”**

原因：

- 它最贴合你的 Claude/Codex/Agent 工作流主线。
- 它不是功能描述，可以写成“长任务为什么跑偏”的实操文章。
- 它能自然合并 Swyx 的 subagent fanout、Zara 的 skill 封装、Garry 的 long-running multi-stage agent tasks。
- 开头容易写得有痛点，不会像简单产品新闻。

第二优先：

**Claude 为什么不能只靠确认弹窗：用户会批准 93% 的权限请求**

这篇更有反直觉和点击点，适合做一篇偏安全/权限管理的 agent 工程文章。

## Sources & Metadata

- Markdown export path: `/Users/zhouqingyi/repos/follow-builders/data/2026-06-16/digest.md`
- Central prepare JSON: `/tmp/follow-builders-digest-2026-06-16-latest.json`
- Central prepare generated at: `2026-06-16 07:06 Asia/Shanghai`
- Central feed generated at: `2026-06-15 16:30 Asia/Shanghai`
- Central feed stats: `podcastEpisodes=1`, `xBuilders=11`, `totalTweets=24`, `blogPosts=0`
- Central feed sources: `x=origin_main`, `podcasts=origin_main`, `blogs=origin_main`
- Local fresh podcast feed: `/tmp/fb-local-2026-06-16-latest/feed-podcasts.json`, generated at `2026-06-16 07:08 Asia/Shanghai`
- Local fresh blog feed: `/tmp/fb-local-2026-06-16-latest/feed-blogs.json`, generated at `2026-06-16 07:08 Asia/Shanghai`, `blogPosts=6`
- Local fresh blog additions used: Anthropic Engineering `how-we-contain-claude`, `april-23-postmortem`, `managed-agents`; Claude Blog `claude-for-foundation-models`, `claude-managed-agents-updates`, `new-in-claude-managed-agents`
- Local fetch limitations: `.env` 当前没有 `X_BEARER_TOKEN`，所以 X 只使用中心 feed；本地 Claude Code Releases 和 OpenAI Codex Releases 抓取超时；Latent Space、The MAD Podcast、AI & I by Every 播客源失败。

Generated through the Follow Builders skill: https://github.com/zarazhangrui/follow-builders
