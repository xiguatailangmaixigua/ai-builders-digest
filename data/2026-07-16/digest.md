AI Builders Digest — 2026-07-16

## X / TWITTER

### OpenAI Codex 与 ChatGPT 团队成员 Thibault Sottiaux

Thibault Sottiaux 表示，ChatGPT 可能很快达到 900 万用户，并询问是否要再次重置 ChatGPT Work 和 Codex 的用量限制。OpenAI 还发起了 GPT-5.6 Sol 体验征集：用户分享喜欢 Sol 的原因或切换原因，前 1 万名参与者可获得 100 美元 Codex credits。与此同时，他继续收集 ChatGPT Work 的改进反馈。

https://x.com/thsottiaux/status/2077271889626706300
https://x.com/thsottiaux/status/2077248807533003257
https://x.com/thsottiaux/status/2077212009071075330

### Anthropic Claude Code 工程师 Thariq

Thariq 分享了一个用 Claude Code 辅助 Pokemon Champions 的案例：Claude Code 调用 Smogon 的 npm library，抓取实时使用数据，再生成 matchup、breakpoint 和 team theorycraft 报告。这个例子说明，coding agent 的价值不只在写代码，也在于把外部数据、领域规则和分析流程串成一个可重复的研究工具。

https://x.com/trq212/status/2077051280267399550
https://x.com/trq212/status/2077051282146431092

### Vercel CEO Guillermo Rauch

Vercel 正在开放 AI Gateway 的 token flow 数据集，供开发者分析不同模型的使用趋势。Rauch 还介绍了 AgentMail 的安装方式：直接让 agent 执行 `vercel install agentmail`，无需单独注册，支持自动配置和统一计费。

https://x.com/rauchg/status/2077176141790752798
https://x.com/rauchg/status/2077154901013221444

### Box CEO Aaron Levie

Aaron Levie 认为，代码之所以特别适合 agent，是因为结果可以快速通过运行应用或测试验证；但股票交易、合同谈判、销售演示等知识工作，往往只有进入真实世界后才能知道结果。因此，企业接下来需要为更多工作建立 evals，能够判断模型、prompt 或系统变化究竟让流程变好还是变坏。

他还支持建立独立于监管机构的 AI standards body，以更快推进标准制定和行业协作，但前提是产业界先对主要安全风险形成一定共识。

https://x.com/levie/status/2077201458546745553
https://x.com/levie/status/2077043523703243070

### OpenAI CEO Sam Altman

Sam Altman 表示，GPT-5.6 Sol 的增长非常快，inference 团队正在努力扩容，但短期内可能出现一些 hiccups。这个信号说明当前主要瓶颈已经从模型发布转向大规模推理服务的容量和稳定性。

https://x.com/sama/status/2077106587307798989

### Claude

Anthropic 发布 Claude for Teachers，面向 K-12 教育场景。产品不会用教师或学生对话训练模型，学生信息由符合 FERPA 要求的数据处理协议保护；教师还可以让 Claude 连接 Learning Commons，基于州级教学标准和高质量课程材料生成 lesson plan 及学生版教学资料。

https://x.com/claudeai/status/2077047280767488218
https://x.com/claudeai/status/2077047279689535705
https://x.com/claudeai/status/2077047282109714488

### Cursor 设计师 Ryo Lu

Ryo Lu 反思了 AI 对设计和编程工作的影响：模型可以让产出更快，甚至接管一部分过去被视为个人能力证明的工作，但它不能替人决定什么值得热爱。对 builder 来说，真正需要保护的可能不是手工完成每个 artifact 的能力，而是持续产生判断、兴趣和方向的源头。

https://x.com/ryolu_/status/2077162119506833627

## PODCASTS

### Training Data: Anthropic's Katelyn Lesse & Angela Jiang: Building an Ecosystem, not a Walled Garden

**一句话结论：** Anthropic 正在把平台从一个 stateless Messages API，扩展成支持 long-running agents 的模块化基础设施，同时通过开放接口让开发者自由组合自己的运行环境。

Anthropic Platform 同时服务外部开发者和内部产品团队，目标是让 builder 能用 Claude 做出接近 custom software 的产品。随着 agent 开始执行任务、编辑多个系统中的文件，平台需要补齐 sandbox 的治理与安全、可恢复的 transcript session storage，以及 harness engineering。Anthropic 将这些能力封装进更高阶的 Cloud Managed Agents，并继续提供 self-hosted sandboxes、MCP tunnels，以及对 Modal、Vercel、Cloudflare 等基础设施的连接。

团队强调，他们并不要求所有 agent 都运行在 Anthropic 自己的基础设施上，更在意接口和架构是否足够可靠、可扩展。下一层会是 coordination layer，也就是把 token 分配给不同角色的 strategies：有的 token 负责 advising，有的负责 execution，有的负责 grading 或反思。正如团队所说：“the last mile of custom software now in theory should be very, very achievable.”

https://www.youtube.com/watch?v=vPnVTHYplrQ

Generated through the Follow Builders skill: https://github.com/zarazhangrui/follow-builders
