---
name: triggers
description: Create, test and publish Ballet triggers that run playbooks when something changes in an app. Use when the user wants event-driven or polling automation. Only available where Triggers are enabled for the workspace.
---

# Triggers

A trigger watches one app for one kind of change and hands what it finds to connected playbooks.

Flow: `create_trigger` → `test_trigger` (required before publishing) → `try_playbook_filter`
→ `connect_playbook_to_trigger` → `publish_trigger`.

- Read tools: `list_triggers`, `get_trigger`. Edits only change the working copy.
- **Live** actions — `publish_trigger`, `set_trigger_schedule`, `resume_trigger` — start real
  checking and runs. Confirm with the user and state the schedule in their own time zone first.
- `pause_trigger` stops checking but keeps its place. `disconnect_playbook_from_trigger`
  removes a connection from the working copy.
- If the tools are missing, Triggers are not enabled for this workspace; say so.
