---
name: team-room-reservations
description: 부영청소년수련원 must reserve dedicated team rooms (필요부분 tab) — hard constraint for room assignment
metadata:
  type: project
---

From the `필요부분` tab of `01 호텔방 데이터.xlsx` ("부영청소년수련원 추가 필요 방배정"), these team rooms must be reserved at 부영청소년수련원 in addition to normal assignment:

- 중국팀 (China team): **2 rooms**
- 찬양팀 (praise/worship team): **2 rooms** (14명 참석 / 14 attendees)
- 미디어팀 (media team): **2 rooms**
- 자원봉사팀 (volunteer team): **5 rooms**

Total = **11 rooms** held for teams. The user flagged this as a key factor to remember.

**How to apply:** When building the room-assignment logic, treat these as reserved team blocks (keep each team together — consistent with the family/group-togetherness rule), not free pool. Cross-check team counts against the 참가자 카테고리 (중국 = 20). See [[printable-room-schedule]].
