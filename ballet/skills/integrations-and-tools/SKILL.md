---
name: integrations-and-tools
description: Work with Ballet native integrations, custom HTTP tools, secrets and external MCP servers via MCP. Use when connecting an app, calling an API, or storing credentials.
---

# Integrations, tools and secrets

1. `list_integrations` unscoped for a summary; with `{ query }` for operations. Use a native
   integration whenever one exists.
2. No native integration? Probe the API with `run_scratch_code`, then `create_tool` using
   `{{SECRET_NAME}}` placeholders. See guide `tool` / `connector`.
3. Secrets: `list_secrets` (names only), `create_secret` / `update_secret`. Values are never
   returned and must never be echoed in chat or logs.
4. External MCP servers: `create_mcp_server`, `connect_mcp_server`, `list_mcp_tools`. If the
   server needs OAuth, tell the user to finish the connection in the Ballet UI.
5. Ask before `delete_tool` / `delete_mcp_server`.
