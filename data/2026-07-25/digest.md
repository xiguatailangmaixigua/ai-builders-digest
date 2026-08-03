# AI Builders Digest | 2026-07-25

## X / TWITTER

### Swyx

Swyx 正在内测一个 agentic GitHub clone，并已通过 Workers for Platforms 集成 CI/CD。他表示产品正式上线前还有 3 个想法要实现，目前正处于适合早期参与并影响路线图的阶段。

来源：https://x.com/swyx/status/2080500752183960017

他也特别肯定 Poolside 的开放程度：不只是发布了表现强劲的小模型和研究论文，还公开了完整 eval 数据集，覆盖 6 个公开 benchmark、每项 4 次运行和数百轮交互。关键价值在于，外部研究者可以自行检查模型是否存在 reward hacking，而不用只相信厂商给出的汇总分数。

来源：https://x.com/swyx/status/2080387171723137440

### OpenAI Codex 与 ChatGPT 团队 Thibault Sottiaux

Thibault Sottiaux 把 ChatGPT 桌面端的新体验描述为一种“离开键盘也能继续工作”的方式，并用 Jarvis、Samantha、TARS 等科幻助手作类比。真正值得注意的不是命名玩笑，而是 ChatGPT 正尝试把语音从问答入口变成持续工作的交互层。

来源：https://x.com/thsottiaux/status/2080408012515340394

### AI 实用内容创作者 Peter Yang

Peter Yang 认为 Voice 工作流的下一步，是同时启动多个 ChatGPT Voice 线程，让一组 agent 不仅分别与用户交流，也能彼此协作。他的具体反馈是，多线程任务完成后应主动通知用户；同时，当前中文发音仍有明显改进空间。

来源：

- https://x.com/petergyang/status/2080508139091427741
- https://x.com/petergyang/status/2080505108216111303

### Meta AI 高级总监 Madhu Guru

Madhu Guru 提出了 agent 普及后最容易被低估的企业安全问题：传统 IAM 面向数量有限、生命周期清晰的员工身份设计，但一名员工现在可以创建数百个 agent，agent 还可能继续派生子 agent。企业必须重新回答权限继承、生命周期、子 agent 授权和全链路审计等问题，否则“无限 agent”会迅速突破现有身份治理边界。

来源：https://x.com/realmadhuguru/status/2080315474093760714

他同时提醒，优秀 builder 要理解模型能力参差不齐的“jagged frontier”，优秀 leader 也要理解团队成员能力与状态的类似边界。

来源：https://x.com/realmadhuguru/status/2080460579966501257

### Replit CEO Amjad Masad

Amjad Masad 称 Replit Autoscale Deployments 这一通常最昂贵的扩展环节下降了 80%。他还展示了用 autoresearch agent 研究国际象棋与现代 LLM fine-tuning 的实验，并分享了一个更具产品意义的案例：Viktor 先用 Replit 改造传统 agency，再借助 Replit 团队提供的 MCP，把编码之外的 agency 流程也装进 agent loop，逐步构建自治 agency。

来源：

- https://x.com/amasad/status/2080513361301925957
- https://x.com/amasad/status/2080512523389005894
- https://x.com/amasad/status/2080371567221944657

### Vercel CEO Guillermo Rauch

Guillermo Rauch 宣布，Python 代码在 Vercel 上的启动速度现在自动提升至原来的 2 倍。这是一个直接影响 serverless Python 冷启动体验的基础设施改进，用户无需额外迁移或手动配置。

来源：https://x.com/rauchg/status/2080454509508387251

### Box CEO Aaron Levie

Aaron Levie 认为，AI 最有价值的用法是放大已有专业判断，或加快自己真正想掌握的新领域；既没有判断力、也无意培养判断力的第三类用法，最终大多只会生产 slop。随着工具变强，专业化不会消失，反而可能更重要，因为工程师、设计师等专家更知道如何纠正 agent、评估质量，并把输出真正纳入生产。

来源：https://x.com/levie/status/2080471989060559336

### FirstMark Capital VC、MAD Podcast 主持人 Matt Turck

Matt Turck 把推理速度视为 AI 计算的新瓶颈，并围绕 Cerebras CEO Andrew Feldman 的实践列出一条清晰的问题链：tokens per second 如何影响用户体验，prefill 与 decode 有何差别，SRAM 与 HBM 为什么决定推理性能，agents 又为何会重新拉动 CPU 需求。议题还延伸到 OpenAI 的 750MW 推理合作、TSMC 供应链、CUDA 的护城河，以及更快 token 生成可能怎样改变 SaaS。

来源：https://x.com/mattturck/status/2080333707483725876

### FPV Ventures Partner Nikunj Kothari

Nikunj Kothari 认为，“neo”、full stack、labs、partner、forward deployed 等科技行业标签因过度使用而正在失去信号，RL 也在逐渐走向同样处境。他的批评指向一个常见问题：当定位词被大量复制，真正的产品能力、技术边界和组织差异反而更难判断。

来源：https://x.com/nikunj/status/2080293627784212933

### Claude

Claude Voice mode 正在 public beta 中升级：语音对话可使用包括 Claude Opus 和 Sonnet 在内的更强模型，也能在对话过程中调用用户已连接的 email、calendar 等工具。更新覆盖 mobile、desktop 和 web，并扩展了 Spanish、French、Hindi、Japanese 等语言。

来源：

- https://x.com/claudeai/status/2080376096873177300
- https://x.com/claudeai/status/2080376099268169943

## OFFICIAL BLOGS

### Claude Blog

#### Claude Code now supports artifacts

Claude Code 现在可以把工作过程直接发布为持续更新、可分享的可视化页面，例如 PR walkthrough、系统说明、可筛选 dashboard、事故时间线和 release checklist。artifact 会使用当前 session 的完整上下文，包括代码库、connectors 和对话，因此可以把失败测试、关联函数、监控异常和 root-cause reasoning 汇集在同一个页面中。

它不是一次性导出。每次 publish 都会在同一链接生成新版本，已打开的页面会原地刷新，并保留 version history。官方用一句话概括其低门槛特性：“you don't need to wire up data sources or stand up infrastructure.”

权限方面，artifact 默认仅作者可见，可分享给团队或组织，但不能公开访问；管理员可以通过组织级开关、role-based scoping、retention policy 和 compliance API 管理访问。该功能目前以 beta 形式面向 Claude Team 与 Enterprise 组织，可从 Claude Code CLI 和 desktop app 创建，并在任意浏览器中查看。

来源：https://claude.com/blog/artifacts-in-claude-code

Generated through the Follow Builders skill: https://github.com/zarazhangrui/follow-builders
