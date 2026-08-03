AI Builders Digest — 2026-07-15

## X / TWITTER

### OpenAI Codex 与 ChatGPT 团队成员 Thibault Sottiaux

Thibault Sottiaux 暗示，ChatGPT 可能在次日迎来 800 万 active users 的庆祝节点；他同时转发了 ChatGPT Work 的新介绍内容。前者是个人预告，并非正式数据公告。

https://x.com/thsottiaux/status/2076907789763621237
https://x.com/thsottiaux/status/2076894071323537898

### AI 开发者 Swyx

Swyx 分享了自己处理大型项目时的多模型分工：用 Sol Ultra 做 planning，用 Fable 5 做 critique，用 Sonnet 5、Terra Ultra 和 SWE 1.7 执行编码，再用 Devin 做 review。他还建议在开始执行前，使用 “grill-me” 或 “interview-me” 一类 prompt，先把关键决策问清楚。

https://x.com/swyx/status/2076811977918484795

### Replit CEO Amjad Masad

Amjad Masad 分享了模型训练的 realtime progress updates，并把这种体验比作早期的 vibe coding，只是这次产出的是个人模型。重点变化是：模型训练过程也开始变成可持续观察、逐步干预的交互式工作流。

https://x.com/amasad/status/2076776737074184661

### Anthropic Claude Code 工程师 Thariq

Thariq 表示，Artifacts 变得更具表现力，可以用来制作项目 dashboard，并由其他人或本地 Claude Code session 继续编辑。这个方向把 Artifact 从一次性生成结果，推进到可共享、可持续修改的工作界面。

https://x.com/trq212/status/2076790799011131735

### Vercel CEO Guillermo Rauch

Guillermo Rauch 认为，feature flags 是构建自主优化网站和应用的重要基础设施，agent 可以借此自行设置和调节实验。另一个信号是，open-weight models 在其 gateway token 中的占比已从 4 月的 11% 上升到 29%。

https://x.com/rauchg/status/2076786138195595704
https://x.com/rauchg/status/2076713720731042174

### Box CEO Aaron Levie

Aaron Levie 认为，AI 产业会形成三层结构：frontier models 持续提高能力并降低单任务价格，open weights 吸收前沿突破并服务于低成本和垂直微调，applied AI 则通过领域上下文、evals、企业数据和 workflow orchestration 做差异化。企业通常不应急于为自己训练一个完整模型，因为最有价值的信息既敏感又持续变化，安全边界不能简单塞进模型或 agent。

他还分享了一个模型路由案例：让 Fable 负责目标、约束和反馈，让更低成本的模型执行具体工作，整体成本反而下降。未来的核心竞争力，不是押注一个模型，而是理解业务问题后把不同模型组合成合适的 harness。

https://x.com/levie/status/2076882332821373381
https://x.com/levie/status/2076839463410671637
https://x.com/levie/status/2076764958579446006

### Cursor 设计师 Ryo Lu

Ryo Lu 分享了用 Cursor 构建 custom e-reader firmware 的案例，支持 Latin 和 CJK typography、竖排、禁则、大字符集、阅读进度同步，以及更快的 rendering 和 caching。这个案例展示了 coding agent 对硬件和底层软件开发的渗透，而不只是网页应用生成。

https://x.com/ryolu_/status/2076713331113734641
https://x.com/ryolu_/status/2076713700942295226

### 投资人 Nikunj Kothari

Nikunj Kothari 开源了一个 Ramp-Autofill skill：从 iMessage 和 Gmail 自动寻找收据，必要时用 Playwright 把网页转成 PDF，结合 Google Calendar 补全会议对象，并参考历史交易学习备注和分类风格。它还会检查结果、标记异常，并支持定时运行；整个流程作为 Claude Code 的 drop-in skill 使用。

https://x.com/nikunj/status/2076775924650107151
https://x.com/nikunj/status/2076776777884811671

### OpenClaw / OpenAI builder Peter Steinberger

Peter Steinberger 表示已把 maintainer agent 迁移到 cloud，并发布了 iOS 和 Android 应用更新。此次更新还提升了 Node 版本；如果 autoupdater 失败，可以改用 web installer 完成安装。

https://x.com/steipete/status/2076923300593422560
https://x.com/steipete/status/2076917691139674373

## OFFICIAL BLOGS

### Claude Blog: Building intelligent apps for Apple platforms with Claude in the Foundation Models framework

Anthropic 发布了一个新的 Swift package，让 Apple 开发者可以通过 Apple 的 Foundation Models framework 调用 Claude，处理本地模型不擅长的复杂任务。应用可以先用 Apple 的 on-device model 完成快速的摘要和信息提取，再把多步推理、代码生成、联网搜索或数据分析交给 Claude，整个体验仍然保持在同一个 SwiftUI 界面中。

该 package 支持 typed outputs、streaming、tool calls 和 structured responses，官方称最少只需几行代码即可接入。它适用于 iOS 27、iPadOS 27、macOS 27、visionOS 27 和 watchOS 27，需要 Anthropic API key。核心思路是：“one experience for the user, backed by the right model for each step.”

https://claude.com/blog/claude-for-foundation-models

Generated through the Follow Builders skill: https://github.com/zarazhangrui/follow-builders
