AI Builders Digest — 2026-07-06

## Brief

### 今日关键信号

- **Benchmark 的旧表格越来越不够用了**：Noam Brown 在 No Priors 里强调，模型能力已经变成 test-time compute 的函数。只给一个 benchmark 分数，而不说明 token / cost / time 预算，会误导用户和安全评估。
- **Agent 管理不是“开很多标签页”**：Linear 的 Nan Yu 直接说，炫耀开 10 个 Claude Code tabs 是 theater，像 RTS 一样 micro-manage agents 是死路。
- **Claude Code workflows 正在从 coding 扩展到运营任务**：Cat Wu 展示了用 Claude Code 做 candidate sourcing 的动态 workflow，从角色定义到找 100 个候选人、整理 LinkedIn/Twitter/blog/podcast 和 one-line pitch，再生成 artifact 邮件发给自己。
- **Fable 的长任务行为继续暴露产品问题**：Dan Shipper 用玩笑说 Fable 为改按钮颜色拉起 100 个 agents，也提到 “make no mistakes” 这类提示下模型会过度铺开。问题不是能力不够，而是怎样让强模型在正确预算、正确粒度下工作。

### 适合谁读

适合关注 AI reasoning、test-time compute、模型 eval、安全评估、Claude Code / Fable、agent workflow、AI product management、以及 AI 如何改变研究和创业工作方式的人。

### 公众号候选

- **高 Test-time Compute 改写模型评估**：No Priors / Noam Brown；keywords: test-time compute / benchmarks / safety evals / cost budget / GPT-5.5；适合写 AI eval 方法论。
- **高 Agent 管理的 RTS 模式是死路**：Nan Yu / Dan Shipper；keywords: Claude Code tabs / multi-agent / Fable / agent orchestration / process visibility；适合写 agent 产品交互设计。
- **中 Claude Code 做招聘 sourcing workflow**：Cat Wu；keywords: Claude Code / workflows / artifacts / sourcing candidates / dynamic workflow；适合写非工程岗位如何用 coding agent。
- **中 Founder 和 VC 会议如何被 AI 重构**：Nikunj Kothari；keywords: VC chat / product feedback / fundraising / prompts / Claude；适合写 AI 时代融资沟通效率。

## X 动态

### Peter Yang，AI 教程作者

- **一句话**：Peter Yang 今天主要是体育和频道运营相关动态，没有实质 AI 产品更新。
- **要点**：他提到即将发布 podcast episodes，并希望在 2026-07-09 生日之前 YouTube 达到 100K 订阅；另外两条是比赛观感。
- **为什么重要**：今天不作为 AI builder 主线。
- **链接**：https://x.com/petergyang/status/2073930836551032858；https://x.com/petergyang/status/2073945318283252167；https://x.com/petergyang/status/2073966701629374820

### Linear 产品负责人 Nan Yu

- **一句话**：Nan Yu 认为把 agent 当作 RTS 单位来 micro-manage 是死路，炫耀开很多 Claude Code 标签页只是表演。
- **要点**：他说 “Bragging about running 10 Claude code tabs is just theater”，并认为“实时战略游戏”式管理 agents 的模型明显走不通，因为即使是已经过时的 AI，也能在游戏里 micro 超过 99% 的人类玩家。
- **为什么重要**：这是一条很强的 agent 产品判断：未来的 agent UX 不能靠人类手动调度多个执行体。真正的产品层要解决目标分解、协调、状态呈现、失败恢复和结果验收，而不是让用户盯着 10 个 tab。
- **链接**：https://x.com/thenanyu/status/2073920959011074292；https://x.com/thenanyu/status/2073920326304460847；https://x.com/thenanyu/status/2073873527082566097

### Anthropic 的 Amanda Askell

- **一句话**：Amanda Askell 用医生不给概率的例子，点出人类专家决策中的不确定性表达问题。
- **要点**：她说，从医生那里要一个 probability 是“不必要的 boss battle”，即使你只是请求一个 interval-valued subjective probability，本质上也只是要对方给一个 hunch。
- **为什么重要**：这条不是直接讲 AI，但和 AI safety / decision support 强相关。AI 系统越来越常被要求输出概率、置信区间和不确定性，而现实专家系统常常连主观概率都不愿表达。
- **链接**：https://x.com/AmandaAskell/status/2073786264059625897

### Anthropic Claude Code / Cowork 的 Cat Wu

- **一句话**：Cat Wu 展示了 Claude Code + workflows + artifacts 在招聘 sourcing 上的用法。
- **要点**：她会先告诉 Claude Code 角色和想找的背景，然后让它启动一个动态 workflow 去找 100 个 candidates，并为每个人补充 LinkedIn、Twitter、blog、podcasts 和 one-line pitch；最后让 Claude Code 生成 artifact 并邮件发给她，她合上电脑离开，等任务完成后在路上 review。
- **为什么重要**：这说明 Claude Code 的边界正在从“写代码”扩展到“长时间运行的业务研究和运营任务”。Artifacts 在这里不是展示层，而是异步工作结果的可审阅交付物。
- **链接**：https://x.com/_catwu/status/2073806626965049686

### Claude Code 的 Thariq

- **一句话**：Thariq 今天是 SF / ASI 文化梗，没有实质产品或技术更新。
- **要点**：内容是把 “God gave me a sign” 改写成被未来 ASI acausally influenced 来 maximize EV for humanity。
- **为什么重要**：可视为 AI 圈文化信号，不作为今日技术主线。
- **链接**：https://x.com/trq212/status/2073956140610924936

### Replit CEO Amjad Masad

- **一句话**：Amjad Masad 今天是美国 250 周年相关轻量动态，没有 AI 产品更新。
- **要点**：原文为 “Happy 250”。
- **为什么重要**：今天不作为 AI builder 主线。
- **链接**：https://x.com/amasad/status/2073840276414616006

### Vercel CEO Guillermo Rauch

- **一句话**：Guillermo Rauch 今天是体育预测，没有 AI / Vercel 产品信号。
- **要点**：他预测 USA 对 Argentina 决赛。
- **为什么重要**：今天不作为 AI builder 主线。
- **链接**：https://x.com/rauchg/status/2073822630742983062

### YC President & CEO Garry Tan

- **一句话**：Garry Tan 把当下创业机会归结为：leverage 约束被删除后，真正稀缺的是好想法和行动。
- **要点**：他说，人类财富的真正约束从来不是资源，而是“如何服务彼此的好想法”和执行这些想法的 leverage；现在 leverage 约束被删除了，剩下的只有 ideas。他还用日本作为例子：30 年零增长仍然造出了最好的 trains、service 和 craft，当不能靠更多竞争时，就靠更好竞争，而未来应该是 better and more at the same time。
- **为什么重要**：这是典型 AI boom 下的 founder framing：AI 把建造和执行的杠杆大幅下放后，想法质量、审美、服务意识和持续建设会更重要。
- **链接**：https://x.com/garrytan/status/2073881439700168925；https://x.com/garrytan/status/2073881438123110512；https://x.com/garrytan/status/2073997128222040471

### FirstMark VC Matt Turck

- **一句话**：Matt Turck 今天的 AI 相关内容是对“让 AI agent 不犯错”的调侃。
- **要点**：他发了一条 “when I ask my AI agent to ‘make no mistakes’” 的 meme，其他两条是足球相关。
- **为什么重要**：轻量但契合今天 Fable / agent 讨论：用户想要“别出错”，但 agent 往往会把简单目标展开成复杂过程，产品需要更好的约束、验证和可解释进度。
- **链接**：https://x.com/mattturck/status/2073972907491865062；https://x.com/mattturck/status/2073890630569251150；https://x.com/mattturck/status/2073889293567693110

### Zara Zhang，builder

- **一句话**：Zara Zhang 重新推荐了自己做的代码理解 skill。
- **要点**：她说现在“understanding your code is in vogue”，所以 resurfacing 这个 skill。
- **为什么重要**：代码理解正在重新成为 agent workflow 的基础能力。随着模型能改更多代码，解释 diff、理解 codebase、提炼架构和建立上下文的 skill 会比单次生成更重要。
- **链接**：https://x.com/zarazhangrui/status/2073768913310200310

### FPV Ventures partner Nikunj Kothari

- **一句话**：Nikunj Kothari 认为 founder 和 VC 的 30 分钟标准 pitch call 效率很低，应该先玩产品、带反馈再聊。
- **要点**：他希望有 founder 会要求 VC 在聊天前先使用产品，并至少带来两条反馈。他质疑整天在 Zoom 上重复讲同一套 deck 的价值，认为与其这样，不如做 product brainstorm，或者干脆互相把个人 “prompts” 上传给 Claude 先数字化处理。
- **为什么重要**：这是 AI 对融资流程的直接冲击。重复讲故事、浅层问答和标准 diligence 很适合被 AI 预处理，真正的人类时间应更多用于产品反馈、判断力交换和关系建立。
- **链接**：https://x.com/nikunj/status/2073903310982218088；https://x.com/nikunj/status/2073860953687638344；https://x.com/nikunj/status/2073803608722939935

### Peter Steinberger，OpenClaw / OpenAI builder

- **一句话**：Peter Steinberger 推荐通过一个链接使用某个工具，但 feed 中缺少足够上下文说明具体对象。
- **要点**：原文是 “Can’t recommend enough. use via ...”，没有更多可安全展开的信息。
- **为什么重要**：由于缺少上下文，今天不作为主要信号。
- **链接**：https://x.com/steipete/status/2074007001802367446

### Every CEO Dan Shipper

- **一句话**：Dan Shipper 用 Fable 的行为调侃当前 agent 的过度执行倾向。
- **要点**：他写道，让 Fable 改一个按钮颜色，它像是“拉起一队 100 个 agents 来完成”；另一条是 “fable on ultracode ‘make no mistakes’”。这不是正式评测，但很准确地捕捉了强推理模型的产品问题：当模型有更大预算和更多 agent 能力时，简单任务可能被过度展开。
- **为什么重要**：agent 产品不只要追求更强，还要学会按任务规模合理分配 test-time compute、并把工作过程讲清楚。否则用户会觉得它既强又不可控。
- **链接**：https://x.com/danshipper/status/2073764166700048480；https://x.com/danshipper/status/2073894034225897602

### Sam Altman

- **一句话**：Sam Altman 用孩子第一次把两个词放在一起，类比 GPT-5.6 发现新数学带来的惊讶。
- **要点**：他说自己对孩子这一 cognitive feat 的惊讶，大致相当于对 GPT-5.6 discovering new math 的惊讶。
- **为什么重要**：这条是轻量个人表达，但它和今天 Noam Brown 的播客形成呼应：frontier models 在数学发现和推理任务上正在出现让内部研究者也惊讶的能力。
- **链接**：https://x.com/sama/status/2073791666553844074

## Podcasts

### No Priors — Really Big Test-Time Compute in AI Changes Benchmarks, Safety and Research with OpenAI Research Scientist Noam Brown

**The Takeaway**：Noam Brown 的核心观点是，今天的模型能力不能再用单个 benchmark 分数描述，因为能力已经变成 test-time compute 的函数。

Noam Brown 是 OpenAI research scientist，也是 AI reasoning / inference-time scaling 早期推动者。他认为 GPT-5.5 这类模型被低估，部分原因是传统 benchmark grid 只显示“模型在某题上的一个分数”，却没有控制模型用了多少 thinking time、token、cost 或 wall-clock time。5.5 看上去只比 5.4 高几个百分点，但如果按相同 thinking budget 比，差距会更明显，因为 5.5 更高效。

这会直接影响 eval 和 safety。过去 GPT-3 时代，给模型 1 美元、10 美元或 1000 万美元预算，能力差距不会大到改变安全框架；现在不同了。Brown 的话很直接：“the capability of the model is a function of how much money you put into it”。如果一个模型拿 10,000 美元预算能做出 10 美元预算下做不到的事情，那么 preparedness frameworks 和 responsible scaling policies 就必须回答：到底用什么预算评估危险能力？

他也反对只靠“多跑几次模型、投票选最好”来刷 benchmark。routing layer、model consensus、multi-agent scaffold 当然可能提高分数，但问题是：在相同 test-time compute 下，它是否真的比让一个强模型多想更好？否则只是把更多预算藏进系统。

最值得记住的判断是：模型 release cycle 已经快到几个月一次，但某些能力天花板可能要跑数周、数月才知道。Brown 认为现在没人真正知道已发布模型的上限，因为还没人用足够长时间和足够预算把它们推到极限。对研究、产品和安全评估来说，未来的标准图表不该只有一张 grid，而应该有 x 轴：tokens、cost 或 time。

**链接**：https://www.youtube.com/watch?v=AZrU6y3pUcU

Generated through the Follow Builders skill: https://github.com/zarazhangrui/follow-builders
