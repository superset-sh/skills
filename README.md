# Superset Agent Skills

Official [agent skills](https://skills.sh) from [Superset](https://superset.sh) — the desktop app for running 10+ parallel AI coding agents on your machine, each in its own isolated Git worktree.

## Install

```bash
npx skills add superset-sh/skills
```

## Skills

> These ship automatically with the [Superset desktop app](https://superset.sh) — if you use Superset, your agents already have them (namespaced `superset:*` in Claude Code). Install from here for standalone agents.

| Skill | Use it to |
| --- | --- |
| [`superset-orchestrate`](skills/superset-orchestrate/SKILL.md) | Coordinate multiple terminal coding agents through the Superset CLI with isolated workspaces, follow-ups, dependency tracking, and structured handoffs. |
| [`superset-setup`](skills/superset-setup/SKILL.md) | Make a repository Superset-ready: author `.superset/config.json` setup scripts and verify them with a real workspace. |
| [`superset-automate`](skills/superset-automate/SKILL.md) | Turn a recurring chore into a scheduled Superset automation and review its first run. |
| [`superset-standup`](skills/superset-standup/SKILL.md) | Digest what your agents did across workspaces, tasks, and terminals: what needs review, what's blocked. |
| [`superset-doctor`](skills/superset-doctor/SKILL.md) | Diagnose and fix Superset problems: expired auth, offline hosts, stale versions. |
| [`superset-feedback`](skills/superset-feedback/SKILL.md) | File a bug report or feature request — privately to the Superset team or as a public GitHub issue. |
| [`superset-10x`](skills/superset-10x/SKILL.md) | Audit how you use Superset and learn the advanced features you're missing. |
| [`superset-contribute`](skills/superset-contribute/SKILL.md) | Set up a Superset open-source contribution end to end, following the repo's contribution rules. |
| [`superset-mcp`](skills/superset-mcp/SKILL.md) | Connect an agent to the Superset MCP server: setup one-liners for Claude Code, Codex, and Gemini CLI, the OAuth/API-key auth flow, and the 27-tool catalog. |

`superset-orchestrate` replaces the former `superset` and `superset-orchestration` skills.

## Resources

- [Documentation](https://docs.superset.sh) · [llms.txt](https://superset.sh/llms.txt)
- [MCP server docs](https://docs.superset.sh/mcp-server)
- [Agent auth walkthrough](https://superset.sh/auth.md)
- [Superset on GitHub](https://github.com/superset-sh/superset)
