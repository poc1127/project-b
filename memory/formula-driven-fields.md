---
name: formula-driven-fields
description: 참가자 tab accommodation fields are Excel formulas (auto-update) — don't overwrite with static values
metadata:
  type: project
---

From v11, these 참가자 columns are **Excel formulas** that auto-recompute from the night ✓ grid (cols **6월26일~7월4일**, R:Z — 7월5일 was removed in v14 since 7/5 is Departure with no overnight) and party columns — do NOT overwrite them with static values on future edits:

- **숙박일수** = `IF(COUNTA(nights)=0,"",COUNTA(nights)&"박")` — total nights stayed (counts ✓ and ✓*).
- **도착일** = `INDEX(night headers, MATCH("*", nights, 0))` — first checked night.
- **출발일** = `LOOKUP(2,1/(nights<>""),{checkout dates})` — checkout = **last night + 1** (true departure; matches how explicit NOC departures were entered).
- **총인원** = `SUM(본인:기타)` — party columns 본인/배우자/자녀/기타 are **numeric**; rows with all-blank party have **본인 set to 1** so SUM ≥ 1.

**IMPORTANT layout (from v12/v13):** BOTH the 참가자 and 객실 tabs have a **description row at row 1**, **column headers at row 2**, and **data from row 3**. The night-header reference in 도착일 is `$R$2:$Z$2` (9 nights, post-v14). 요약 formulas reference both 참가자 and 객실 data as `3:{last}`. When adding rows or rebuilding, account for this offset on both tabs.

So editing the night grid or family sizes auto-updates these. The 요약 tab's SUM/COUNTIF over 총인원/숙박일수 still work. If adding new rows, copy these formulas (adjust row refs) rather than hardcoding. See [[edit-master-in-place]], [[official-support-from-0629]].
