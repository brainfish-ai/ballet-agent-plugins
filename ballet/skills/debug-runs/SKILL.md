---
name: debug-runs
description: Investigate failed or surprising Ballet playbook runs via MCP. Use when a run errored, produced wrong output, or is stuck.
---

# Debugging runs

1. `list_runs` (filter by playbook) → pick the run; `get_run` for status and result.
2. `get_run_steps` for per-step input/output and the first failing step.
3. Form 1–2 hypotheses from the evidence (bad input, missing secret, wrong model, API change,
   filter too strict). Confirm with `run_scratch_code` or by re-reading the step config.
4. Fix with `update_playbook` (complete steps), `verify_playbook`, then `run_playbook`.

Report: what failed, the evidence (step + message), what you changed, and what you did not verify.
