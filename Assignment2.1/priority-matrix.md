# Priority Matrix — Conference Room Booking System

| Story # | Title | Business Value | Technical Complexity | Priority | Sprint |
|--------:|-------|----------------|----------------------|----------|--------|
| 1 | Basic Room Booking | High | Medium | High | 1 |
| 2 | Recurring Meeting Setup | Medium | High | Medium | 2 |
| 3 | Room Capacity Filtering | High | Low | High | 1 |
| 4 | Booking Cancellation | High | Low | High | 1 |
| 5 | Room Equipment Requirements | Medium | Low | Medium | 2 |
| 6 | Admin Dashboard Viewing | High | Medium | High | 1 |
| 7 | Room Maintenance Scheduling | Medium | Medium | Medium | 2 |
| 8 | Visitor Booking Assistance | Medium | Low | Medium | 2 |
| 9 | Booking Conflict Resolution | High | Medium | High | 1 |
| 10 | Usage Reports Generation | Medium | Medium | Medium | 3 |

---

## Prioritisation Rationale

**Sprint 1 — High priority, high value, foundational:**
Stories #1, #3, #4, #6, and #9 are prioritised first because they form the core booking experience and the admin oversight layer. Without these working, no other story can be built or tested. Story #9 is included in Sprint 1 because conflict handling must be in place as soon as bookings are live.

**Sprint 2 — Medium priority, builds on the core:**
Stories #2, #5, #7, and #8 add depth and role-specific features. Recurring meetings (#2) carry the highest technical complexity in the backlog and are scheduled once the booking engine is proven stable. Equipment filtering (#5) and visitor booking (#8) are low complexity and add immediate user value. Maintenance scheduling (#7) is needed before the system goes live but is not a day-one blocker.

**Sprint 3 — Reporting and polish:**
Story #10 (Usage Reports) delivers strategic business value but does not affect daily operations. It is safely deferred to Sprint 3 once sufficient booking data exists to generate meaningful reports. This sprint also accommodates bug fixes, performance testing, and UAT feedback.
