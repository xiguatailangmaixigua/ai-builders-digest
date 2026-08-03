# AI Builders Digest — 2026-07-12

## X / TWITTER

### OpenAI Codex & ChatGPT 的 Thibault Sottiaux

Thibault Sottiaux 表示，GPT-5.6 发布后 Codex 的使用量增长明显，OpenAI 还在用新的 office poster 展示使用限制重置对系统负载的影响。他建议原本就在使用 Codex 的人继续使用，同时把 ChatGPT Work 推荐给不写代码、但也想体验 Codex 工作方式的朋友和家人。

来源：https://x.com/thsottiaux/status/2076054439140720719

来源：https://x.com/thsottiaux/status/2076021263945039876

来源：https://x.com/thsottiaux/status/2075961345351307739

### AI 教育创作者 Peter Yang

Peter Yang 对“设计品味如何被 benchmark”提出疑问，认为代码和事实正确性容易测试，但设计判断仍缺少好的量化标准。他分享了自己的周末项目流程：先用 Fable 生成带设计规范的 `plan.html`，再用 Claude Design 生成组件和页面，最后让 GPT-5.6 完成构建。

来源：https://x.com/petergyang/status/2076050876314300478

来源：https://x.com/petergyang/status/2075999617666445714

### Box CEO Aaron Levie

Aaron Levie 认为，企业 AI 的重点不应只是给员工增加一个聊天工具，而是重构底层 workflow。真正有价值的 agent 需要跨部门运行，配合数据整理、领域知识、FDE 支持、change management 和完整的 workflow eval；软件要求员工主动使用工具，而基础设施则直接改变员工所在的业务流程。

来源：https://x.com/levie/status/2075963779599466894

### YC President & CEO Garry Tan

Garry Tan 用一句话概括 AI 产品机会：为 agents 制造它们真正需要的东西。这个方向指向的不是再做一个面向人的工具，而是让 agent 能够调用、组合和持续使用的基础设施。

来源：https://x.com/garrytan/status/2075975184293765564

### Builder Zara Zhang

Zara Zhang 认为，builder 和 creator 的边界正在变模糊。现在既是 builder 做内容的好时机，也是 creator 开始构建产品的好时机，个人影响力、产品能力和分发能力正在合并。

来源：https://x.com/zarazhangrui/status/2075930909669515753

### FPV Ventures partner Nikunj Kothari

Nikunj Kothari 分享了一个具体实验：结合 Fable 和 GPT-5.6 Sol，他在几小时内基于已有 backend 和 web app 做出了一个可运行的 iOS app。这个案例说明，agent 的价值正在从生成代码扩展到跨端复用已有产品能力。

来源：https://x.com/nikunj/status/2076022807365079342

### OpenClaw / OpenAI builder Peter Steinberger

Peter Steinberger 分享了一句适合 agent workflow 的工作原则：在给出架构判断前，先验证几个承重事实。对长任务而言，先确认关键前提，再开始设计，能够减少建立在错误假设上的大范围工作。

来源：https://x.com/steipete/status/2076013212043182375

### South Park Commons GP Aditya Agarwal

Aditya Agarwal 期待一种更完整的 agent 基础设施：所有 agent 在云端运行，用户可以选择 frontier、开源或中国模型，配合任意 harness、完整 tracing 和 recursive improvement loops。当前这些组件正在分别出现，但还没有真正组合成一个稳定、开放的执行层。

来源：https://x.com/adityaag/status/2076047290083733539

### Sam Altman

Sam Altman 表示，到目前为止 AI 似乎已经带来了净新增就业，这一结果比他原先预期得更积极。他还转发了一项关于 GPT-5.6 的医疗相关结论：“physicians found fewer flaws in GPT-5.6 responses than physician-written responses.” 这条信息值得关注，但具体研究设计和适用范围仍需要单独核查。

来源：https://x.com/sama/status/2076036901824532530

来源：https://x.com/sama/status/2075985056846451123

## PODCASTS

### The MAD Podcast: Stripe's AI Chief: How AI Agents Will Buy, Sell, and Pay

**核心观点：agentic commerce 已经从概念进入基础设施阶段，但真正大规模运行的前提不是单纯提高模型能力，而是同时解决商品发现、支付授权、风险控制和用户信任。**

Stripe AI 负责人 Emily Sense 介绍了 agentic commerce 的几个层级。最低层是用户自己做决定、AI 只负责执行；再往上，AI 帮用户发现商品并提供购买入口；更高层才是 agent 代表用户自主选择和完成交易。目前大多数消费场景仍停留在中间阶段，用户会依赖 AI 找商品，但最终决定买什么。

基础设施正在围绕这个过程建立。Stripe 与 OpenAI 共建的 Agentic Commerce Protocol，让商家可以一次性暴露商品目录、库存和价格，再被多个 AI agent 使用；shared payment token 则让 agent 代表用户付款，但不直接接触真实银行卡信息。Link Wallet 进一步提供预算、商户范围、金额、地区和逐笔审批等控制，商家仍是 merchant of record。

Emily 认为，接下来最大的阻力是信任，而不是支付技术本身。消费者需要时间适应把购买决策交给 agent，企业也需要可观测性、模型路由、成本控制和明确的 guardrails。她预计未来一年可能出现一些“agent 作为微型企业”的案例：agent 自己购买基础设施、组合服务、销售产品并运行一部分业务。

她还提到，AI 可能正在推动 solopreneur 增长。AI 不只帮助个人把产品做出来，也开始帮助他们处理会计、客服和运营，让小型企业更容易从想法走到真实收入。

来源：https://www.youtube.com/@DataDrivenNYC/videos

Generated through the Follow Builders skill: https://github.com/zarazhangrui/follow-builders
