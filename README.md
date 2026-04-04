# Rostyman

**Local-first desktop API client — powerful, private, and free**

Rostyman runs entirely on your machine with no account required. Your APIs. Your machine. Your rules.

![Rostyman](https://img.shields.io/badge/version-0.1.0--beta.13-blue) ![Platforms](https://img.shields.io/badge/platforms-Windows%20%7C%20macOS%20%7C%20Linux-green) ![Protocols](https://img.shields.io/badge/protocols-8-orange)

## Download

Get the latest release for your platform:

| Platform | Download | Install |
|----------|----------|---------|
| **Windows** | [Rostyman Setup (.exe)](https://github.com/amitsri/rostyman-releases/releases/latest) | Run the installer |
| **macOS** | [Rostyman (.dmg)](https://github.com/amitsri/rostyman-releases/releases/latest) | Drag to Applications, then see note below |
| **Linux** | [Rostyman (.AppImage)](https://github.com/amitsri/rostyman-releases/releases/latest) | `chmod +x` and run |

### macOS — First Launch

Rostyman is not yet code-signed. macOS will block the app on first launch with "Apple cannot check it for malicious software." Open **Terminal** and run:

```bash
xattr -cr /Applications/Rostyman.app
```

Then open Rostyman from Applications normally. You only need to do this once.

## What's New in beta.13

### Workspace Management
- **Multiple workspaces** — separate projects with their own collections, environments, globals, vault, mock servers, workflows, and jobs
- **Workspace switcher** in the title bar — search, switch, create, rename, export, and import workspaces
- **Per-workspace settings** — HTTP timeout, SSL, redirects, and proxy settings per workspace
- **Tab persistence** — open tabs are saved and restored when switching workspaces
- **Export / import** as `.rostyman-workspace` files

### Binary Response Viewer
- **Images** (PNG/JPG/GIF/WebP/SVG) with zoom controls
- **Video** (MP4/WebM) with native player
- **Audio** (MP3/WAV/OGG) inline player
- **PDF** embedded viewer, **CSV** as table
- Triggered automatically — no configuration needed

### Update Manager
- Silent background updates every 4 hours
- Status bar badge when a new version is ready — restart on your schedule
- Full release history in Settings → About → Updates

### Full Interface Translations
- Scheduler, MCP, WebSocket, Socket.IO, MQTT, gRPC tabs now fully translated in all 18 languages
- No more English strings in non-English modes

### More
- Environment selector on all protocol tabs (WS, gRPC, Socket.IO, MQTT, SSE, MCP)
- Multi-select in collection tree (Ctrl+Click, Shift+Click)
- Screenshot to clipboard (Ctrl+Shift+P)
- First-run welcome dialog + demo workspace

See [full release notes](https://github.com/amitsri/rostyman-releases/releases/tag/v0.1.0-beta.13) for details.

## Features

### 8 Protocols
- **HTTP/HTTPS** — full request builder with auth, headers, body, params, scripts
- **GraphQL** — Monaco editor, schema introspection, autocomplete, variables
- **gRPC** — proto import, unary + streaming, auth, scripts
- **WebSocket** — connect/disconnect, send/receive, message log
- **Socket.IO** — emit events, auto-capture, auth/query config
- **MQTT** — publish/subscribe, QoS 0/1/2, retain flag, topic management
- **SSE** — Server-Sent Events with real-time event log
- **MCP** — Model Context Protocol server (18 tools) + client (stdio + HTTP)

### AI Assistant
- Multi-turn conversational chat with persistent history
- 3 providers: Anthropic Claude, OpenAI, Ollama (local)
- 7 quick actions: Generate, Explain, Tests, Fix, Mock Data, Document, Validate Schema
- Vault-secured API keys

### MCP Support
- **MCP Server** — expose collections to AI agents (Claude, Cursor, Windsurf, VS Code)
- **18 tools** for reading, executing, and creating API resources
- **TLS/HTTPS** support via mkcert, tunnel support (ngrok, cloudflared)
- **Connected clients tracking** with disconnect capability
- **MCP Client** — connect to external MCP servers (stdio + HTTP)

### Collections & Sharing
- Collections with folders, nested subfolders, drag-and-drop
- **Folder-level auth & scripts** — set once, inherited by all child requests
- **Cloud sharing** — connect Google Drive or Dropbox, share collections via link, publish updates
- **Drag & drop import** — drop files to import, auto-detect format
- **Source watching** — auto-detect when linked files or URLs change
- **Collection descriptions** — editable, auto-saved
- Bulk operations — multi-select, bulk delete, copy cURL

### Environments & Variables
- Collection-scoped environments with `{{variable}}` resolution
- Global variables and encrypted Vault
- Variable hover popups with source badges (E/C/G/V)

### Import & Export
- Import from: Postman, Insomnia, OpenAPI, HAR, Thunder Client, Hoppscotch, Bruno, cURL, Rostyman
- Export to: Rostyman JSON, Postman v2.1, and more via plugins
- Import from URL — paste any link, auto-sync when content changes
- `.rostyman` file association — double-click to open on any OS

### Visual Workflow Editor
- Drag-and-drop canvas with 8 node types
- Flow Tracer — execution event log with node tracking
- Save and manage workflows from sidebar

### More
- **20 built-in themes** + custom theme builder
- **Mock Server** — local API mocks with variables and environments
- **Scheduler** — cron-based job scheduling with timezone support
- **Collection Runner** — run collections with data files
- **Git Sync** — built-in Git panel with diff viewer, conflict detection, branch management
- **CLI Runner** — `rosty-cli` for CI/CD integration
- **Notifications Center** — searchable panel with native OS alerts
- **Screenshot & Video Capture** — screen capture with mic audio, recording settings, media sidebar
- **Request History** — full request + response saved, schema change detection
- **Response Viewer** — JSON viewer, code snippets (30+ languages)
- **System Tray** — minimize to tray
- **Onboarding Tour** — 8-step first-run tour
- **19 keyboard shortcuts** — all cross-platform (Ctrl/Cmd)
- **18 built-in languages** — fully translated
- **100% Offline** — no cloud, no account, no telemetry

## Documentation

- [Docs Site](https://rostyman.com)
- [Wiki Home](https://github.com/amitsri/rostyman-releases/wiki)
- [Getting Started](https://github.com/amitsri/rostyman-releases/wiki/Getting-Started)
- [Collections & Requests](https://github.com/amitsri/rostyman-releases/wiki/Collections-and-Requests)
- [AI Assistant](https://github.com/amitsri/rostyman-releases/wiki/AI-Assistant)
- [Scripting API](https://github.com/amitsri/rostyman-releases/wiki/Scripting)
- [Cloud Storage](https://github.com/amitsri/rostyman-releases/wiki/Cloud-Storage)

## Report Issues

Found a bug? [Open an issue](https://github.com/amitsri/rostyman-releases/issues).
