# MARIS

**看懂 AI 工作中真正影响结果的选择。**

**Understand the choices that shape an AI result.**

AI 给出了答案，但你还想知道：为什么这样做？哪个条件变了，结论就会变？

MARIS 是一个轻量的 Agent Skill，帮助你围绕当前工作中的选择、假设或限制，得到具体、可以追问的解释。适合读 AI 写的代码、理解分析结论，或看懂一项建议的依据。

## 一个例子

你问：

> 用 MARIS 带我看懂这份实验统计，特别是成功率为什么这样算。

假设任务中有 10 次实验：8 次成功，2 次失败。MARIS 的目标回答可以是：

> 这里的关键是分母。如果只保留成功记录，再拿成功记录数除以保留下来的记录数，得到的是 100%；如果衡量全部尝试的成功率，分母应包括失败的两次，结果是 80%。前者不能说明整个方法的可靠性。

这是**示意回答**，不是实测结果。实际解释取决于你提供的材料和所使用的模型。

## 安装

### Claude 网页版和桌面版

1. 下载本仓库的 [maris-claude.zip](maris-claude.zip)。
2. 确认 Claude 的文件创建与代码执行功能已启用。
3. 在 Claude 中找到 Skills，选择上传 Skill，然后上传这个 ZIP。界面可能显示为 **Customize** 或 **Plugins**，以你的账户为准。
4. 开启 MARIS，在相关对话里说：“用 MARIS 带我看懂这里，尤其是它为什么影响结果。”

参见 [Claude 官方安装说明](https://support.claude.com/en/articles/12512180-use-skills-in-claude)。

### 其他支持 Agent Skills 的工具

将 [`maris/`](maris/) 文件夹放入所用工具的 Skill 目录，并按该工具的方式调用。格式遵循 [Agent Skills 规范](https://agentskills.io/specification)；具体发现、加载和调用方式因工具而异。

## 适合什么时候用？

- AI 修改了代码：**“为什么用这个方法？换个输入会怎样？”**
- AI 分析了数据：**“哪个统计口径最影响这个结论？”**
- AI 给出建议：**“如果预算或约束改变，建议还成立吗？”**

你可以继续问“再举个例子”或“我懂了，继续”。MARIS 会优先使用当前可用的材料，不依赖画像、脚本或外部服务。它不会替代事实核查、代码审查或领域专家的判断。

## 参与改进

这是一个早期版本。欢迎在 GitHub Issues 分享一个真实任务：你问了什么、MARIS 如何回答、哪里仍然没看懂，以及普通提示是否已经足够。分享前请移除敏感内容。

灵感来自 [HumanLayer 的 show-me](https://github.com/humanlayer/skills) 和 [Matt Pocock 的 skills](https://github.com/mattpocock/skills)；MARIS 聚焦当前判断背后的关键条件，这一侧重点是否带来额外价值仍需要检验。

## License

[MIT](LICENSE)
