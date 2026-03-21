# Rostyman

**Local-first desktop API client — a powerful alternative to Postman**

Rostyman runs entirely on your machine with no account required. Your APIs. Your machine. Your rules.

![Rostyman](https://img.shields.io/badge/version-0.1.0--beta.7-blue) ![Platforms](https://img.shields.io/badge/platforms-Windows%20%7C%20macOS%20%7C%20Linux-green) ![Protocols](https://img.shields.io/badge/protocols-7-orange)

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

## What's New in beta.7

- **Language Manager** — import, export, and create custom `.rostyman-lang` language packs. In-app translation editor with validation, completion tracking, and protected keys. The only API client with community-driven localization
- **New Request Dialog** — Postman-style centered grid with colored icons for all 13 request/utility types, hover descriptions, and pin-to-top support
- **Sidebar Labels** — navigation icons now show text labels below for easier discoverability (like Postman)
- **Language Picker Reorder** — international languages on top, Indian languages in collapsible sub-menu
- **Full i18n Sweep** — all tab titles, toast messages, and dialogs now update when switching languages
- **Auth Inherit Preview** — "Inherit from Parent" now shows actual inherited auth details with masked secrets
- **Crisp Tray Icons** — pre-rendered platform-specific icons (macOS Retina @2x, Windows DPI-aware, Linux 24px)
- **Bug Fixes** — duplicate media tabs, inner tab state, duplicate delete toasts

## Features

### 7 Protocols
- **HTTP/HTTPS** — full request builder with auth, headers, body, params, scripts
- **GraphQL** — Monaco editor, schema introspection, autocomplete, variables
- **gRPC** — proto import, unary + streaming, auth, scripts, settings
- **WebSocket** — connect/disconnect, send/receive, message log
- **Socket.IO** — emit events, auto-capture, auth/query config, reconnection
- **MQTT** — publish/subscribe, QoS 0/1/2, retain flag, topic management
- **SSE** — Server-Sent Events with real-time event log, POST+body, auto-detect, search

### AI Assistant
- Multi-turn conversational chat with persistent history
- 3 providers: Anthropic Claude, OpenAI, Ollama (local)
- 7 quick actions: Generate, Explain, Tests, Fix, Mock Data, Document, Validate Schema
- Action buttons on code blocks — apply as body, test script, or import cURL
- Vault-secured API keys — never stored in renderer memory

### Collections & Folders
- Collections with folders, nested subfolders, drag-and-drop
- **Folder-level auth & scripts** — set once, inherited by all child requests
- **Auth inheritance chain** — Request → Folder → Parent Folder → Collection
- Collection-level auth and scripts
- Bulk operations — multi-select, bulk delete, copy cURL
- Request templates — save and reuse from + menu

### Environments & Variables
- Collection-scoped environments with `{{variable}}` resolution
- Global variables and encrypted Vault (AES-256-GCM)
- Variable hover popups with source badges (E/C/G/V)

### Import & Export
- Import from: Postman, Insomnia, OpenAPI, HAR, Thunder Client, Hoppscotch, Bruno, cURL, Rostyman
- Export to: Rostyman JSON, Postman v2.1, and more via plugins
- Automatic script migration on import

### Visual Workflow Editor
- Drag-and-drop canvas with 8 node types
- Flow Tracer — live execution visualization
- Save and manage workflows from sidebar

### More
- **20 built-in themes** + custom theme builder with 70+ CSS variables
- **Mock Server** — local API mocks with variables, environments, LAN access
- **Scheduler** — cron-based job scheduling with retry logic
- **Collection Runner** — run collections with iterations and data files
- **Git Sync** — built-in Git panel with diff viewer, conflict detection, branch management
- **CLI Runner** — `rosty-cli` for CI/CD integration
- **Screenshot & Video Capture** — built-in screen capture with media sidebar
- **Request History** — full request + response saved, schema change detection, sparklines, filter, export CSV, pin
- **Response Viewer** — timing waterfall, JSON table view, code snippets (30+ languages)
- **System Tray** — minimize to tray, close prevention for active operations
- **Onboarding Tour** — 8-step first-run tour with feature discovery tips
- **19 keyboard shortcuts** — all cross-platform (Ctrl/Cmd)
- **Language Manager** — import/export/create custom language packs, in-app editor with validator
- **18 built-in languages** — fully translated, plus community language pack support
- **100% Offline** — no cloud, no account, no telemetry

## Documentation

- [Wiki Home](https://github.com/amitsri/rostyman-releases/wiki)
- [Getting Started](https://github.com/amitsri/rostyman-releases/wiki/Getting-Started)
- [Collections & Requests](https://github.com/amitsri/rostyman-releases/wiki/Collections-and-Requests)
- [AI Assistant](https://github.com/amitsri/rostyman-releases/wiki/AI-Assistant)
- [Scripting API](https://github.com/amitsri/rostyman-releases/wiki/Scripting)
- [Socket.IO](https://github.com/amitsri/rostyman-releases/wiki/Socket-IO)
- [MQTT](https://github.com/amitsri/rostyman-releases/wiki/MQTT)
- [Git Sync](https://github.com/amitsri/rostyman-releases/wiki/Git-Sync)
- [Mock Server](https://github.com/amitsri/rostyman-releases/wiki/Mock-Server)
- [Themes](https://github.com/amitsri/rostyman-releases/wiki/Themes)
- [Data Management](https://github.com/amitsri/rostyman-releases/wiki/Data-Management)
- [Keyboard Shortcuts](https://github.com/amitsri/rostyman-releases/wiki/Keyboard-Shortcuts)

## Report Issues

Found a bug? [Open an issue](https://github.com/amitsri/rostyman-releases/issues)

## License

Proprietary — All rights reserved.
