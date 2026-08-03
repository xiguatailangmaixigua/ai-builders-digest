AI Builders Digest — 2026-06-10

## X / TWITTER

### Andrej Karpathy
Andrej Karpathy 认为 Claude Fable 5 不只是 benchmark 上更强，而是一次足够称得上“大版本升级”的能力跃迁，特别体现在长时间、复杂问题求解上。他的判断是，随着“能工作的软件”越来越像拧开水龙头就能得到的东西，Jevons paradox 会把软件需求继续推高，解释器、可视化工具、超定制 dashboard、一次性小应用和测试扩展都会因此爆发。与此同时，他也明确提醒不要盲信产出，模型依然有 quirks，离“生产环境里完全不看代码”还差一步。
原帖：https://x.com/karpathy/status/2064409694761054332

### Swyx
Swyx 的几条更新都围绕同一个判断展开：Claude Fable 5 已经开始改写实际开发工作流。他建议直接让 Claude Code 用“review my code for issues”做一次系统检查，因为在 Fable 上这种审查能力会让你重新意识到过去很多上线流程有多粗糙；另一条信息则强调，从合作落地到 Mythos 级模型正式发布只用了 34 天，背后反映的是 AI 基础设施和产品化节奏都在明显提速。
原帖：https://x.com/swyx/status/2064492823781789969
原帖：https://x.com/swyx/status/2064421542503797186

### Anthropic Claude Code 团队 Boris Cherny
Boris Cherny 给出的信号很直接：Fable 5 是自 Opus 4.5 之后，他感受到的最大一次模型跃迁。他最看重的不是“更会写代码”，而是模型开始表现出更像 thought partner 的判断力、品味和方法感，尤其是在 debug 时会主动测量、加日志、验证修复，而不是草率宣告完成。与这套能力配套的关键机制是 self-verification loops，也就是让模型在长时间执行过程中不断自查，这决定了 agent 能不能在更少人工盯防的前提下跑更久、跑得更准。
原帖：https://x.com/bcherny/status/2064431111154053187
原帖：https://x.com/bcherny/status/2064426115255730578

### Anthropic Claude Code 团队 Thariq
Thariq 把 Fable 的变化概括为一次真正的 step-change，并给出的行动建议也很明确：现在该把目标定得更大一些。这个判断和 Anthropic 团队其他人的表述一致，核心不是“同样的活更快做完”，而是过去不会交给模型的任务，现在值得重新拿出来定义成更高阶的 objective。
原帖：https://x.com/trq212/status/2064437561930682672

### Vercel CEO Guillermo Rauch
Guillermo Rauch 这次发的是偏基础设施层的更新。Vercel CLI 现在可以直接创建 AI Gateway API key，并给 key 配上 `--budget` 和 `--refresh-period`，本质上是在把 AI token 消耗做成类似“可控额度的虚拟信用卡”。这类能力很实用，因为它把团队内部分发模型访问权限、做预算治理和配额刷新这些原本容易失控的环节，前移到了命令行和平台层。
原帖：https://x.com/rauchg/status/2064551967461114111

### Anthropic 研究员 Alex Albert
Alex Albert 给新一代模型的使用建议很具体：先把任务规模拉大，把 `xhigh` 或 `high` effort 当成默认选项，再把旧时代为了约束模型而写的 skills 和 `CLAUDE.md` 说明尽量减掉，让 Fable 自己发挥判断。更重要的是，他建议把“给任务”改成“给 objective”，清楚定义完成标准和验证方法，再让模型自己找路径，这也是 `/loop` 和 `/goal` 这类工作方式的天然适配场景。他同时把 Fable 5 列入 Anthropic 少数几个真正改变内部协作方式的版本，认为模型开始更像协作者，而不只是被驱动的工具。
原帖：https://x.com/alexalbert__/status/2064467657483829441
原帖：https://x.com/alexalbert__/status/2064394410004304003

### Box CEO Aaron Levie
Box CEO Aaron Levie 这轮输出的重点，不是单纯夸前沿模型，而是把“模型能力提升”和“企业落地难度”这两件事强行放在一起看。他引用并扩展了一个对 applied AI 很关键的观点：真正难复制的价值，往往不在模型本身，而在于把企业私有数据、实际工具链和组织流程整理到足以让模型行动的程度，这里面既有集成，也有变更管理，还有长期维护。他还补充说，推理时到底投入多少 compute，会显著影响模型表现，因此未来更合理的 benchmark 方向应该是 compute-normalized，而不是只看一个静态分数。
原帖：https://x.com/levie/status/2064569513023328268
原帖：https://x.com/levie/status/2064379199629181139
原帖：https://x.com/levie/status/2064396746953023647

### Builder Zara Zhang
Zara Zhang 提出的观察很值得产品团队记住：非技术用户用不好 coding agent，瓶颈从来不是聊天框这种 interface，而是不知道“该问什么”。空白输入框默认用户已经理解能力边界，但大多数人并不具备这种心智模型，所以更好的 agent onboarding 应该主动展示可代办工作流，而不是被动等用户下指令。她另外也预告了一场分享，会拆解自己如何作为非技术背景创作者与 coding agents 协作、如何避免做出 AI slop，以及为什么她把 code 看成一种叙事媒介。
原帖：https://x.com/zarazhangrui/status/2064587398529606082
原帖：https://x.com/zarazhangrui/status/2064486120386379950

### FPV Ventures 合伙人 Nikunj Kothari
Nikunj Kothari 展示的是一种越来越典型的 builder 工作流：先从播客里提炼概念，再把研究和实现一起交给模型。他听完关于 S-curves 的内容后，先让 Claude 在 research mode 下整理历史上的 S-curve 案例和结构，再生成一个 Claude Code prompt，最后几乎 one-shot 做出了一个讲解过去 200 年技术 S-curve、拐点和泡沫评论的网站。它说明的不只是“能做个站”，而是内容理解、研究组织、prompt 编排和前端产出已经能被串成一条更短的链路。
原帖：https://x.com/nikunj/status/2064506504888373758
原帖：https://x.com/nikunj/status/2064508462034501997

### Claude
Claude 官方账号确认，Claude Fable 5 已全面开放，而 Claude Mythos 5 暂时只向 Glasswing partners 及一小部分防御型网络安全和关键基础设施提供方开放。官方给出的定位也很清楚：Mythos 5 和 Fable 5 使用相同底层模型，但在部分安全限制上做了放宽，后续还计划通过更广泛的 trusted access program 扩大到 defensive cybersecurity 和 biomedical research 场景。
原帖：https://x.com/claudeai/status/2064394160522559632
原帖：https://x.com/claudeai/status/2064394158056386684
原帖：https://x.com/claudeai/status/2064394159318782217

## PODCASTS

### AI & I by Every: We Automated Everything With AI and Tripled Our Headcount
核心观点：AI 在企业里的真实作用，不是直接替代人，而是把“昨天的专家能力”变便宜后，反过来放大对专家判断、流程设计和系统搭建的需求。

Every CEO Dan Shipper 在这期内容里试图解释一个很多人直觉上会觉得矛盾的现象：团队已经非常 AI native，内部到处都是 agents，结果不是人变少了，而是从 4 个人长到 30 个人，还在继续招人。按照他的说法，AI 最先压低成本的是可复制的输出层，比如代码、文案、设计草稿和分析框架，于是更多非专家都能更快地产出“七八成对”的东西；问题在于，这些结果往往接近正确，但不真正贴合当下场景，于是企业会突然需要更多专家来收尾、校准、设规则、建 review 流程，并把这些看似便宜的产出推进到真正可用。

他最值得记住的一句原话是：“the further away an agent gets from a human, the less valuable it is.” 这句话基本概括了整套逻辑。Dan Shipper 的意思不是 agent 不强，而是离人越远，价值越容易塌缩，因为真正稀缺的部分不是把任务做出来，而是判断什么值得做、什么算完成、什么适合这个具体组织。也正因为如此，他认为 AI 会持续推高专家需求，同时把高手的产能边界往外扩。对正在做 applied AI、企业软件或内部自动化的人来说，这期内容的启发是：不要只盯着模型能力曲线，更要盯住那些把模型嵌进真实业务所需的流程、数据和人机协作结构。
原始链接：https://www.youtube.com/playlist?list=PLuMcoKK9mKgHtW_o9h5sGO2vXrffKHwJL

Generated through the Follow Builders skill: https://github.com/zarazhangrui/follow-builders
