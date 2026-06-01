---
name: room-dashboard
description: room-dashboard.html — single-file room-assignment dashboard (auto-assign + manual + Excel/PDF export)
metadata:
  type: project
---

`Project_B/room-dashboard.html` is the single-file room-assignment dashboard (the project's primary deliverable). Usage doc: `room-dashboard 사용법.md`.

**Architecture:**
- Loads the **live master .xlsx** via a file-picker (SheetJS CDN). Maps columns by **header name** (row 2) — robust to the user reordering columns in Excel, which they do. Night columns detected by `/\d+월\d+일/` header pattern. Recomputes headcount (본인+배우자+자녀+기타, min 1) and arrival/departure from the night grid itself.
- Three venues: 부영청소년수련원 + 유어스 (inventory) and 부영호텔 (off-inventory, NOC locked) — see [[three-venues]].
- **Auto-assign** (validated greedy): respects 배정숙소 locks; skips 배정필요=No; order = **families first (big→small), then teams, then single individuals** (fillers) — this ordering matters, families-last caused 51 unplaceable vs 17 with families-first. Compatibility rule: a **family occupies a whole room alone** (M/F label ignored); **individuals** match the room's M/F label and never mix M&F strangers; ondol filled first; best-fit packing.
- Manual drag-drop between rooms/pool, 🔒 lock (excluded from re-auto), live warnings (over-capacity, gender clash, split groups, unassigned).
- Export: **Excel** (배정결과 + 객실roster tabs) + **resume JSON** (includes assign, locks, and edited stays); load JSON to continue. **Print → PDF** with one consistent layout per hotel (부영=동/층, 유어스=객실유형).
- **Headcount = 총인원** (per user): reads the 총인원 column, falls back to party-column sum (본인+배우자+자녀+기타) since the formula has no cached value when openpyxl saves — the two are identical (766).
- **Two views** (tabs top-right): "배정 보기" (rooms) and "타임라인 보기" (Gantt). Timeline = one **compact** row per participant, **grouped by hotel** with a colored sticky band (horizontal split). Date axis = the 9 master nights **+ 4 buffer days on the right** (state.dates; shaded 연장 zone) so longer stays can be dragged past 7/4. **Draggable bar** (ends resize, middle moves; empty track click adds a night); 6/26–6/28 shaded unofficial; filter by search/venue/category (caps at 500). Bar indices are into state.dates (master nights are the prefix). Note: 유어스 호실 was blank in source → filled '객실1'~'객실50' in master v18; 부영 keeps real source numbers.
- **Category markers**: colored badge + abbrev per 카테고리 (개인/가족/NOC/AFF/중국/자원봉사/미디어/찬양) on chips, timeline rows, and card header. (Old ◆/● group/team dots were removed as redundant.) Headcount shown as **👪N**.
- Timeline extras: leftmost **ID column**; hotel group bands are **foldable** (click to collapse, state.collapsed); rows **drag-reorderable vertically** by the name cell (state.orderList; dragging into another hotel band reassigns via assignToHotel auto-pick); **bar double-click** also opens the card. **자동배정** shows a loading spinner overlay (runs in setTimeout so the paint happens first). Resume JSON (ver 3) persists assign+locked+stays+orderList+collapsed.
- **Detail card**: double-click any person → modal with 인적사항·숙박·인원/동반·참가행사·현재배정 (blank fields omitted).
- Timeline edits change the dashboard's in-memory stay (and arr/dep, persisted in JSON) — they do NOT rewrite the master night grid.

**Known reality:** inventory demand ~718 vs capacity 714 → after auto-assign ~17 single men remain unassigned (true shortage). Resolve via the assumed ondol 117–123, more 부영호텔 rooms, or fewer guests. See [[room-capacity-model]], [[formula-driven-fields]].
