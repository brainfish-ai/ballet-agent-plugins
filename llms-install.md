# Install Ballet (for AI coding agents)

Follow these steps to connect Ballet. Prefer the remote MCP server first; skills are optional.

## 1. Add the Ballet MCP server

Add a Streamable HTTP MCP server named `ballet` pointing at:

```text
https://api.ballet.dev/mcp
```

Example MCP config fragment:

```json
{
  "mcpServers": {
    "ballet": {
      "type": "http",
      "url": "https://api.ballet.dev/mcp"
    }
  }
}
```

This repo also ships a root [`.mcp.json`](./.mcp.json) with the same entry for clients and directories that auto-detect it.

## 2. Authenticate with OAuth

On the first MCP tool call, complete the browser OAuth sign-in (OAuth 2.1 + PKCE). Do not ask the user for an API key. After approval, retry the tool call.

## 3. Optional: install skills via marketplace

Skills teach the agent how to build playbooks, agents, tables, triggers, and debug runs. Install them when the client supports plugin marketplaces.

**Claude Code**

```text
/plugin marketplace add brainfish-ai/ballet-agent-plugins
/plugin install ballet@ballet-plugins
```

**Codex**

```text
codex plugin marketplace add brainfish-ai/ballet-agent-plugins
```

**Cursor**: add `brainfish-ai/ballet-agent-plugins` as a plugin marketplace, then install the `ballet` plugin.

## 4. Verify

1. List MCP tools from the `ballet` server (for example `list_builder_guides` or `list_playbooks`).
2. If OAuth is still pending, finish the browser sign-in and retry.
3. Prefer reading builder guides before creating playbooks or agents.

## References

- Product: https://ballet.dev
- Docs: https://ballet.dev/docs
- Claude Connectors Directory: https://claude.com/marketplace
- This marketplace repo: https://github.com/brainfish-ai/ballet-agent-plugins
