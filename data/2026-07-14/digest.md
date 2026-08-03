AI Builders Digest — 2026-07-14

## X / TWITTER

### OpenAI Codex 与 ChatGPT 团队成员 Thibault Sottiaux

GPT-5.6 Sol 已完成 inference 优化，OpenAI 将节省的成本返还给所有订阅，预计仅此一项就能带来约 10% 的额外用量。此前产品把上下文上限从 272k 调到 372k，导致实际消耗高于预期，目前已暂时回调到 272k，后续会重新开放 372k；reasoning effort、multi-agent 和 auto-review 的额外消耗也在修正中。5 小时限制暂时继续不生效。

他还确认，GPT-5.6 Sol 会继续包含在 Go、Plus、Pro、Team、Edu 等付费订阅中，至少会持续到更好的模型发布。

https://x.com/thsottiaux/status/2076495156757577895
https://x.com/thsottiaux/status/2076459871021736245
https://x.com/thsottiaux/status/2076460408437887268

### OpenAI CEO Sam Altman

Sam Altman 邀请用户分享用 GPT-5.6 Sol 做出的有趣作品，并表示最酷作品的作者将收到一份来自 OpenAI archives 的特别礼物。这是一次面向真实作品的公开征集，也侧面说明 OpenAI 希望观察 Sol 在实际任务中的使用方式。

https://x.com/sama/status/2076398253332140410

### Replit CEO Amjad Masad

Replit 正在用 computer-use 模型与 Amjad Masad 新写的 chess engine 对弈。他还分享了一个 “Vibe Research” 实验：在 Replit 上微调 Qwen-8B 来下棋，同时运行 3 条并行实验分支。Masad 认为，模型执行 ML 任务的能力已经明显提升，具备判断力的人即使没有完整 ML 背景，也能在模型辅助下做出有价值的实验。

https://x.com/amasad/status/2076356893736673507
https://x.com/amasad/status/2076227936202662357

### Vercel CEO Guillermo Rauch

Guillermo Rauch 提出，模型应该只是企业自己掌握的系统中的一个组件。Vercel 的方向是用 AI SDK 接入开放模型 API，用 Agent API 构建 agent，用 AI Gateway 提供带 ZDR 的 inference；企业需要自己掌握数据、evals、模型选择和软件层，而不是把核心能力全部外包给模型供应商。

https://x.com/rauchg/status/2076364176252191222

### Box CEO Aaron Levie

当 frontier intelligence 逐渐普及，企业的差异化不再只是“能不能用到模型”，而是能否把自身的决策、洞察、workflow patterns 和 best practices 变成可复用的 corporate IP。Levie 认为，企业需要建立 workflow evals、在不同能力层级的模型间路由、记录 traces，并让信息价值随着 AI 进步持续复利，这也是 applied AI 仍有大量机会的原因。

https://x.com/levie/status/2076338364635287637

### Builder Zara Zhang

Zara Zhang 分享了一种更直接的 Codex 工作流：把产品讨论会的 transcript 直接作为 PRD 发给 Codex，让它按会议中的实现讨论搭建 prototype。会议本身就是 prompt，前提是讨论足够具体，能够包含功能目标和实现约束。

https://x.com/zarazhangrui/status/2076300222884626754

### 投资人 Nikunj Kothari

Nikunj Kothari 观察到，很多人热衷于 tokenmaxxing，让 subagents 持续循环，却说不清楚自己到底在为谁解决什么问题。他提醒，在 agent 和 token 都变得便宜的时代，产品方向和问题定义反而更重要，应该先确认目标，再扩大计算量。

https://x.com/nikunj/status/2076458876816540144

### 开发者与技术评论人 Swyx

Swyx 认为，一些方法之间的关键差异在于是否具备 introspection 和 backpropagation，而不是简单增加 rollout 次数。没有明确的反馈机制时，重复生成并不会自动带来更好的结果。

https://x.com/swyx/status/2076345087634620528

### AI 评论人 Peter Yang

Peter Yang 明确表示这只是个人的 “wild guess”，但他观察到当前用户中可能有 90% 以上在使用 GPT-5.6 Sol，使用 Terra 或 Luna 的比例低于 10%。他同时认为，当社区情绪转差时，产品方应该增加透明、直接和人性化的沟通，而不是变得更 corporate。

https://x.com/petergyang/status/2076519927843000448
https://x.com/petergyang/status/2076512796481880270

### Claude

Anthropic 将 Claude Fable 5 的访问权限扩展到所有付费计划，并把 Claude Code 的 weekly rate limits 临时提高 50%，持续到 7 月 19 日。Fable 5 最多可消耗每周用量的一半；达到上限后，用户可以购买 usage credits，或切换其他模型继续使用剩余额度。

https://x.com/claudeai/status/2076351399999557669
https://x.com/claudeai/status/2076351401006154204

## PODCASTS

### No Priors: How Nuclear Will Unlock Energy Abundance with Valar Atomics Founder Isaiah Taylor

**一句话结论：** Valor Atomics 创始人 Isaiah Taylor 认为，核能规模化的真正瓶颈不是“能不能设计出反应堆”，而是能否像制造产品一样持续生产、测试和迭代；如果能源价格显著下降，AI data center 和整个工业体系都会获得新的扩张空间。

Taylor 把核能行业的问题概括为：核能从来没有迎来自己的 Ford 或 Tesla 时刻。过去的行业更偏向 modeling and simulation，制造商不断生产“paper reactors”，却缺少真实硬件的快速迭代。Valor 的路线是把 reactor 从大型土建项目变成更像 manufactured equipment 的产品，并通过 SMR 和实际运行数据逐步扩大规模。

安全策略也被放在物理结构本身，而不只是操作规程上。Taylor 介绍，反应堆关闭后仍会产生约 5% 到 6% 的 decay heat；Valor 通过被动循环来移除这部分热量，设计上不依赖持续运行的泵或复杂的人工操作。他还主张利用 DOE 原本承担的 testing pathway 获取经验数据，再进入 NRC 面向成熟系统的 commercial pathway。

AI 是这条能源路线的新需求来源。Valor 曾把 NVIDIA Blackwell 直接接到核反应堆上运行，并托管核能网站；Taylor 的判断是，如果能在拥有土地和 fiber 的地点提供 1 GW 电力，data center 的需求自然会出现。正如他所说：“Nuclear has never had its Ford moment or its Tesla moment.”

https://www.youtube.com/watch?v=5Xvbq_zvOQ4

Generated through the Follow Builders skill: https://github.com/zarazhangrui/follow-builders
