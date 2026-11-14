<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="./assets/ballet-logo-dark.svg">
    <img src="./assets/ballet-logo-light.svg" alt="Ballet" height="40">
  </picture>
</p>

<!-- Demo GIF placeholder: add assets/demo.gif when available, then uncomment:
<p align="center">
  <img src="./assets/demo.gif" alt="Building a Ballet playbook from a coding agent" width="800">
</p>
-->

<p align="center">
  <strong>Build with Ballet in your AI coding agent</strong>: skills and the Ballet MCP server,
  for Claude Code, Codex, and Cursor.
</p>

<p align="center">
  Automate ops and RevOps work across your systems from a coding agent: playbooks, agents, and data tables via MCP.
</p>

<p align="center">
  <a href="https://opensource.org/licenses/MIT"><img src="https://img.shields.io/badge/License-MIT-yellow.svg" alt="MIT license"></a>
  <a href="https://modelcontextprotocol.io/"><img src="https://img.shields.io/badge/MCP-Streamable%20HTTP-555.svg" alt="MCP"></a>
  <a href="./.claude-plugin/marketplace.json"><img src="https://img.shields.io/badge/Claude%20Code-plugin-d97706.svg" alt="Claude Code plugin"></a>
  <a href="./.cursor-plugin/marketplace.json"><img src="https://img.shields.io/badge/Cursor-plugin-000000.svg" alt="Cursor"></a>
  <a href="./.agents/plugins/marketplace.json"><img src="https://img.shields.io/badge/Codex-plugin-1a1a1a.svg" alt="Codex"></a>
</p>

<p align="center">
  <a href="https://ballet.dev">ballet.dev</a> ·
  <a href="https://ballet.dev/docs">Docs</a> ·
  <a href="https://app.ballet.dev">App</a> ·
  <a href="https://claude.com/marketplace">Claude Connectors Directory</a> ·
  <a href="./CONTRIBUTING.md">Contributing</a> ·
  <a href="./llms-install.md">Agent install</a>
</p>

Ballet is an agent operations platform. Create playbooks, agents, tools and data tables, and
debug runs, from natural language. This repo is the plugin marketplace for `ballet`: one plugin
source, three coding-agent targets, sharing one set of skills and one MCP server.

Remote MCP: `https://api.ballet.dev/mcp` (Streamable HTTP). Sign in with OAuth on the first tool
call. No API keys to paste.

## Quick start

**Claude Code**

```
/plugin marketplace add brainfish-ai/ballet-agent-plugins
/plugin install ballet@ballet-plugins
```

**Cursor**: add this repo as a plugin marketplace, then install `ballet`.

**Codex**

```
codex plugin marketplace add brainfish-ai/ballet-agent-plugins
```

**Any MCP client** (no skills): add to your MCP config:

```json
{ "mcpServers": { "ballet": { "type": "http", "url": "https://api.ballet.dev/mcp" } } }
```

The first tool call opens a browser sign-in (OAuth 2.1 + PKCE). No API keys to paste.

AI coding agents can follow [`llms-install.md`](./llms-install.md).

## What you can build

Ask your coding agent (after install) things like:

- "Build a playbook that compiles a weekly pipeline summary and posts it to Slack every Monday."
- "Enrich this lead from the company website and LinkedIn, then update the CRM contact and owner."
- "Create an invoice approval flow: when an invoice arrives, route by amount, wait for finance approval, then mark it paid in the ledger."
- "Triage new support tickets: classify urgency, draft a reply from our docs, and assign an owner."
- "When a deal moves to Closed Won, draft the handover from the last call and send it to the account owner in Slack."

## What's included

| Skill                    | Use it to                                              |
| ------------------------ | ------------------------------------------------------ |
| `ballet`                 | Start here: index of everything                        |
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
.mcp.json                         Root MCP config (directory auto-detect)
ballet/                           the plugin (manifests per client, .mcp.json, skills/)
llms-install.md                   Install steps for AI coding agents
```

## Local development

Point the client at a local server by editing `ballet/.mcp.json` and `ballet/mcp.json` to
`http://localhost:4111/mcp`.

## License

MIT
