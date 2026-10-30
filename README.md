# MARIS

**看懂 AI 工作中真正影响结果的选择。**

**Understand the choices that shape an AI result.**

AI 给出了答案，但你还想知道：为什么这样做？哪个条件变了，结论就会变？

MARIS 是一个轻量的 Agent Skill，帮助你围绕当前工作中的选择、假设或限制，得到具体、可以追问的解释。适合读 AI 写的代码、理解分析结论，或看懂一项建议的依据。

## 看懂关键选择

你问：

> 用 MARIS 带我看懂这份实验统计，特别是成功率为什么这样算。

比如，10 次实验中有 8 次成功、2 次失败。计算成功率时，分母的选择会改变结果：

> 这里的关键是分母。如果只保留成功记录，再拿成功记录数除以保留下来的记录数，得到的是 100%；如果衡量全部尝试的成功率，分母应包括失败的两次，结果是 80%。前者不能说明整个方法的可靠性。

## 安装

MARIS 采用 [Agent Skills](https://agentskills.io/) 格式，可在支持该格式的 AI 工具中使用，包括 Claude 和 Codex。

### 让 Agent 安装

在支持安装 Skill 的 Agent 中，直接发送：

> 请帮我安装这个 Skill：https://github.com/chenyongssss/maris-skill.git

安装后，开始新会话并说：“用 MARIS 带我看懂这里。”

### Claude 网页版和桌面版

1. 下载本仓库的 [maris-claude.zip](maris-claude.zip)。
2. 确认 Claude 的文件创建与代码执行功能已启用。
3. 在 Claude 中找到 Skills，选择上传 Skill，然后上传这个 ZIP。界面可能显示为 **Customize** 或 **Plugins**，以你的账户为准。
4. 开启 MARIS，在相关对话里说：“用 MARIS 带我看懂这里，尤其是它为什么影响结果。”

参见 [Claude 官方安装说明](https://support.claude.com/en/articles/12512180-use-skills-in-claude)。

### Claude Code、Codex 等命令行工具

安装 [Node.js](https://nodejs.org/) 22.20 或更高版本后，在终端运行：

```bash
npx skills add chenyongssss/maris-skill --skill maris
```

按提示选择 Claude Code、Codex 或其他支持的工具，以及项目安装或全局安装。安装后在对话中说“用 MARIS 带我看懂这里”；也可以在 Claude Code 中使用 `/maris`，或在 Codex 中使用 `$maris`。

你也可以手动安装：将 [`maris/`](maris/) 文件夹复制到 Claude Code 的 `~/.claude/skills/` 或 Codex 的 `~/.agents/skills/` 目录，再开始新会话。各工具的 Skill 路径和调用方式请参见 [Claude Code 文档](https://code.claude.com/docs/en/skills)和 [Codex 文档](https://developers.openai.com/codex/skills/)。

## 适合什么时候用？

- AI 修改了代码：**“为什么用这个方法？换个输入会怎样？”**
- AI 分析了数据：**“哪个统计口径最影响这个结论？”**
- AI 给出建议：**“如果预算或约束改变，建议还成立吗？”**

你可以继续问“再举个例子”或“我懂了，继续”。MARIS 使用当前可用的材料，帮助你理解关键选择及其影响。

## 参与改进

欢迎在 GitHub Issues 分享你的使用场景和建议。你的反馈将帮助 MARIS 更好地解释 AI 工作中重要的选择。

## License

[MIT](LICENSE)
