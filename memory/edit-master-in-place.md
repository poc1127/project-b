---
name: edit-master-in-place
description: Apply data fixes directly to ICMDA Master Data.xlsx in place; do NOT re-run build_master_data.py
metadata:
  type: feedback
---

`build_master_data.py` was only for the one-time consolidation of the three source files. It is effectively retired.

The master file `ICMDA Master Data.xlsx` is now a living document the user hand-edits (e.g. correcting the 검토필요 rows). Any further data fixes must be applied **directly to that xlsx in place** (load → modify the relevant cells → save, preserving other cells, manual edits, and the category row colors).

**Why:** Re-running `build_master_data.py` regenerates from source and would clobber the user's manual edits.

**How to apply:** Use a small in-place openpyxl edit (heredoc/`python -c`), not the build script. Set encoding via `sys.stdout.reconfigure(encoding="utf-8")` inside the code rather than a `PYTHONIOENCODING=...` shell prefix. See [[no-permission-prompts]].
