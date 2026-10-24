# Sprint Plan

> Maintained by QuorQ AI SDLC. Text between `sdlc:auto` markers is regenerated; anything outside them is yours and is kept.

<!-- sdlc:auto:start sprints -->
## Sprint 1: Sprint 1 - Core arithmetic & entry

Deliver the core tape: entry, continuously updating running total, broad number acceptance, input rejection, and penny-accurate decimal arithmetic.

Capacity: 20 points · Committed: 19

| Key | Type | Title | Points | Role | Depends on |
|---|---|---|---|---|---|
| US-001 | Story | Add a number as a new line on the tape | 5 | frontend-agent | — |
| US-002 | Story | See the running total update continuously | 3 | frontend-agent | US-001 |
| US-009 | Story | Enter whole numbers, decimals, money amounts and measurements | 3 | frontend-agent | US-001 |
| US-011 | Story | Have non-numeric input rejected at the point of typing | 3 | frontend-agent | US-001 |
| US-012 | Story | Get a total that is correct to the penny | 5 | frontend-agent | US-002, US-009 |

## Sprint 2: Sprint 2 - Tape editing & scale

Add delete, edit and clear for the tape, confirm it scales to unlimited lines and the two-number case, and support negative numbers for subtraction.

Capacity: 20 points · Committed: 17

| Key | Type | Title | Points | Role | Depends on |
|---|---|---|---|---|---|
| US-003 | Story | Build a tape of unlimited length | 3 | frontend-agent | US-001 |
| US-004 | Story | Add just two numbers | 1 | qa-agent | US-001, US-002 |
| US-005 | Story | Delete a single line from the tape | 3 | frontend-agent | US-001 |
| US-006 | Story | Edit a line's value | 5 | frontend-agent | US-001, US-002 |
| US-007 | Story | Clear the tape and start again | 3 | frontend-agent | US-001 |
| US-010 | Story | Subtract by entering a negative number | 2 | frontend-agent | US-009 |

## Sprint 3: Sprint 3 - Persistence, copy & responsive UX

Persist the tape across refresh, add copy-to-clipboard, and make the app fully responsive with mobile keypad and desktop keyboard-only operation.

Capacity: 20 points · Committed: 19

| Key | Type | Title | Points | Role | Depends on |
|---|---|---|---|---|---|
| US-008 | Story | Copy the total to the clipboard | 3 | frontend-agent | US-002 |
| US-013 | Story | Use the tape comfortably on any screen size | 5 | frontend-agent | US-001 |
| US-014 | Story | Get a numeric keypad on mobile | 2 | frontend-agent | US-013 |
| US-015 | Story | Drive the whole tape from the keyboard on desktop | 3 | frontend-agent | US-001 |
| US-016 | Story | Survive an accidental refresh | 5 | frontend-agent | US-001 |
| US-017 | Story | Work with one tape at a time on this device | 1 | qa-agent | US-001 |

## Sprint 4: Sprint 4 - Privacy, zero-friction start & offline

Confirm zero-friction, account-free start, verify no data leaves the device, and ship offline use plus home-screen install.

Capacity: 20 points · Committed: 8

| Key | Type | Title | Points | Role | Depends on |
|---|---|---|---|---|---|
| US-018 | Story | Start using the app immediately with no sign-in | 1 | qa-agent | US-001 |
| US-019 | Story | Keep my numbers off any server | 2 | security-agent | — |
| US-020 | Story | Keep using the app offline and from the home screen | 5 | frontend-agent | US-016 |

## Unscheduled

_Nothing unscheduled._
<!-- sdlc:auto:end sprints -->
