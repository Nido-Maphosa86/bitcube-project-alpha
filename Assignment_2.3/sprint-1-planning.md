# Sprint 1 Planning Session

Date: 2026-05-06
Sprint Goal: Enable employees to successfully book and manage conference rooms without conflicts, while giving admins real-time visibility and control over all bookings.

## Attendees

- Product Owner: Palesa Lesekele (Facilities Operations Manager)
- Scrum Master:  Nido Maphosa
- Development Team: Thapelo Magwai (Full-Stack), Caitlin Ngwana (Backend), Thato Madida (Frontend)

## Velocity Target

21 story points. This is the team's first sprint on this system so a conservative target was set. The team agreed that delivering 5 well-tested stories is preferable to rushing 8 incomplete ones.

## Selected User Stories

| Story # | Title                       | Story Points |
|---------|-----------------------------|--------------|
| #1      | Basic Room Booking          | 5            |
| #3      | Room Capacity Filtering     | 3            |
| #4      | Booking Cancellation        | 3            |
| #6      | Admin Dashboard Viewing     | 5            |
| #9      | Booking Conflict Resolution | 5            |
| **Total** |                           | **21**       |

## Dependencies

- Story #3 depends on Story #1 — capacity filter requires the booking search to exist first
- Story #4 depends on Story #1 — you can only cancel a booking that exists
- Story #6 depends on Story #1 — dashboard has nothing to show without live bookings
- Story #9 depends on Story #1 and Story #6 — conflict resolution requires both bookings and the admin dashboard

## Risks

| Risk | Probability | Impact | Mitigation |
|------|-------------|--------|------------|
| Real-time availability engine more complex than estimated | Medium | High | Spike task on Day 1 to validate approach before full build |

| Email integration delays from company IT | Medium | Medium | Use mock email service during development, swap in for production |


| Team member unavailable mid-sprint | Low | Medium | All work documented daily in standups so another member can pick up |

## Standup Cadence

Time: 09:00 daily
Format: Yesterday / Today / Blockers
