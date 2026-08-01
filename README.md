# Superset Agent Skills

Official [agent skills](https://skills.sh) from [Superset](https://superset.sh) — the desktop app for running 10+ parallel AI coding agents on your machine, each in its own isolated Git worktree.

## Install

```bash
npx skills add superset-sh/skills
```

## Skills

| Skill | Use it to |
| --- | --- |
| [`superset`](skills/superset/SKILL.md) | Drive Superset from the `superset` CLI: create worktree workspaces, spawn coding agents, open terminals, schedule automations, and manage tasks from any shell. |
| [`superset-orchestration`](skills/superset-orchestration/SKILL.md) | Coordinate multiple terminal coding agents through the Superset CLI with isolated workspaces, follow-ups, dependency tracking, and structured handoffs. |
| [`superset-mcp`](skills/superset-mcp/SKILL.md) | Connect an agent to the Superset MCP server: setup one-liners for Claude Code, Codex, and Gemini CLI, the OAuth/API-key auth flow, and the 27-tool catalog. |

## Resources

- [Documentation](https://docs.superset.sh) · [llms.txt](https://superset.sh/llms.txt)
- [MCP server docs](https://docs.superset.sh/mcp-server)
- [Agent auth walkthrough](https://superset.sh/auth.md)
- [Superset on GitHub](https://github.com/superset-sh/superset)
