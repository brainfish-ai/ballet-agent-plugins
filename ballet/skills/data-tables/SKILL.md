---
name: data-tables
description: Create and query Ballet persistent data tables and records via MCP. Use when the user needs to store, look up, update or export structured data across playbook runs.
---

# Data tables

- Discover: `list_data_tables`, `get_data_table` (schema) before reading or writing.
- Create: `create_data_table` with typed fields; evolve with `update_data_table`
  (rename, add fields, reorder). `delete_data_table` removes **all** records — ask first.
- Query: `list_data_table_records` supports filter, sort, cursor and search. Page with the
  cursor; summarize counts and a few examples rather than dumping rows.
- Write:
  - `create_data_table_record` — fails if the key exists.
  - `upsert_data_table_record` — full replace by key, no version check.
  - `update_data_table_record` — partial merge, needs the record `version`; on
    `RECORD_CONFLICT` (409) re-read with `get_data_table_record` and retry.
