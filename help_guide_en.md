# ezcoder-ecli Configuration Guide

[🌐 中文版](./help_guide.md)

## Quick Start

1. Launch the ezcoder-ecli desktop app
2. Choose the configuration method below based on your use case
3. Type `ecli` / `/ecli` / `启动ecli` in Copilot Chat to begin
4. Please try to use advanced models. Auto might work wonders.

> 💡 **The built-in terminal requires no configuration**

---

## VS Code Configuration

### Project Level (Recommended)

Create `.vscode/mcp.json` in your project root:

```json
{
  "servers": {
    "ezcoder-ecli": {
      "type": "stdio",
      "command": "C:\\Users\\<username>\\AppData\\Local\\ezcoder-ecli\\ezcoder-ecli-mcp-server.exe",
      "args": []
    }
  }
}
```

Applies only to the current project. Can be committed to version control.

### Global Level

Recommended (new): edit user-level `mcp.json` (Windows default: `%APPDATA%\\Code\\User\\mcp.json`):

```json
{
  "servers": {
    "ezcoder-ecli": {
      "type": "stdio",
      "command": "C:\\Users\\<username>\\AppData\\Local\\ezcoder-ecli\\ezcoder-ecli-mcp-server.exe",
      "args": []
    }
  }
}
```

Legacy compatibility: if your VS Code still reads MCP from `settings.json`, you can use:

```json
{
  "mcp": {
    "servers": {
      "ezcoder-ecli": {
        "type": "stdio",
        "command": "C:\\Users\\<username>\\AppData\\Local\\ezcoder-ecli\\ezcoder-ecli-mcp-server.exe",
        "args": []
      }
    }
  }
}
```

Both are global configurations and apply to all projects.

---

## Copilot CLI Configuration

### Project Level (Recommended)

Create `.mcp.json` in your project root:

```json
{
  "mcpServers": {
    "ezcoder-ecli": {
      "type": "stdio",
      "command": "C:\\Users\\<username>\\AppData\\Local\\ezcoder-ecli\\ezcoder-ecli-mcp-server.exe",
      "args": []
    }
  }
}
```

Applies only to the current project (Copilot CLI v1.0.22+).

### Global Level

Edit `~/.copilot/mcp-config.json` (Windows: `%USERPROFILE%\.copilot\mcp-config.json`):

```json
{
  "mcpServers": {
    "ezcoder-ecli": {
      "type": "stdio",
      "command": "C:\\Users\\<username>\\AppData\\Local\\ezcoder-ecli\\ezcoder-ecli-mcp-server.exe",
      "args": []
    }
  }
}
```

Applies to all Copilot CLI sessions.

---

## Other Configurations

If your tool is not listed above, you can manually configure the MCP server with these key parameters:

| Parameter | Value |
|-----------|-------|
| **type** | `stdio` |
| **command** | Full path to the `ezcoder-ecli-mcp-server` executable |
| **args** | `[]` |

---

## Usage

### Built-in Terminal (No Configuration Needed)

- Open the app and type the trigger word in the terminal to start a conversation

### External AI Clients

- Open Copilot Chat (VS Code or CLI)
- Type `ecli` / `/ecli` / `启动ecli` to start an ecli session
- Messages will automatically sync to the ezcoder-ecli desktop app
- Type messages in the desktop app, and Copilot will receive and reply automatically

## Settings

| Setting | Description |
|---------|-------------|
| **Polling Timeout** | Controls how often the "running MCP" prompt refreshes (seconds). Does not affect message latency. |
| **MCP Instructions** | Customize Copilot's behavior instructions. Reconnect MCP after changes to take effect. |

## FAQ

**Q: Can't find the MCP tool after configuration?**
A: Make sure the ezcoder-ecli desktop app is running, then restart the MCP connection.

**Q: No reply after sending a message?**
A: Check the Output panel for MCP-related error messages.

**Q: How to update MCP instructions?**
A: Open the settings panel to edit instructions, save, then reconnect MCP.

**Q: MCP tool keeps asking for permission every time, how to fix?**
A: Set MCP permissions to Workspace level to avoid repeated authorization prompts. In VS Code, when the MCP tool authorization prompt appears, select **"Allow for Workspace"** to grant permanent access for the current project. Other permissions (file read/write, terminal execution, etc.) can be handled according to your actual needs.

**Q: Copilot shows "has been working on this problem for a while"?**
A: This is the VS Code max requests limit. Open VS Code Settings (`Ctrl+,`), search for `Max Requests`, and increase `Chat: Agent Max Requests` (recommended: 200) to avoid frequent interruptions.

**Q: Copilot doesn't invoke MCP tools after typing the trigger word?**
A: If the trigger word doesn't work, try asking Copilot in natural language to connect to MCP. For example:
- "Connect to ecli and keep the MCP connection alive"
- "Start ecli and begin a conversation"
- "Talk to ecli"
- "连接 ecli 并保持长连接"
