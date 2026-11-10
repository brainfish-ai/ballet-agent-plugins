# Contributing

- Skills live in `ballet/skills/<name>/SKILL.md` with `name` and `description` frontmatter.
  The description is what agents route on — write it as a trigger ("Use when…").
- Keep `version` in sync across the three `ballet/*-plugin/plugin.json` files.
- Skills may only reference MCP tools that exist on the Ballet server; verify against `tools/list`.
- Never include secrets, tokens, or customer data in skills or examples.
