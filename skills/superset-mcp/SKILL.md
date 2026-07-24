---
name: superset-mcp
description: Connect to the Superset MCP server to create Git-worktree workspaces, launch coding-agent sessions, schedule automations, and manage tasks on a user's Superset account. Use when an agent needs to orchestrate parallel coding agents programmatically over MCP instead of the CLI.
---

# Superset MCP Server

[Superset](https://superset.sh) runs parallel AI coding agents in isolated Git worktrees on a user's registered machines. Its MCP server (Streamable HTTP, JSON-RPC 2.0) exposes the full orchestration surface as tools.

```
https://api.superset.sh/api/v2/agent/mcp   (alias: https://api.superset.sh/mcp)
```

## Setup

```bash
# Claude Code
claude mcp add superset --transport http https://api.superset.sh/api/v2/agent/mcp

# OpenAI Codex
codex mcp add superset --url https://api.superset.sh/api/v2/agent/mcp

# Gemini CLI
gemini mcp add --transport http superset https://api.superset.sh/api/v2/agent/mcp
```

Any MCP client that speaks Streamable HTTP works — point it at the URL above.

## Authentication

Unauthenticated requests return `401` with `WWW-Authenticate: Bearer resource_metadata="https://api.superset.sh/.well-known/oauth-protected-resource"`. Two options:

1. **OAuth 2.1 (recommended)** — authorization code + PKCE with RFC 7591 dynamic client registration; the user approves access in a browser. Most MCP clients handle this automatically on first connect.
2. **API key** — the user creates one in the Superset app and the agent sends it as a Bearer token.

Full walkthrough: <https://superset.sh/auth.md>

## Tools

27 tools across seven families (call `tools/list` for the live catalog with input schemas, or fetch <https://api.superset.sh/.well-known/mcp/server-card.json>):

- **hosts / projects** — `hosts_list`, `projects_list`: enumerate the user's registered machines and checked-out repos. IDs are host-scoped, so start here.
- **workspaces** — create (branch- or PR-scoped Git worktrees), list, rename, delete.
- **agents** — launch a coding-agent session (Claude Code, Codex, OpenCode, ...) with a prompt inside a workspace; list installed agent presets.
- **terminals** — open a PTY in a workspace, optionally running a one-off command.
- **automations** — schedule recurring agent runs (RFC 5545 RRULE), pause/resume/dispatch, read run logs.
- **tasks** — create, search, update, delete tasks; list statuses and organization members.

Tools carry MCP behavioral annotations: reads are `readOnlyHint`, the three `*_delete` tools are `destructiveHint` — confirm with the user before calling those.

## Typical flow

1. `hosts_list` → pick an online host.
2. `projects_list` (on that host) → pick a repo.
3. `workspaces_create` with `branch` or `pr` — optionally pass `agents` to spawn a coding agent in the new worktree in the same call.
4. Track follow-up work with `tasks_create` / `automations_create`.

## Learning surface

The documentation is also served over MCP, unauthenticated, at `https://docs.superset.sh/mcp` (`docs_search` + `docs_read`). Human-readable docs: <https://docs.superset.sh/mcp-server>.
