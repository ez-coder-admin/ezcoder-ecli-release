# ezcoder-ecli 发布仓库

本仓库用于托管 [ezcoder-ecli](https://github.com/ez-coder-admin/ezcoder-ecli) 桌面应用的更新资源，供 Tauri 自动更新功能使用。

## 什么是 ezcoder-ecli？

ezcoder-ecli 是一个基于 Tauri 的桌面应用，通过 MCP（Model Context Protocol）实现与 VS Code GitHub Copilot 的双向通信。你可以从桌面端向 Copilot 发送消息、接收回复，支持多项目多会话管理、图片发送、文件引用等功能。

## 下载安装

前往 [Releases](https://github.com/ez-coder-admin/ezcoder-ecli-release/releases/latest) 页面下载最新版本的安装包。

| 平台 | 文件 |
|------|------|
| Windows x64 | `ezcoder-ecli_*_x64-setup.exe` |

## 自动更新

应用内置 Tauri updater 自动更新支持。启动后可在界面上手动检查更新，检测到新版本后可一键下载安装。

更新流程：
1. 客户端从本仓库的 latest release 获取 `latest.json`
2. 比较版本号，若有新版本则提示用户
3. 用户确认后自动下载安装包并验证签名
4. 下载完成后重启安装

## 发布文件说明

每个 Release 包含以下文件：

| 文件 | 说明 |
|------|------|
| `ezcoder-ecli_*_x64-setup.exe` | Windows x64 NSIS 安装包 |
| `ezcoder-ecli_*_x64-setup.exe.sig` | 安装包签名文件（用于自动更新验证） |
| `latest.json` | Tauri updater manifest（版本号、下载地址、签名） |