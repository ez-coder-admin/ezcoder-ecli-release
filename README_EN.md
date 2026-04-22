# ezcoder-ecli

[中文](./README.md) | English

> 🚀 Give your AI coding assistant a dedicated desktop window

**ezcoder-ecli** is a Windows desktop app that connects to GitHub Copilot, Claude, Cursor, and other AI coding tools via the MCP protocol. Manage all your projects' AI sessions in one window with permanently saved conversation history — never lose a chat again.

![ezcoder-ecli demo](./screenshots/demo.gif)

---

## ✨ Why ezcoder-ecli?

| Pain Point | ezcoder-ecli Solution |
|------------|----------------------|
| Claude Opus 4.6 / Claude Sonnet 4.6 / GPT-5.4 / GPT-5.3-Codex and more | Full-power, native models |
| No proxies, no third-party middlemen | Model fidelity with more accurate model context |
| Reduce wasted conversation rounds through precise context, significantly improving token (quota) usage |
| AI chat squeezed into IDE sidebar — small and clunky | Standalone desktop window — pin on top or go fullscreen |
| Switching projects means switching IDE windows; chat history gets mixed up | One window for all projects, independent multi-session switching |
| Conversation history lost after IDE restart | Sessions saved permanently — revisit anytime |
| Re-explaining context every time | Custom Instructions — set once, auto-applied every time |
| Pay-per-use billing; repeated back-and-forth wastes quota | Rich context helps AI understand intent on the first try, fewer wasted rounds |
| Locked into a specific IDE or AI tool | Compatible with any MCP-enabled client |

---

## 🖥️ Feature Highlights

- 💬 **Standalone Desktop Chat Window** — Pin on top or go fullscreen; 3× the conversation space of a sidebar
- 📁 **Multi-Project × Multi-Session** — Manage all projects in one window; isolated sessions, zero interference
- 💾 **Permanent Session History** — IDE restarts won't lose your chats; revisit past conversations anytime
- 📎 **@ File References** — Directory browsing + glob search to quickly attach context
- 🖼️ **Image Sending** — Send screenshots directly to AI (up to 3 per message)
- ⚡ **More Efficient Quota Usage** — Rich file context + preset instructions reduce wasted rounds
- ⚙️ **Custom Instructions** — Set coding style, project background; configure once, apply every time
- 🔒 **Secure, Transparent & Model-Faithful** — No token interception, no third-party routing, no model output modification; all prompts visible in terminal
- 🔌 **Compatible with All AI Clients** — VS Code Copilot, Claude Desktop, Cursor, JetBrains, and more
- 🌐 **Bilingual Interface** — Chinese & English
- ⬆️ **Auto Updates** — Silent background detection, one-click upgrade

---

## 🔒 Security & Privacy

> ezcoder-ecli is not a proxy, not a middleman. Every conversation goes directly through the official AI client.

- **Never touches your tokens** — Authentication is handled entirely by the official CLI / VS Code / Claude Desktop / Cursor client
- **No third-party servers** — All communication stays local (127.0.0.1)
- **No model output modification** — You receive the AI's native response, zero tampering
- **Standard MCP Protocol** — Industry-standard Model Context Protocol interface

> ⚠️ **Saving money doesn't require taking risks**
>   - Don't use proxies. Don't use proxies. Don't use proxies.
>   - Don't use token pools. Don't use token pools. Don't use token pools.
>   - Important enough to say three times.
>
>   - We reduce wasted conversation rounds through precise context, significantly improving token (quota) usage.

---

## 📦 Download & Install

### [⬇️ Download Latest Release](https://github.com/ez-coder-admin/ezcoder-ecli-release/releases/latest)

| Platform | Installer |
|----------|-----------|
| Windows x64 | `ezcoder-ecli_*_x64-setup.exe` |

Download and double-click the installer to complete setup.

---

## 🚀 Quick Start

1. **Install** ezcoder-ecli and launch it
2. Click **Help** in the app, select your AI client, and click **Auto Configure**
3. Select a model, type the trigger word in the terminal, and start chatting 🎉
4. Use an advanced model for best results — basic models may underperform.

The app includes one-click configuration for the following clients:

| AI Client | Configuration |
|-----------|--------------|
| **Built-in Terminal** | **No setup needed** — ready to use |
| VS Code Copilot | Project-level (`.vscode/mcp.json`) / Global (`settings.json`) |
| Copilot CLI | Project-level (`.mcp.json`) / Global (`~/.copilot/mcp-config.json`) |
| JetBrains + Copilot | Global config (`mcp.json`) |
| Claude Desktop | Global config (`claude_desktop_config.json`) |
| Claude Code CLI | Project-level (`.mcp.json`) / Global (`~/.claude.json`) |
| Cursor | Project-level (`.cursor/mcp.json`) / Global settings |
| Other MCP Clients | Help page provides generic parameters for manual setup |

> 💡 The built-in terminal requires no configuration — ready to use out of the box. External client config paths are auto-generated based on your environment; first-time setup takes less than 1 minute.

📖 Detailed configuration guide: [中文](./help_guide.md) | [English](./help_guide_en.md)

---

## 🔧 Requirements

- Windows 10 / 11 (x64)
- Any AI client with MCP support, for example:
  - [GitHub Copilot CLI](https://docs.github.com/en/copilot/how-tos/copilot-cli/cli-getting-started)
  - [VS Code](https://code.visualstudio.com/) + [GitHub Copilot](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot)
  - [Claude Desktop](https://claude.ai/download) / [Claude Code CLI](https://docs.anthropic.com/en/docs/claude-code/overview)
  - [Cursor](https://cursor.sh/)
  - [JetBrains IDE](https://www.jetbrains.com/) + [GitHub Copilot](https://plugins.jetbrains.com/plugin/17718-github-copilot)

---

## 💬 Feedback & Support

Found a bug or have a feature request? [Open an Issue](https://github.com/ez-coder-admin/ezcoder-ecli-release/issues)
