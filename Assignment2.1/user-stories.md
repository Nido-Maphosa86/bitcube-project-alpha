# User Stories — Conference Room Booking System


## Story #1: Basic Room Booking

**As a** Employee
**I want to** search for and book an available conference room for a specific date and time
**So that** I can reserve a space for my meeting without double-booking conflicts

### Acceptance Criteria:
- [ ] Given I am logged in, When I select a date, start time, and end time, Then the system displays only rooms available for that slot
- [ ] Given I select an available room, When I confirm the booking, Then I receive an email confirmation with booking reference, room name, date, and time
- [ ] Given a room is already booked for that slot, When I attempt to book it, Then the system prevents the booking and shows a conflict message

### Story Points:
5

### Priority:
High

### Dependencies:
- None

### Technical Notes:
- Real-time availability must reflect cancellations and new bookings without page refresh
- Booking confirmation emails require integration with the company email service
- Minimum booking duration: 30 minutes; maximum: 8 hours

### Design Notes:
- Calendar/time-picker UI should be intuitive and mobile-friendly
- Available rooms shown as a list or grid with key details (name, floor, capacity) visible at a glance
- Confirmation screen should summarise all booking details before final submission

---

## Story #2: Recurring Meeting Setup

**As a** Employee
**I want to** set up a recurring room booking (daily, weekly, or monthly)
**So that** I don't have to manually rebook the same room for regular team meetings

### Acceptance Criteria:
- [ ] Given I am creating a booking, When I enable the recurrence option, Then I can select a pattern (daily / weekly / monthly) and an end date or number of occurrences
- [ ] Given I set a recurring booking, When any occurrence has a conflict, Then the system notifies me of the conflicting dates and asks whether to skip or cancel the whole series
- [ ] Given a recurring series is saved, When I view my bookings, Then each occurrence appears individually and is labelled as part of a series

### Story Points:
8

### Priority:
Medium

### Dependencies:
- Story #1: Basic Room Booking

### Technical Notes:
- The recurrence engine must handle edge cases: month-end dates (e.g. 31st), public holidays, and rooms going offline for maintenance
- Each occurrence is stored as an independent booking record linked by a series ID to allow individual cancellations

### Design Notes:
- Recurrence configuration should be a collapsible panel to keep the base booking form uncluttered
- Conflict warnings should list affected dates clearly, not just a count

---

## Story #3: Room Capacity Filtering

**As a** Employee
**I want to** filter available rooms by minimum seating capacity
**So that** I can find a room that comfortably fits all meeting attendees

### Acceptance Criteria:
- [ ] Given I am searching for rooms, When I enter the number of attendees, Then only rooms with capacity ≥ that number are shown
- [ ] Given filtered results are displayed, When I view a room card, Then the actual capacity is clearly shown alongside the room name
- [ ] Given no rooms meet the capacity requirement for the chosen slot, When the filter is applied, Then the system displays a message and suggests the nearest available slot when a suitable room becomes free

### Story Points:
3

### Priority:
High

### Dependencies:
- Story #1: Basic Room Booking

### Technical Notes:
- Capacity data is stored in the room configuration table and maintained by Admin
- Filter should combine with other filters (equipment, floor) in a single query

### Design Notes:
- Attendee count input can be a simple stepper (+ / −) or number field
- Room capacity should be visually prominent (e.g. person icon + number)

---

## Story #4: Booking Cancellation

**As a** Employee
**I want to** cancel a room booking I have made
**So that** the room becomes available for colleagues when I no longer need it

### Acceptance Criteria:
- [ ] Given I have an upcoming booking, When I navigate to "My Bookings" and select cancel, Then I am prompted to confirm before the booking is removed
- [ ] Given I confirm cancellation, When the booking is deleted, Then I receive a cancellation confirmation email and the room slot is immediately released
- [ ] Given a booking is part of a recurring series, When I cancel, Then the system asks whether to cancel only that occurrence or the entire series

### Story Points:
3

### Priority:
High

### Dependencies:
- Story #1: Basic Room Booking
- Story #2: Recurring Meeting Setup (for series cancellation)

### Technical Notes:
- Cancellations within 15 minutes of the start time should trigger a notification to the Receptionist dashboard
- Cancelled slots must be released in real time so other users can book immediately

### Design Notes:
- "Cancel Booking" action should require a two-step confirmation to prevent accidental deletions
- Series cancellation must clearly distinguish "This occurrence" vs "All future occurrences"

---

## Story #5: Room Equipment Requirements

**As a** Employee
**I want to** filter rooms by available equipment (e.g. projector, video conferencing, whiteboard)
**So that** I can book a room that has everything my meeting requires

### Acceptance Criteria:
- [ ] Given I am searching for rooms, When I select one or more equipment filters, Then only rooms with all selected equipment are shown
- [ ] Given I view a room's detail page, When I open the equipment list, Then each item is shown with its current availability status (available / under maintenance)
- [ ] Given a room has equipment under maintenance, When I search using that equipment filter, Then the room is excluded from results for the maintenance period

### Story Points:
3

### Priority:
Medium

### Dependencies:
- Story #1: Basic Room Booking
- Story #3: Room Capacity Filtering (shared filter UI)

### Technical Notes:
- Equipment records are managed by the Facilities Manager (Story #7)
- Equipment filter works as an AND condition — all selected items must be present

### Design Notes:
- Equipment filters should use icon-labelled checkboxes for quick scanning
- Room cards in results should display matched equipment icons as confirmation

---

## Story #6: Admin Dashboard Viewing

**As an** Admin
**I want to** view a real-time dashboard of all current and upcoming room bookings across the office
**So that** I can monitor utilisation, identify issues, and support staff with booking queries

### Acceptance Criteria:
- [ ] Given I am logged in as Admin, When I open the dashboard, Then I see a live view of all rooms with their current status (Available / In Use / Upcoming / Maintenance)
- [ ] Given I select a specific room on the dashboard, When the detail panel opens, Then I can see the full booking schedule for that room for the current day and the next 7 days
- [ ] Given I search by employee name or booking reference, When results are returned, Then I can view, edit, or cancel any booking from the dashboard

### Story Points:
5

### Priority:
High

### Dependencies:
- Story #1: Basic Room Booking

### Technical Notes:
- Dashboard data must refresh automatically (polling interval ≤ 30 seconds or via WebSocket)
- Admin actions (edit/cancel on behalf of a user) must be logged in an audit trail with timestamp and admin user ID

### Design Notes:
- Floor-plan view (optional enhancement) shows rooms colour-coded by status
- Dashboard must be usable on a large monitor in a reception or facilities context

---

## Story #7: Room Maintenance Scheduling

**As a** Facilities Manager
**I want to** schedule maintenance windows for conference rooms
**So that** rooms are automatically blocked from bookings during cleaning, repairs, or upgrades

### Acceptance Criteria:
- [ ] Given I am logged in as Facilities Manager, When I select a room and enter a maintenance start/end date and time, Then the room is blocked from new bookings for that period
- [ ] Given a maintenance window is created, When an existing booking overlaps with it, Then affected users are notified by email and the Admin dashboard flags the conflict
- [ ] Given maintenance is completed early, When I end the maintenance window ahead of schedule, Then the room becomes immediately available for booking

### Story Points:
5

### Priority:
Medium

### Dependencies:
- Story #1: Basic Room Booking
- Story #6: Admin Dashboard Viewing

### Technical Notes:
- Maintenance blocks must integrate with the same availability engine used for bookings so no booking can be made during a blocked period
- Requires role-based access control: only Facilities Manager and Admin can create/edit maintenance windows

### Design Notes:
- Maintenance scheduling UI should be separate from the standard booking flow to avoid confusion
- Colour-code maintenance periods distinctly from standard bookings across all views

---

## Story #8: Visitor Booking Assistance

**As a** Receptionist
**I want to** book a conference room on behalf of a visitor or external guest
**So that** guests are accommodated quickly without needing system access themselves

### Acceptance Criteria:
- [ ] Given I am logged in as Receptionist, When I create a booking on behalf of a visitor, Then I can enter the visitor's name and company as the booking contact
- [ ] Given the booking is confirmed, When the visitor arrives, Then the front-desk view shows the visitor's booking prominently with room number, host employee name, and start time
- [ ] Given I need to amend a visitor booking, When I search by visitor name or host employee, Then I can update or cancel the booking without requiring the visitor's credentials

### Story Points:
3

### Priority:
Medium

### Dependencies:
- Story #1: Basic Room Booking

### Technical Notes:
- Visitor bookings are linked to a host employee account for accountability
- Receptionist role has permission to book and modify, but not to access admin reports or maintenance scheduling

### Design Notes:
- Receptionist front-desk view should be optimised for speed — minimal clicks to create a walk-in booking
- Today's visitor bookings should be surfaced prominently on the Receptionist's home screen

---

## Story #9: Booking Conflict Resolution

**As an** Admin
**I want to** identify and resolve double-booking conflicts
**So that** I can ensure fair allocation of rooms and minimise disruption to meetings

### Acceptance Criteria:
- [ ] Given a booking conflict exists (e.g. caused by a system error or manual override), When I open the conflict resolution screen, Then each conflict is listed with both competing bookings and their details
- [ ] Given I am reviewing a conflict, When I select which booking to keep, Then the other booking is cancelled and its owner is notified by email with a reason
- [ ] Given all conflicts are resolved, When I view the dashboard, Then the conflict indicator is cleared and no overlapping bookings remain

### Story Points:
5

### Priority:
High

### Dependencies:
- Story #1: Basic Room Booking
- Story #6: Admin Dashboard Viewing

### Technical Notes:
- The system should prevent conflicts at the point of booking (Story #1), so this story handles edge cases from data migration, API errors, or admin overrides
- All resolution actions must be logged in the audit trail

### Design Notes:
- Conflict list should show both bookings side-by-side for easy comparison
- The "keep this booking" action should be a single clear button, not buried in a menu

---

## Story #10: Usage Reports Generation

**As an** Admin
**I want to** generate usage reports for conference rooms over a specified date range
**So that** I can analyse utilisation trends and make informed decisions about room allocation or office planning

### Acceptance Criteria:
- [ ] Given I am logged in as Admin, When I select a date range and click "Generate Report", Then the system produces a report showing each room's total bookings, total hours booked, and utilisation percentage
- [ ] Given the report is generated, When I choose to export, Then I can download it as a CSV or PDF file
- [ ] Given I filter the report by department or employee, When results are returned, Then only bookings attributed to that department or employee are included in the metrics

### Story Points:
5

### Priority:
Medium

### Dependencies:
- Story #1: Basic Room Booking
- Story #6: Admin Dashboard Viewing

### Technical Notes:
- Reports are generated from the bookings database; historical data must be retained for at least 12 months
- CSV export must include all raw fields; PDF export should be formatted for presentation (charts, summary table)

### Design Notes:
- A summary card section at the top of the report (most booked room, peak hours, overall utilisation) adds quick insight
- Date range picker should support presets: Last 7 days, Last 30 days, This month, Custom