---
name: names-uppercase
description: In ICMDA Master Data, the English participant name (이름) must be ALL CAPS
metadata:
  type: feedback
---

In the consolidated master data (`ICMDA Master Data.xlsx`), the English participant name column (`이름`) must be fully UPPERCASE (e.g. `NZAME YOLANDE`).

**Why:** User's chosen convention for the participant list.

**How to apply:** In [build_master_data.py](build_master_data.py) the name is set with `.upper()`. See [[dates-no-time]] for the related date-only rule.

Related: 소속 (affiliation) and 직책 (title) get capitalization normalization via the `normcap()` helper — capitalize the first letter of each lowercase word, leaving acronyms (ICMDA) and mixed-case (McDonald) untouched.
