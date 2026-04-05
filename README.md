# Rostyman

**Local-first desktop API client — powerful, private, and free**

Rostyman runs entirely on your machine with no account required. Your APIs. Your machine. Your rules.

![Rostyman](https://img.shields.io/badge/version-0.1.0--beta.14-blue) ![Platforms](https://img.shields.io/badge/platforms-Windows%20%7C%20macOS%20%7C%20Linux-green) ![Protocols](https://img.shields.io/badge/protocols-8-orange)

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

## What's New in beta.14

### Workflow Editor Redesign
- **Rich node cards** — each node shows its type icon, a live status badge (idle/running/passed/failed/skipped), and a step number during execution
- **Layout direction picker** — switch between Left→Right, Top→Bottom, Right→Left, and Bottom→Top with a single click; **Auto-Layout** repositions all nodes instantly
- **Undo / Redo** — full undo history (up to 50 steps) with Ctrl+Z / Ctrl+Y
- **Zoom controls** — zoom slider in the toolbar plus a fit-to-view button
- **Snap to grid** — nodes align to a 20 px dot grid by default; toggle between dot and line backgrounds
- **Save canvas to image** — export the workflow diagram as PNG, SVG, or JSON from the toolbar
- **Collapsible node palette** — drag nodes from a collapsible left panel; hover any node type to see a description popup

### Retry Logic (Free)
- Any HTTP Request node can automatically retry on failure — set retry count (up to 5), backoff strategy (Fixed, Linear, or Exponential), delay, and which status codes trigger a retry (e.g. `429, 500, 503`)

### Response Assertions (Free)
- Add pass/fail checks to any request node without writing scripts — check status code, JSON body fields (JSONPath), response headers, or response time using operators like eq, contains, inRange, and more

### Error Handling Edges (Free)
- Every node now has an error handle. Connect it to any downstream node to route failures gracefully. `$error.message`, `$error.status`, and `$error.nodeId` are available on the error path

### Run History (Free)
- Every workflow execution is automatically saved. Open the History tab in the palette to replay any past run — full trace, timings, and variable snapshots

### New Node Types (Free)
- **Comment node** — sticky-note annotations for documenting workflows; does not affect execution
- **Sub-Workflow node** — call another saved workflow as a single step; circular references are automatically blocked

### Auth Inheritance on Request Nodes (Free)
- HTTP Request nodes can now inherit auth from a parent collection — choose Bearer, Basic, API Key, or Inherit

### Import / Export Workflows (Free)
- Export any workflow as a `.rostyman-workflow` file to share or back up; import restores all nodes, edges, and configuration

### 5 Built-in Templates (Free)
- Start a new workflow from a template: API Health Check, Data Pipeline, Auth Flow, CRUD Suite, or Retry Resilience

### Pencil Edit Icon on All Tabs
- Every tab title now shows a pencil icon on hover — click it to rename the tab inline with the cursor placed at the end

### Protocol Translations
- WebSocket, Socket.IO, MQTT, gRPC, and GraphQL status and system messages are now fully translated in all 18 languages

See [full release notes](https://github.com/amitsri/rostyman-releases/releases/tag/v0.1.0-beta.14) for details.

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
