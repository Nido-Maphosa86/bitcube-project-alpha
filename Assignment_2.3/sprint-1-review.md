# Sprint 1 Review

Date: 2026-05-13
Presented by: Thabo Dlamini (Scrum Master)
Attendees: Full development team, Product Owner (Palesa Lesekele), stakeholder representatives

---

## Sprint Goal Outcome

**Partially met.**

The core employee-facing booking experience is fully delivered. Employees can search, book, filter by capacity, and cancel rooms. The Admin Dashboard is live with real-time room status. Story #9 (Booking Conflict Resolution) was partially completed — conflict detection is working but the audit trail logging and resolution UI require one additional day of work which will be the first task picked up in Sprint 2.

---

## Completed Work

| Story # | Title                   | Acceptance Criteria Met |
|---------|-------------------------|-------------------------|
| #1      | Basic Room Booking      | All 3 criteria met. Rooms display for selected slots, confirmation email fires (mock service), conflict message shown on double-book attempt. |
| #3      | Room Capacity Filtering | All 3 criteria met. Filter returns only rooms meeting minimum capacity, capacity shown on room cards, no-results message with suggestion works. |
| #4      | Booking Cancellation    | All 3 criteria met. Two-step confirmation works, cancellation email fires, slot released immediately, series prompt implemented. |
| #6      | Admin Dashboard Viewing | All 3 criteria met. Live room status view working with 30-second polling, 7-day schedule panel functional, search by employee name returns correct results. |

---

## Incomplete Work

| Story # | Title                       | Reason                                                                                          | Next Action                                                                 |
|---------|-----------------------------|-------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------|
| #9      | Booking Conflict Resolution | Conflict detection logic complete but audit trail logging and admin resolution UI not finished. Edge case complexity exceeded the 5-point estimate. | Carry remaining work as first priority in Sprint 2. Estimated 1–2 days to complete. |

---

## Sprint Metrics

- Planned points: 21
- Completed points: 16 (Stories #1, #3, #4, #6)
- Incomplete points: 5 (Story #9 — partial)
- Actual velocity: 16

---

