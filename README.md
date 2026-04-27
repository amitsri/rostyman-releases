# Rostyman

**Local-first desktop API client — powerful, private, and free**

Rostyman runs entirely on your machine with no account required. Your APIs. Your machine. Your rules.

![Rostyman](https://img.shields.io/badge/version-0.1.0--beta.17-blue) ![Platforms](https://img.shields.io/badge/platforms-Windows%20%7C%20macOS%20%7C%20Linux-green) ![Protocols](https://img.shields.io/badge/protocols-8-orange)

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

## What's New in beta.17

### Databases — ER Diagram
- Open a visual entity-relationship diagram for any database schema as a tab inside the database panel
- Relationships are detected automatically from column names (`user_id`, `order_fk`, etc.) and drawn as arrows
- Drag nodes to rearrange; positions are remembered for the session
- Export to PNG image or PDF document with one click
- Reopens instantly from cache — only re-fetches on explicit refresh

### Databases — Rich EXPLAIN Visualizer
- PostgreSQL: indented tree with colour-coded node types, cost and actual-time badges, Planning/Execution time summary
- MySQL/MariaDB: full EXPLAIN table with colour-coded type column and parsed Extra badges
- SQLite: EXPLAIN QUERY PLAN parent-child tree with operation colours
- Other drivers: keyword-highlighted plain text

### Databases — AI Tools
- **AI Query Assistant** — describe what you want in plain English; the AI writes the correct query for your database using your live schema
- **AI Schema Analysis** — get specific recommendations for missing indexes, constraints, data-type issues, and design problems
- **Stored Procedure Generator** — describe a stored procedure, function, trigger, or view in English; the AI generates the DDL

### Databases — Generate CRUD API Collection
- Click Generate API in the database panel toolbar to build a full Rostyman collection from your schema
- One folder per table with List, Get by ID, Create, Update, and Delete requests
- Collection opens in the sidebar immediately

### Databases — Query History & Saved Queries
- Every query is saved to a searchable per-connection history with duration, row count, and status
- Save any query with a name, description, tags, and folder for quick access

### Databases — MongoDB & Redis Native Views
- MongoDB query results shown as expandable document cards with formatted JSON
- Redis connections include a key browser panel with pattern filtering, type/TTL/value display, and per-key delete

## What's New in beta.15

### File Sharing — Groups Tab
- **Members** — see all devices in the group with live online/offline status dots
- **Messages** — a merged read-only timeline of all messages with group members: WhatsApp-style date separators (Today / Yesterday / date), emoji reactions (hover to react, click pill to toggle), and sender/recipient device names above each bubble
- **Sent Files** — all files you have sent to any group member, with a Send Files button to send more
- **Received Files** — all files received from group member devices

### File Sharing — Stable Device Identity
- Devices are now identified by a permanent hardware ID (BIOS UUID on Windows, IOPlatformUUID on macOS, machine-id on Linux) instead of just their IP address
- Contacts, block lists, and device history stay intact even when a device changes IP, reconnects, or reinstalls the app
- The hardware ID survives uninstalling and reinstalling Rostyman

### File Sharing — Instant Offline
- Toggle **Auto-Discovery** off and other devices see you go offline immediately — no waiting. Previously it could take up to two minutes to disappear from their list

### File Sharing — Emoji Reactions
- Hover any message in the device chat to reveal the reaction bar and pick an emoji — 700+ emojis, 7 categories, searchable
- Type `:shortcodes:` like `:thumbsup:` or `:rocket:` and they convert automatically before sending
- Reactions sync in real time; click your own reaction pill to remove it

### File Sharing — Message Delivery Status
- Every sent message shows a delivery indicator: **Sent**, **Delivered**, **Pending** (queued while offline), or **Failed**

### File Sharing — Offline Message Queuing
- Send a message even when the other device is offline — it queues and delivers automatically when they reconnect. Rostyman retries in the background for up to 24 hours

### File Sharing — File Attachments in Chat
- Files sent alongside a message appear as an attachment card inside the chat bubble on both sides as soon as the transfer completes. Click to open or reveal in the file manager

### File Sharing — Device Tab Memory
- The File Sharing panel remembers which tab (Chat, Files, Logs) you were last on for each device, across restarts

### File Sharing — Stronger Block Enforcement
- Blocked devices are identified by hardware ID, not IP — they cannot bypass a block by switching networks. Applies to messages, file transfers, and reactions

See [full release notes](https://github.com/amitsri/rostyman-releases/releases/tag/v0.1.0-beta.15) for details.

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
- Drag-and-drop canvas with 10 node types (Start, End, HTTP Request, Condition, Loop, Transform, Delay, Set Variable, Comment, Sub-Workflow)
- **Retry logic** — automatic retries with fixed/linear/exponential backoff
- **Response assertions** — pass/fail checks on status, body, headers, and response time
- **Error handling edges** — route failures to any downstream node
- **Run history** — replay any past execution with full trace and timings
- **5 built-in templates** — Health Check, Data Pipeline, Auth Flow, CRUD Suite, Retry Resilience
- Flow Tracer — live execution log with node tracking

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
- [Visual Workflows](https://github.com/amitsri/rostyman-releases/wiki/Visual-Workflows)

## Report Issues

Found a bug? [Open an issue](https://github.com/amitsri/rostyman-releases/issues).
