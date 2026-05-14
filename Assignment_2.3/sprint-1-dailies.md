# Sprint 1 — Daily Standups

Sprint Duration: 2026-05-06 to 2026-05-13
Standup Time: 09:00 daily
Format: Yesterday / Today / Blockers


## Day 1 — Wednesday 2026-05-06

### Thapelo Magwai (Full-Stack)
Yesterday: Sprint planning session completed. Asana board set up with all 10 stories.
Today: Begin designing the booking data model. Define tables for rooms, bookings, users, and booking status.
Blockers: None.

### Caitlin Ngwana (Backend)
Yesterday: Sprint planning session completed. Reviewed Story #1 acceptance criteria.
Today: Set up the development environment and database. Create initial migration scripts for the room and booking tables.
Blockers: None.

### Thato Madida (Frontend)
Yesterday: Sprint planning session completed. Reviewed UI design notes for Story #1.
Today: Create wireframes for the booking form — date picker, time selector, and room results grid.
Blockers: None.



## Day 2 — Thursday 2026-05-07

### Thapelo Magwai (Full-Stack)
Yesterday: Booking data model designed. Schema covers rooms, bookings, users, and series ID for future recurring support.
Today: Begin implementing the availability check logic. Query to return only rooms free for a given date and time slot.
Blockers: None.

### Caitlin Ngwana (Backend)
Yesterday: Dev environment set up. Database migrations for rooms and bookings tables complete.
Today: Start building the POST /bookings API endpoint. Input validation and conflict check before confirming a booking.
Blockers: Waiting on company email service credentials from IT to test confirmation emails. Using mock service in the meantime.

### Thato Madida (Frontend)
Yesterday: Wireframes for booking form completed and shared with the team for feedback.
Today: Begin building the booking UI component — date picker and time range selector first.
Blockers: None.



## Day 3 — Friday 2026-05-08

### Thapelo Magwai (Full-Stack)
Yesterday: Availability check logic implemented and manually tested with sample data. Returns correct results for free and occupied slots.
Today: Integrate availability check with the API endpoint Lebo is building. Begin Story #3 capacity filter logic.
Blockers: None.

### Caitlin Ngwana (Backend)
Yesterday: POST /bookings endpoint built. Booking succeeds for free rooms, returns conflict error for occupied slots. Email still mocked.
Today: Write unit tests for the API endpoint — success case, conflict case, and validation errors.
Blockers: Email credentials still outstanding from IT. Escalated to Scrum Master.

### Thato Madida (Frontend)
Yesterday: Date picker and time selector components complete. Room results grid started.
Today: Complete room results grid. Each room card must show name, floor, and capacity. Begin confirmation screen.
Blockers: None.



## Day 4 — Monday 2026-05-11

### Thapelo Magwai (Full-Stack)
Yesterday: Story #3 capacity filter logic complete. Integrated with availability check as a combined query.
Today: Move Story #1 and Story #3 to In Review. Begin Story #4 cancellation logic — delete booking, release slot in real time.
Blockers: None.

### Caitlin Ngwana (Backend)
Yesterday: Unit tests for booking API complete. All passing. Email blocker partially resolved — mock service approved for demo, real credentials expected next week.
Today: Support Story #4 backend — cancellation endpoint, real-time slot release, and two-step confirmation logic.
Blockers: Email integration remains on mock for now. Not blocking Sprint 1 completion.

### Thato Madida (Frontend)
Yesterday: Room results grid and confirmation screen complete. Story #1 frontend ready for review.
Today: Build the capacity filter UI — stepper input, filter applied to results. Also begin Admin Dashboard layout for Story #6.
Blockers: None.


## Day 5 — Tuesday 2026-05-12

### Thapelo Magwai (Full-Stack)
Yesterday: Story #4 cancellation logic complete on backend. Slot releases immediately on cancel. Two-step confirmation implemented.
Today: Begin Story #6 admin dashboard — room status view (Available, In Use, Upcoming, Maintenance). Wire up to live booking data.
Blockers: Story #9 conflict resolution is at risk. Edge case testing for simultaneous bookings is taking longer than expected. Flagged to Scrum Master.

### Caitlin Ngwana (Backend)
Yesterday: Cancellation endpoint complete and tested. Story #4 backend done.
Today: Begin Story #9 — conflict detection query. Identify overlapping bookings caused by admin overrides or data migration issues.
Blockers: Story #9 complexity is higher than the 5-point estimate suggested. Raised in checkpoint.

### Thato Madida (Frontend)
Yesterday: Capacity filter UI complete. Stories #1 and #3 frontend both in review.
Today: Admin dashboard UI — room status cards colour-coded by status. 7-day schedule panel for selected room.
Blockers: None.


