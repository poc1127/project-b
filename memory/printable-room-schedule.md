---
name: printable-room-schedule
description: Dashboard must export a printable-to-PDF room-arrangement schedule with ONE consistent layout across all hotels
metadata:
  type: project
---

The dashboard must produce a **room-arrangement schedule that is printable to PDF**, modeled on the "Room Arrangement of BYYTC" / "Room Arrangement of YOUUS Hotel" sheets in `01 호텔방 데이터.xlsx`.

**Key requirement:** use **ONE consistent layout and formatting for every hotel** (부영청소년수련원 / 유어스호텔 / 부영호텔), even though the original source sheets differ per venue. Do not reproduce each venue's idiosyncratic columns — unify them.

Each printed venue sheet should show:
- A title banner per venue (e.g. "Room Arrangement of …").
- Each room as a **multi-row block sized to its capacity** (BYYTC ondol = 6 beds, YOUUS twin = 2), one occupant per row.
- Per-occupant columns: Room No. / Type / Male-Female, Country, Name, Paid, categorization.
- **Per-night columns** with a ✓ for each night the occupant stays (BYYTC 29-Jun…5-Jul, YOUUS 29-Jun…6-Jul in the source; unify the date span).
- Honor 필수 온돌방 117–127, 133, 134 and the reserved team blocks — see [[team-room-reservations]].

**How to apply:** Build this as the dashboard's PDF/print view from the latest `ICMDA Master Data v{N}.xlsx` (see [[master-versioning]]). Defer until the data is final and the user says to build the dashboard.
