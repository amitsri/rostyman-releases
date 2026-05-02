# Rostyman

**Local-first desktop API client — powerful, private, and free**

Rostyman runs entirely on your machine with no account required. Your APIs. Your machine. Your rules.

![Rostyman](https://img.shields.io/badge/version-0.1.0--beta.16.1-blue) ![Platforms](https://img.shields.io/badge/platforms-Windows%20%7C%20macOS%20%7C%20Linux-green) ![Protocols](https://img.shields.io/badge/protocols-8-orange)

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

## What's New in beta.16.1

### Generate API Collection — Progress Dialog
- Generating from your database schema now shows a dialog with the table count → request count stats and a live progress bar
- Sidebar refreshes the moment generation completes — no more restart needed to see the new collection
- Cancel and Escape blocked while writing so you cannot close mid-write

### ER Diagram & Workflow — Canvas Navigation
- **ER MiniMap** — built-in minimap in the bottom-right corner; drag the viewport rectangle to pan, scroll over it to zoom
- **Zoom to Area** on both canvases — click the crop icon, drag a rectangle on the canvas, release to zoom into that area; Esc cancels

### Workflow Tracer
- Rows now show actual final status (✓ / ✗ / skipped) once a run completes or when replaying past runs — no more perpetual spinners
- Delay rows show "waiting 5000ms…" while running and "waited 5000ms" once complete, so you can tell whether a wait is active
- Stop button during a long Delay now interrupts immediately (was doing nothing)

### Transform Node — Array Wildcards
- Path expressions support `[*]` — `$[*].title` extracts an array of titles from a JSON array response
- Previously returned null because only `$.field`, `$.a.b`, and `$.array[0]` were supported

### Feature Guides — Reading Order
- Every in-app feature guide reordered to strict left-to-right, top-to-bottom reading order
- Spotlight popups no longer jump back across the screen — 11 guides reordered

### PNG Export — Console Cleanup
- Silenced the SecurityError flood from html-to-image trying to embed Monaco's cross-origin CDN stylesheet during ER and workflow PNG exports

See [full release notes](https://github.com/amitsri/rostyman-releases/releases/tag/v0.1.0-beta.16.1) for details.

## What's New in beta.16

### Databases — Headline Feature
- **8 supported drivers** — SQLite, PostgreSQL, MySQL, MariaDB, Microsoft SQL Server, MongoDB, Redis, CockroachDB
- **Connection wizard** with brand icons, password masking, friendly error classifier (refused / not found / timeout / auth failed / TLS / unknown), and connection-string URI support
- **Schema browser** with resizable panel, Browse mode (paginated rows, multi-column sort, inline cell editing, one-click delete)
- **Monaco-based query editor** with schema-aware autocomplete, dot-completion, SQL hover tooltips, multiple query tabs per connection (state persists across restarts)
- **EXPLAIN visualizer** — color-coded execution plan tree per driver
- **Variable resolution** for `{{tokens}}` from environment, globals, and vault
- **Result formats** — JSON, CSV, INSERT, Markdown table
- **Transactions, schema diff, destructive query safety, long-running query notifications, auto-reconnect**
- **CSV / JSON data import**, environment-aware connections, SSH tunnel support
- **DB Verify** tab on every HTTP request — run a SQL query after the response and assert the database changed as expected

### ER Diagram
- **Visual entity-relationship diagram** with auto-detected foreign keys
- **Drag tables** to organise the layout — positions persist per connection across restarts
- **Reset Layout, Export / Import Layout JSON** (self-healing merge if tables changed)
- **High-resolution PNG export** (3× pixel ratio)
- **True vector PDF export** — text and shapes stay sharp at any zoom
- **Smart refresh** — schema only re-fetched on demand

### AI Database Tools
- **Natural-language query assistant** — describe what you want; AI generates SQL or MongoDB matching your driver and schema
- **Schema analysis** — one-click audit for missing indexes, missing constraints, and type mismatches with per-table recommendations
- **Stored procedure / function / trigger / view generator** from English description
- **Generate CRUD API Collection** — one click creates a full collection from your schema (List / Get by ID / Create / Update / Delete per table)

### Query History, Saved Queries & Native Views
- **Query history** auto-saved per connection — replay, see timing, row count, success state
- **Saved queries** with name, description, tags, organised in folders
- **MongoDB document cards** — expandable formatted JSON
- **Redis key browser** — type-aware (STRING / HASH / LIST / SET / ZSET / JSON) with pattern filter
- **DB Projects** — three-level hierarchy (Project → Group → Connection), drag-drop between groups, redesigned Assign-to-Group dialog with inline + New Group

### Beyond Databases
- **AI tool-use** — AI assistant can now create collections, folders, requests, and full visual workflows directly from chat
- **Convert WEBM Recordings to MP4** — quality / resolution / audio presets via system FFmpeg, real FFmpeg errors surfaced on failure
- **Universal Ctrl+S Save** across every protocol tab
- **Sidebar More Popup** — Themes / Languages / Git / AI / Plugins / Cookies grouped in a flyout; Theme Manager and Language Manager finally reachable
- **File Sharing — Device-Global** — devices, groups, and messages follow you across workspace switches
- **Themed in-app dialogs** replace remaining native OS dialogs
- **Live font changes** — interface and editor font apply across the whole app without restart

### Performance & Security
- **Renderer bundle** reduced from 5 MB to 1.6 MB
- **Bulk schema introspection** replaces N+1 patterns for PostgreSQL / MySQL / MSSQL
- **Monaco tab-open lag** eliminated
- **Git command-injection hardened** (array-form arguments)
- **Auto-updater** follows redirects only to allowlisted GitHub release hosts
- **Temporary files** moved to per-user temp directory (no more world-readable `/tmp`)
- **Shell open scheme allowlist** (http / https / mailto only)
- **MCP server CSP headers**; analytics secrets redactor

### Internationalisation
- All 18 languages now in full key-parity at **3,529 strings**
- Major translation pass across 17 non-English languages — between 295 and 422 strings translated per language

See [full release notes](https://github.com/amitsri/rostyman-releases/releases/tag/v0.1.0-beta.16) for details.

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
