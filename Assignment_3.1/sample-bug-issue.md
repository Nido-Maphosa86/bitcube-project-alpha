# Bug Report

## Summary

Booking confirmation email is not being received after a room is successfully booked.

## Steps to Reproduce

Step 1. Log in as an Employee using a valid account.
Step 2. Select a date, start time, and end time on the booking form.
Step 3. Choose an available room from the results list.
Step 4. Review the booking details on the confirmation screen.
Step 5. Click Confirm Booking.
Step 6. Check your email inbox including spam folder.

## Expected Behaviour

After confirming a booking the employee should receive an email containing the booking reference number, room name, floor, date, and time as described in Story 1 acceptance criteria.

## Actual Behaviour

The booking is created successfully and shows up correctly in My Bookings. The confirmation screen also displays without any errors. However no email arrives in the inbox or spam folder even after waiting 10 minutes.

## Screenshots or Error Messages

No error is shown on screen. The booking confirmation page displays normally. No errors appear in the browser console.

## Environment

| Field                  |      Details        |

| Browser                |      Chrome 124     |
| Operating System       |      Windows 11     |
| User Role              |      Employee       |
| Date and Time of Issue | 2026-05-13 at 10:15 |

## How Often Does This Happen

Every time

## Additional Context

This is connected to the known email integration issue from Sprint 1. The system is currently running on a mock email service because IT has not yet provided production credentials. This bug was flagged in the Sprint 1 retrospective and is assigned to Caitlin Ngwana as a Sprint 2 Day 1 action item. Related to Story 1 Basic Room Booking and Story 4 Booking Cancellation which both depend on the same email service.

Raised by: Thapelo Magwai
Date: 2026-05-13
