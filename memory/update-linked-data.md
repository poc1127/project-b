---
name: update-linked-data
description: On any master-data edit, also update every related/linked/derived value — descriptions, notes, counts, references
metadata:
  type: feedback
---

When making a change to the master workbook, **always sweep for and update everything tied to that change** — not just the cells directly edited.

**Why:** The user caught two stale spots after the v15 ID renumber: 참가자!**A1** description still said "P=실인원, PH=플레이스홀더" (PH had been dropped), and 요약!**B2** still said "데이터 v14 기준" (never bumped). Their instruction: *"you have to always remember to update all related or linked data where needed, for example, cell A1 should be updated."*

**How to apply:** After any structural/data edit, before saving, check for downstream items that reference what changed:
- **Description / header rows** (row 1 of 참가자 & 객실) that explain a column whose meaning or format just changed.
- **Hardcoded notes** like 요약!B2 version string (see [[master-versioning]]).
- **Formulas / ranges** in 요약 and elsewhere that point at moved/renamed columns (cf. the v14 column-shift fix in [[formula-driven-fields]]).
- **Comments** (e.g. the 필수온돌 header comment in [[room-capacity-model]]).
- Any prose that names a count, prefix, range, or scheme you just altered.

Grep the workbook for the old term/prefix/value to find every mention. A change isn't done until the linked data agrees with it.
