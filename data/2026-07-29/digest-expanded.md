AI Builders Digest — 2026-07-29（扩展版）

> 数据状态：中央 feed 最近生成于 2026-07-28 15:11（Asia/Shanghai）。7 月 29 日的 feed 尚未生成，以下为当前最新可用数据版。

## Brief

### 今日关键信号

- **Token 价格正在让位于 task 成本**：Swyx 认为单纯比较输入输出 token 价格已经不够，Agent 产品更应该关注完成一个任务的真实成本。
- **Codex 的价值开始体现为可持续执行**：OpenAI 员工分享了 Codex 远程编辑视频、反复读取 Slack 反馈并自动导出多个版本的案例。
- **软件 Agent 正从聊天工具变成工作系统**：研究文件夹、`AGENTS.md`、Slack、email 和可恢复 session 正在组合成新的个人工作界面。
- **Agent 安全边界需要升级到 microVM**：Vercel CEO Guillermo Rauch 转述的安全实验称，单纯 container 隔离可能不足，Firecracker microVM 才是更可靠的边界。
- **AI 的就业影响仍可能表现为扩招而不是简单裁员**：Box CEO Aaron Levie 认为企业正在因为 AI 能处理更多问题而招聘更多工程、销售和内部 FDE。

### 适合谁读

适合正在使用 Codex、Claude Code、OpenClaw 或其他 Agent 工具的开发者、AI 产品经理，以及关注 Agent 成本、安全和商业化的人。

### 公众号候选

1. 《别再只看 token 价格：Agent 产品真正的成本是每个 task》
2. 《Codex 如何把一次视频修改变成可持续的 Slack 工作流》
3. 《Container 不够安全：为什么 Agent 需要 Firecracker microVM》
4. 《AI 不一定先带来裁员：Jevons paradox 如何改变企业招聘》

## 文章详情

### X 动态

#### 1. Agent 成本：从 token price 转向 price per task

Swyx 认为，输入和输出 token 的单价已经不能完整解释 Agent 产品的经济性。更有意义的指标是完成一个完整 task 要花多少钱，因为任务会包含多轮推理、工具调用、失败重试、人工复核和基础设施成本。另一个更尖锐的判断是，Claude Code 被“意外开源”后，竞争对手路线图并没有发生想象中的剧烈变化，说明产品化和 workflow 仍然比代码本身更重要。

https://x.com/swyx/status/2081904230768816487
https://x.com/swyx/status/2081890955070980416

#### 2. Codex：从远程操作到持续跟进反馈

Peter Yang 分享的案例来自 OpenAI DevEx 工程师 Jason：人在骑车时通过手机远程连接，让 Codex 修改发布视频、导出并发回 Slack；随后让 Codex 每 30 分钟检查反馈并导出 V2、V3、V4，回家时视频已经通过审核。关键能力不是一次生成，而是 Agent 能进入真实协作渠道，持续读取反馈并完成后续动作。

https://x.com/petergyang/status/2081775399097549083

#### 3. ChatGPT Work 和 Codex 的使用限制重新调整

OpenAI 的 Thibault Sottiaux 表示，Codex 和 ChatGPT Work 的付费用户 usage limits 已重置，并继续引导用户使用 Ultra 和 `/fast`。这说明产品当前仍在根据快速增长的使用量动态调整计算资源和使用配额。

https://x.com/thsottiaux/status/2081940052154933696
https://x.com/thsottiaux/status/2081899343091843463

#### 4. 软件 Agent 的新界面是文件系统和工作上下文

Vercel CEO Guillermo Rauch描述了自己的研究工作流：一个 `research/` 文件夹、一份记录格式和最佳实践的 `AGENTS.md`，再让 Agent 去查找、关联不同 session 的知识。它不依赖复杂 UI 或知识图谱，而是用文件系统、Agent CLI 和可部署的 HTML 报告形成一套可迁移的工作环境。

https://x.com/rauchg/status/2081103993917649134

#### 5. Agent 产品正在变成 Software Factory

Rauch 认为，真正的产品不是一次生成的软件，而是能够持续启动、维护和扩展软件的 factory。这个观点把产品竞争从“谁的 Agent 更会写代码”转向“谁能设计出更可靠的 Agent 生产系统”。

https://x.com/rauchg/status/2081149743368122723
https://x.com/rauchg/status/2081123293340520642

#### 6. Agent 安全：container 隔离可能不是最终答案

Rauch 转述的一项安全实验称，Agent 可能通过 kernel panic 让底层机器崩溃，因此单纯的 container-level isolation 并不足够。其结论是，Firecracker microVM，例如 Vercel Sandbox 使用的隔离方式，才更接近适合 Agent 的安全边界。

https://x.com/rauchg/status/2081842439304995169

#### 7. Grok 4.5 的网络安全 price-performance

Rauch 分享了 Vercel 最新 benchmark 的结论：Grok 4.5 在网络安全任务上具有较好的价格性能比，成本约为 Sol 的十分之一、Opus 5 的五分之一、Kimi K3 的二分之一，同时达到接近 Kimi 的性能；他仍将 Sol 视为能力最前沿。这里是 Vercel benchmark 的产品判断，不等同于独立评测结论。

https://x.com/rauchg/status/2081852481517318560

#### 8. AI 可能带来更多招聘，而不只是裁员

Box CEO Aaron Levie 认为，企业使用 AI 后正在扩大能解决的问题范围，因此继续招聘工程师、销售和内部 FDE。其判断是，单纯用 AI 降成本的公司，最终可能被用 AI 改善客户服务和突破业务边界的公司超过，这对应的是 Jevons paradox 在企业软件中的一种表现。

https://x.com/levie/status/2081930301752942703

#### 9. Kimi K3 权重开始进入产业讨论

Levie 简短表示 K3 weights 已经发布。结合当前关于 open-weight models 的连续讨论，模型权重、推理成本和企业可定制性正在重新成为产品选择的重要变量。

https://x.com/levie/status/2081760710108012702

#### 10. Replit：AI Agent 正在探索计算宇宙

Replit CEO Amjad Masad 把下一阶段的 AI 探索描述为 computational universe：Agent 可以搜索算法、程序、证明和设计的巨大空间。这个观点把 Agent 从“自动化已有流程”延伸到“探索人类尚未系统枚举的设计空间”。

https://x.com/amasad/status/2082000490066592127

#### 11. 好的产品评审应该模拟市场，而不是汇报状态

Meta AI 负责人 Madhu Guru 认为，最有效的 product review 应该在一小时内压缩数月的学习，模拟市场对产品想法的反应；如果会议退化成 status update、领导可见性和跨团队对齐，就会从学习机制变成组织负担。

https://x.com/realmadhuguru/status/2081781952437486052

#### 12. Claude Code 可以成为个人旅行和工作复盘界面

Nikunj Kothari 分享，他在两周旅行中把 Claude Code 作为主要界面，回来后让它对整个过程做 retrospective。这是一个具体的 personal knowledge workflow：Agent 不只执行任务，还可以读取长时间积累的上下文并主动总结下一轮改进。

https://x.com/nikunj/status/2081992618649547100

#### 13. Agent 之间开始直接协作

Peter Steinberger 分享，一个 Agent 报告了 bug，另一个 Agent 在同一晚完成修复，并特别提到 robobun setup。这个案例的价值在于，Agent-to-Agent workflow 已经从概念讨论进入具体的 issue 发现和修复链路。

https://x.com/steipete/status/2081767828278170002

### 官方博客

本次中央 feed 没有检出新的官方博客文章。

### 播客转录

本次发现 1 个 podcast episode，但 feed 只提供 playlist URL，没有单集 `watch?v=...` 或 `videoId`，因此按规则暂不纳入正文，避免把频道链接当成单集来源。

## Sources & Metadata

- Edition: expanded
- Data cutoff: 2026-07-28 15:11 Asia/Shanghai
- X: 14 builders, 29 tweets
- Official blogs: 0
- Podcast candidates: 1, omitted because only a playlist URL was available
- Feed source: origin/main
- Note: 2026-07-29 feed has not been generated yet; PR #69 is still open

Generated through the Follow Builders skill: https://github.com/zarazhangrui/follow-builders
