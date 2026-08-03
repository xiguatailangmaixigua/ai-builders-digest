AI Builders Digest — 2026-07-26

> 数据状态：本次重新拉取成功，但中央 feed 最新生成时间为 2026-07-25 15:03（Asia/Shanghai）。以下为当前最新可用数据版，不代表已经确认的 7 月 26 日新增动态。

## Brief

### 今日关键信号

- **Claude Opus 5 已进入主流工作流竞争**：官方宣布全量付费计划和 API 可用，价格与 Opus 4.8 相同，Fast mode 约为默认速度的 2.5 倍。早期使用反馈同时显示，旧的 skills 和插件工作流可能需要重建。
- **Agent 安全的重点正在从“每一步都确认”转向“限制爆炸半径”**：Anthropic 把 sandbox、VM、文件系统边界和网络出口控制放到产品安全的核心位置。
- **企业 Agent 的价值开始用真实任务指标衡量**：Box 在复杂企业文档任务中测试 Opus 5，尽调、生命科学、法律等场景分别取得 17%、30%、12% 的提升。
- **Agentic commerce 的关键不是聊天，而是减少完成任务的摩擦**：DoorDash 表示，使用 Ask DoorDash 的餐饮搜索中，50% 最终来自用户从未点过的餐厅；杂货订单的购物篮子平均扩大 40%。
- **工作流速度和可持续执行仍是体验瓶颈**：一边是对 1 至 5 分钟等待的强烈反感，另一边是 autoreview skill 已能连续跑到 66 轮重构审查。

## 文章详情

### X 动态

#### Claude Opus 5：能力升级，但工作流兼容性需要重新评估

Claude 官方宣布 Opus 5 已在所有付费计划和 Claude API 上线，定价与 Opus 4.8 相同；它是 Claude Max 的默认模型、Claude Pro 的最强模型，并提供约 2.5 倍速度的 Fast mode。

Dan Shipper 的早期测试提醒，Opus 5 可能不会平滑继承旧模型的 skills、plugins 和复杂工作流：已有流程可能提前停止或漏掉指令，从头重建后反而表现更好，较低 thinking level 也可能比“想得更久”更稳定。

https://x.com/claudeai/status/2080699515271528827
https://x.com/danshipper/status/2080700057892815114

#### Claude Code：少写系统 prompt，多做边界设计

Claude Code 的 Boris Cherny 表示，Opus 5 在代码、数据分析和知识工作中表现突出，尤其关注 prompt injection 防护。Thariq 则透露，新模型已经移除了约 80% 的 Claude Code 系统 prompt，这意味着开发者需要把重点放在清晰的 skills、CLAUDE.md 和运行环境边界上，而不是继续堆叠超长系统指令。

https://x.com/bcherny/status/2080713091688583312
https://x.com/trq212/status/2080710971228918066

#### 企业 Agent：模型升级是否转化为真实业务收益

Box CEO Aaron Levie 分享了 Box AI Agent 的 Complex Work Eval 结果：尽调任务提升 17%，生命科学目标识别提升 30%，法律合同审查提升 12%，技术和医疗任务分别提升 19% 和 13%。这类结果的价值在于，它衡量的是多步骤、非结构化企业文档工作，而不是单轮问答分数。

https://x.com/levie/status/2080704871934931221

#### ChatGPT Work 已面向付费用户全球可用

OpenAI 的 Thibault Sottiaux 表示，ChatGPT Work 已在移动端、Web 和桌面端面向所有付费计划全球开放。它强化的是 ChatGPT 从对话工具走向工作入口的方向。

https://x.com/thsottiaux/status/2080876712439747052

#### Agent 工作流的两个体验指标：等待时间与长任务稳定性

Zara Zhang 认为，当前模型智能已经够用，最影响体验的是每个任务等待 1 至 5 分钟的尴尬区间。Peter Steinberger 则分享，autoreview skill 已在一次复杂重构中完成 66 轮审查，说明 Agent 的价值不只是一次生成，而是能否持续执行、复查和收敛。

https://x.com/zarazhangrui/status/2080829737044439444
https://x.com/steipete/status/2080899298838098034

### 官方博客

#### Anthropic Engineering：How we contain Claude across products

Anthropic 将 Agent 风险分为用户误用、模型误行为和外部攻击，并提出三层防线：运行环境、模型本身以及模型可接触的外部内容。文章提到，Claude Code 用户约 93% 的权限请求都会被批准，频繁确认会造成 approval fatigue；Auto mode 试图自动处理更安全的批准，而 containment 则通过 sandbox、VM 和 egress controls 限制 Agent 的实际触达范围。核心结论是，Agent 越强，越不能只依赖用户逐步监督，必须把权限边界设计成系统能力。

https://www.anthropic.com/engineering/how-we-contain-claude

### 播客转录

#### No Priors：Building an Autonomous Delivery Experience with DoorDash Co-Founders Andy Fang and Stanley Tang

**The Takeaway：** Agentic commerce 的落地重点不是把一个 LLM 塞进产品，而是围绕真实用例重做搜索、推荐、调度、API 和履约系统。

DoorDash 联合创始人 Andy Fang 和 Stanley Tang 分享，Ask DoorDash 让用户用自然语言表达餐饮和杂货需求，餐饮搜索中约 50% 的路径最终导向用户此前没点过的餐厅，杂货购物篮子则扩大约 40%。两人还回顾了从 2018 年开始的 robotics 和 autonomy 探索：最重要的经验是 “build towards a use case”，不要先造技术再寻找问题。DoorDash 每年处理超过 30 亿次、几乎没有两次完全相同的配送，因此未来更可能是人类 Dasher、机器人、无人机和其他自动化方式组成的 multimodal fleet，而不是单一技术替代一切。

https://www.youtube.com/watch?v=vNpcg_Ma-FA

## Sources & Metadata

- Edition: standard
- Feed generated at: 2026-07-25T07:03:44.085Z（2026-07-25 15:03 Asia/Shanghai）
- X: 21 builders, 48 tweets
- Official blogs: 1
- Podcasts: 1
- Feed source: origin/main

Generated through the Follow Builders skill: https://github.com/zarazhangrui/follow-builders
