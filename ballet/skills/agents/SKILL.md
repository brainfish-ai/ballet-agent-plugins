---
name: agents
description: Create and tune Ballet agents and skills via MCP — pick a model, write instructions, attach tools and skills. Use when the user wants a specialist agent or reusable skill inside Ballet.
---

# Agents and skills

1. `get_builder_guide` → `agent` (and `skill` for skills).
2. `list_agents` / `list_skills` first — update an existing one rather than duplicating.
3. `list_models` **before** `create_agent`; never guess a model id.
4. Create dependencies (`create_tool`, `create_skill`, `create_mcp_server`), then `create_agent`
   with a trigger-style description ("Use when…") and the smallest tool set that does the job.
5. Change an agent with `get_agent` → `update_agent` (send only what changes).
6. Test by running it from a playbook step and reading `get_run_steps`.

Instructions should state role, concrete steps, constraints, and the shape of the final answer.
Ask before `delete_agent` / `delete_skill`.
