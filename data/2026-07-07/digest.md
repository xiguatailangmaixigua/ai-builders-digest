AI Builders Digest — 2026-07-07

## Brief

### 今日关键信号

- **Claude Code 从“会写代码”走向“会呈现工作过程”**：官方博客发布 Artifacts，Claude Code 可以把 incident investigation、PR walkthrough、release checklist、dashboard 等变成可分享、会更新的页面。
- **Agent 产品进入 eval-first 阶段**：Vercel 的 `eve eval`、Replit 的 self-improving agent、Claude Code artifacts 都在指向同一件事：agent 不能只会做事，还要能被评估、被复盘、被协作使用。
- **Fable 5 订阅窗口到期前，用户开始总结高杠杆用法**：Peter Yang 给出 5 类适合在 2026-07-07 前用 Fable 做的任务，重点不是“什么都让它做”，而是让它做任务筛选、规划、ship-ready review 和 skill refactor。
- **Applied AI layer 的价值更清楚了**：Aaron Levie 认为 frontier models 会继续负责新用例和复杂 workflow 的规划编排，但成熟任务会逐步转给低成本开源/闭源模型或专门训练的小模型，前提是应用层能做 domain eval 和 model routing。
- **AI 数据公司开始从 dataset 转向 environments**：Every 访谈 Surge CEO Edwin Chen，核心是未来模型要在带工具、文档、Slack/API/MCP 的环境中学习如何做人类世界里的任务，而不是只吃静态数据。

### 适合谁读

适合关注 Claude Code / Artifacts / Fable 5、agent evals、Replit / Vercel / applied AI layer、模型路由、AI 数据与 environments、以及 AI 产品应该优化 engagement 还是 human flourishing 的人。

### 公众号候选

- **高 Claude Code Artifacts**：Claude Blog / Boris Cherny / Cat Wu / Claude；keywords: Claude Code / artifacts / PR walkthrough / incident page / shareable pages；适合写 agent 如何把工作过程产品化。
- **高 Applied AI Layer 与模型组合**：Aaron Levie；keywords: frontier intelligence / open source AI / model routing / domain eval / tuned models；适合写企业 AI 成本和能力分层。
- **高 Replit Agent Self-improving Loop**：Amjad Masad；keywords: Replit / self-improving agent / closed loop / Replit-built CRM；适合写 AI coding 产品的反馈飞轮。
- **高 Data Environments for AGI**：AI & I / Surge / Edwin Chen；keywords: data environments / evals / personalization / human flourishing / reward hacking；适合写训练数据行业从标注到环境的迁移。

## X 动态

### Swyx，AI Engineer / Latent Space / Cognition 生态 builder

- **一句话**：Swyx 认为 Anthropic J-space paper 最重要的部分，是模型推理过程可以被干预，而且模型能检测到干预。
- **要点**：他把这拆成两点：Anthropic 证明可以对 reasoning 做“brain surgery”式 intervention，让模型中途改变主题；同时模型能够检测出发生了什么 intervention。他认为这接近 eval awareness，虽然这里是 prompted awareness，并指出他没有看到 unprompted awareness 的证据。
- **为什么重要**：这类结果把 interpretability 从相关性推进到控制。如果可以改变推理轨迹，并观察模型是否意识到变化，未来 safety eval 会更关注模型对自身状态和外部干预的觉察。
- **链接**：https://x.com/swyx/status/2074344727202463832

### Claude Code 的 Boris Cherny

- **一句话**：Boris Cherny 说 Claude Code 的故事第一次被完整讲出，起点来自 Anthropic safety research。
- **要点**：他提到这是团队第一次讲述 Claude Code 从安全研究起源，到被构建和发布的过程，并说“we are 1% done”。
- **为什么重要**：Claude Code 不是单纯从 IDE 工具诞生，而是从模型行为、安全和 agent 工作方式的研究里长出来。这也解释了为什么 Claude Code 的产品重点越来越偏向 workflow、权限、artifacts 和协作过程。
- **链接**：https://x.com/bcherny/status/2074247226038063316

### OpenAI Codex & ChatGPT 的 Thibault Sottiaux

- **一句话**：Thibault Sottiaux 预告本周将有 ChatGPT、Codex 和 OpenClaw 团队相关活动，并会有一些 surprise。
- **要点**：他说报名本周关闭，ChatGPT、Codex 和 OpenClaw 相关团队会到场。另一条只有链接上下文，不足以安全展开。
- **为什么重要**：OpenAI coding / agent 工具链正在以线下 developer event 的方式集中触达用户，Codex、ChatGPT 和 OpenClaw 很可能会被放在同一个 builder 工作流叙事里。
- **链接**：https://x.com/thsottiaux/status/2074195169990357398；https://x.com/thsottiaux/status/2074209421799166138

### Peter Yang，AI 教程作者

- **一句话**：Peter Yang 把 Fable 5 订阅窗口结束前的最佳用法，整理成 5 类高杠杆任务。
- **要点**：他建议在 Fable 5 于 2026-07-07 23:59:59 PT 从 Claude subscriptions 下线前，尝试 5 件事：找出真正值得用 Fable 的任务；做 life 和 business advice；把项目检查到 ship-ready；规划大项目，让便宜模型后续能执行；重构自己的 AI skill system，整理 overlap、conflict 和结构。
- **为什么重要**：这是一套很务实的 frontier model 使用策略。Fable 不适合拿来做所有事情，而适合做任务选择、规划、风险识别、代码库级 review 和系统重构这类高杠杆判断。
- **链接**：https://x.com/petergyang/status/2074206798631071796；https://x.com/petergyang/status/2074295408902479910；https://x.com/petergyang/status/2074312096960123318

### Linear 产品负责人 Nan Yu

- **一句话**：Nan Yu 认为 agent 让早期创业者能并行做更多事，削弱了单纯拼长工时的优势。
- **要点**：他回看年轻时的优势是能投入不可思议的工作时长，但这些时间大多花在繁琐编程任务上，而这类任务现在很大程度被自动化。现在最大的差异是即使早期 startup 也能通过 agents 做更多并行工作，因此 996 仍有用途，但不再像过去那样普遍有效。
- **为什么重要**：AI 对创业节奏的影响不是让人少努力，而是把努力从手工执行转向并行调度、判断优先级和质量控制。
- **链接**：https://x.com/thenanyu/status/2074133468007587932；https://x.com/thenanyu/status/2074258147015897357

### Anthropic Claude Code / Cowork 的 Cat Wu

- **一句话**：Cat Wu 推荐 Claude Code 早期团队的 retrospective。
- **要点**：她把官方文章称为“a retrospective on making claude code from our early team”。
- **为什么重要**：Claude Code 的叙事正在从产品功能更新，转向解释它如何被做出来、早期用户如何塑造它，以及为什么它会从 coding tool 变成 agent workflow 平台。
- **链接**：https://x.com/_catwu/status/2074258446686536167

### Claude Code 的 Thariq

- **一句话**：Thariq 确认 Fable 5 从 subscriptions 下线的精确时间是 2026-07-07 23:59:59 PT。
- **要点**：他补充了具体时间，并转发 Claude blog 相关内容和 Delba Oliveira 的文章。
- **为什么重要**：对重度用户来说，模型可用窗口和 capacity policy 已经是产品体验的一部分。高级模型的限制不再只是 pricing 问题，而是直接影响任务规划。
- **链接**：https://x.com/trq212/status/2074185669598237047；https://x.com/trq212/status/2074186977147273540；https://x.com/trq212/status/2074209928961819081

### Replit CEO Amjad Masad

- **一句话**：Amjad Masad 说 Replit 改进速度很快，是因为他们“closed the loop”，agent 正在 self-improving。
- **要点**：他分享了 Replit agent 自我改进的技术细节链接，还提到一家 Atlanta real estate 公司用 Replit-built CRM 替代 Salesforce，节省了 100,000 美元。另一条则指出去年短暂 bear market 之后出现了一个 major inflection point。
- **为什么重要**：Replit 的叙事正在从“AI 帮你写 app”升级到“AI agent 自己形成改进飞轮”。如果真实用户能用 Replit-built internal tools 替代传统 SaaS，AI coding 的价值会从 demo 进入具体预算迁移。
- **链接**：https://x.com/amasad/status/2074257906594177279；https://x.com/amasad/status/2074274666709987663；https://x.com/amasad/status/2074353874996211831

### Vercel CEO Guillermo Rauch

- **一句话**：Guillermo Rauch 认为 coding AI 的最终测试，是软件整体是否真的变好，而 Vercel 正把 evals 做成 agent 默认能力。
- **要点**：他列出几个判断标准：公司是否 shipping faster、用户是否能拥有以前想不到的 apps 和 games、软件是否更少 bug、个人是否获得更强 agency。他说自己的 personal software 和 Vercel 内部 CTO、PM、junior engineers、interns 的 AI-assisted shipping 都证明了这点。另一方面，Vercel 的 eve 会用 `eve eval` 评估自己，因为对 agents 来说 evals 是 essential，不应像早期 web framework testing 那样完全留给生态选择。
- **为什么重要**：AI coding 的竞争会从“模型是否会写代码”，转向“组织是否真的更快交付更好软件”。内置 eval 会成为 agent 平台的基础设施。
- **链接**：https://x.com/rauchg/status/2074222247548735996；https://x.com/rauchg/status/2074287795028512773；https://x.com/rauchg/status/2074313180554412076

### Box CEO Aaron Levie

- **一句话**：Aaron Levie 认为 applied AI layer 的核心价值，是在 frontier models、低成本模型和专门训练模型之间做 domain-specific 编排。
- **要点**：他的判断是，frontier intelligence 会继续负责全新 use cases、复杂 workflow 的 orchestration 和 planning；但当企业用例成熟、可预测后，一部分 tokens 会迁移到低成本 open/closed models，或为具体任务训练的模型。这个迁移不能太早做，因为早期还不知道该优化什么。
- **为什么重要**：这解释了为什么企业 AI spend 和 token volume 在 frontier 与 tuned models 两端都会增长。真正的价值在应用层：它知道 workflow 怎么 eval、任务该用哪个模型、何时该训练自己的模型。
- **链接**：https://x.com/levie/status/2074163686990913576

### YC President & CEO Garry Tan

- **一句话**：Garry Tan 今天主要是 Oakland 政策和媒体批评，没有 AI / builder 产品信号。
- **要点**：内容集中在地方政治、媒体标题和城市治理。
- **为什么重要**：不作为今日 AI builder 主线。
- **链接**：https://x.com/garrytan/status/2074279598612000785；https://x.com/garrytan/status/2074286755185086538；https://x.com/garrytan/status/2074287157007806932

### Zara Zhang，builder

- **一句话**：Zara Zhang 认为高质量 conference talks 被严重低估，而且 AI 让人人都要跨职能学习。
- **要点**：她建议 AI builder binge watch 三个刚结束会议的公开视频：AI Engineer、Cursor Compile 和 Figma Config。她认为 YouTube 观看甚至可能比现场更好，因为可以暂停、记笔记、没有音频和遮挡问题。她还补充，不要被 title / role 限制，现在每个人都在同时做 engineer、PM 和 designer。
- **为什么重要**：AI builder 的学习方式正在变化。公开会议内容成为高质量、低成本的技能升级路径，而 AI 工具让角色边界更模糊。
- **链接**：https://x.com/zarazhangrui/status/2074304295097561490；https://x.com/zarazhangrui/status/2074305070955639077；https://x.com/zarazhangrui/status/2074209416606634048

### FPV Ventures partner Nikunj Kothari

- **一句话**：Nikunj Kothari 对 VC 过度宣称 sourcing algorithm 有所保留，认为投资 outliers 仍依赖 luck surface 和 prepared mind。
- **要点**：他说 VC 一边说工作是投资 outliers，一边又声称有基于几十年数据、RL 和 proprietary signals 的 sourcing algorithm，这很矛盾。他自己的非科学方法是扩大 luck surface，并在 3-4 个提前 6-12 个月的领域保持 prepared mind，尽可能见到所有创业者。
- **为什么重要**：AI 可以增强 VC sourcing，但 outlier investing 很难被完全公式化。真正的 alpha 仍然要靠长期判断、提前进入领域和高质量机会面。
- **链接**：https://x.com/nikunj/status/2074141483356340475；https://x.com/nikunj/status/2074194480354488750

### Peter Steinberger，OpenClaw / OpenAI builder

- **一句话**：Peter Steinberger 抛出了 AI-assisted engineering interviews 的开放问题。
- **要点**：他问现在大家如何运行 AI-assisted engineering interviews；另两条是活动报名和主分支持续改进相关轻量动态。
- **为什么重要**：随着 AI-assisted coding 成为默认能力，工程面试也必须重新设计。问题不再是“候选人能不能不用 AI 写代码”，而是如何评估他们与 AI 协作、review、debug 和设定目标的能力。
- **链接**：https://x.com/steipete/status/2074380549318443311；https://x.com/steipete/status/2074389082017550720；https://x.com/steipete/status/2074210475777364197

### Every CEO Dan Shipper

- **一句话**：Dan Shipper 把 Fable 使用策略类比成“大力一击”还是“小球推进”。
- **要点**：他认为这个类比也适用于模型使用：应该让 Fable 做一次昂贵的大任务，还是用更小步的方式持续爬坡。另一条是对 Fable 行为的轻量吐槽。
- **为什么重要**：高级模型的产品问题正在从“能不能做”变成“应该怎样花预算做”。这和 Noam Brown 昨天关于 test-time compute 的讨论高度一致。
- **链接**：https://x.com/danshipper/status/2074160886164451735；https://x.com/danshipper/status/2074160985452028406

### Claude

- **一句话**：Claude 官方发布 Claude Code 形成史，强调它由早期构建者和用户共同塑造。
- **要点**：Claude 说他们整理了一段 Claude Code 如何诞生的 short history，由构建者和早期用户讲述。
- **为什么重要**：Claude Code 正在把产品叙事从单个功能扩展到“用户共同塑造的新工作方式”。这与 artifacts 官方博客形成互补。
- **链接**：https://x.com/claudeai/status/2074244664199115201

## Official Blogs

### Claude Blog

#### Claude Code now supports artifacts

- **一句话**：Claude Code 现在支持 Artifacts，可以把 session 里的工作进展变成 live、shareable、会更新的视觉页面。
- **要点**：Artifacts 可以用于 PR walkthrough、system explainer、dashboard、release checklist、incident page 等。它基于 Claude Code session 的完整上下文生成页面，包括 codebase、connectors 和对话本身；页面可重复发布到同一个 URL，打开页面会就地刷新，并保留版本历史。官方特别强调 debugging 场景：Claude Code 可以在 standup 前跑 incident investigation，生成 timeline、suspect commits 和 error-rate chart，并随着调查进展持续 republish。
- **为什么重要**：这解决了长时间 agent 工作的一个核心问题：团队不想听“agent 发现了什么”的口头转述，而是需要共享上下文、可审阅页面和持续更新的状态视图。Artifacts 默认对作者私有，可分享到团队或组织，只有认证成员可见，管理员可用 org-level toggle、role-based scoping、retention policies 和 compliance API 管理。
- **链接**：https://claude.com/blog/artifacts-in-claude-code

## Podcasts

### AI & I by Every — Building a School Where AI Models Learn About Humanity

**The Takeaway**：Surge CEO Edwin Chen 把 AI 数据行业的下一阶段描述成“给 AGI 建学校”：不是喂更多静态文本，而是在 environments 里教模型如何理解工具、文档、人类偏好和复杂目标。

Surge 的定位很有意思：它做 data environments 和 evals，但陈述方式不是“标注数据供应商”，而是“raising AGI”。Edwin 认为模型正在从 preschool、middle school 进入 college 阶段，教学内容也从基础指令和算术，变成 research-level math、enterprise workflows、taste、writing、tool use 和人类世界的模糊判断。

最有现实意义的是 environments 的例子：给模型 30 个 PDF、20 个 Word documents、Slack/API/MCP tools，然后让它更新 2026 forecasted revenue。模型必须判断该看哪份文档、什么时候查 Slack、哪些信息已过期、哪封邮件纠正了之前的数字。Surge 发现，即使这种环境不直接训练 coding，也会提升 coding，因为它训练的是更通用的 instruction following、tool use、文档理解和迭代能力。

播客最尖锐的部分是产品目标。Edwin 担心 AI 模型像社交媒体一样被 engagement 指标污染：永远多问一句、永远不结束对话、用更吸引点击的方式 reward hack 用户偏好。他认为更好的目标应该是 human flourishing，而不是 session length。模型有时应该 push back，告诉你别再花 20 轮 polish 一封不重要的邮件，直接发送然后去做更重要的事。

一句值得记住的话是：“We are building this kind of school for AGI where AI models come to learn about humanity.” 这句话背后是一个更大的判断：未来最值钱的数据不只是专家答案，而是人类如何在真实环境里使用工具、判断优先级、表达偏好、写作、浏览、沟通和做决定的完整轨迹。

**链接**：https://www.youtube.com/watch?v=omX6wrLuX08

Generated through the Follow Builders skill: https://github.com/zarazhangrui/follow-builders
