AI Builders Digest - 2026-06-22

## Brief

### 今日关键信号

- Agent 产品的竞争焦点从“会聊天”转向 harness、权限、审计、上下文和长任务。
- 模型正在吞掉一部分 agent harness，应用层需要把护城河转向垂直场景和工作流。
- Headless software 会让 agent 使用企业软件的频率远超人类，平台要重新设计 guardrails。
- AI coding 已经让个人 app、移动 app 和内部工具的构建速度明显上升。
- 高质量输出的关键不是更短 prompt，而是更长、更真实、更有约束的 context。

### 适合谁读

适合 AI coding、agent infra、企业 SaaS、AI 产品设计、开发者平台、内容生成和个人软件创业方向的读者。

### 公众号候选

- **高 Model eats the harness**：Logan Kilpatrick / Google DeepMind; keywords: agent harness / Gemini / Antigravity / AI Studio; 可写 agent 平台护城河迁移。
- **高 Agent 会 100X 使用软件**：Aaron Levie; keywords: headless software / guardrails / audit / enterprise data; 适合企业 AI SaaS 视角。
- **高 Context 不是 prompt**：Zara Zhang / Garry Tan; keywords: context engineering / personal brain / company brain / AI slop; 可写高质量 AI 工作流。
- **中 HTML 是 agentic video 的基础**：Peter Yang; keywords: HTML / CSS / JavaScript / video agent; 适合 AI 视频生产工具文章。
- **中 AI Studio 生成 35 万 Android app**：Training Data / Logan Kilpatrick; keywords: Android / vibe coding / personal software; 可写个人软件爆发。

## 文章详情

### X 动态

#### Thibault Sottiaux

- **一句话**：OpenAI Codex 团队在主动收集 app 体验反馈，尤其是 usage resets 和“不够 delightful”的部分。
- **要点**：他问用户在 Codex 可以积攒 usage resets 后，是会囤着不用还是放心使用；也直接征集 Codex app 应该改进什么。
- **完整内容**：这说明 Codex 当前不只是模型能力迭代，也在调使用配额、心理负担和产品细节。usage resets 的“banking”会影响用户是否敢把 Codex 当高频工作流，而不只是偶尔调用的工具。
- **为什么重要**：AI coding 产品的瓶颈正在从能力扩展到日常使用体验，包括额度、等待、反馈、信任和交互摩擦。
- **链接**：https://x.com/thsottiaux/status/2068792010715324444, https://x.com/thsottiaux/status/2068736857312198928

#### Peter Yang

- **一句话**：Peter Yang 把两条 agent 趋势放在一起：tokenmaxxing 和用 HTML 做 agentic video。
- **要点**：他把 unlimited token plans 下“尽量烧满 token”的心理称为 tokenmaxxing；同时转述 Liu Bin 的观点：HTML 是 LLM 的原生语言，因此适合让 agent 表达视频里的视觉结构。
- **完整内容**：在视频 agent 方向，他引用的核心判断是 agent 没有天然视觉智能，所以要转向 code。HTML、CSS、JavaScript 能同时表达信息、视觉美学、素材、图片、SVG 和交互层，适合作为产品视频生成的中间表示。他还推荐 Ferryman 这类跨平台分发工具，说明内容生产链路正在被 AI 和自动化重塑。
- **为什么重要**：这给 AI 视频工具一个务实路径：不要直接让模型“看懂视频”，先让模型生成可控的 Web 表达，再渲染成视频。
- **链接**：https://x.com/petergyang/status/2068874249167884544, https://x.com/petergyang/status/2068854663534031124, https://x.com/petergyang/status/2068755908319236338

#### Linear Head of Product Nan Yu

- **一句话**：Nan Yu 用“Quality is irrational”解释高质量产品背后的非理性承诺。
- **要点**：他认为持续选择质量、从头到尾控制体验，而不是默认使用通用框架，需要一种非理性的投入和自信。
- **完整内容**：这条观点不是 AI 特定，但对 AI 产品尤其 relevant：当生成和模板化越来越便宜，真正能拉开差距的反而是对细节、默认行为和端到端体验的坚持。
- **为什么重要**：AI 产品容易因为“能生成”而变粗糙，质量控制会成为品牌和留存的分水岭。
- **链接**：https://x.com/thenanyu/status/2068778750800531640

#### Vercel CEO Guillermo Rauch

- **一句话**：Guillermo Rauch 强调性能细节和 coding agents 带来的 IKEA effect。
- **要点**：Vercel 团队优化了站点性能，包括 painting、layout、WebGPU shaders、blocking scripts，并会更新相关 lessons learned；他还说 coding agents 会最大化用户的 IKEA effect。
- **完整内容**：性能优化那条展示的是工程端的持续打磨，agent 那条则指出一个产品心理：当用户和 coding agent 一起构建东西，用户会更强烈地感到“这是我做出来的”，从而提升参与度和成就感。
- **为什么重要**：AI coding 不只是省时间，也改变用户和软件之间的所有权感。
- **链接**：https://x.com/rauchg/status/2068838709517336756, https://x.com/rauchg/status/2068778558672273422

#### Box CEO Aaron Levie

- **一句话**：Aaron Levie 提出两个关键判断：agent 会 100 倍于人类使用软件，多模型路由层会产生巨大价值。
- **要点**：他认为 agent 使用企业软件后，需要防数据泄露、防误改、权威数据源、日志、审计、人机协作等 guardrails；同时他评价 Sakana 的 Fugu 是把模型选择、委派、验证和综合封装成单一 API 的方向。
- **完整内容**：Levie 的核心是 headless software：当 CRM、文档、企业知识库、analytics 等系统主要由 agent 调用，单个 agentic task 可能拉取比人类用户一个月触达还多的数据。平台如果能支持这种无头交互，并有相应商业模式和技术策略，会处于更好位置。对 Fugu，他认为应用 AI 产品已经在构建类似 agent harness，但把这种多模型调度做成开发者可直接调用的 LLM/API，是值得关注的产品化方向。
- **为什么重要**：企业 SaaS 的使用量和价值可能因为 agent 反而上升，但前提是权限、审计和可靠数据层先跟上。
- **链接**：https://x.com/levie/status/2068917230570795178, https://x.com/levie/status/2068851573175021864

#### Cursor Designer Ryo Lu

- **一句话**：Ryo Lu 在 ryOS 里做了 Books，体现 AI coding 后的“个人软件”形态。
- **要点**：这个功能支持任意 epub，并通过 ryOS account 同步进度；他从 Cursor mobile 开始，再手调动画和纹理直到质感合适。
- **完整内容**：这条动态很小，但信号明确：AI coding 让设计师和产品人能更快把个人审美、交互和功能做成真实软件，同时仍然保留人工打磨的部分。
- **为什么重要**：AI coding 会降低开始门槛，但最后的质感仍来自人对动画、纹理和节奏的判断。
- **链接**：https://x.com/ryolu_/status/2068924375341179347, https://x.com/ryolu_/status/2068923971136098633

#### Y Combinator CEO Garry Tan

- **一句话**：Garry Tan 认为 AGI 给你 intelligence，但真正 unlock 来自 personal brain 和 company brain。
- **要点**：他说 2026 年可用 AGI 早期，一个被低估的事情是收集个人和公司上下文有多重要。
- **完整内容**：Garry 用这点解释自己为什么做并开源 GBrain。通用 intelligence 只能提供能力，真正让 AI 帮你工作的，是你长期积累的个人 context、公司知识、历史判断和项目状态。
- **为什么重要**：这和 Zara Zhang 的 context 观点一致：AI 工作流的质量越来越取决于上下文工程，而不是单次 prompt 技巧。
- **链接**：https://x.com/garrytan/status/2068701357696323769, https://x.com/garrytan/status/2068701356358308112

#### Zara Zhang

- **一句话**：Zara Zhang 给了一个判断 AI slop 的简单规则：输入 context 是否比输出长。
- **要点**：她说自己通常需要让输入达到输出长度的 3 到 5 倍，AI 才更可能产出高质量结果；如果输入远短于输出，几乎一定会产生 slop。
- **完整内容**：她特别区分“context”不是“prompt”。这意味着高质量 AI 写作、设计和分析不是靠一句万能指令，而是靠足够多的材料、约束、例子、判断标准和真实背景。
- **为什么重要**：这是一条可操作的 AI 工作流原则：想减少 slop，先增加高质量 context，而不是继续压榨 prompt wording。
- **链接**：https://x.com/zarazhangrui/status/2068964055235321954, https://x.com/zarazhangrui/status/2068923768500793603

#### Peter Steinberger

- **一句话**：Peter Steinberger 认为 OpenClaw 正从早期 hype 转向质量和团队建设，并继续关注多模型路由。
- **要点**：他说 OpenClaw 热度下降后，他们提高了质量、组建了团队，并创建了非营利组织；他还提到自己此前对多模型路由持怀疑态度，现在看起来判断是对的。
- **完整内容**：这条是对 OpenClaw 状态的解释：相比 VC 支持的竞争者，OpenClaw 选择非营利路径和质量优先。他还分享了新的 Twitter 阅读方式，但技术信息较少。
- **为什么重要**：agent 工具生态会同时出现 VC 公司、开源项目和非营利组织，不同治理结构会影响产品节奏和信任。
- **链接**：https://x.com/steipete/status/2068961217524490739, https://x.com/steipete/status/2068960117253632160, https://x.com/steipete/status/2068965200343224367

#### swyx

- **一句话**：swyx 的本期可用信号偏创业市场而非 AI 技术：Corgi 在保险细分市场的口碑和渗透速度异常强。
- **要点**：他为 New Media Lab 寻找保险服务时，听到 broker 建议直接选择 Corgi，并称 Corgi 在绿色地带市场获得接近 100% market share 的情况在保险业很少见。
- **完整内容**：这条和 AI 无直接关系，但对 builder 有参考价值：在传统行业里，极强 NPS 和渠道口碑仍然可能形成突破。
- **为什么重要**：垂直市场的增长信号常常先出现在专业渠道推荐中，而不是公开营销声量里。
- **链接**：https://x.com/swyx/status/2068924451887129055

### 官方博客

本期 feed 中没有新的官方博客文章。

### 播客转录

#### Training Data: Google DeepMind's Logan Kilpatrick: Why the Model Eats the Harness

- **一句话**：Logan Kilpatrick 的核心判断是，agent harness 会先成为产品差异化，然后逐步被模型系统吸收，创业公司的机会要转向垂直场景、客户理解和工作流执行。
- **要点**：Logan 负责 Google AI Studio 和 Gemini API。他说 Google 正进入 “agentic Gemini era”：Gemini 曾经是 Google 产品的 AI through line，现在 Antigravity agent harness 会成为新的 through line，连接 Search、Gemini app、Cloud、AI Studio 等产品。Antigravity 不只是 IDE，还包括 web 上的 agent-first experience、CLI、SDK 和 managed agent。
- **完整内容**：访谈先讨论 Google 如何看 agentic AI。Logan 认为 agentic 产品短期仍处于 crawl 阶段，因为 Google 有大量十亿级用户产品，不能直接让 AI 大规模自动行动；更接近 walk 的是 Gemini app 和 Antigravity。对“AI 会不会蚕食 Google 旧业务”，他的回答不是最大化 eyeball time，而是最大化用户 outcome。关于 coding，他承认开发者圈过去更多使用 Claude 和 Codex，但强调 Google 正通过 Antigravity、Windsurf 团队和内部 10 万名工程师的 dogfooding 加速编码模型。他认为 coding 已经接近一种 narrow superintelligence，让人类开发者有更大 agency，可以把原本够不到的想法做出来。AI Studio 的 Android app 生成是一个具体例子：他说过去一周已有约 350,000 个 Android apps 在 AI Studio 中被构建，其中很多是原本不会被开发的个人软件。关于生成媒体，他用 Omni 改视频的例子说明模型正在表现出 world understanding：不是替换人的声音和身份，而是改变场景、布景等非人格部分，让原始内容被增强。最重要的一段是 “model eats the harness”：过去模型只是 weights，现在所谓 Gemini、GPT、Claude 都是围绕 weights 的系统，包含 tool calling、hosted tools、search、code execution、container、agent harness。外部 scaffolding 往往先领先模型几步，然后被模型吸收成原生能力。Logan 认为未来 12 个月，今天很多人手写 harness 的 alpha 会被模型消化，价值会迁移到别处。不过他也强调，外部 harness 仍会在搜索、code execution、特殊工具和多模型适配中有价值，行业甚至需要 “harness bench” 来衡量模型适配不同 harness 的能力。对应用层，他并不悲观：大模型公司解决的是通用问题，创业公司可以在垂直领域、客户知识、风险偏好和专注度上跑赢大公司。
- **为什么重要**：这期播客给 agent 创业者一个清晰提醒：如果你的护城河只是“我有一个 harness”，它可能很快被上游模型吃掉；如果你的护城河是垂直知识、真实工作流、用户信任、风险承担和端到端产品体验，机会反而比 24 个月前更大。
- **链接**：https://www.youtube.com/watch?v=cMAs8z2dehs

## Sources & Metadata

- Markdown export path: `/Users/zhouqingyi/repos/follow-builders/data/2026-06-22/digest.md`
- Prepared JSON: `/tmp/fb-prepared-2026-06-22.json`
- Historical feed commit: `6882ab5`
- Feed files used: `feed-x.json`, `feed-blogs.json`, `feed-podcasts.json`
- Feed generated at: `2026-06-22T08:29:37.749Z`
- Feed sources: `6882ab5:feed-x.json`, `6882ab5:feed-podcasts.json`, `6882ab5:feed-blogs.json`
- Stats: 11 X builders, 27 tweets, 1 podcast episode, 0 blog posts
- Generated through the Follow Builders skill: https://github.com/zarazhangrui/follow-builders
