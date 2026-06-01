---
name: master-versioning
description: Master data versioning — version in filename, prior version moves to history/ on each edit
metadata:
  type: project
---

The master data file is versioned **in its filename**: `ICMDA Master Data v{N}.xlsx` in the project root, where the highest N is the current/latest. As of 2026-06-01 the current file is `ICMDA Master Data v1.xlsx`.

On every programmatic edit:
1. Apply the change and save as `ICMDA Master Data v{N+1}.xlsx` in the root.
2. **Move** the previous `ICMDA Master Data v{N}.xlsx` from root into `history/`.
3. Append a row (version, date, change summary) to `history/VERSION_LOG.md`.
4. Set the workbook `properties.version` to the new N.

On every bump, also update the in-sheet version note **요약!B2** (`데이터 v{N} 기준 · …`) to the new N — it's a hardcoded string, not a formula, so it goes stale silently. This is a specific case of [[update-linked-data]].

Root always holds exactly one (the latest) master file; `history/` accumulates older versions. Edits are applied **in place / cloned**, never by re-running [[edit-master-in-place]]'s retired build script. See [[no-permission-prompts]].
