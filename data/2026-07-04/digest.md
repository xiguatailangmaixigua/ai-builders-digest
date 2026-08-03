AI Builders Digest — 2026-07-04

## Brief

### 今日关键信号

- **Claude/Fable 线继续升温**：Claude Tag 扩展到更广泛组织用例，Fable 的订阅可用性、额度窗口和未来恢复标准订阅都成为开发者关心的问题。
- **AI infra 开始从模型 API 走向“流量治理”**：Vercel 把 AI Gateway 解释成 Token Delivery Network，并推出 Rules 来动态 rewrite 模型路由，解决模型突然退役、容量紧张和生产流量稳定性问题。
- **企业 agent 落地需要 FDE 和 deployco**：Aaron Levie 明确说，agent 不是直接丢进老流程就能跑，需要清数据、现代化 IT、做 eval、改流程、设计 human-in-the-loop。
- **AI compute 把能源问题重新推到台前**：No Priors 访谈 Valar Atomics，核心论点是核能要从 paper reactor 设计问题变成硬件迭代和制造规模问题，AI 数据中心只是第一波需求信号。

### 适合谁读

适合关注 Claude Code / Claude Tag / Fable、AI Gateway、agent deployment、企业 AI 落地、FDE / deployco、AI compute 电力需求、核能和硬科技制造的人。

### 公众号候选

- **高 Claude Tag 与 Fable 产品化**：Boris Cherny / Cat Wu / Thariq / Claude；keywords: Claude Code / Claude Tag / Fable / Enterprise credits / subscription capacity；适合写 Anthropic 如何把 coding agent 扩散到组织。
- **高 AI Gateway Rules**：Guillermo Rauch；keywords: Token Delivery Network / model rewrite / Fable retired / production traffic / AI Gateway Rules；适合写模型 API 基础设施的生产风险治理。
- **高 企业 Agent 落地为什么需要 FDE**：Aaron Levie；keywords: FDE / deployco / business process / evals / change management / human in the loop；适合写 applied AI 公司的服务化趋势。
- **高 核能与 AI compute**：No Priors / Isaiah Taylor / Valar Atomics；keywords: nuclear / AI compute / hardware iteration / manufactured reactors / energy abundance；适合写 AI 时代的能源基础设施。

## X 动态

### Swyx，AI Engineer / Latent Space / Cognition 生态 builder

- **一句话**：Swyx 今天的重点在 AI Engineer 现场和 AI builder 社群氛围。
- **要点**：他预告 AIE Expo 的 surprise 和 Latent Space 与 Etched 的 live pod，也提到今年 keynote 中最受掌声的一点，是让男性在 hypergrowth 环境里谈情绪和心理健康变得正常。
- **为什么重要**：这不是一个产品发布，但它说明 AI builder 场域的议题正在变宽：除了模型、sandbox、world models，也开始讨论高压增长环境下团队和个人如何长期运转。
- **链接**：https://x.com/swyx/status/2072760421627597198；https://x.com/swyx/status/2072754722059239471；https://x.com/swyx/status/2072722973652660432

### Claude Code 的 Boris Cherny

- **一句话**：Boris Cherny 说 Claude Code 里的 Artifacts 已经改变工作方式，并将扩展到 Pro 和 Max。
- **要点**：他的表述很直接：Artifacts in Claude Code have been life changing，并对扩展到 Pro / Max 表示兴奋。
- **为什么重要**：Claude Code 如果把 artifact 体验扩展到更广泛付费层，可能会让代码、文档、交互式产物和 agent workflow 更自然地合在一个工作面里。
- **链接**：https://x.com/bcherny/status/2072777472970563995

### OpenAI Codex & ChatGPT 的 Thibault Sottiaux

- **一句话**：Thibault Sottiaux 为 GPT-5.6 Sol Ultra 预热，让用户把最难的 prompt 先存起来。
- **要点**：他的原话是 “Stash your hardest prompts somewhere”，信号很明确：新模型会被期待处理当前模型难以稳定完成的高难任务。
- **为什么重要**：模型发布前的开发者预期正在变成一种测试文化。builder 会保留自己的 hard prompts，用来快速判断新模型是否真的跨过能力台阶。
- **链接**：https://x.com/thsottiaux/status/2072607914217320644

### Peter Yang，AI 教程作者

- **一句话**：Peter Yang 给出在 2026-07-07 前最大化使用 Fable 的方法论。
- **要点**：他建议先用便宜模型准备上下文，再让 Fable 做规划，执行则交给其他模型；也可以用 Medium 这类较低 effort，同时人工盯住 Fable 在做什么。他还提到将和 NousResearch 讨论 Hermes 起源、agent memory、真实用例、团队运营和长期差异化。另一条轻量但有趣的用例是，他和女儿用 Codex + image generation 把手绘龙图变成多姿势贴纸并送去打印。
- **为什么重要**：高级模型的用法正在从“全程都用最强模型”变成“把最强模型放在最有杠杆的位置”，也就是用它做任务选择、规划和关键判断。
- **链接**：https://x.com/petergyang/status/2072842766053499353；https://x.com/petergyang/status/2072838004310507975；https://x.com/petergyang/status/2072756657856422379

### Linear 产品负责人 Nan Yu

- **一句话**：Nan Yu 用一句反讽回应多实体协作问题，暗指工作协调系统的重要性。
- **要点**：他说 “If only there were a system of some kind that coordinates work between multiple entities”，上下文来自引用内容，但 feed 中没有足够原文可完整展开。
- **为什么重要**：对 Linear 这样的产品来说，AI agent 增多后，“协调多个实体工作”的系统价值反而更明显。agent 多了，project management 和 issue system 不会消失，只会变成 agent 可读、可写、可追踪的协调层。
- **链接**：https://x.com/thenanyu/status/2072714076614950961；https://x.com/thenanyu/status/2072699613929156660

### Anthropic Claude Code / Cowork 的 Cat Wu

- **一句话**：Cat Wu 把 Claude Tag 定位成跨组织 productivity layer，而不只是工程工具。
- **要点**：她说 Anthropic 内部版本已经落地 65% 的 product PRs，并且 Claude Tag 正在解锁工程、产品、数据、销售、营销等全组织生产力。Anthropic 还给 Claude Enterprise orgs 提供 25,000 美元 credits，给 Claude Team orgs 提供 2,500 美元 credits，可用于 Claude Tag 到 2026-09-01。
- **为什么重要**：Claude Code 到 Claude Tag 的路径，是 coding agent 从个人开发工具扩展到组织协作工具的典型案例。关键问题会从代码能力转向 rollout playbook、安全设计、权限和跨部门 adoption。
- **链接**：https://x.com/_catwu/status/2072731500928508331；https://x.com/_catwu/status/2072743070316257662

### Claude Code 的 Thariq

- **一句话**：Thariq 澄清 Fable 的订阅可用性：2026-07-07 后会从 subscription plans 下线，但 Anthropic 希望在 capacity 允许后尽快恢复为标准订阅的一部分。
- **要点**：他提到已经听到很多关于 Fable availability 的问题，并强调恢复订阅可用性是目标，只是受 capacity 限制。
- **为什么重要**：frontier model 的产品体验越来越受供应约束影响。模型能力强是一回事，能否稳定作为日常订阅模型使用，是另一件事。
- **链接**：https://x.com/trq212/status/2072814903170408784；https://x.com/trq212/status/2072814904210509905

### Vercel CEO Guillermo Rauch

- **一句话**：Guillermo Rauch 把 Vercel AI Gateway 称为 Token Delivery Network，并推出 AI Gateway Rules 做动态模型路由。
- **要点**：他的类比是 CDN：生产系统需要在不重新部署的情况下动态 reroute 或 deny traffic。Fable 突然退役让 Vercel 担心依赖它的生产 workloads，因此他们推出规则能力，可以把 `anthropic/claude-fable-5` 这类源模型动态 rewrite 到另一个目标模型。他还展示了 Vercel Services 的 private connectivity：在 `vercel.json` 中注册 bindings，然后通过 internal URL 让 Node、Python、Dockerfile 等服务互通。
- **为什么重要**：AI app 的生产可靠性不只取决于单个模型。模型退役、GPU capacity 紧张、老版本仍有生产流量，这些都会要求平台层具备路由、降级和治理能力。
- **链接**：https://x.com/rauchg/status/2072741369848746315；https://x.com/rauchg/status/2072715658157027375；https://x.com/rauchg/status/2072711610712330658

### Box CEO Aaron Levie

- **一句话**：Aaron Levie 认为企业 agent 落地的真实难点，是把 AI 系统对齐到底层业务流程和结果。
- **要点**：他指出，大多数企业 workflow 并不是为 agent 直接接入而设计的：数据碎片化、legacy systems 断裂、机构知识没有文档化。要可靠地大规模部署 agent，需要清理数据、现代化 IT、建立 evals、推动 change management、设计 human-in-the-loop，并重新定义公司的 IP。
- **为什么重要**：这解释了为什么 applied AI 公司正在加强 FDE efforts 和推出 deploycos。未来关键岗位不只是模型工程师，也包括能把 AI 嵌入真实业务流程的 FDE。
- **链接**：https://x.com/levie/status/2072875685811716182

### YC President & CEO Garry Tan

- **一句话**：Garry Tan 今天的 tech 主线是继续强调 “It’s time to build”。
- **要点**：其中一条是政治/城市公共事件评论，另一条只有链接上下文不足。可安全提炼的部分，是他继续围绕 build culture 表达立场。
- **为什么重要**：对 YC 生态来说，“build”仍是核心叙事，但今天 feed 中没有足够细节可展开为具体产品或技术判断。
- **链接**：https://x.com/garrytan/status/2072846648854954240；https://x.com/garrytan/status/2072846822566133768；https://x.com/garrytan/status/2072930664962539860

### FirstMark VC Matt Turck

- **一句话**：Matt Turck 发布与 NVIDIA AI 的 Bryan Catanzaro 关于 Nemotron 和 NVIDIA AI lab 的长访谈。
- **要点**：议题包括 open source AI 是否追上 frontier、closed labs 是否通过阻断 distillation 放慢开源、美国是否落后中国、企业为何选择 open models、NVIDIA 为什么自己做模型、Nemotron Nano / Super / Ultra、agent 为什么需要速度、4-bit 训练 550B 模型、Hybrid Mamba-Transformer、Mixture of Experts、NVL72、百万 token context、多 token prediction、多 teacher distillation，以及 NVIDIA 研究组织如何运作。
- **为什么重要**：NVIDIA 已经不只是芯片供应商，它也在通过模型、研究组织和完整 stack 影响 AI infra 的方向。Nemotron 这类开放模型是 NVIDIA 生态绑定 developer 和 enterprise workload 的重要入口。
- **链接**：https://x.com/mattturck/status/2072723410975629364；https://x.com/mattturck/status/2072723415870411232

### Zara Zhang，builder

- **一句话**：Zara Zhang 今天给出三条 agent workflow 经验：AI slop 的根源是没内容、AI 可以重塑学习、群聊比 DM 更适合 agent。
- **要点**：她说 AI slop 的根源不是风格差，而是没有 substance。她还提到一位应届毕业生在学校时把 lecture decks 喂给 AI，让 AI 教材料，而且常觉得 AI 比教授讲得好。第三条是 agent 协作建议：尽量在群里沟通，而不是 DM，因为群聊更容易形成共享上下文。
- **为什么重要**：这三点都指向同一个判断：AI workflow 的质量取决于上下文和内容密度。没有内容，再好的风格也是空；没有共享上下文，agent 也难以稳定协作。
- **链接**：https://x.com/zarazhangrui/status/2072943922385715262；https://x.com/zarazhangrui/status/2072729444943577601；https://x.com/zarazhangrui/status/2072726336158998760

### FPV Ventures partner Nikunj Kothari

- **一句话**：Nikunj Kothari 继续为 SF 的长期 builder 文化辩护。
- **要点**：他说 AGI summer 里很多人像游客一样短暂访问 SF，然后回去说这里没有灵魂、只是 996 和 AI。他的建议是不要用几天或几周判断这个城市，真正花时间待在这里；如果这里不适合你，就回去把自己的地方建设成你想要的样子。他还强调，把人连接到机会本身就很有意义，即使你没有任何直接收益。
- **为什么重要**：AI boom 下，地点和社群仍然重要。对创业者和投资人来说，机会网络、长期信任和非零和连接，仍是技术浪潮之外的基础设施。
- **链接**：https://x.com/nikunj/status/2072780155924480074；https://x.com/nikunj/status/2072684481824309411

### Peter Steinberger，OpenClaw / OpenAI builder

- **一句话**：Peter Steinberger 今天是轻量个人动态，但有一个 adoption 信号：AT&T 代表也每天使用 OpenClaw。
- **要点**：他提到自己与 AT&T 代表沟通 Apple Watch 计划变更时，对方知道并每天使用 OpenClaw。
- **为什么重要**：这条不构成产品发布，但说明 agent 工具的用户面可能正在扩散到意想不到的日常职业场景。
- **链接**：https://x.com/steipete/status/2072744099678212487

### Every CEO Dan Shipper

- **一句话**：Dan Shipper 认为长时间运行的 AI 需要更好的“讲述自己做了什么”的方式。
- **要点**：他提到 Fable 可以连续运行数小时，最后只回来给两段解释，这让他强烈感到需要更好的机制，让 AI 把自己的工作过程讲清楚。
- **为什么重要**：随着 agent 任务变长，用户不只需要最终结果，还需要过程叙事、可追踪中间状态和可信的工作日志。否则长任务会变成黑箱。
- **链接**：https://x.com/danshipper/status/2072805884376301737

### South Park Commons GP Aditya Agarwal

- **一句话**：Aditya Agarwal 今天主要是个人和美国节日相关动态，没有足够 AI / builder 内容可展开。
- **要点**：其中一条是带孩子看 USMNT 比赛后的感受，另一条只有引用回应。
- **为什么重要**：今天不作为 AI builder 信号重点。
- **链接**：https://x.com/adityaag/status/2072879173136474186；https://x.com/adityaag/status/2072735608485945555

### Sam Altman

- **一句话**：Sam Altman 今天是世界杯和美国节日相关轻量动态，没有 AI 产品或技术信号。
- **要点**：内容是观看美国队在美国生日周赢球的体验。
- **为什么重要**：不作为今日 AI 主线。
- **链接**：https://x.com/sama/status/2072773542576586790

### Claude

- **一句话**：Claude 官方把 Claude Tag、Fable 5 和 life sciences hackathon 放在同一天推进。
- **要点**：Claude 发布 Boris Cherny 和 Cat Wu 的对谈，讲从 Claude Code 到 Claude Tag 的路径，以及它如何从工程扩展到 Anthropic 其他部门，并确认 Claude Fable 5 现在可用于 Claude Tag。Claude 还宣布 Built with Claude: Life Sciences 全球虚拟 hackathon，将与 Gladstone Institutes 合作，时间为 2026-07-07 到 2026-07-13，奖池为 100,000 美元 credits，面向 Claude Science 和 Claude Code 构建。
- **为什么重要**：Anthropic 正在把 Claude 的用途拆成几个垂直入口：coding、组织协作、science/life sciences。Fable 5 加入 Claude Tag，也强化了高级模型在企业内部 agent workflow 中的作用。
- **链接**：https://x.com/claudeai/status/2072725610061803522；https://x.com/claudeai/status/2072681853971001849；https://x.com/claudeai/status/2072681856730792282

## Podcasts

### No Priors — How Nuclear Will Unlock Energy Abundance with Valar Atomics Founder Isaiah Taylor

**The Takeaway**：Isaiah Taylor 的核心观点是，核能复兴不是再写一份更漂亮的 reactor design，而是把核电变成硬件迭代、制造和规模化部署问题。

Valar Atomics 的叙事和 AI compute 直接相连。Taylor 说，能源是 commodity，需求由价格决定，只要能把 energy 做得更便宜，就会自动诱发更多需求。AI 数据中心让大家重新意识到 power 的重要性，但他的野心更大：用制造化、极安全、可批量生产的核反应堆，把人类能源成本降低 10 倍甚至更多。

他最反对的是 “paper reactor” 文化。传统核能创业公司往往用 modeling 和 simulation 试图绕过监管和实证数据问题，而 Valar 选择先把东西造出来、打开、运行、积累数据。Taylor 把关键指标叫 tick rate，也就是从一次 reactor criticality 到下一次的时间间隔。Valar 从成立到第一次 split atom 用了两年四个月，从 Project Nova 到 Ward 250 又用了约七个月，目标是最终缩短到分钟级。

安全观也很重要。他区分了两种风险降低方式：降低事故发生概率，或降低事故后果。Valar 选择从后果端设计，让系统即使所有 safety systems 都失败，也不会向公众或工人造成 radiation dose。他们计划演示 scram 后关闭全部电力和安全系统，只依靠物理几何、材料和 passive circulation 处理 decay heat。

最有力的一句话是：“Energy is the fundamental input to the quality of human life.” 如果 AI 和机器人把人力投入逐步转化为 energy input，那么更便宜的能源会让制造、运输和物质生活成本系统性下降。对 AI 行业来说，这意味着 compute 的边界最终会撞到能源，而能源技术本身会成为 AI 时代的核心基础设施。

**链接**：https://www.youtube.com/watch?v=5Xvbq_zvOQ4

Generated through the Follow Builders skill: https://github.com/zarazhangrui/follow-builders
