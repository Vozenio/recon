# Recon

A native HTTP workbench for macOS and Windows, with Repeater, an intercepting Proxy, Findings and a local MCP server. Inspect agent results, share selected HTTP exchanges as context, and register shell tools without rebuilding the app.

## Download

Get **Recon 0.2.3** at [recon.vozen.io](https://recon.vozen.io). This repository hosts downloads and release notes.

| Platform | Download | Requirements |
| --- | --- | --- |
| Windows | [Installer](https://github.com/Vozenio/recon/releases/latest/download/Recon-windows-x64-setup.exe) | Windows 10+, x64, Direct3D 11 capable graphics driver |
| Windows | [Portable ZIP](https://github.com/Vozenio/recon/releases/latest/download/Recon-windows-x64.zip) | Same requirements; unzip and run `recon.exe` |
| macOS | [App bundle](https://github.com/Vozenio/recon/releases/latest/download/Recon-macos.zip) | macOS 15+, Apple Silicon (arm64) |

The interface supports English and 简体中文. No Java, Node.js, Rust or Visual Studio installation is needed to use Recon.

## What's new in 0.2.3

- Project Resources: reusable Markdown guides, variables and credential references for agents through MCP.
- In-app updates from About, with verified downloads, saved work and rollback when startup fails.
- Complete forwarding of large HTTP responses, independent of history capture limits.
- Findings with severity filtering, resizable list/detail panes and preserved selection and return position.
- Resources with type/status filters, expiry presets, inline validation and saved-state feedback.
- Clear project ownership, restored Workspace browsing position and better small-window layouts.

See the [release notes](https://github.com/Vozenio/recon/releases/tag/v0.2.3) for details. Install 0.2.3 manually to get the updater; future releases can be downloaded from About.

![Recon Dashboard](https://recon.vozen.io/app-dashboard.png)

## Windows screenshots

Click a screenshot to view it at full size.

### Repeater

[![Recon Repeater on Windows](https://recon.vozen.io/app-windows-repeater.png)](https://recon.vozen.io/app-windows-repeater.png)

### Dashboard

[![Recon Dashboard on Windows](https://recon.vozen.io/app-windows-dashboard.png)](https://recon.vozen.io/app-windows-dashboard.png)

### Findings

[![Recon Findings on Windows](https://recon.vozen.io/app-windows-findings-demo.png)](https://recon.vozen.io/app-windows-findings-demo.png)

### Shell tools

[![Recon shell tool editor on Windows](https://recon.vozen.io/app-windows-tools.png)](https://recon.vozen.io/app-windows-tools.png)

## Install

On Windows, run the installer. It installs for your account and adds a Start menu shortcut; a desktop shortcut is optional. The portable ZIP can be unzipped to any writable folder. Windows packages are currently unsigned, so a publisher or SmartScreen notice may appear. Uninstalling keeps your settings and projects.

On macOS, unzip and move `Recon.app` to `/Applications`. The app is ad-hoc signed and not notarized. On first launch, use Right-click → Open → Open. If macOS still blocks it, remove the quarantine flag with `xattr -dr com.apple.quarantine /Applications/Recon.app`.

Open Recon and start a project. Enable Proxy or MCP when you need them.

## Connections and tools

- Proxy defaults to `127.0.0.1:8080`. Enable Allow LAN devices in Settings only when you need another device to connect.
- MCP uses Streamable HTTP at `http://127.0.0.1:9877/mcp` with a bearer token. Copy the connection configuration from MCP → Connection → Add client.
- Configure Allow / Ask / Deny per capability. Scope enforcement and request limits are optional; new or changed shell commands require review under Ask.
- Resources belong to the current project. Store reusable instructions, identifiers and credentials; agents discover references through MCP, and supported HTTP requests resolve credential references inside Recon when sending.
- Shell registrations are shared across projects; availability and default arguments belong to the current project. Commands receive JSON arguments on stdin and execute locally through `/bin/sh` on macOS or Windows PowerShell 5.1 on Windows.
- Project data stays on your computer. Default projects are under `~/Library/Application Support/Recon/projects` on macOS and `%LOCALAPPDATA%\Recon\projects` on Windows. Recon does not require a cloud account.

## Feedback

Report bugs or suggestions in [Issues](https://github.com/Vozenio/recon/issues). Include the app version and steps to reproduce; remove credentials and sensitive HTTP data before attaching examples.
