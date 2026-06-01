---
name: dates-no-time
description: In ICMDA Master Data output, date fields (birthday etc.) must be date-only, no time component
metadata:
  type: feedback
---

In the consolidated master data (`ICMDA Master Data.xlsx`), date values must be formatted as date-only (`YYYY-MM-DD`) — never with a `00:00:00` time component. First raised about 생년월일 (birthday).

**Why:** The source cells are datetimes, so openpyxl renders them as `1957-07-15 00:00:00`; the user wants clean dates.

**How to apply:** In [build_master_data.py](build_master_data.py) use the `to_date()` helper for any date column. Apply the same rule to future date fields, not just birthday.
