# Pull Request: Evolve README into Team Onboarding Document

## Branch
Assignment_3.1

## Why These Changes Are Being Made

The README in this repository did not exist as a proper onboarding document. A new developer joining the Conference Room Booking System project would have no idea what the system does, how to set it up locally, what the folder structure means, or how to raise a Pull Request correctly.

This PR updates the README so that anyone joining the team after Sprint 1 can get up and running on their own without needing to ask Nido, Thapelo, Caitlin, or Thato for help. It also documents the contribution workflow so that new contributors follow the same branch and PR process the team has been using throughout the sprint.

This change follows the completion of Sprint 1 where the team identified that documentation needs to grow alongside delivery. The sprint retrospective action items included improving onboarding so this PR directly addresses that.

## What Was Changed

The README now includes a project overview explaining what the system does and which roles it serves. There is a system context section covering the four main components which are the Frontend, Backend API, Database, and Email Service. A full onboarding guide walks a new developer through prerequisites and every setup step from cloning the repo to starting the dev server. The folder structure section has been updated to reflect the actual layout of the bitcube-project-alpha repository as it exists today. The contribution workflow section explains the Pull Request process, branch naming convention, and how to write a good commit message. A current sprint status section points to the Sprint 1 review document and a planned sections area flags what documentation still needs to be written.

## Updated Folder Structure

The README now reflects the actual repository structure:

```
bitcube-project-alpha/
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
```

## What Reviewers Should Focus On

Please check whether the onboarding steps in the Getting Started section are in the right order and nothing important is missing. Also check the environment variables table and confirm all required variables are listed. Review the folder structure section and confirm it matches what you see in the repo. The folder names must match exactly including capitalisation.

You do not need to review the sprint artefact descriptions as those are based on documents already produced and agreed by the team during Assignments 2.2, 2.3, and 2.4.

## Related Sprint Documentation

This Pull Request references the following documents already in the repo.

Assignment_2.3/sprint-1-planning.md
Assignment_2.3/sprint-1-dailies.md
Assignment_2.3/sprint-1-checkpoint.md
Assignment_2.3/sprint-1-review.md
Assingment2.4/sprint-1-retrospective.md
Assingment2.4/sprint-1-summary.md
Assingment2.4/personal-reflection.md

## Definition of Done for This PR

README renders correctly on GitHub with no broken formatting.
All setup steps have been tested and produce a working local environment.
Folder structure in the README matches the actual repo exactly.
At least one teammate has reviewed and approved.

