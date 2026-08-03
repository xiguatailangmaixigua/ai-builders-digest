AI Builders Digest — 2026-07-22

> 说明：截至当前抓取时间，feed 最近更新为 2026-07-21 15:10（Asia/Shanghai），尚未出现 7 月 22 日的新来源记录。以下为当前可用的最新内容。

## X / TWITTER

### AI 开发者 Swyx

Swyx 转述 RLM 论文中的一项重要讨论：即使模型没有直接训练在 benchmark 测试集上，也可能通过训练测试集的“相似样本”来定向优化分数。由于 open-weight 模型通常不公开完整数据集和 RL 环境，外部很难判断是否存在这种 benchmark overfitting；论文作者正在尝试用隐藏 trajectory 的 NLP distance metrics 检查模型是否能泛化到具有相同 latent structure 的新任务。

https://x.com/swyx/status/2079411861150429402

### AI 教育创作者 Peter Yang

Peter Yang 分享了一个适用于视频短片等主观任务的 agent workflow：一个 agent 负责生成内容，另一个独立 agent 按 rubric 负责复核和反馈。原因是模型容易产生 self-preferential bias，更愿意给自己的输出宽松评价，独立 verifier 可以降低这种偏差。

https://x.com/petergyang/status/2079257646939742542

### Meta AI 产品负责人 Madhu Guru

Madhu Guru 认为，通往 AGI 的路径会经过大量具有经济价值的任务，因此 enterprise AI 是重要前沿。她还指出，今天真正值得讨论的“tokenomics”已经不是加密货币，而是 open weights 与 closed weights、inference 成本以及 model routing。

https://x.com/realmadhuguru/status/2079369965569003691
https://x.com/realmadhuguru/status/2079227605031829700

### Vercel CEO Guillermo Rauch

Guillermo Rauch 提出，AI 正在让更多工作变成 code：slide deck、design、promo video 和 Excel automation 都可以被看作可生成、可修改、可执行的结构化产物。这个判断意味着 coding agent 的边界正在从软件工程扩展到更广泛的数字工作。

https://x.com/rauchg/status/2079274102129304026

### Box CEO Aaron Levie

Aaron Levie 转述 Cursor 的研究称，在复杂任务中，让 frontier model 负责拆解、规划和关键设计决策，再让更便宜的 workhorse model 执行，整体 token 成本最高可改善 15 倍。真正的效率来自按任务阶段路由不同模型，而不是让最强模型处理每一个 token；这也将成为 applied AI 在 coding、finance、legal 和 healthcare 等领域的核心差异化能力。

https://x.com/levie/status/2079402164988895293

### Builder Zara Zhang

Zara Zhang 分享了一种 AI 时代的招聘流程：第一轮不允许使用 AI，考察领域知识和现场解决问题的能力；第二轮要求候选人必须使用 AI 完成一个没有 AI 很难完成的项目，并同时评估最终结果和与 agent 的聊天记录。她还认为，coding agent 诞生后的公司往往从一开始就保持小团队、项目制协作、个人闭环和极少内部会议。

https://x.com/zarazhangrui/status/2079409165424799889
https://x.com/zarazhangrui/status/2079225776545968166

### 投资人 Nikunj Kothari

Nikunj Kothari 提醒，AI 时代即使传统意义上的 moat 变少，也不代表规模和资本自动成为新的 moat。创始人仍需要找到值得坚持十年以上的独特洞察，不能让融资和组织规模代替产品判断。

https://x.com/nikunj/status/2079328912912355470

## PODCASTS

### No Priors: Travel Through the Lens of AI with Booking.com CEO Glenn Fogel

**一句话结论：** AI 不会简单绕过 Booking 这样的旅行平台，真正的机会在于把复杂的库存、合作伙伴和用户偏好组织起来，让旅行决策变得更容易。

Booking Holdings CEO Glenn Fogel 认为，旅行不是一个只要接入模型就能被自动化的简单品类。平台不仅要处理用户需求，还要连接航空、酒店等合作伙伴的实时库存和复杂规则；AI 的价值是让旅客更容易表达需求，同时让 marketplace 两端都获得更好的结果。

Priceline 的 agentic AI 系统 Penny 已经展示出这一方向：用户可以提出包含家庭成员安排、座位偏好和里程使用方式的复杂需求，Penny 会通过追问逐步澄清。节目中提到，Penny 的采用率连续数月翻倍，并带来更高转化、更快搜索、更短 booking 路径、更低取消率和更高 customer success。

Fogel 还强调，企业需要持续让员工 AI literate，并为未来的变化训练团队。他的判断是：“There is no such thing as a moat.” 今天的竞争优势可能很快消失，长期护城河来自持续理解客户、合作伙伴和行业复杂性的能力。

https://www.youtube.com/watch?v=8nj_0wZkbtA

Generated through the Follow Builders skill: https://github.com/zarazhangrui/follow-builders
