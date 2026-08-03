AI Builders Digest - 2026-06-25

## Brief

### 今日关键信号

- Claude Tag 是本期主线：agent 正从单人工具变成 Slack 里的持久在线团队成员。
- Agent-first 产品设计正在转向 API、CLI、权限、memory、状态可见性和工作流接入。
- 模型价格会继续分层，应用层的价值在路由、eval、领域数据和流程理解。
- Biohub 把 AI biology 做成 open-source world model + wet lab 闭环，而不是押注单个疾病。

### 适合谁读

适合做 AI coding、企业协作 agent、agent 平台、AI infra、AI commerce、生命科学 AI 的产品和技术团队。

### 公众号候选

- **高 Claude Tag 里的 Slack agent**：Anthropic / Claude Code; keywords: Claude Tag / Agent / Slack / 多人协作; 很适合写“agent 第三种 UI”的长文。
- **高 Agent-first 设计会吞掉传统 UI 吗**：Karpathy / Peter Yang / Box; keywords: API / CLI / headless software / enterprise content; 可写产品设计视角。
- **中 AI 模型价格分层后的应用层机会**：Aaron Levie / Madhu Guru; keywords: token pricing / model routing / evals / applied AI; 有商业分析空间。
- **中 Shopify UCP CLI 和 embedded shops**：Nikunj Kothari; keywords: Shopify / CLI / commerce agent; 可写 agent commerce 原型。
- **中 Biohub 的 open-source virtual biology**：No Priors; keywords: ESM Fold / virtual cell / AI biology / open source; 适合偏深度科技读者。

## 文章详情

### X 动态

#### Andrej Karpathy

- **一句话**：Karpathy 把 Claude Tag 视为 LLM UI/UX 的第三次大改版。
- **要点**：第一代是网页里的 LLM，第二代是桌面 app，第三代是有组织上下文、工具、memory、安全边界和异步执行能力的“团队成员”。
- **完整内容**：他认为真正难的是底层工程：工具集成、计算环境、memory、权限和安全都要让 Claude “just work”。一旦这些做完，Claude 就不再像一个需要人手动打开的工具，而像一个可以在组织里被自然对话调度的异步实体。
- **为什么重要**：这给企业 agent 产品定了一个新评价标准：不是 chat 好不好，而是能否进入组织协作流。
- **链接**：https://x.com/karpathy/status/2069547676849557725

#### Anthropic Claude Code / Claude Tag 线索：Boris Cherny、Cat Wu、Thariq、Alex Albert、Claude

- **一句话**：Anthropic 正在把 Claude Code 从本地编码工具扩展成 Slack 里的多人、主动、带沙箱的协作 agent。
- **要点**：Claude Tag beta 面向 Claude Enterprise 和 Team；在 Slack channel 里 tag Claude，它会为线程启动独立实例，在隔离 sandbox 中 clone repo、写代码、测试、编译，结束后销毁环境；每个 channel 可以有自己的 memory 和权限。
- **完整内容**：Boris Cherny 说，它可以被要求监控 Slack channel，主动回答问题、草拟 PR，并用指定 emoji 标记线程状态。Cat Wu 补充说，内部版本已经合并 65% 的产品 PR，这是 Anthropic 第一个原生多人、主动式产品。Thariq 分享了实际操作习惯：给 Claude 做 status emoji、用 pinned message 维护多线程状态，甚至单独建 scheduling channel 让 Claude 帮忙找会议时间。Alex Albert 的总结更像用户感受：这不像使用工具，更像管理一个团队。
- **为什么重要**：这是企业 AI coding 的关键转向：代码生成只是能力之一，真正的产品形态是可审计、可授权、可持续运行的组织协作 agent。
- **链接**：https://x.com/bcherny/status/2069474691010707486, https://x.com/bcherny/status/2069474689819480394, https://x.com/bcherny/status/2069474688619958517, https://x.com/_catwu/status/2069486403696869555, https://x.com/_catwu/status/2069484330938998993, https://x.com/_catwu/status/2069473118742331608, https://x.com/trq212/status/2069474343512617390, https://x.com/trq212/status/2069474342220820657, https://x.com/trq212/status/2069474339679052144, https://x.com/alexalbert__/status/2069470389391241314, https://x.com/claudeai/status/2069468701548531895, https://x.com/claudeai/status/2069468699766005847, https://x.com/claudeai/status/2069468698071494976

#### Peter Yang

- **一句话**：Peter Yang 把 agent 时代的产品设计问题说得很直接：如果访问产品的是 agent，设计对象可能不再是屏幕，而是 API 或 CLI。
- **要点**：他还把 human-agent interaction 比作管理高能力员工，暗示未来产品需要支持任务分派、状态汇报、反馈和绩效式管理。
- **完整内容**：这和 Claude Tag 同频：当 agent 是主要操作者，产品的“界面”会变成 agent 可调用的能力边界、权限模型、日志、CLI、API 和状态呈现。Google Workspace CLI 被他点名为“非常有用”，也说明 CLI 正重新成为 agent 产品分发面。
- **为什么重要**：面向人设计 UI 和面向 agent 设计操作面是两套产品能力，后者会决定软件能否进入 agent workflow。
- **链接**：https://x.com/petergyang/status/2069603490524254473, https://x.com/petergyang/status/2069551302246592799, https://x.com/petergyang/status/2069530765352907180

#### Box CEO Aaron Levie

- **一句话**：Aaron Levie 认为 AI pricing 会走向两端分化，应用层会因此更重要。
- **要点**：一端是昂贵 frontier models，另一端是便宜但足够好的 open/closed weight models；应用层的任务是按 workload 动态路由、降低 token 成本、弥补低价模型质量差距。
- **完整内容**：他强调，越靠近真实工作流，越能为具体业务流程调优模型使用方式。这需要 domain-specific FDE、customer/process eval、数据准备和 agent 工作流理解。他还把 Claude Tag + Box 称为 headless software 的例子：企业内容可以通过 Slack 变成可携带知识库。
- **为什么重要**：这解释了为什么企业 AI 价值不只在模型，而在“理解流程并调度模型”的应用层。
- **链接**：https://x.com/levie/status/2069639600310767616, https://x.com/levie/status/2069596515560267891

#### Madhu Guru

- **一句话**：Madhu Guru 认为 token pricing 争论本质上是在争“价值会沉淀到哪一层”。
- **要点**：模型、应用层、分发层、数据提供方、agent startup、企业客户都在实时摸索商业模式、moat 和价值交换。
- **完整内容**：他提醒，不同玩家会用强观点塑造叙事，因为每一层都希望证明自己能捕获更多价值。这和 Aaron Levie 的 applied AI 观点形成互补。
- **为什么重要**：对创业者来说，模型价格不是单纯成本问题，而是产业链利润重新分配的信号。
- **链接**：https://x.com/realmadhuguru/status/2069455097193697393

#### Google Labs VP Josh Woodward

- **一句话**：Josh Woodward 分享了 Gemini App 图像模板和 NotebookLM 的校园案例。
- **要点**：Gemini App 新模板可以把用户照片变成球队主题 trading card、mural 或 virtual plushie；Florida State University 称 NotebookLM 帮一些学生在数周内改变学习习惯和成绩。
- **完整内容**：这两条分别指向消费者 AI 的模板化创作和教育场景的学习辅助。前者是降低图像生成门槛，后者是把 NotebookLM 放进大学学习流程。
- **为什么重要**：Google 的 AI 应用正在同时做轻量娱乐模板和高频学习场景，两者都是留存入口。
- **链接**：https://x.com/joshwoodward/status/2069408025362714957, https://x.com/joshwoodward/status/2069406832523624696

#### swyx

- **一句话**：swyx 强调 Z.ai / GLM 正从低认知度走到开放模型前沿。
- **要点**：他提到 Z.ai 今年 1 月以 HK$120 发行，过去很多人不了解 GLM，现在他们已经发布了被称为超过 DeepSeek 的顶级开放模型，并将在 AI Engineer 活动上回到旧金山。
- **完整内容**：这条不是技术细节，而是开源模型竞争格局的市场信号：中文模型团队正在更积极地面向全球开发者和商业合作。
- **为什么重要**：开源模型竞赛会继续压低通用能力价格，也会强化应用层和分发层的重要性。
- **链接**：https://x.com/swyx/status/2069598378191941835

#### Thibault Sottiaux

- **一句话**：OpenAI Codex 团队继续把公开反馈转成修复节奏。
- **要点**：Thibault Sottiaux 说 Codex “had a bug. Fixed”，并鼓励继续反馈；另一条说 Codex 喜欢“slurping up bugs”。
- **完整内容**：内容很短，但信号明确：Codex 当前迭代重点是通过真实用户 bug 反馈快速修产品。
- **为什么重要**：AI coding 工具进入高频生产流后，bug 修复速度本身就是产品信任的一部分。
- **链接**：https://x.com/thsottiaux/status/2069592160966733853, https://x.com/thsottiaux/status/2069579993588625574

#### Replit CEO Amjad Masad

- **一句话**：Amjad Masad 把新产品起点压缩成一句话：它从 prompt 和 idea 开始，但背后需要大量工程。
- **要点**：他祝贺 Yousef 和团队，并用“it starts with a prompt”描述从想法到成品的 AI-native 构建路径。
- **完整内容**：这条更像创作哲学：prompt 降低了起点，但不是替代工程。真正的工作仍然在把 idea 变成可运行、可交付的产品。
- **为什么重要**：对 AI builder 来说，prompt 是入口，不是护城河。
- **链接**：https://x.com/amasad/status/2069588152285794373, https://x.com/amasad/status/2069322872456364540

#### Vercel CEO Guillermo Rauch

- **一句话**：Guillermo Rauch 在收集 eve builder 的高质量批评和需求。
- **要点**：他准备开一个 X Chat group，把深度构建 agent 的用户和 eve engineers 拉到一起。
- **完整内容**：这说明 Vercel 的 agent 产品探索正在靠高密度设计伙伴反馈推进，而不是只做公开发布。
- **为什么重要**：agent 产品还没有稳定范式，早期产品质量高度依赖真实 builder 的尖锐反馈。
- **链接**：https://x.com/rauchg/status/2069590431646769472, https://x.com/rauchg/status/2069513849578082474

#### Y Combinator CEO Garry Tan

- **一句话**：Garry Tan 点名 Linzumi 是“真正多人协作版 Codex”。
- **要点**：他称 Linzumi 对团队很有魔力，并补充创始人 Sean Grove 曾在 OpenAI 参与减少 ChatGPT sycophancy 的工作。
- **完整内容**：同时他也提醒 Dropbox 应该支持超过 3TB 的计划，因为 AI 会让可用数据量指数级增长。
- **为什么重要**：两个信号都指向团队级 AI coding 和数据量爆炸：多人 agent、协作上下文和更大存储会成为基础需求。
- **链接**：https://x.com/garrytan/status/2069474420113146355, https://x.com/garrytan/status/2069434452628185241

#### Nikunj Kothari

- **一句话**：Nikunj Kothari 用 Shopify UCP CLI 做了一个 agent commerce 原型 Plug That Shop。
- **要点**：用户输入网站后，系统生成四个高度相关、可一键嵌入的 shop；买家可用 Shop 一键 checkout。
- **完整内容**：他说明这个 demo 使用 Conductor、Anthropic Opus 4.8、Shopify UCP CLI 和 Railway 构建，并且免费、无 affiliate revenue。
- **为什么重要**：Shopify 把商品能力暴露到 CLI 后，agent 可以直接生成上下文相关的商业组件，这可能是 commerce agent 的早期形态。
- **链接**：https://x.com/nikunj/status/2069547206504566980, https://x.com/nikunj/status/2069534712763490668

#### Peter Steinberger

- **一句话**：Peter Steinberger 继续把注意力放在 Google Workspace CLI 这种 agent 可调用界面上。
- **要点**：他转述了 Google Workspace CLI 背后的组织故事，并借机强调自己不受 Google 内部限制。
- **完整内容**：这条本身偏吐槽，但结合 Peter Yang 的观点，它强化了同一个产品趋势：传统 SaaS 一旦有了 CLI/API，就更容易被 agent 接入。
- **为什么重要**：agent 时代的“可用性”会越来越依赖机器可操作界面。
- **链接**：https://x.com/steipete/status/2069594195522941059

### 官方博客

本期 feed 中没有新的官方博客文章。

### 播客转录

#### No Priors: Biohub: The Future of Biology is Open-Source with Co-Founders Mark Zuckerberg, Priscilla Chan, and Head of Science Alex Rives

- **一句话**：Biohub 的核心赌注是把 frontier AI 和 frontier biology 接成闭环，用 open-source 工具加速整个科学共同体。
- **要点**：Mark Zuckerberg、Priscilla Chan 和 Alex Rives 讨论了 Biohub 如何从长期工具建设转向 virtual biology：先建蛋白世界模型，再走向细胞、免疫系统、炎症和更完整的生物系统模型。他们强调，生物学不像互联网文本那样有现成海量数据，必须通过 wet lab、成像、细胞工程、传感器和 cryo-EM 等方法创造新数据。
- **完整内容**：他们回顾了 CZI / Biohub 的起点：科学进展被 silo、论文延迟、工具停留在单个 postdoc 电脑里拖慢，所以 Biohub 的策略不是自己“治愈所有疾病”，而是构建让更多科学家更快工作的共享工具。Priscilla Chan 用 CellByGene 和 Human Cell Atlas 说明，单细胞转录组数据最初像“stamp collecting”，但 LLM 时代让大规模数据有机会转化为机制理解。Alex Rives 解释了新 ESM Fold：这是训练在数十亿蛋白序列上的蛋白 biology world model，可高速预测原子级结构，并在 protein-protein interaction 和 protein-antibody interaction 上接近或达到 state of the art。他们已经折叠超过 11 亿个蛋白结构，并用模型设计蛋白和 single-chain antibodies，再通过 96-well plate、cryo-EM 和细胞实验验证，找到 nanomolar binders。对临床转化，Chan 强调目标不是先挑一个疾病，而是理解个体基因、蛋白、疾病机制之间的链条；模型还可能提前预测 off-target effects，例如药物是否会影响 kidney cell 上也表达的 receptor。罕见病部分很关键：患者组织可以自建 registry、biobank 和 trial，把过去十几年周期压缩到三到五年。Zuckerberg 的开放哲学也很明确：“We just wanna give tools to the whole scientific community.” 他认为 Biohub 的优势是非营利、中立、十到十五年时间线、开放源码，以及把 frontier AI lab 和 frontier biology lab 放在同一个组织里。
- **为什么重要**：这期播客把“AI for biology”的抽象愿景落到了数据生成、模型结构、实验验证、开放生态和临床转化路径上。它也提示 AI 行业一个普遍规律：真正有价值的 world model 不只靠模型 scaling，还需要能持续产生高质量反馈数据的现实闭环。
- **链接**：https://www.youtube.com/@NoPriorsPodcast

## Sources & Metadata

- Markdown export path: `/Users/zhouqingyi/repos/follow-builders/data/2026-06-25/digest.md`
- Prepared JSON: `/tmp/fb-prepared.json`
- Feed files used: `feed-x.json`, `feed-blogs.json`, `feed-podcasts.json`
- Feed generated at: `2026-06-24T07:29:07.207Z`
- Feed sources: `origin/main` for X, podcasts, and blogs
- Stats: 19 X builders, 41 tweets, 1 podcast episode, 0 blog posts
- Note: the podcast object in the feed only provided `https://www.youtube.com/@NoPriorsPodcast` as its `url`; I did not guess a specific video URL.
- Generated through the Follow Builders skill: https://github.com/zarazhangrui/follow-builders
