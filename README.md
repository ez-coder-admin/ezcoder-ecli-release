# ezcoder-ecli

[English](./README_EN.md) | 中文

> 🚀 给你的 AI 编程助手一个独立桌面窗口

**ezcoder-ecli** 是一款 Windows 桌面应用，通过 MCP 协议连接 GitHub Copilot、Claude、Cursor 等 AI 编程工具。一个窗口管理所有项目的 AI 会话，对话记录永久保存，不再丢失。

![ezcoder-ecli demo](./screenshots/demo.gif)

---

## ✨ 为什么选择 ezcoder-ecli？

| 痛点 | ezcoder-ecli 的解决方案 |
|------|------------------------|
| Claude Opus 4.6 / Claude Sonnet 4.6 / GPT-5.4 / GPT-5.3-Codex 等模型 | 原装满血 |
| 非中转、非三方 | 模型保真、更精准的模型上下文 |
| 通过更精准的上下文减少无效对话轮次，显著提高 Token（配额）使用率，一个Pro管饱 |
| AI 聊天挤在 IDE 侧边栏，空间小、操作不便 | 独立桌面窗口，可置顶、可全屏 |
| 切项目要切 IDE 窗口，聊天记录混乱 | 一个窗口管理所有项目，多会话独立切换 |
| IDE 重启后对话历史丢失 | 会话永久保存，随时回顾 |
| 每次都要重新说明上下文 | 自定义 Instructions，一次设定，每次自动生效 |
| 按次计费，反复沟通浪费配额 | 丰富的上下文让 AI 一次理解意图，减少无效轮次 |
| 被绑定在某个 IDE 或 AI 工具上 | 兼容所有支持 MCP 的客户端 |

---

## 🖥️ 功能亮点

- 💬 **独立桌面聊天窗口** — 可置顶、可全屏，比侧边栏大 3 倍的对话空间
- 📁 **多项目 × 多会话** — 一个窗口管理所有项目，会话独立、切换零干扰
- 💾 **会话永久保存** — IDE 重启不丢记录，随时回顾历史对话
- 📎 **@ 文件引用** — 目录浏览 + Glob 搜索，快速附加上下文
- 🖼️ **图片发送** — 截图直接发给 AI（每条消息最多 3 张）
- ⚡ **更高效地使用配额** — 丰富的文件上下文 + 预设指令，减少无效轮次
- ⚙️ **自定义 Instructions** — 设定编码风格、项目背景，一次配置每次生效
- 🔒 **安全透明，模型保真** — 不碰 Token、不过第三方、不改模型输出、所有提示词终端可见
- 🔌 **兼容所有 AI 客户端** — VS Code Copilot、Claude Desktop、Cursor、JetBrains 等
- 🌐 **中英文双语界面**
- ⬆️ **自动更新** — 后台静默检测，一键升级

---

## 🔒 安全与隐私

> ezcoder-ecli 不是代理，不是中间人。你的每一次对话都直接通过 AI 客户端官方处理。

- **不接触你的 Token** — 认证完全由 CLI / VS Code / Claude Desktop / Cursor 等官方客户端处理
- **不经过第三方服务器** — 所有通信在本地完成（127.0.0.1）
- **不修改模型输出** — 你收到的就是 AI 原生回复，零篡改
- **使用标准 MCP 协议** — 业界通用的 Model Context Protocol 接口

> ⚠️ **省钱不需要冒风险** 
>   - 别用中转，别用中转，别用中转。
>   - 别搞号池，别搞号池，别搞号池。
>   - 重要的事情讲三遍。
>
>   - 我们通过更精准的上下文减少无效对话轮次，显著提高 Token（配额）使用率，一个Pro管饱。

---

## 📦 下载安装

### [⬇️ 点击下载最新版](https://github.com/ez-coder-admin/ezcoder-ecli-release/releases/latest)

| 平台 | 安装包 |
|------|--------|
| Windows x64 | `ezcoder-ecli_*_x64-setup.exe` |

下载后双击安装包，按提示完成安装即可。

---

## 🚀 快速上手

1. **安装** ezcoder-ecli 并启动
2. 点击应用内的 **帮助**，选择你的 AI 客户端，点击 **自动配置**
3. 选择模型，终端输入启动词即可开始对话 🎉
4. 尽量选择高级模型，否则会很呆。

应用内置一键配置，支持以下客户端：

| AI 客户端 | 配置方式 |
|-----------|---------|
| **内置终端** | **无需配置**，打开即用 |
| VS Code Copilot | 项目级（`.vscode/mcp.json`）/ 全局级（`settings.json`） |
| Copilot CLI | 项目级（`.mcp.json`）/ 全局级（`~/.copilot/mcp-config.json`） |
| JetBrains + Copilot | 全局配置（`mcp.json`） |
| Claude Desktop | 全局配置（`claude_desktop_config.json`） |
| Claude Code CLI | 项目级（`.mcp.json`）/ 全局级（`~/.claude.json`） |
| Cursor | 项目级（`.cursor/mcp.json`）/ 全局设置 |
| 其他 MCP 客户端 | 帮助页面提供通用参数，手动配置即可 |

> 💡 内置终端无需配置，打开即用。外部客户端的配置路径均根据当前运行环境自动生成，首次配置不到 1 分钟。

📖 详细配置指南：[中文](./help_guide.md) | [English](./help_guide_en.md)

---

## 🔧 环境要求

- Windows 10 / 11（x64）
- 任何支持 MCP 的 AI 客户端，例如：
  - [GitHub Copilot CLI](https://docs.github.com/en/copilot/how-tos/copilot-cli/cli-getting-started)
  - [VS Code](https://code.visualstudio.com/) + [GitHub Copilot](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot)
  - [Claude Desktop](https://claude.ai/download) / [Claude Code CLI](https://docs.anthropic.com/en/docs/claude-code/overview)
  - [Cursor](https://cursor.sh/)
  - [JetBrains IDE](https://www.jetbrains.com/) + [GitHub Copilot](https://plugins.jetbrains.com/plugin/17718-github-copilot)

---

## 💬 反馈与支持

遇到问题或有功能建议？欢迎提交 [Issue](https://github.com/ez-coder-admin/ezcoder-ecli-release/issues)
