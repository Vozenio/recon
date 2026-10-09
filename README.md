# Recon

A native macOS HTTP workbench with Repeater, an intercepting Proxy, Findings and a local MCP server. Inspect agent results, share selected HTTP exchanges as context, and register shell tools without rebuilding the app.

## Download

Get **Recon 0.2.1** at [recon.vozen.io](https://recon.vozen.io), or download `Recon-macos.zip` from [the latest release](https://github.com/Vozenio/recon/releases/latest). This repository hosts downloads and release notes.

Requirements: **macOS on Apple Silicon (arm64)**. The interface supports English and 简体中文.

## What's new in 0.2.1

- Resume the last page used in each project, including Repeater drafts and restored focus.
- A focused Dashboard with project status, pending findings, recent work and running tasks.
- MCP calls show arguments, progress and complete results inline, using the same HTTP components as Repeater.
- Manage built-in availability and custom shell tools per project; agents can use `manage_tool` to list, add, update and disable tools.
- Share HTTP exchanges with agents as project context, with notes and explicit copy actions in context menus.
- Consistent GPUI Kit controls, improved Chinese input, readable Markdown, compact menus and layouts for narrow windows.
- Saving failures preserve work for retry; damaged sessions retain recovery copies.

See the [release notes](https://github.com/Vozenio/recon/releases/tag/v0.2.1) for details.

![Recon Dashboard](https://recon.vozen.io/app-dashboard.png)

## Install

1. Download and unzip, then move `Recon.app` to `/Applications`.
2. The app is ad-hoc signed and **not notarized**. On first launch, use **Right-click → Open → Open**. If macOS still blocks it, remove its quarantine flag with `xattr -dr com.apple.quarantine /Applications/Recon.app`.
3. Open Recon and start a project. Enable Proxy or MCP when you need them.

## Connections and tools

- Proxy defaults to `127.0.0.1:8080`. Enable Allow LAN devices in Settings only when you need another device to connect.
- MCP uses Streamable HTTP at `http://127.0.0.1:9877/mcp` with a bearer token. Copy the connection configuration from MCP → Connection → Add client.
- Configure Allow / Ask / Deny per capability. Scope enforcement and request limits are optional; new or changed shell commands require review under Ask.
- Shell registrations are shared across projects; availability and default arguments belong to the current project. Commands receive JSON arguments on stdin and execute locally.
- Project data stays on your Mac under `~/Library/Application Support/Recon/projects/`. Recon does not require a cloud account.

## Feedback

Report bugs or suggestions in [Issues](https://github.com/Vozenio/recon/issues). Include the app version and steps to reproduce; remove credentials and sensitive HTTP data before attaching examples.
