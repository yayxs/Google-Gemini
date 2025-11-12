## Gemini 对话的多元入口

gemini.google.com

Gemini 移动应用 (Android & iOS)

Google AI Studio

对于同一个 Gemini 模型，Google AI Studio 的能力更强。

核心原因在于，两者虽然使用相同的底层模型，但定位和开放的控制权限完全不同。

gemini .google .com (Gemini 网页版) 是一个面向普通消费者的产品。它提供了一个简单易用的聊天界面，但模型本身被一层由谷歌预设的“系统指令”所包装。这层包装会引导模型表现得像一个“友好、乐于助人的个人助理”，并附加了严格的安全和行为护栏。用户无法修改这些底层设置。

Google AI Studio 是一个面向开发者、研究人员和 AI 爱好者的开发工具。它提供了对模型更“原始”的访问权限，允许用户进行深度定制和控制，从而挖掘出模型的更强潜力。

# 2.5 pro

| 版本                         | 日期               | 描述                          |
| ---------------------------- | ------------------ | ----------------------------- |
| gemini-2.5-pro               | 2025 年 6 月 17 日 | 稳定版 (Stable Version)       |
| gemini-2.5-pro-preview-06-05 | 2025 年 6 月 5 日  | 预览版 (Preview Versions)     |
| gemini-2.5-pro-preview-05-06 | 2025 年 5 月 6 日  | 预览版 (Preview Versions)     |
| gemini-2.5-pro-preview-03-25 | 2025 年 4 月 4 日  | 预览版 (Preview Versions)     |
| gemini-2.5-pro-exp-03-25     | 2025 年 3 月 25 日 | 实验版 (Experimental Version) |

2 月 6 日，谷歌预告其智能对话机器人 Bard 即将上线；
北京时间 2 月 8 日晚间，谷歌在巴黎举行 AI 发布会，向外界正式披露聊天机器人产品 Bard。作为 ChatGPT 最重要的挑战者，谷歌过去两周没少为这场发布造势，但万众瞩目的产品演示却出了重大纰漏——Bard 在回答「詹姆斯·韦伯空间望远镜的新发现」这个简单问题时，错误地把另一个望远镜取得的成就安给了前者。

## Gemini CLI

核心命令

- /about: 显示版本信息，包括 CLI 版本、操作系统和模型版本。
- /auth: 更改身份验证方法，用于登录和授权。
- /bug: 提交错误报告。此命令会生成一个包含调试信息的 URL，以便您在浏览器中轻松创建 issue。
- /clear: 清除屏幕和当前的对话历史记录。
- /compress (或 /summarize): 通过将当前对话上下文替换为摘要来压缩它，有助于在长对话中节省 token。
- /copy: 将上一次 AI 的回答或代码片段复制到剪贴板。
- /docs: 在浏览器中打开 Gemini CLI 的完整文档。
- /help (或 /?): 显示关于 Gemini CLI 的帮助信息。
- /init: 分析当前项目并创建一个定制的 GEMINI.md 文件，用于为后续交互提供上下文。
- /privacy: 显示隐私声明。
- /quit (或 /exit): 退出 Gemini CLI。
- /stats (或 /usage): 查看当前会话的统计信息。
  - model: 显示与模型相关的用量统计。
  - tools: 显示与工具相关的用量统计。
- /tools: 列出所有可用的 Gemini CLI 内置工具。
  - desc: 列出工具并显示其详细描述。

对话管理

- /chat: 管理对话历史记录。
  - list: 列出所有已保存的对话检查点。
  - save <tag>: 将当前对话保存为一个检查点，并用 <tag> 标记。
  - resume <tag> (或 load <tag>): 从指定的检查点恢复对话。
  - delete <tag>: 删除一个已保存的对话检查点。
  - share <file>: 将当前对话以 Markdown 或 JSON 格式分享到指定文件。

功能与设置

- /editor: 设置您偏好的外部编辑器。
- /ide: 管理与 IDE 的集成。
  - status: 检查与 IDE 的连接状态。
  - install: 为您当前使用的 IDE（如 VS Code）安装所需的配套扩展。
  - enable: 启用 IDE 集成。
  - disable: 禁用 IDE 集成。
- /memory: 与 CLI 的“记忆”功能交互。
  - show: 显示当前记忆的内容（通常来自 GEMINI.md 文件）。
  - add <text>: 将指定的文本添加到记忆中。
  - refresh: 从源文件（GEMINI.md）重新加载记忆。
  - list: 列出当前正在使用的所有 GEMINI.md 文件的路径。
- /model: 打开一个对话框来配置所使用的模型。
- /permissions: 管理文件夹的信任设置，用于控制 CLI 在不同项目目录中的权限。
- /settings: 查看和编辑 Gemini CLI 的各项设置。
- /terminal-setup: 为您的终端（支持 VS Code, Cursor, Windsurf）配置快捷键，以实现多行输入。
- /theme: 更改 CLI 的显示主题（颜色方案）。
- /vim: 开启或关闭 Vim 输入模式。

扩展与集成

- /extensions: 管理 CLI 的扩展。
  - list: 列出所有已安装和激活的扩展。
  - update <name|--all>: 更新指定的扩展或所有扩展。
  - explore: 在浏览器中打开扩展市场页面。
  - restart <name|--all>: 重启指定的或所有激活的扩展。
  - enable <name>: 启用一个扩展。
  - disable <name>: 禁用一个扩展。
- /mcp: 管理模型上下文协议 (Model Context Protocol) 服务器的配置。
  - list: 列出已配置的 MCP 服务器和工具。
  - desc: 列出服务器和工具，并附带详细描述。
  - schema: 列出服务器和工具，并附带描述和 schema 定义。
  - auth <server>: 对支持 OAuth 的 MCP 服务器进行身份验证。
  - refresh: 重启所有 MCP 服务器并刷新工具列表。
- /policies: 管理工具执行的策略。
  - list: 列出所有活动的策略规则。
- /restore: 恢复一个之前被建议但未执行的工具调用。
- /setup-github: 帮助您在当前的 GitHub 仓库中设置用于代码审查、Issue 分类等的 GitHub Actions 工作流
