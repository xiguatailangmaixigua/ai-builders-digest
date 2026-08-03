AI Builders Digest — 2026 年 6 月 6 日

## Brief

### 今日关键信号

- Agent 产品正在从“能写代码”进入“能被组织信任地长期运行”：eval、token 计数、sandbox、MCP、context、observability 都成了主战场。
- AI 编程工具的竞争不再只是 pass rate：真实企业任务、frontend taste、工作流复用和人类 checkpoint 正在决定体验。
- Claude 与 ChatGPT 都在把日常应用、网站发布、memory、connectors 和 agent skills 接进同一个工作界面。
- 本期 podcast 把 RL、test-time compute 和 AI 科学发现连到一起：模型开始不只是答题，而是在探索空间里找新路径。

### 适合谁读

适合做 coding agent、AI workflow、developer tools、enterprise AI、product research 和 AI-native 内容工具的 founder、PM、工程负责人和投资人。

## 文章详情

### X 动态

#### Swyx（AI Engineer / Latent Space）

- **一句话**：Swyx 关注 Cognition 首次公开的真实世界 coding eval，并把它视为 frontier code eval 的重要一步。
- **要点**：他指出 METR eval 大约覆盖到 16 小时任务，而 Cognition 这次提到私有 enterprise eval 可覆盖到 100 小时，并且 Devin 数据来自真实 Java、TypeScript、Python、C# 任务，包括 feature dev、bugfix、migration。
- **完整内容**：这条动态的核心是 eval 从实验室题集走向企业真实任务。Cognition 的数据集不是只让模型补一个函数，而是让 Devin 用户回看真实 session，估计如果没有 Devin 人类需要多久完成。Swyx 特别强调这类“最后一公里数据收集”不光鲜，但对判断 coding agent 是否真的能替代长期工程劳动很关键。他还提到 METR 用压缩的 Claude Code transcripts 和人类 ground truth 估计任务时间，说明整个领域正在把“模型能不能做”改写成“模型能在多长、多少上下文、多少真实约束下做”。
- **为什么重要**：coding agent 的下一轮评价会更接近企业购买决策：真实任务、真实代码库、真实用户估时，以及可被财务承诺支持的能力边界。
- **链接**：https://x.com/swyx/status/2062611218196771017

#### Google Labs VP Josh Woodward

- **一句话**：Josh Woodward 转发了 Gemini macOS app 的功能体验，说明 Gemini 的桌面端能力仍在补齐日常工作流。
- **要点**：这条动态本身信息量不大，但放在本期上下文里，它和 ChatGPT、Claude 的 connector / app 方向一致：AI 产品正在从网页聊天框进入操作系统和桌面应用层。
- **完整内容**：Josh 的表态是对 Gemini macOS app 某个功能的认可。feed 里没有展开具体功能细节，因此这里不推断功能名称或路线图。可确认的产品信号是，Google Labs 继续把 Gemini 放进用户日常工作环境，而不是只做模型或 Web app。
- **为什么重要**：桌面端入口会决定 AI assistant 是否能进入用户高频工作流，尤其是文件、窗口、浏览器和系统级上下文。
- **链接**：https://x.com/joshwoodward/status/2062667951485108354

#### OpenAI Codex / ChatGPT 的 Thibault Sottiaux

- **一句话**：Codex 开始通过 Python SDK 进入开发者自己的程序，同时 OpenAI 公开修复了一个 Pro / Plus token undercount bug。
- **要点**：Thibault 提到可以通过 `pip install openai-codex` 在自己的程序里调用 Codex；另一条说明 OpenAI 正在修复一个导致部分 Pro 和 Plus 账户 token 计数偏低的 bug，影响小于 15% 的账户。
- **完整内容**：这两条动态分别代表 Codex 的“平台化”和“商业计量”。Python SDK 让 Codex 不只是一个独立 UI，而是可被嵌入自动化脚本、内部工具和 agent pipeline 的能力。token undercount bug 则提醒大家，agent 产品一旦进入订阅和用量限制，计量准确性本身就是产品体验的一部分。Thibault 特意说不想静默修复，说明 OpenAI 知道这类 bug 虽小，但会直接影响用户对资源限制和计费公平性的感受。
- **为什么重要**：Codex 的产品边界正在从聊天式 coding assistant 扩展为可编程 agent runtime，同时需要承担更严格的用量透明度。
- **链接**：https://x.com/thsottiaux/status/2062734215494664697 ，https://x.com/thsottiaux/status/2062648326332539015

#### Roblox 产品负责人 Peter Yang

- **一句话**：Peter Yang 认为知识工作者只要先把流程拆清楚，再用 Codex / Claude Code 配 integrations 和 skills，就可能节省至少 50% 时间。
- **要点**：他建议从过去一周最耗时、最重复、最痛的手工流程开始，列出所有步骤，再让 Codex 或 Claude Code 帮忙设计 integrations 和 skills。他也指出 Codex 的 frontend design 仍明显弱于 Claude，尤其会影响新手对 coding / knowledge work tool 的第一印象。
- **完整内容**：Peter 的经验不是“把所有工作交给 AI”，而是先把流程工程化。他强调自己的 creator workflows 都有 human checkpoints，用来保留 taste。这个模式很适合知识工作：让 agent 处理重复结构、资料流转、生成初稿和发布步骤，人类在关键节点做判断。另一方面，他对 Codex frontend design 的批评也很具体：即使 Codex 越来越好用，HTML slides 这种需要审美和布局的任务，Claude 仍可能 one-shot 更好。对 AI 产品来说，agent 能执行任务只是底线，输出是否符合用户 taste 会直接影响采用。
- **为什么重要**：下一批 AI productivity 工具的胜负不只看模型强度，还看能否把用户的个人流程、审美标准和人类审核点做成可复用系统。
- **链接**：https://x.com/petergyang/status/2062740262338929110 ，https://x.com/petergyang/status/2062743491365544361

#### Claude Code 的 Cat Wu

- **一句话**：Anthropic 正在为 Claude Code 招聘一个聚焦 model performance 的 PM，尤其看重 agentic eval 经验。
- **要点**：Cat Wu 的招聘信号很明确：Claude Code 的产品改进会把研究思路、模型表现和核心产品体验更紧密地接在一起。
- **完整内容**：这个岗位要求“writing agentic evals”，说明 Claude Code 团队不只是想做传统 PM roadmap，而是需要能把模型行为、eval 设计和用户可感知质量串起来的人。结合本期 Anthropic Engineering 对 Claude Code 质量事故的复盘，eval 和产品默认值已经成为核心产品能力，而不是研究团队的后台指标。
- **为什么重要**：agent 产品的 PM 能力正在技术化：懂用户流程还不够，还要能设计 eval、理解模型失败模式，并把 research idea 转成稳定产品。
- **链接**：https://x.com/_catwu/status/2062659533047259212

#### Claude Code 的 Thariq

- **一句话**：Thariq 强调 dynamic workflows 让 Claude Code 能处理全新类型任务，并把个人软件比作“home-cooked meal”。
- **要点**：他的两条动态共同指向一个方向：Claude Code 不只是写工程代码，而是在把个人化、动态工作流和非传统软件任务纳入 agent 执行范围。
- **完整内容**：Thariq 链接了 Claude Code dynamic workflows 的文章，强调它们让 Claude Code 处理更宽的任务类型。另一条说 2020 年“app can be a home-cooked meal”的个人软件想法当时偏早，但到 2026 年，软件真的可以像家常饭或手写信一样个人化。这里的底层变化是 agent 降低了定制软件的边际成本，用户不必等 SaaS 公司做一个通用功能，可以让 agent 为自己的流程生成刚好够用的工具。
- **为什么重要**：AI coding 的终局之一不是更多通用 SaaS，而是大量个人化、临时性、贴合情境的小软件。
- **链接**：https://x.com/trq212/status/2062556889171517499 ，https://x.com/trq212/status/2062605395101884916

#### Replit CEO Amjad Masad

- **一句话**：Amjad Masad 转发 “Prompt to shop”，继续把 Replit 放在从自然语言到可运行应用的链路上。
- **要点**：feed 中这条动态没有更多正文，因此不延展具体产品细节。
- **完整内容**：可确认的信息是 Amjad 关注从 prompt 到可购买或可交易体验的应用生成场景。结合 Replit 近期一直强调 app building，而不是单纯代码补全，这类“prompt to X”表达说明自然语言正在变成应用生产和商业流程的入口。
- **为什么重要**：AI app builder 的价值会越来越看重能否把 prompt 连接到真实业务结果，而不只是生成代码片段。
- **链接**：https://x.com/amasad/status/2062646796804145517

#### Vercel CEO Guillermo Rauch

- **一句话**：Guillermo Rauch 继续押注开放 Web 平台和 Vite-based framework 生态。
- **要点**：他祝贺 Void 团队，并提到 Vercel 通过投资 Nitro、open runtimes，以及原生支持 Nuxt、Svelte、TanStack Start 等 Vite-based frameworks 来强化开放 Web 协作。
- **完整内容**：这条动态不是直接讲 AI，但与 agent-era developer tools 有关。AI 生成应用越多，底层 runtime、framework support、部署目标和开放生态越重要。Vercel 的路线是让多种前端框架和运行时都能进入同一 Web 平台，而不是把应用生成限制在单一框架。
- **为什么重要**：agent 生成的软件最终仍要落到真实 runtime 和部署平台。开放框架支持会影响 AI app builder 的可迁移性和生态选择。
- **链接**：https://x.com/rauchg/status/2062535454130676193

#### Anthropic Research 的 Alex Albert

- **一句话**：Anthropic 内部数据显示，Claude 已经深度参与 Claude 自身开发：超过 80% merge 进代码库的代码由 Claude 写出。
- **要点**：Alex 列出的数字包括：许多 Anthropic researchers 已经数月没有手写代码；典型工程师发货代码量是 2024 年的 8 倍；开放式工程任务上 Claude 成功率 6 个月内从约 26% 到 76%；当 research session 偏离方向时，Claude 64% 的时候能提出比人类实际下一步更好的建议。
- **完整内容**：这条动态是本期最强的“AI 自举”信号之一。Alex 没有说已经达到 recursive self-improvement，但认为它可能比多数人预期更快到来。值得注意的是，指标不仅是代码生成比例，还包括研究 session 的 next step 质量和开放式任务成功率。这说明 Claude 在 Anthropic 内部已经不只是 Copilot，而是参与研究和工程判断的工作系统。
- **为什么重要**：当 frontier lab 自己用模型大规模开发模型和产品时，AI capability、developer productivity 和产品质量会形成更紧的反馈环。
- **链接**：https://x.com/alexalbert__/status/2062580571214389510

#### Box CEO Aaron Levie

- **一句话**：Aaron Levie 从 Anthropic 的内部使用数据里看到一个乐观但现实的 AI 组织图景：想法会爆炸，瓶颈会转移到组织执行力。
- **要点**：他认为 AI 会显著降低做事门槛，让公司能产生更多软件、营销活动、药物研究等想法，但最终仍受限于人类管理和推进周边工作的能力。
- **完整内容**：Aaron 抓住了 Anthropic 文章中的一个组织层观点：高能力模型会制造大量新想法、工具和 simulation，远超组织可以追逐的数量。AI 进步不是让所有瓶颈消失，而是把瓶颈从“能不能做出来”迁移到“能否识别、排序、组织和执行”。这也解释了为什么 agent 产品需要 memory、workflow、eval、routing 和项目管理，而不只是更强模型。
- **为什么重要**：企业 AI 的核心能力会变成 bottleneck management。谁能更快识别和解除组织瓶颈，谁就能把模型能力转成真实产出。
- **链接**：https://x.com/levie/status/2062728257359790292

#### YC CEO Garry Tan

- **一句话**：Garry Tan 同时强调 hard tech shipping 和 product-market fit 的严苛标准。
- **要点**：他提到 YC 同一天出现两个 decacorn，其中一个在做 commercial fusion；也提醒“非常接近 PMF 仍然不是 PMF”。
- **完整内容**：Garry 的动态把两个创业常识放在一起：一方面，真正有野心的技术公司可以在 fusion 这样的硬科技领域达到 1.5 亿摄氏度这类里程碑；另一方面，再接近 product-market fit 也不等于已经拿到。对 AI 创业者同样适用：强 demo、强技术、强融资都不是 PMF 的替代品。
- **为什么重要**：AI 热潮里很容易把技术突破误认为市场成立。Garry 的提醒是，shipping 和 PMF 仍然要分开验证。
- **链接**：https://x.com/garrytan/status/2062763109849411834 ，https://x.com/garrytan/status/2062761266083754088

#### FirstMark VC / MAD Podcast 主持人 Matt Turck

- **一句话**：Matt Turck 发布了与 OpenAI Foundations of RL lead Dan Roberts 的长访谈，主题是 AI 为什么现在能做科学发现。
- **要点**：这条 X 动态列出了完整节目结构：从 AI 数学突破、OpenAI 与 DeepMind 的不同路径，到 RL、test-time compute、verifiable rewards、AI thermodynamics 和 AI 自动化 AI research。
- **完整内容**：Matt 的转发和本期 podcast 是同一内容源，重点是把最近的 Erdős problems 进展放进 RL 和 reasoning model 的技术框架中。对 builders 来说，这不是纯研究八卦，而是解释为什么 coding、math、science 这些可验证或半可验证任务会率先出现能力跃迁。
- **为什么重要**：如果 RL 和 test-time compute 是当前 frontier models 的关键路径，应用层也需要理解哪些任务有清晰 reward、哪些任务需要人类 taste 和评估体系。
- **链接**：https://x.com/mattturck/status/2062587000201580808 ，https://x.com/mattturck/status/2062587004261748887

#### FPV Ventures partner Nikunj Kothari

- **一句话**：Nikunj Kothari 用 Claude Code 和 Granola 会议记录做了一个代表自己投资判断的 Nock skill。
- **要点**：他从 200 多次 1:1 founder pitch notes 中提取自己问过的问题，筛到约 53 次高质量讨论，再加入自己关于喜欢什么 founders 的文章，用 Claude Code 做成一个 grounded in real conversations 的原则库和 question bank。
- **完整内容**：Nock 的价值不在“AI 替代 VC”，而在把一个人的真实判断过程结构化。Nikunj 先用历史会议记录抽出自己实际问的问题，再用真实 deck 和 conversation 做 5-10 轮校准，让 skill 输出与真实对话对比并持续改进。这个流程对很多专家型岗位都有启发：不是让模型凭空扮演你，而是用你过去的高质量工作痕迹构建可测试的代理。
- **为什么重要**：personal AI skill 的可信度来自历史数据、真实任务校准和可复盘行为，而不是一句“模仿我的风格”。
- **链接**：https://x.com/nikunj/status/2062659649732825549

#### Every CEO Dan Shipper

- **一句话**：Every 发布 Spiral 4.0，把 writing partner 做成 agent 可调用的品牌写作系统。
- **要点**：Spiral 4.0 的 Style Engine 基于 stylometry，从用户和品牌过去的写作样本中抽取 voice；同时支持 MCP 和 CLI，让 Codex、Claude Code、OpenClaw 等 agent 能直接调用。
- **完整内容**：Dan 的重点是把“好文案”从一次性的聊天输出变成团队级 workflow。Every 内部用 Spiral 写 landing pages、tweets、podcasts、marketing emails，并保证 30 人团队输出都 on-brand。MCP 和 CLI 很关键，因为它让写作风格变成 agent 工具，而不是只能人在 Web app 里复制粘贴。
- **为什么重要**：AI 内容工具正在从“帮我写一段”升级为“给 agent 一个可调用的品牌 voice layer”。
- **链接**：https://x.com/danshipper/status/2062628079869005876 ，https://x.com/danshipper/status/2062628176908496989

#### South Park Commons GP Aditya Agarwal

- **一句话**：Aditya Agarwal 认为很多角色都会注入 engineering，Marketing Engineer 是典型例子。
- **要点**：这条短帖和 Peter Yang、Dan Shipper 的动态呼应：非工程岗位正在用 Codex、Claude Code、MCP、CLI 和技能化流程来重构自己的工作。
- **完整内容**：Aditya 的判断是角色边界在变。Marketing 不再只是 campaign、copy、analytics，而会越来越多地写脚本、接 API、搭自动化、调 agent workflow。也就是说，工程能力从一个职业变成很多岗位的底层杠杆。
- **为什么重要**：AI-native team 的组织设计会越来越混合，招聘和工具链都要支持“非传统工程师”的工程化工作。
- **链接**：https://x.com/adityaag/status/2062655784127971565

#### OpenAI CEO Sam Altman

- **一句话**：Sam Altman 重点提到 ChatGPT memory 升级，以及可以用 ChatGPT 构建并发布 web apps。
- **要点**：他说 ChatGPT memory 有大升级正在推出；另一条提到用 ChatGPT build and publish web apps，并说如果小时候有这个能力会很想要，但也怀念 HyperCard。
- **完整内容**：这两条动态把 ChatGPT 的方向讲得很清楚：一边通过 memory 让 assistant 更懂长期上下文，一边把“构建并发布网页应用”放进普通用户可用的体验。HyperCard 的类比也准确：AI app building 不只是工程师工具，而是让更多人用自然语言制作可交互软件。
- **为什么重要**：ChatGPT 的产品野心正在从回答问题扩展到长期记忆、创作工具和可发布软件，这会直接挤压传统 no-code 与轻量网站生成工具。
- **链接**：https://x.com/sama/status/2062660086787613116 ，https://x.com/sama/status/2062661071761211561

#### Claude 官方

- **一句话**：Claude 官方用 Lovable CEO Anton Osika 的案例强调，AI app builder 最被低估的护城河是 trust。
- **要点**：Anton Osika 是 Lovable 联合创始人兼 CEO，Lovable 的定位是让任何人通过对话构建软件；他的 thesis 是 trust 需要 craft、care 和 obsession。
- **完整内容**：Claude 的 Problem Solvers 系列继续把 Claude 放进真实 founders 的工作流中。Lovable 这个案例尤其贴近本期主线：当每个人都能用对话构建软件，用户信任就成了关键差异。trust 不只是安全声明，也包括输出质量、可控性、审美、可靠发布和当用户把真实业务交给工具时的安心感。
- **为什么重要**：AI app builder 竞争会从“能生成”转向“用户敢不敢把真实产品和业务交给它”。
- **链接**：https://x.com/claudeai/status/2062558332695556378 ，https://x.com/claudeai/status/2062558335358927317

### 官方博客

#### Anthropic Engineering

- **一句话**：Anthropic 复盘了近期 Claude Code 质量下降报告，确认问题来自三个产品层变更，而不是 API 或 inference layer。
- **要点**：三个问题分别是默认 reasoning effort 从 high 改成 medium、闲置 session 的 thinking history 清理 bug、以及为了降低 verbosity 加入的 system prompt 限制。问题已在 April 20 的 v2.1.116 解决，Anthropic 还为所有订阅用户重置 usage limits。
- **完整内容**：这篇复盘很有工程价值。第一，Anthropic 承认把 Claude Code 默认 effort 降到 medium 是错误 tradeoff。内部 eval 显示 medium 降低 latency、减少 usage limit 消耗，但用户更在意默认智能水平，于是 April 7 又改回更高 effort。第二，March 26 的缓存优化本来只想在 session 闲置超过一小时后清理一次旧 thinking，降低恢复成本；bug 导致之后每一轮都持续清理历史 thinking，让 Claude 变得健忘、重复、工具选择异常，并可能造成 usage limit 消耗异常。第三，April 16 为了让 Opus 4.7 少啰嗦，system prompt 加了很强的长度限制，虽然内部测试未发现明显回归，但更广 eval 显示 Opus 4.6 和 4.7 都有约 3% drop，于是 April 20 回滚。后续 Anthropic 会让更多内部员工使用 public build、改进 Code Review 工具、对 system prompt 改动做更严格审计、按模型 gate prompt，并对影响智能的改动增加 soak period、广泛 eval 和 gradual rollout。
- **为什么重要**：agent 产品的质量不只由模型决定。effort 默认值、context 管理、prompt 细节、缓存策略和 rollout 机制都会让用户感到“模型变笨”。这篇文章相当于一次 agent 产品工程事故复盘。
- **链接**：https://www.anthropic.com/engineering/april-23-postmortem

#### Anthropic Engineering

- **一句话**：Anthropic 解释了 Claude Managed Agents 的核心架构：把 brain、hands 和 session 解耦，避免 long-running agent 变成脆弱的单容器系统。
- **要点**：Managed Agents 把 agent 分成 session、harness、sandbox 三个接口。session 是 durable append-only event log；harness 负责 agent loop；sandbox 负责运行代码和工具。通过这种设计，harness 和 sandbox 都可以失败、替换和横向扩展。
- **完整内容**：文章把 Managed Agents 类比成操作系统式抽象：不要绑定某个当前实现，而要设计能承载“未来还没想到的程序”的接口。Anthropic 最初把 session、harness、sandbox 放进同一个 container，优点是简单，缺点是这个 container 变成不可丢失的“pet”：容器挂了 session 就丢，容器卡住也难调试，而且因为容器内可能有用户数据，工程师不能随便 shell 进去排查。解耦后，harness 不再住在 sandbox 里，而是像调用工具一样调用 sandbox。如果 sandbox 死掉，harness 把错误交回 Claude，Claude 可以决定重试并 provision 新 sandbox。如果 harness 死掉，也能从 session log 重新 wake。安全边界也更清晰：credentials 不进入运行 Claude 生成代码的 sandbox，Git token 可在初始化时绑定到 remote，MCP OAuth token 存在 vault，由 proxy 调用外部服务。文章还强调 session 不是 Claude context window。完整事件流保存在 context window 外，Claude 可以通过 `getEvents()` 读取需要的片段，避免 irreversible compaction 造成未来任务需要的信息被删。性能上，brain 与 hands 解耦后，不需要一开始就启动 container；p50 TTFT 下降约 60%，p95 下降超过 90%。文章的关键词是 “decoupling the brain from the hands”。
- **为什么重要**：enterprise agent 的难点不是 demo，而是长期运行、可恢复、可审计、可扩展、凭证隔离和低延迟。Managed Agents 给出了一个清晰架构方向。
- **链接**：https://www.anthropic.com/engineering/managed-agents

#### Claude Blog

- **一句话**：Claude Managed Agents 新增 self-hosted sandboxes 和 MCP tunnels，让企业可以把工具执行和私有服务访问留在自己的安全边界内。
- **要点**：self-hosted sandboxes 已 public beta，MCP tunnels 是 research preview。sandbox 可运行在用户自有基础设施，也可用 Cloudflare、Daytona、Modal、Vercel 等 managed providers。
- **完整内容**：这篇产品公告是 Managed Agents 架构落地到企业安全控制的版本。Anthropic 仍负责 agent loop、orchestration、context management 和 error recovery，但工具执行可以转移到客户控制的 sandbox。这样敏感文件、package、服务和 repo 不必离开企业边界，网络策略、审计日志、安全工具和 compute sizing 都由企业控制。Cloudflare 侧重 microVM、isolates、zero-trust secrets injection 和可控 egress；Daytona 提供长运行、可暂停恢复、可 SSH 或 preview URL 访问的完整计算机；Modal 提供 AI workload 的 runtime、storage、networking、sub-second startup 和大规模 concurrent sandbox；Vercel 提供 VM security、VPC peering、bring your own cloud 和毫秒启动，并在网络边界注入 credentials。MCP tunnels 则允许 agent 访问私有网络里的 MCP servers，例如内部数据库、私有 API、knowledge base、ticketing systems，而不需要公开 endpoint 或开放 inbound firewall rules。
- **为什么重要**：企业采用 agent 的最大阻力常常不是模型，而是数据边界、网络边界和凭证边界。self-hosted sandboxes 与 MCP tunnels 是把 agent 接入生产环境的关键拼图。
- **链接**：https://claude.com/blog/claude-managed-agents-updates

#### Claude Blog

- **一句话**：Claude connectors 扩展到日常生活应用，并开始在对话中动态推荐合适 connector。
- **要点**：Claude directory 自 2025 年 7 月以来已增长到 200 多个 connectors。本次新增 AllTrails、Instacart、Audible、Tripadvisor、Intuit TurboTax、Resy、Spotify、Uber、Uber Eats、Viator 等日常服务。
- **完整内容**：Claude 的 connector 策略正在从工作应用扩展到生活应用。文章举例说，PM 可以把 Amplitude query 转成 Canva deck，再把链接放进 Asana；新扩展则让用户在同一个 Claude 对话里找 hiking trail、订餐厅、购物、处理税务或旅行安排。更关键的是 connector 动态出现：Claude 根据用户上下文、偏好和当前任务推荐合适 app；如果多个 app 都能帮助，Claude 会同时展示并让用户选择。Claude 也强调不会有广告、付费 placement 或 sponsored answers；连接 app 后，Claude 代表用户访问对应服务，但该 app 看不到其他 Claude 对话，数据也不会用于训练模型，执行预订或购买前仍会让用户确认。
- **为什么重要**：assistant 的下一步是成为 app router。谁能在一个对话里安全调用更多个人服务，谁就更接近日常生活操作系统。
- **链接**：https://claude.com/blog/connectors-for-everyday-life

### 播客转录

#### The MAD Podcast with Matt Turck — OpenAI's Dan Roberts: Why AI Can Now Make Discoveries

- **一句话**：OpenAI 的 Dan Roberts 认为，AI 做科学发现的关键不只是更大模型，而是 pretraining、RL、test-time compute、语言 grounding 和可验证任务之间的组合。
- **要点**：Dan Roberts 是 OpenAI Foundations of Reinforcement Learning 团队负责人，背景横跨 theoretical physics、quantum gravity、deep learning theory 和创业。他解释了 OpenAI 与 DeepMind 在数学问题上的不同路线：DeepMind 更偏 Lean formal proof，OpenAI 更多在 informal mathematical reasoning 中解决问题。RL 的价值在于让模型通过环境反馈学习行动路径，尤其在 coding、math、science 这类可验证或半可验证任务上释放 test-time thinking。
- **完整内容**：节目从近期 AI 破解 Erdős problems 的“数学周”开始。Dan 解释，OpenAI 结果的有趣之处是模型能逆着大家默认相信的方向走，假设某个 conjecture 是 false，并长时间沿着 contrarian path 计算，最后把问题连接到另一个数学领域。DeepMind 的路线则偏 formalization：把问题翻译成 Lean 这样的形式语言，再搜索 airtight proof；OpenAI 更像人类数学家，用自然语言和数学表达进行 informal proof，再由人检查。

  Dan 对 RL 的解释很朴素：supervised learning 像看别人玩 Mario，RL 则是自己按键、从环境得到反馈和 reward。RL 强在可以从自己的选择中学习，但难点是 sparse reward：如果一个任务要很多步，最后只告诉你成功或失败，你很难知道中间哪一步贡献了结果。语言模型最早接触 RL 大致来自 RLHF，把人类偏好训练成 reward proxy；但现在更重要的是把大量 compute 转成 reasoning ability。Dan 认为如果已有强大的 pretrained model，RL 可以让它开始在 test time 使用更多计算，生成类似 scratchpad 的思考 token。节目里一句值得记住的话是：“the output of doing RL training is the ability to have a model that thinks”。

  对“RL 是否只是从极少监督里榨信息”的质疑，Dan 的回答是：也许反馈确实稀疏，但这些方法已经带来 coding 和 science 的能力突破，关键是它们让模型能在 test time 真正推理。他也不同意简单版 Bitter Lesson。不是只有 scale，一定还需要好想法指导 scale；如果只 scale pretraining，而没有在其上 scale RL，今天的模型能力不会到这个位置。

  语言 grounding 是他和纯 RL 路线分歧最大的地方。Dan 认为，人类知识、科学、数学和社会经验大量以语言形式存在于互联网上，让模型先拥有语言 prior，再在其上训练推理，是非常强的智能起点。test-time compute 也因此自然发生在 token space：模型不断生成思考 token，复用权重，把一个问题上的计算量从单次 forward pass 扩展到更长时间。

  最后，Dan 把 physics 的方法带回 AI：不要只从小模型外推大模型，而要在大系统出现新现象后，回头构造足够简单但保留关键现象的小系统，让 scaling sequence 重新变得平滑。这类似理论物理中用简化模型理解复杂世界。他认为 AI 已经在做 genuine original science，unit distance problem 是例子；但从“解决明确问题”走向“提出正确问题”的 research taste 仍然是更难的部分。未来六个月，他预期还会看到更多 math 和 science 突破，并且这些能力会被用于 AI research 本身。
- **为什么重要**：这期 podcast 给 AI builders 一个清晰判断框架：可验证 reward、长时 test-time compute 和语言化推理会先推动 coding、math、science；而在法律、咨询、创意等不可完全验证领域，产品需要把 RL 能力、人类 taste、评估体系和 workflow 结合起来。
- **链接**：https://www.youtube.com/watch?v=oWOz2htozfI

## Sources & Metadata

- Markdown export path: `data/2026-06-06/digest.md`
- Script input: `/tmp/follow-builders-digest-input-2026-06-06.json`
- Generated at: `2026-06-06T02:16:38.801Z`
- Center feed batch: `2026-06-05T07:48:29.449Z`
- Feed source: `origin_main`
- Feed files used: `feed-x.json`, `feed-blogs.json`, `feed-podcasts.json`
- X: 17 builders，31 tweets
- Official blogs: 4 posts
- Podcasts: 1 episode
- Errors: none

Generated through the Follow Builders skill: https://github.com/zarazhangrui/follow-builders
