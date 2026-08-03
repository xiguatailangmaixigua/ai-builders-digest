# AI Builders Digest — 2026-08-03

> **数据说明**：上游中央 feed 最近生成于 2026-08-02 15:09（Asia/Shanghai）。本期为当前最新可用数据版，主要覆盖 8 月 2 日动态。

## X / TWITTER

### Andrej Karpathy

Andrej Karpathy 用《指环王》第一段文本、约 100 万 token 预算和 Three.js 测试 Opus 5。模型运行约两小时，写出约 5500 行代码，程序化生成了一个可渲染的故事世界，展示了长任务耐力和低成本定制世界的潜力；但模型仍难以高效观看视频或实际玩自己生成的游戏，因此无法自主完成可靠的视觉和交互审计。

https://x.com/karpathy/status/2083749667410727319

### Swyx

Swyx 推荐了一场“fighting slop with slop”的演讲，并提到 AI-native programming language 的方向。他认为，与其单纯反对 AI 生成的低质量代码，不如从编程语言和代码运行机制的第一性原理出发，重新思考如何让系统更能容忍和利用 AI 生成内容。

https://x.com/swyx/status/2083753582160191988

### Thibault Sottiaux（OpenAI Codex 与 ChatGPT 团队）

Thibault Sottiaux 预告，工作日主题是效率，周末则将迎来“10 个重大科学突破”，并表示“会有迹象”。原帖没有透露具体模型、产品或研究名称，因此目前只能作为发布信号跟踪，不能当作已发布功能。

https://x.com/thsottiaux/status/2083556636455752050

### Peter Yang

Peter Yang 认为 Opus 4.6 是人格和写作风格最好的 Opus 模型，而 Opus 5 更容易给出过长回答，频繁使用固定的“Claude 式”表达，并显得更具评判性。这是一条个人体验反馈，但对模型升级后的语气、默认长度和对话亲和力有参考价值。

他还反馈了 OpenAI plugins 的问题：尝试将自己的 `/no-ai-slop` skill 作为 plugin 发布时，遇到了影响用户体验的 bug。

https://x.com/petergyang/status/2083755374994415904

https://x.com/petergyang/status/2083594381748302160

### Nan Yu（Linear 产品负责人）

Nan Yu 提议，用户可以为自己提交的 issue 或开源仓库 issue 质押 token；维护者接受后，GitHub 将把 issue 原样交给云端 coding agent，费用由发起者承担。这个机制试图让需求方为 agent 工作付费，同时减少低质量 PR。

他还展示了一个持续工作的 issue loop：agent 在 issue 下留言并附上完整上下文，用户补充细节、解除阻塞后，agent 自动继续工作。这比一次性生成代码更接近真实的软件协作流程。

https://x.com/thenanyu/status/2083722999430050281

https://x.com/thenanyu/status/2083534333428580501

### Guillermo Rauch（Vercel CEO）

Guillermo Rauch 分享了一个开源 agentic CRM：模型无关、可自托管或无服务器部署，支持多渠道，并提供 headless 形态，构建在外链项目和 Next.js 之上。原帖没有展开项目名称和实现细节，因此这里只保留明确可确认的信息。

https://x.com/rauchg/status/2083684679362965605

### Aaron Levie（Box CEO）

Aaron Levie 判断，AI 在个人生活和日常生产力中的提升，与数学、科学、法律、编程等深领域的提升会逐渐分化。消费场景的需求相对容易达到“够用”，但专业领域的能力上限更高，模型进步还需要落到专业数据集和工作流中，最终才可能转化为生命科学、现实自动化和网络安全方面的突破。

https://x.com/levie/status/2083589132660711452

### Garry Tan（Y Combinator CEO）

Garry Tan 认为，2026 年的一个重要变化是 OpenAI 更像一个开放平台：提供可直接调用的智能，而不是要求开发者把产品完整整合进 OpenAI 的全栈体系。这是他的战略观察，不是 OpenAI 的正式产品公告。

https://x.com/garrytan/status/2083684825333105107

### Nikunj Kothari

Nikunj Kothari 用一个反差概括当前市场：模型已经开始解决 NP-hard 问题，但传统企业仍在质疑 token 投入的 ROI。他据此认为，未来数十年重要的工作之一会是推动模型能力在企业中的扩散。

https://x.com/nikunj/status/2083502573546263002

### Peter Steinberger

Peter Steinberger 分享了两个 agent 进入真实设备工作流的实验：让 agent 帮忙安装 Gmail 工具，以及把 agent 接入 ESP32 设备和摄像头，端到端测试语音唤醒。这些是个人实验，不能证明工具稳定性，但说明 agent 正从代码仓库和桌面软件进入邮件、嵌入式硬件和摄像头等环境。

https://x.com/steipete/status/2083759812970786997

https://x.com/steipete/status/2083694161933594703

## OFFICIAL BLOGS

### Anthropic Engineering：How we contain Claude across products

Anthropic 复盘了 claude.ai、Claude Code 和 Claude Cowork 如何限制 agent 的潜在破坏半径。文章将防御拆成三层：环境层用 sandbox、虚拟机、文件系统边界和网络出口控制限制 agent 能访问什么；模型层用提示词、分类器、探针和训练调整降低危险行为概率；外部内容层则把 MCP、插件、网页搜索和工具返回内容视为潜在 prompt injection 来源。

文章还总结了三种隔离方式：claude.ai 的临时容器、Claude Code 的人工监督与本地 sandbox、Claude Cowork 的本地虚拟机。Telemetry 显示用户约 93% 的权限提示会被批准，说明人工审批存在 approval fatigue；Claude Code 的 OS-level sandbox 曾让权限提示减少 84%。文章的核心原则是：“The deterministic boundary is what gets hit when everything probabilistic misses.”

https://www.anthropic.com/engineering/how-we-contain-claude

## PODCASTS

### No Priors：Building an Autonomous Enterprise for Real-World Services with Netic Founder Melisa Tokmak

**The Takeaway：** AI 在现实世界最先大规模落地的地方，可能不是替代现场技工，而是接管 HVAC、管道、电气、汽车和宠物服务企业背后的客户沟通、需求判断、人员调度和预约运营。

Netic 创始人 Melisa Tokmak 将公司定位为服务现实世界企业的 AI 基础设施：“Netic builds AI to run millions of real world businesses that keep the world running.” Agent 可以通过电话、短信或网站与客户交互，理解设备、故障、时间、客户价值和人员技能，再决定由谁、何时、以什么方式提供服务。节目中提到，超过 70% 的 Netic 客户已经是 AI-first，客户与企业的第一次互动由 Netic agent 完成。

这类业务的难点不在普通客服，而在 mission-critical workflow：服务需求具有季节性，现场人员有限，企业必须同时优化响应速度、客户体验、利润率和技工调度。嘉宾认为，AI 真正的下一个未解问题，是让系统在关键业务中自主执行，而不只是充当 copilot。机器人取代现场人员仍需要更长时间，因为现实环境中的灵巧操作和客户面对面的情绪互动都很复杂。

https://www.youtube.com/watch?v=wWbX3NL6_Uo

Generated through the Follow Builders skill: https://github.com/zarazhangrui/follow-builders
