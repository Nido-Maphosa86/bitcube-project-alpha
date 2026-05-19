# Conference Room Booking System

## Project Overview

The Conference Room Booking System is a web based application that allows employees to search for and book conference rooms across the office. It also gives admins real time visibility over all bookings and provides role specific tools for facilities managers and receptionists.

The system was built to solve a common workplace problem where rooms get double booked, employees waste time looking for available space, and admins have no central view of what is happening across the office.

### Who This System Is For

| Role               |                                       What They Can Do                                 |

| Employee           | Search rooms, book by date and time, filter by capacity and equipment, cancel bookings |
| Admin              | View all bookings on a live dashboard, resolve conflicts, generate usage reports       |
| Facilities Manager | Schedule maintenance windows that block rooms from being booked                        |
| Receptionist       | Book rooms on behalf of walk in visitors and external guests                           |

---

## System Context

The system is made up of four main components that work together.

**Frontend** handles everything the user sees and interacts with. This includes the booking form, room results, the admin dashboard, and the cancellation flow. It is built to be mobile friendly.

**Backend API** receives requests from the frontend and processes them. It handles availability checks, booking creation, cancellation logic, conflict detection, and role based access control.

**Database** stores all rooms, bookings, users, equipment records, maintenance windows, and audit trail logs. Historical booking data is retained for at least 12 months to support usage reporting.

**Email Service** sends booking confirmation emails, cancellation notifications, and conflict resolution notices to affected users. Currently integrated via a mock service during development. Production credentials are being sourced from IT.

---

## Onboarding Guide

### Prerequisites

Before you can run this project locally you need the following installed on your machine.

- .Net version 8 Long Term Support
- Flutter latest version
- PostgreSQL version 14 or higher
- Git

### Getting Started

Step 1. Clone the repository

```bash
git clone https://github.com/Nido-Maphosa86/bitcube-project-alpha.git
cd bitcube-project-alpha
```

Step 2. Install dependencies


Step 3. Set up your environment variables. Copy the example file and fill in your local values.

Step 4. Set up the database. Run the migration scripts to create all required tables.


Step 5. Seed the database with sample room and user data for local testing.

Step 6. Start the development server.


### Environment Variables

| Variable          |              Description                               |

| DATABASE_URL      | PostgreSQL connection string                           |
| EMAIL_SERVICE_URL | URL for the email service (use mock URL for local dev) |
| JWT_SECRET        | Secret key used for authentication tokens              |
| PORT              | Port the server runs on (default 3000)                 |



---

## Folder Structure

conference-room-booking-system/
│
├── Assignment2.1/
│   ├── epics.md
│   ├── priority-matrix.md
│   └── user-stories.md
│
├── Assignment2.2/
│   └── (screenshots)
│
├── Assignment_2.3/
│   ├── sprint-1-checkpoint.md
│   ├── sprint-1-dailies.md
│   ├── sprint-1-planning.md
│   └── sprint-1-review.md
│
├── Assingment2.4/
│   ├── personal-reflection.md
│   ├── sprint-1-retrospective.md
│   ├── sprint-1-review.md
│   └── sprint-1-summary.md
│
├── Assignment_3.1/
│   ├── documentation-and-collaboration-reflection.md
│   ├── pull-request-description.md
│   ├── sample-bug-issue.md
│   └── peer-review-comment.md
│
├── .github/
│   └── ISSUE_TEMPLATE/
│       ├── bug_report.md
│       └── feature_request.md
│
├── src/
├── assets/
├── .gitignore
└── README.md

### Key Markdown Artefacts

The docs folder contains all sprint documentation produced during Sprint 1. These files are useful for a new developer to understand the history of decisions made, what was built and why, and what is still in progress.

If you are joining the team mid project, reading sprint-1-review.md and sprint-1-retrospective.md first will give you the clearest picture of where the project stands.

---

## Contribution Workflow

This project uses a Pull Request workflow. No one commits directly to the main branch. Every change goes through a branch and a Pull Request so that work can be reviewed before it is merged.

### Step by Step

Step 1. Create a new branch from main. Name it clearly based on what you are working on.

```bash
git checkout -b feature/room-capacity-filter
```

Step 2. Make your changes and commit them with a clear message.

```bash
git add .
git commit -m "Add capacity filter logic to room search query"
```

Step 3. Push your branch to the remote repository.

```bash
git push origin feature/room-capacity-filter
```

Step 4. Open a Pull Request on GitHub. Your PR description must include what you changed, why you changed it, and what the reviewer should focus on.

Step 5. Request a review from at least one teammate.

Step 6. Address any review comments. Once approved, merge into main.

### Branch Naming Convention

| Type           | Format                    |        Example        |

| New feature    | feature/short-description | feature/admin-dashboard |
| Bug fix        | fix/short-description     | fix/double-booking-conflict |
| Documentation  | docs/short-description    | docs/update-readme |
| Technical debt | chore/short-description   | chore/add-email-integration |

### Commit Message Format

Write commit messages in plain English. Start with a verb. Describe what the commit does not what you did.

Good: `Add booking cancellation endpoint with two step confirmation`
Bad: `fixed stuff` or `working on story 4`

---

## Current Sprint Status

Sprint 1 has been completed. Stories 1, 3, 4, and 6 are done. Story 9 (Booking Conflict Resolution) is partially complete and is the first priority for Sprint 2.

For the full sprint breakdown see docs/sprint-1-review.md.

---

## Planned Sections

The following sections will be added as the project progresses.

- API Reference — full documentation of all endpoints, request and response formats
- Testing Guide — how to run the test suite and write new tests
- Deployment Guide — how to deploy to staging and production environments
- Role Based Access Control — detailed explanation of permissions per user role
- Email Integration — setup guide for connecting the production email service
