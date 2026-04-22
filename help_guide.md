# ezcoder-ecli 配置指南

[🌐 English Version](./help_guide_en.md)

## 快速开始

1. 启动 ezcoder-ecli 桌面应用
2. 根据使用场景选择下方配置方式
3. 在 Copilot Chat 中输入 `ecli` / `/ecli` / `启动ecli` 即可开始
4. 请尽量使用高级模型，使用Auto也许会有奇效

> 💡 **推荐直接使用内置终端，无需任何配置**

---

## VS Code 配置

### 项目级别（推荐）

在项目根目录创建 `.vscode/mcp.json`：

```json
{
  "servers": {
    "ezcoder-ecli": {
      "type": "stdio",
      "command": "C:\\Users\\<用户名>\\AppData\\Local\\ezcoder-ecli\\ezcoder-ecli-mcp-server.exe",
      "args": []
    }
  }
}
```

仅对当前项目生效，可纳入版本控制。

### 全局级别

推荐（新版）：编辑用户级 `mcp.json`（Windows 默认：`%APPDATA%\\Code\\User\\mcp.json`）：

```json
{
  "servers": {
    "ezcoder-ecli": {
      "type": "stdio",
      "command": "C:\\Users\\<用户名>\\AppData\\Local\\ezcoder-ecli\\ezcoder-ecli-mcp-server.exe",
      "args": []
    }
  }
}
```

兼容（旧版）：如果你的 VS Code 仍按 `settings.json` 读取 MCP，也可以使用：

```json
{
  "mcp": {
    "servers": {
      "ezcoder-ecli": {
        "type": "stdio",
        "command": "C:\\Users\\<用户名>\\AppData\\Local\\ezcoder-ecli\\ezcoder-ecli-mcp-server.exe",
        "args": []
      }
    }
  }
}
```

以上两种都属于全局配置，对所有项目生效。

---

## Copilot CLI 配置

### 项目级别（推荐）

在项目根目录创建 `.mcp.json`：

```json
{
  "mcpServers": {
    "ezcoder-ecli": {
      "type": "stdio",
      "command": "C:\\Users\\<用户名>\\AppData\\Local\\ezcoder-ecli\\ezcoder-ecli-mcp-server.exe",
      "args": []
    }
  }
}
```

仅对当前项目生效（Copilot CLI v1.0.22+）。

### 全局级别

编辑 `~/.copilot/mcp-config.json`（Windows: `%USERPROFILE%\.copilot\mcp-config.json`）：

```json
{
  "mcpServers": {
    "ezcoder-ecli": {
      "type": "stdio",
      "command": "C:\\Users\\<用户名>\\AppData\\Local\\ezcoder-ecli\\ezcoder-ecli-mcp-server.exe",
      "args": []
    }
  }
}
```

对所有 Copilot CLI 会话生效。

---

## JetBrains IDEA 配置

### 项目级别（推荐）

在项目根目录下创建 `.idea/mcp.json`：

```json
{
  "servers": {
    "ezcoder-ecli": {
      "type": "stdio",
      "command": "C:\\Users\\<用户名>\\AppData\\Local\\ezcoder-ecli\\ezcoder-ecli-mcp-server.exe",
      "args": [],
      "env": {
        "ECLI_WORKSPACE": "/path/to/your/project"
      }
    }
  }
}
```

仅对当前项目生效。`ECLI_WORKSPACE` 需设置为当前项目的绝对路径，JetBrains IDE 不会自动传递项目路径给 MCP Server。

### 全局级别

编辑 MCP 配置文件（Windows: `%LOCALAPPDATA%\github-copilot\intellij\mcp.json`）：

```json
{
  "servers": {
    "ezcoder-ecli": {
      "type": "stdio",
      "command": "C:\\Users\\<用户名>\\AppData\\Local\\ezcoder-ecli\\ezcoder-ecli-mcp-server.exe",
      "args": []
      // "env": {
      //   "ECLI_WORKSPACE": "/path/to/your/project"
      // }
    }
  }
}
```

对所有 JetBrains IDE（IntelliJ IDEA、WebStorm、PyCharm 等）中的 Copilot 生效。

---

## Claude Desktop 配置

编辑配置文件（Windows: `%APPDATA%\Claude\claude_desktop_config.json`）：

```json
{
  "mcpServers": {
    "ezcoder-ecli": {
      "command": "C:\\Users\\<用户名>\\AppData\\Local\\ezcoder-ecli\\ezcoder-ecli-mcp-server.exe",
      "args": []
    }
  }
}
```

修改后重启 Claude Desktop 生效。

---

## Claude Code CLI 配置

### 项目级别

在项目根目录创建 `.mcp.json`：

```json
{
  "mcpServers": {
    "ezcoder-ecli": {
      "command": "C:\\Users\\<用户名>\\AppData\\Local\\ezcoder-ecli\\ezcoder-ecli-mcp-server.exe",
      "args": []
    }
  }
}
```

### 全局级别

运行以下命令添加全局 MCP 服务：

```bash
claude mcp add ezcoder-ecli -- "C:\Users\<用户名>\AppData\Local\ezcoder-ecli\ezcoder-ecli-mcp-server.exe"
```

或手动编辑 `~/.claude.json`（Windows: `%USERPROFILE%\.claude.json`）。

---

## Cursor 配置

### 项目级别

在项目根目录创建 `.cursor/mcp.json`：

```json
{
  "mcpServers": {
    "ezcoder-ecli": {
      "command": "C:\\Users\\<用户名>\\AppData\\Local\\ezcoder-ecli\\ezcoder-ecli-mcp-server.exe",
      "args": []
    }
  }
}
```

### 全局级别

打开 Cursor 设置 → MCP，添加服务器配置。

---

## 其他配置

如果你使用的工具不在上述列表中，可以手动配置 MCP 服务，关键参数如下：

| 参数 | 值 |
|--------|------|
| **type** | `stdio` |
| **command** | `ezcoder-ecli-mcp-server` 可执行文件的完整路径 |
| **args** | `[]` |

### 环境变量

| 变量名 | 说明 |
|--------|------|
| **ECLI_WORKSPACE** | 指定项目工作目录的绝对路径。设置后 MCP 会话将关联到该目录对应的项目，而非 MCP 进程的当前工作目录。适用于 JetBrains IDEA 等 IDE 不会自动传递项目路径的场景。建议在项目级 `.idea/mcp.json` 中配置。 |

示例（项目级 `.idea/mcp.json` 配置）：

```json
{
  "servers": {
    "ezcoder-ecli": {
      "type": "stdio",
      "command": "C:\\Users\\<用户名>\\AppData\\Local\\ezcoder-ecli\\ezcoder-ecli-mcp-server.exe",
      "args": [],
      "env": {
        "ECLI_WORKSPACE": "/path/to/your/project"
      }
    }
  }
}
```

---

## 使用方式

### 内置终端（无需配置）

- 打开应用，在终端中输入启动词即可开始对话

### 外部 AI 客户端

- 打开 Copilot Chat（VS Code 或 CLI）
- 输入 `ecli` / `/ecli` / `启动ecli` 启动 ecli 会话
- 消息会自动同步到 ezcoder-ecli 桌面应用
- 在桌面应用中输入消息，Copilot 会自动接收并回复

## 设置说明

| 设置项 | 说明 |
|--------|------|
| **轮询超时** | 控制 "running MCP" 提示的刷新频率（秒），不影响消息延迟 |
| **MCP 提示词** | 自定义 Copilot 的行为指令，修改后需重新连接 MCP 生效 |

## 常见问题

**Q: 配置后找不到 MCP 工具？**
A: 确保 ezcoder-ecli 桌面应用已启动，然后重启 MCP 连接。

**Q: 消息发送后没有收到回复？**
A: 检查 Output 面板中是否有 MCP 相关错误信息。

**Q: 如何更新 MCP 提示词？**
A: 打开设置面板修改提示词，保存后重新连接 MCP。

**Q: MCP 工具每次使用都需要授权，很烦怎么办？**
A: 建议将 MCP 权限设置为 Workspace 级别，避免反复授权弹窗。在 VS Code 中，当出现 MCP 工具授权提示时，选择 **"Allow for Workspace"** 即可对当前项目永久生效。其他权限（如文件读写、终端执行等）可根据实际需要酌情处理。

**Q: Copilot 提示 "has been working on this problem for a while"？**
A: 这是 VS Code 的最大请求次数限制。打开 VS Code 设置（`Ctrl+,`），搜索 `Max Requests`，将 `Chat: Agent Max Requests` 调高（建议 200），即可避免频繁中断。

**Q: 输入触发词后 Copilot 没有调用 MCP 工具？**
A: 如果触发词失效，可以尝试用自然语言要求 Copilot 主动连接 MCP，例如：
- "连接 ecli 并保持长连接"
- "启动 ecli 并开始对话"
- "跟 ecli 对话"
- "Connect to ecli and keep the MCP connection alive"
