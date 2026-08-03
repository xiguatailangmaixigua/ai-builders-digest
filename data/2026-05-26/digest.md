AI Builders Digest — 2026 年 5 月 26 日

X / TWITTER

Swyx

Swyx 分享了一张关于 SaaS “自研还是采购”的判断图。它真正有价值的地方，不是推荐某个具体工具，而是提醒团队：当 AI 让更多软件变得可以自己做，组织反而更需要一套清晰标准，判断哪些能力应该沉淀在内部，哪些能力应该继续交给外部基础设施。

https://x.com/swyx/status/2053572059767427302

Peter Yang，Roblox 产品负责人

Peter Yang 提了一个很具体的 AI 自动化场景：孩子学校每周发十几页 newsletter，AI 应该直接告诉家长有没有提前放学、截止日期或真正需要注意的事情。

这个例子很小，但很典型。很多有价值的 AI 产品不一定长得像“AI 工作台”，而是把反复出现的冗长文档，压缩成用户可以直接行动的信息。

https://x.com/petergyang/status/2053672364681134511

Thariq，Claude Code 工程师

Claude Code 工程师 Thariq 说，他最近一直在用 HTML 做规划、规格说明、探索、代码审查、报告等工作。

这里的重点不是 HTML 本身，而是 HTML 正在成为 AI 工作流里的轻量中间产物：它足够结构化，可以渲染、检查和迭代；又足够简单，agent 可以快速生成。

https://x.com/trq212/status/2053632475294040084

Thariq 还转发了 Jarred Sumner 重写 Bun 的实验：用 Rust 重写后，已有测试套件通过率达到 99.8%。他的判断很直接：“we're not being ambitious enough”。

这背后的信号是，老代码库可能会变成 AI 辅助重写的原材料。前提是测试足够强，能验证行为没有被破坏。

https://x.com/trq212/status/2053559397654348159

Aaron Levie，Box CEO

Box CEO Aaron Levie 认为，advanced agents 从写代码进入更广泛的知识工作后，不会只是一个顺手做的副项目，而需要严肃的技术负责人。

他的判断是，生产级 agent 需要正确的上下文和数据，需要安全地接入系统，需要质量控制，需要设计人类介入的位置，也需要随着模型和系统升级持续维护。

这也是 Box 开始招聘 AI automation engineering 岗位的原因。Levie 把这个角色描述成一个直接和业务协作的技术岗位，有点像面向内部职能的 forward deployed engineer。

这个岗位很值得看。AI 不只是替代一些工作，也可能在公司内部创造一类新工程角色：专门把 agent 落到关键业务流程里。

https://x.com/levie/status/2053672965125140915

Garry Tan，YC 总裁兼 CEO

YC 总裁兼 CEO Garry Tan 写道，最高级、也最重要的设计，其实是把人的痛苦转化成产品。

这句话很短，但很符合创业公司的设计观：真正的设计不是先从审美和装饰开始，而是先抓住具体、强烈、持续存在的用户痛点。

https://x.com/garrytan/status/2053689459032379860

Peter Steinberger，OpenClaw 与 OpenAI

Peter Steinberger 讲了一个 agent-native 开发方式：他让 Codex 在 OpenClaw 里改进 chat completion endpoint 的端到端测试，同时用 `/side` 在 agent 工作时继续追问问题。

这个模式很有意思：一个 agent 在执行实现任务，用户保留一个并行询问通道，用来继续理解、追问和校准方向。

https://x.com/steipete/status/2053744332675408151

他还分享了 Birdclaw：它接入了他的完整 Twitter 归档，所以他可以让 Codex 查询自己过去收藏或点赞过的旧内容。

这指向一个更个人化的检索方向：agent 只有能查到你的长期数字记忆，才会比“只看当前 repo 或浏览器标签页”更有用。

https://x.com/steipete/status/2053737275268177980

Steinberger 还在 RepoBar 里内置了浏览器，让选中的 issue、PR、SHA 和 workflow 能把上下文带进工作会话。

这条的实践意义很清楚：AI 编程真正变好，往往不是只换模型，而是补齐工作流里的上下文缺口。

https://x.com/steipete/status/2053717468623872230

Dan Shipper，Every CEO

Every CEO Dan Shipper 分享了一个周末小项目：把 MIDI 键盘接到电脑，让 Codex 写一个监听脚本和小网页，显示自己正在弹什么和弦，再让它给练习建议。按他的说法，从想法到可用只花了 5 分钟。

重点不是这个音乐工具本身，而是“个人软件”的形态正在变。以前不值得专门找人做的小工具，现在可以按需生成，直接服务一个很小但真实的场景。

https://x.com/danshipper/status/2053551046299959760

Dan Shipper 还提到，新加入帮助做社交媒体和 YouTube 的同事，发现了一些非常夸张的 A/B test 提升。

对 AI 内容公司来说，运营优势可能不只来自选题和观点，也来自标题、封面、分发包装的快速实验循环。

https://x.com/danshipper/status/2053580741515051114

OFFICIAL BLOGS

Anthropic Engineering：Scaling Managed Agents: Decoupling the brain from the hands

Anthropic 工程团队解释了 Claude Managed Agents 背后的架构设计。核心判断是：长任务 agent 需要围绕 Claude 建立稳定接口，因为 harness 里的假设会随着模型变强而过期。

一个例子是，Claude Sonnet 4.5 接近上下文限制时曾出现“context anxiety”，会过早收尾。团队之前通过 context reset 缓解。但到了 Claude Opus 4.5，同样行为消失了，原来的 reset 反而变成额外负担。

Anthropic 的关键架构变化，是把 “brain”、“hands” 和 “session” 拆开。

brain 是 Claude 和 harness。

hands 是执行动作的 sandbox 和工具。

session 是持久的 append-only 事件日志。

这样做之后，容器可以变成可替换的资源；harness 崩溃后也可以从 session log 恢复；凭证也不会暴露在 Claude 生成代码运行的 sandbox 里。

性能收益很明显：Anthropic 说，这套架构让 p50 time-to-first-token 降低约 60%，p95 降低超过 90%。

更大的意义是，agent 基础设施开始不像一个聪明的循环，而更像操作系统：用稳定抽象承接未来还没被发明出来的 agent 程序。

https://www.anthropic.com/engineering/managed-agents

PODCASTS

No Priors：Baseten CEO Tuhin Srivastava on the AI Inference Crunch, Custom Models, and Building the Inference Cloud

核心 takeaway：inference 可能会成为 AI 里的“最后一个市场”，因为每一次 AI 变得更有用，都会带来更多 inference 需求，而不是更少。

Baseten CEO Tuhin Srivastava 描述了一个高速增长的 AI 基础设施市场：Baseten 过去一年增长了 30 倍，预计今年收入超过 10 亿美元；在他们的客户里，大约 90% 到 95% 的 token 都跑在 dedicated custom model inference 上。

他对应用层的判断也很关键：应用层不会因为模型公司变强就消失，因为真正可持续的价值不只在模型里，也在 workflow 和独特 user signal 里。

比如 Abridge 这样的公司，深入医生工作流，能拿到模型公司很难拿到的临床反馈和后续操作信号。类似逻辑也适用于客服、企业运营和其他多步骤流程：价值不是一次回答，而是整个任务链条里的反馈和执行。

他还反对把问题简单看成“开源模型 vs 闭源模型”。客户通常先追求能力，再优化成本、延迟和可靠性。开源模型重要，是因为更便宜的 intelligence 会扩大使用量：当 inference 变便宜，客户不是停止消费，而是让 agent 跑更久，把智能塞进更多流程里，追求更好的结果。

这期里最值得记的一句话是：“Even if there's AGI, all that's left is inference.”

这也是 Baseten inference cloud 的核心赌注：掌握软件层、runtime、算力供应网络，以及 sandboxes、batch inference、eval 集成、post-training loop 这些相邻基础能力。

https://www.youtube.com/watch?v=XAbKflCncDo

Generated through the Follow Builders skill: https://github.com/zarazhangrui/follow-builders
