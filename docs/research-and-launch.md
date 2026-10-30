# MARIS：竞品分析与发布建议

调研日期：2026 年 10 月 30 日（北京时间）。范围是公开 GitHub 项目、skills.sh 排行及官方文档；不可能穷尽所有相关 Skill，以下是按相关性和热度选出的代表样本。仓库 Star 是整个仓库的热度，不能代表某个 Skill 的安装量或实际效果；安装量也不等于活跃用户数。数值会变化。

## 直接相关的项目

| 项目 | 具体工作和入口 | 对 MARIS 的启发及区别 |
| --- | --- | --- |
| [HumanLayer show-me](https://github.com/humanlayer/skills/blob/main/plugins/show-me/skills/show-me/SKILL.md) | 解释当前话题时选择简洁图、代码结构、差异或 HTML；[README](https://github.com/humanlayer/skills) 提供单条安装命令。 | 是最直接的竞品。MARIS 不以图为默认结果，而先解释对判断有影响的条件；这只是设计假设，必须用对照验证。 |
| [Matt Pocock wait-what](https://github.com/mattpocock/skills/blob/main/skills/productivity/wait-what/SKILL.md) | 用户觉得上一条没听懂时重新讲，补上下文并使用项目术语。 | 入口极清楚，边界是修复上一条消息。MARIS 面向当前任务中的某个结果或选择，不局限上一条；重叠很大。 |
| [Matt Pocock pr](https://github.com/mattpocock/skills/blob/main/skills/engineering/pr/SKILL.md) | 为 PR 正文组织摘要、证据和合并风险，并使用适合的表示。 | 把“帮助判断”绑定到具体交付物。MARIS 不生成 PR 正文，借鉴的是围绕当前判断解释证据与影响。 |
| [Matt Pocock teach](https://github.com/mattpocock/skills/blob/main/skills/productivity/teach/SKILL.md) | 面向持续学习，建立学习材料并组织课程。 | 教学深度和长期产物是另一条路线；MARIS 只服务眼前的问题，不建立课程或测验流程。 |
| [posit-conf explain](https://github.com/posit-conf-2026/llms/blob/main/.github/skills/explain/SKILL.md) | 用适合读者的节奏解释代码、变化或概念；区分直接回答和明确要求教学。 | 有证据说明竞品也关注理解和节奏，不能把自然追问或适配读者当成独有功能。该项目未核实为爆款，因直接相关纳入。 |
| [helderberto explain-code](https://github.com/helderberto/agent-skills/blob/main/skills/explain-code/SKILL.md) | 解释代码，要求类比、ASCII 图、逐步讲解和易错点。 | 输出结构很具体，但每次强制图和类比不适合所有问题。该项目未核实为爆款，因直接相关纳入。 |

## 热门项目和分发方式

| 项目 | 公开热度快照 | 可借鉴之处 |
| --- | --- | --- |
| [mattpocock/skills](https://github.com/mattpocock/skills) | GitHub 约 306.2k stars | 能清楚说出每项 Skill 的触发时刻与结果；其 [grill-me 在 skills.sh](https://skills.sh/) 显示约 1.5M 次安装，不能把该数字套到其他 Skill。 |
| [obra/superpowers](https://github.com/obra/superpowers) | 约 308.0k stars | 完整方法论覆盖软件开发流程；热度证明对工作流有需求，并不证明 MARIS 应复制框架复杂度。 |
| [anthropics/skills](https://github.com/anthropics/skills) | 约 184.7k stars | 官方 Skill 示例和文件格式有助于降低使用门槛，仓库包含多种许可，不能简单将仓库热度归因于某个 Skill。 |
| [vercel-labs/agent-skills](https://github.com/vercel-labs/agent-skills) | 约 33.2k stars | Skill 对准具体任务；README 展示使用场景和安装。 |
| [vercel-labs/skills](https://github.com/vercel-labs/skills) | 约 37.1k stars；skills.sh 的 find-skills 约 4.1M 次安装 | 一条安装命令有利于传播。等仓库地址确定并实际测试后，再发布准确的 `npx skills add` 命令。 |

以上数字来自各项目 GitHub 页面与 [skills.sh](https://skills.sh/) 的页面快照，均为近似值，不同统计口径不能直接相加；并非全网排行榜或效果排名。

## 定位与范围

**面向谁：** 使用 Claude 等 AI 助手完成代码或分析、但需要判断自己能否信任和使用结果的人。

**使用时刻：** AI 已给出结果，用户没跟上一个关键选择，或者需要知道条件变化会不会改变判断。

**产品承诺：** 帮用户看懂当前工作中影响结果的选择；可追问、尽可能用具体材料解释。

**可证伪的差异假设：** 相比普通追问和 show-me，MARIS 能更稳定地指出决定结果的条件，并用贴近任务的例子说明变化。这个假设尚无用户测试支持。show-me 也可能做到这些，不能声称独有。

**不宣传：** 智能体框架、自动审计、保证准确、消除幻觉、读取长期记忆、经过验证的效率提升。首次发布不暗示跨产品已经验证。

**命名建议：** 保留 MARIS，仓库建议 `maris-skill`；GitHub 简介建议：`Understand the choices that shape an AI result.` Topics 可用 `agent-skills`, `claude`, `ai-agents`, `explainability`。仓库名和品牌可用性未核实，发布前再查。

## 宣传草稿

中文短帖：

> AI 帮你完成了任务，但你真的知道哪个选择改变了结果吗？
>
> 我们做了一个小 Skill：MARIS。遇到 AI 的代码、分析或建议看不懂时，让它指出关键条件，再用具体例子解释这个条件如何影响结果。
>
> 第一版只有一个 Skill 文件。我们正在寻找愿意拿真实任务试一试的人：它是否比直接追问 AI 更有帮助？欢迎分享你卡住的地方。

英文短帖：

> AI finished the task. Do you know which choice shaped the result?
>
> MARIS is a small Agent Skill for understanding the assumptions and decisions behind AI-generated work. Ask it to walk you through what matters, then keep asking until the point is clear.
>
> Early release: we're looking for real examples, including cases where a normal prompt works just as well.

两段均为可修改的发布草稿；只有仓库实际公开后才加真实链接，未做效果承诺。

## 最小验证

请已有的 Claude 用户带一个自己真实且可分享的任务，在相同上下文中比较普通追问与 MARIS；可交换顺序或在不同任务上反向比较以减轻先后顺序和重复学习影响。记录对话与是否成功加载 Skill。

1. 不提示答案，让参与者指出哪个条件影响结果、条件变化会如何改变判断，并说明下一步是否会接受结果。
2. 比较解释是否准确、是否引用当前材料、误导和遗漏、理解所花时间，以及他是否愿意再次使用；不要只看输出长短。
3. 至少包含一个条件成立的案例和一个无法从材料确定理由的案例，观察是否错误否定或编造动机。
4. 一个人的体验只能用于发现问题，不能证明普遍效果。若与普通追问或 show-me 没有可感知差别，调整具体行为或重新定位。

## 发布前核对

- 使用真实 Claude 账号上传 ZIP，确认显示和调用；按 [官方说明](https://support.claude.com/en/articles/12512180-use-skills-in-claude) 验证，界面正在逐步调整。
- 完成上面的真实任务对比，再将结果如实加入 README；示例仍应标为示意。
- 确认仓库名、维护者署名和 MIT 许可；创建真实仓库后核对下载链接与安装命令。
- 如发布更新，同步重建 ZIP，使其与 `maris/SKILL.md` 一致。
