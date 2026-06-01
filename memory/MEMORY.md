# Memory Index

- [Dates without time](dates-no-time.md) — master-data date fields must be date-only (YYYY-MM-DD), no 00:00:00
- [Names uppercase](names-uppercase.md) — participant English name (이름) ALL CAPS; 소속/직책/국적 normcap (acronym-aware); email lowercase
- [Edit master in place](edit-master-in-place.md) — fix ICMDA Master Data.xlsx directly; don't re-run build_master_data.py
- [No permission prompts](no-permission-prompts.md) — run python/file commands without asking; allowlist in settings.local.json
- [Master versioning](master-versioning.md) — master file is 'ICMDA Master Data v{N}.xlsx'; on edit bump N, move prior to history/, log it
- [Team room reservations](team-room-reservations.md) — 부영 reserves 11 team rooms (중국2·찬양2·미디어2·자원봉사5); assignment constraint
- [Printable room schedule](printable-room-schedule.md) — dashboard exports PDF room-arrangement; ONE consistent layout across all hotels
- [Volunteer roster](volunteer-roster.md) — authoritative 자원봉사 list in 20260601_Accomodation Planning/; Jeju resident = no room
- [Project memory mirror](project-memory-mirror.md) — keep Project_B/memory/ synced with harness memory on every change
- [Official support from 6/29](official-support-from-0629.md) — accommodation support starts 6/29; pre-6/29 nights marked ✓* in 참가자 tab
- [Room capacity model](room-capacity-model.md) — 객실 기준/추가/총가능; 필수온돌 117-134 (117-123 missing→assumed); YOUUS 6/29=104
- [Formula-driven fields](formula-driven-fields.md) — 참가자 숙박일수/도착일/출발일/총인원 are formulas; auto-update; do not overwrite
- [Conference schedule](conference-schedule.md) — '일정' tab (last) = 2026 ICMDA program 6/30–7/5; 7/5 Departure, no overnight; 7월5일 night col removed
- [Update linked data](update-linked-data.md) — on any edit, also update all related/derived data (descriptions, notes, counts, refs); e.g. A1 desc, 요약 B2 version
- [Three venues](three-venues.md) — 부영청소년수련원 & 유어스 = inventory; 부영호텔(부영 리조트) = separate off-inventory NOC venue
- [Room dashboard](room-dashboard.md) — room-dashboard.html single-file auto-assign + manual + Excel/PDF; loads live xlsx by header name
- [Source file layout](source-file-layout.md) — 02 참가자 데이터 FINAL: headers row 4, data row 5+, match to master by email
