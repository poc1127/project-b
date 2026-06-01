---
name: conference-schedule
description: Master has a '일정' tab (last) with the 2026 ICMDA program 6/30–7/5; 7/5 is Departure (no overnight)
metadata:
  type: project
---

From v14 the master workbook has a **`일정` tab (last position)** reproducing the official **2026 ICMDA World Congress Program**: a time-slot × Day 1–6 grid (Day 1 = 6/30 화 … Day 6 = 7/5 일), with a 3-color track legend — **Student Conference (yellow)**, **Graduate Pre-Conference Streams (green)**, **World Congress (blue)** — and NOC/ICMDA key sessions flagged in **red bold**. Concurrent stream sessions are shown as a second line inside the day cell.

**Key program facts that constrain accommodation:**
- The congress runs **6/30 (Tue) → 7/5 (Sun)**. **Day 6 (7/5) is Departure** — *no one sleeps the night of 7/5*.
- Because of that, v14 **removed the `7월5일` night column** from the 참가자 night grid (it had 36 stray ✓). The grid is now 6월26일~7월4일 (R:Z). The latest possible 출발일 is now **7월5일** (last night 7월4일 + 1). See [[formula-driven-fields]].

**How to apply:** When auto-assigning rooms / building the printable schedule, the last supported night is **7월4일→7월5일 checkout**. Don't schedule overnight stays into 7/5. Ties to [[official-support-from-0629]] (first supported night 6/29) and [[printable-room-schedule]].
