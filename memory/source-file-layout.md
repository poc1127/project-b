---
name: source-file-layout
description: Layout of the source 02 참가자 데이터 FINAL (multi-row header) and how to match its rows to the master
metadata:
  type: reference
---

Source spine for participant fields = **`02 참가자 데이터.xlsx` → sheet `FINAL`** (single sheet, ~634 data rows).

**Header is multi-row (not row 1):**
- Rows 1–3 are the date-grid super-header (Day 0–5 / dates / weekday) over cols R–W.
- **Real column headers are on row 4; data starts row 5.**
- Useful columns: A 카테고리, C 이름(영문), D 성별, F 국적, H 배정필요, **AS(45) 9. Email Address**, **AT(46) 10. ICMDA Event You Plan to Attend** (values: Main Congress Only / Pre-Conference + Main Congress / Student Conference + Main Congress / Pre-Conference Only / blank).

**Matching source → master:** key by **email** (lowercased): master 이메일 ↔ source AS. This is the only reliable key — master 참가자ID was renumbered ([[edit-master-in-place]]) and rows were added from other files. Name-matching adds nothing beyond email. Rows with no email or not in FINAL (teams/placeholders/volunteers, 출처 ≠ FINAL) → leave the new field blank.

Used in v17 to fill the master's **참가예정행사** column. When asked to pull another field from this source, reuse: header row 4, data row 5+, match by email. See [[update-linked-data]].
