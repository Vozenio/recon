# Recon

A Burp-style HTTP repeater + intercepting proxy for macOS, with a local MCP server so AI agents can drive it under guardrails.

## Download

Get it at **[recon.vozen.io](https://recon.vozen.io)**, or grab the latest `Recon-macos.zip` from [Releases](https://github.com/Vozenio/recon/releases/latest).

Requirements: **macOS on Apple Silicon (arm64)**.

## Install

1. Unzip and move `Recon.app` to `/Applications`.
2. The app is ad-hoc signed but **not notarized**, so on first launch macOS says it "cannot be checked for malicious software". Bypass it once:
   - **Right-click `Recon.app` → Open → Open**, or
   - run: `xattr -dr com.apple.quarantine /Applications/Recon.app`

## Notes

- Projects are stored under `~/Library/Application Support/Recon/`.
- The proxy binds `127.0.0.1` by default (enable "Allow LAN devices" in Settings to expose it).
