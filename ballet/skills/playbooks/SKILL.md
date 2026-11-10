---
name: playbooks
description: Create, verify, run and update Ballet playbooks (multi-step automations) via MCP. Use when the user wants to automate a workflow, schedule work, or chain agents, tools and integrations.
---

# Playbooks

## Authoring sequence

1. `get_builder_guide` → `overview`, then `playbook`.
2. Discover: `list_integrations` (query for operations), `list_models`, `list_secrets`.
3. Probe any non-native HTTP API with `run_scratch_code` (`allowNetwork: true`, `secretNames`;
   50s max). Do **not** create a throwaway playbook to test. A `missingSecret` result means the
   name is not in the vault: still reference it as `{{SECRET_NAME}}` and tell the user to add it.
4. Create dependencies first: `create_tool`, `create_skill`, `create_agent`, `create_mcp_server`.
5. `list_collections`; `create_collection` if none fits. `create_playbook` requires `collectionId`.
6. `create_playbook` / `update_playbook` with a **complete** `steps` array.
7. `verify_playbook` repeatedly until clean.
8. `run_playbook` → returns a run ID → `get_run` / `get_run_steps`.

## Rules

- Prefer native integrations over hand-rolled HTTP tools.
- Keep steps small and named by outcome ("Fetch open tickets"), not mechanism.
- Fetch the current playbook with `get_playbook` before `update_playbook`; send the full steps.
- Ask before `delete_playbook` or running anything that sends messages or spends money.
