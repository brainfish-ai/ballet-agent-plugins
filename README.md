<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="./assets/ballet-logo-dark.svg">
    <img src="./assets/ballet-logo-light.svg" alt="Ballet" height="40">
  </picture>
</p>

<p align="center">
  <strong>Build with Ballet in your AI coding agent</strong> — skills and the Ballet MCP server,
  for Claude Code, Codex, and Cursor.
</p>

<p align="center">
  <a href="https://app.ballet.dev">App</a> · <a href="./CONTRIBUTING.md">Contributing</a>
</p>

Ballet is an agent operations platform. Create playbooks, agents, tools and data tables, and
debug runs, from natural language. This repo is the plugin marketplace for `ballet`: one plugin
source, three coding-agent targets, sharing one set of skills and one MCP server.

## Install

**Claude Code**

```
/plugin marketplace add brainfish-ai/ballet-agent-plugins
/plugin install ballet@ballet-plugins
```

**Cursor** — add this repo as a plugin marketplace, then install `ballet`.

**Codex**

```
codex plugin marketplace add brainfish-ai/ballet-agent-plugins
```

**Any MCP client** (no skills) — add to your MCP config:

```json
{ "mcpServers": { "ballet": { "url": "https://api.ballet.dev/mcp" } } }
```

The first tool call opens a browser sign-in (OAuth 2.1 + PKCE). No API keys to paste.

## What's included

| Skill                    | Use it to                                              |
| ------------------------ | ------------------------------------------------------ |
| `ballet`                 | Start here — index of everything                       |
| `playbooks`              | Author, verify and run multi-step automations          |
| `agents`                 | Create and tune agents and skills                      |
| `data-tables`            | Store and query structured records                     |
| `integrations-and-tools` | Native integrations, HTTP tools, secrets, MCP servers  |
| `triggers`               | Run playbooks on app changes                           |
| `debug-runs`             | Diagnose failed or odd runs                            |

## Layout

```
.claude-plugin/marketplace.json   Claude Code marketplace
.cursor-plugin/marketplace.json   Cursor marketplace
.agents/plugins/marketplace.json  Codex marketplace
ballet/                           the plugin (manifests per client, .mcp.json, skills/)
```

## Local development

Point the client at a local server by editing `ballet/.mcp.json` and `ballet/mcp.json` to
`http://localhost:4111/mcp`.

## License

MIT
