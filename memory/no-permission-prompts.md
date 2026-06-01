---
name: no-permission-prompts
description: User wants data/python/file commands run without approval prompts
metadata:
  type: feedback
---

The user does not want to approve routine commands (python data scripts, file ops). Run them without asking.

**Why:** Fast iteration on the master-data file; the approval prompts interrupt the flow.

**How to apply:** Allowlist is in [.claude/settings.local.json](.claude/settings.local.json) (Bash python/pip/ls/cat/mkdir/rm/mv/cp). To stay matchable by `Bash(python:*)`, invoke `python ...` with no inline env-var prefix; set UTF-8 via `sys.stdout.reconfigure(encoding="utf-8")` inside the code. See [[edit-master-in-place]].
