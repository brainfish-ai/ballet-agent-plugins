---
name: ballet
description: Ballet — start here. A table of contents for working with Ballet (agent operations platform) through its MCP tools — playbooks (multi-step automations), agents, skills, custom HTTP tools, native integrations, data tables, triggers, and debugging runs. Read this first to answer "what can I do with Ballet?"
---

# Working with Ballet

Ballet is an agent operations platform. This plugin connects your coding agent to the
workspace through the Ballet MCP server (`https://api.ballet.dev/mcp`). The first tool call
opens a browser OAuth flow; no API keys to paste.

## How to work

- **Read the guide first.** Call `list_builder_guides` / `get_builder_guide` (`overview`, then
  `playbook`, `agent`, `tool`, `skill`, `connector`, `sdk`) before creating anything.
- **Discover before inventing.** `list_integrations`, `list_models`, `list_secrets`,
  `list_collections` — reuse what exists instead of creating duplicates.
- **Never print secret values.** Secrets are write-only; reference them as `{{SECRET_NAME}}`.
- **Narrate and summarize.** Say what you are about to do, then give a short result with names,
  not raw JSON.
- **Verify before you run.** `verify_playbook` until clean, then `run_playbook`.

## Which skill?

| I want to…                                              | Skill                    |
| ------------------------------------------------------- | ------------------------ |
| Build, verify and run a multi-step automation           | `playbooks`              |
| Create or tune an agent (model, instructions, tools)    | `agents`                 |
| Store and query structured records                      | `data-tables`            |
| Connect an app, add an HTTP tool, store a secret        | `integrations-and-tools` |
| Run a playbook when something changes in an app         | `triggers`               |
| Find out why a run failed or behaved oddly              | `debug-runs`             |
