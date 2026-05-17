# Sprint 1 Summary

## Executive Summary

Sprint 1 of the Conference Room Booking System delivered four out of five planned stories and achieved a velocity of 16 story points out of the 21 that were planned. Employees can now book, filter, and cancel conference rooms and the Admin Dashboard is fully live. Story 9 about Booking Conflict Resolution carries into Sprint 2 as the first priority with the conflict detection part already done.

## Key Accomplishments

Story 1 Basic Room Booking was fully delivered. Employees can search for available rooms by date and time, book a room, and get a confirmation. The room availability updates in real time without needing to refresh the page.

Story 3 Room Capacity Filtering was fully delivered. The capacity filter works together with the booking search in one combined query so results are fast and accurate.

Story 4 Booking Cancellation was fully delivered. The two step confirmation works, the room slot is released immediately after cancellation, and the system asks whether to cancel just one booking or the whole series.

Story 6 Admin Dashboard was fully delivered. The dashboard shows live room status and refreshes every 30 seconds. The admin can click any room to see its full 7 day schedule and can search for any booking by employee name or booking reference.

The team also worked on the frontend and backend at the same time throughout the sprint which saved a lot of time. The database schema was agreed and locked on Day 1 which stopped rework later.

## Challenges Faced

Story 9 was harder than expected. The estimate of 5 points did not account for the audit trail logging requirement which added a full day of backend work that was not visible during planning.

The email integration with the company email service could not be completed because IT did not provide the production credentials during the sprint. A mock service was used as a workaround so development could continue but the real integration still needs to be done.

The risk on Story 9 was spotted on Day 3 but was only officially raised in the standup on Day 5. This meant the team had less time to respond than they could have had.

## Process Improvements Identified

The team will run a short investigation before committing any story rated 5 points or more to a sprint.

Any story that includes audit trail, logging, or email notification requirements will be given one extra story point during estimation.

All external dependencies will be confirmed before the sprint starts, not during it.

Risks will be raised in the standup as soon as they are suspected, not when they become confirmed problems.

The Scrum Master will read through the Definition of Done for each story during sprint planning so everyone knows exactly what finished means.

## Velocity and Burndown

### Velocity

| Metric           | Value |
|------------------|-------|
| Planned points   | 21    |
| Completed points | 16    |
| Actual velocity  | 16    |
| Carry over       | 5 pts (Story 9 partial) |

### Burndown Chart

This shows how many story points were still remaining each day of the sprint. The ideal line would reach zero by Day 6.

```
Day 0  |  21 pts remaining  |  ████████████████████
Day 1  |  21 pts remaining  |  ████████████████████
Day 2  |  21 pts remaining  |  ████████████████████
Day 3  |  13 pts remaining  |  █████████████
Day 4  |  10 pts remaining  |  ██████████
Day 5  |   5 pts remaining  |  █████
Day 6  |   5 pts remaining  |  █████
```

Stories 1 and 3 were completed on Day 3 which burned 8 points. Story 4 was completed on Day 4 which burned 3 more. Story 6 was completed on Day 5 which burned another 5. Story 9 was not completed so the last 5 points remained at the end of the sprint. The burndown shape is healthy because work was completed consistently across the sprint and not all left to the last day.