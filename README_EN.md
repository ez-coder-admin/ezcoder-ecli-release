# ezcoder-ecli Release Repository

This repository hosts update resources for the [ezcoder-ecli](https://github.com/ez-coder-admin/ezcoder-ecli) desktop application, used by the Tauri auto-updater.

## What is ezcoder-ecli?

ezcoder-ecli is a Tauri-based desktop application that enables two-way communication with VS Code GitHub Copilot via MCP (Model Context Protocol). Send messages to Copilot from your desktop, receive real-time replies, manage multiple projects and sessions, send images, reference files, and more.

## Download

Head to the [Releases](https://github.com/ez-coder-admin/ezcoder-ecli-release/releases/latest) page to download the latest installer.

| Platform | File |
|----------|------|
| Windows x64 | `ezcoder-ecli_*_x64-setup.exe` |

## Auto Update

The app includes built-in Tauri updater support. You can manually check for updates from the UI. When a new version is available, download and install with one click.

Update flow:
1. The client fetches `latest.json` from the latest release of this repository
2. Compares version numbers; prompts the user if a newer version is available
3. Upon confirmation, downloads the installer and verifies its signature
4. Restarts and installs after download completes

## Release Assets

Each release contains the following files:

| File | Description |
|------|-------------|
| `ezcoder-ecli_*_x64-setup.exe` | Windows x64 NSIS installer |
| `ezcoder-ecli_*_x64-setup.exe.sig` | Installer signature file (for auto-update verification) |
| `latest.json` | Tauri updater manifest (version, download URL, signature) |

## License

[MIT License](https://github.com/ez-coder-admin/ezcoder-ecli/blob/main/LICENSE)
