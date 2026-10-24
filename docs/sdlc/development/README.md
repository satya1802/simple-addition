# Development

> Maintained by QuorQ AI SDLC. Text between `sdlc:auto` markers is regenerated; anything outside them is yours and is kept.

<!-- sdlc:auto:start narrative -->
### DEV-PLAN-001 · approved · source: plan:overall

The development plan for 'Simple addition' is approved at version 1. It organizes work into 4 sprints covering 6 epics and 20 user stories, each with story points and a responsible role.

Plan status: approved, version 1. Scope spans EPIC-001 through EPIC-006, broken into 20 user stories (US-001 to US-020), each tagged with points and an owning role (frontend-agent, qa-agent, or security-agent). No sprint-to-story mapping was supplied in the input, so individual story assignment to a specific sprint is inferred only from sprint goal wording, not stated explicitly.

**Related:** US-001, US-002, US-003, US-004, US-005, US-006, US-007, US-008, US-009, US-010, US-011, US-012, US-013, US-014, US-015, US-016, US-017, US-018, US-019, US-020

- ⚠ No explicit mapping provided of which backlog items belong to which sprint.
- ⚠ No execution/completion status (not started, in progress, done) reported for any sprint or story.
- ⚠ No code, commit, PR, or build artifacts referenced for this phase.

### DEV-SPRINT-1 · approved · source: plan:Sprint 1

Sprint 1 ('Core arithmetic & entry') targets the core tape: entry, a continuously updating running total, broad number acceptance, input rejection, and penny-accurate decimal arithmetic. Capacity is 20 points.

Goal: Deliver the core tape: entry, continuously updating running total, broad number acceptance, input rejection, and penny-accurate decimal arithmetic. Capacity: 20 points. Likely related stories by goal description: US-001 (add a number as a new line), US-002 (running total updates continuously), US-009 (accept whole numbers/decimals/money/measurements), US-011 (reject non-numeric input), US-012 (penny-accurate total) -- this mapping is inferred from the sprint goal text, not an explicit assignment in the input.

**Related:** US-001, US-002, US-009, US-011, US-012

- ⚠ Sprint-to-story assignment is inferred from goal wording only; input does not explicitly list which stories belong to Sprint 1.
- ⚠ No status reported on whether Sprint 1 work has started, is in progress, or is complete.

### DEV-SPRINT-2 · approved · source: plan:Sprint 2

Sprint 2 ('Tape editing & scale') adds delete, edit, and clear for the tape, confirms scaling to unlimited lines and the two-number case, and supports negative numbers for subtraction. Capacity is 20 points.

Goal: Add delete, edit and clear for the tape, confirm it scales to unlimited lines and the two-number case, and support negative numbers for subtraction. Capacity: 20 points. Likely related stories by goal description: US-003 (unlimited-length tape), US-004 (add just two numbers), US-005 (delete a line), US-006 (edit a line's value), US-007 (clear the tape), US-010 (subtract via negative number) -- mapping inferred from goal text only.

**Related:** US-003, US-004, US-005, US-006, US-007, US-010

- ⚠ Sprint-to-story assignment is inferred from goal wording only; input does not explicitly list which stories belong to Sprint 2.
- ⚠ No status reported on whether Sprint 2 work has started, is in progress, or is complete.

### DEV-SPRINT-3 · approved · source: plan:Sprint 3

Sprint 3 ('Persistence, copy & responsive UX') persists the tape across refresh, adds copy-to-clipboard, and makes the app fully responsive with a mobile keypad and desktop keyboard-only operation. Capacity is 20 points.

Goal: Persist the tape across refresh, add copy-to-clipboard, and make the app fully responsive with mobile keypad and desktop keyboard-only operation. Capacity: 20 points. Likely related stories by goal description: US-008 (copy total to clipboard), US-013 (comfortable on any screen size), US-014 (numeric keypad on mobile), US-015 (keyboard-only operation on desktop), US-016 (survive accidental refresh) -- mapping inferred from goal text only.

**Related:** US-008, US-013, US-014, US-015, US-016

- ⚠ Sprint-to-story assignment is inferred from goal wording only; input does not explicitly list which stories belong to Sprint 3.
- ⚠ No status reported on whether Sprint 3 work has started, is in progress, or is complete.

### DEV-SPRINT-4 · approved · source: plan:Sprint 4

Sprint 4 ('Privacy, zero-friction start & offline') confirms zero-friction, account-free start, verifies no data leaves the device, and ships offline use plus home-screen install. Capacity is 20 points.

Goal: Confirm zero-friction, account-free start, verify no data leaves the device, and ship offline use plus home-screen install. Capacity: 20 points. Likely related stories by goal description: US-017 (single tape per device), US-018 (start with no sign-in), US-019 (keep numbers off any server), US-020 (offline use and home-screen install) -- mapping inferred from goal text only.

**Related:** US-017, US-018, US-019, US-020

- ⚠ Sprint-to-story assignment is inferred from goal wording only; input does not explicitly list which stories belong to Sprint 4.
- ⚠ No status reported on whether Sprint 4 work has started, is in progress, or is complete.

### EPIC-001 · approved · source: plan:EPIC-001

Epic covering adding-machine tape entry and the continuously updating running total.

EPIC-001 'Adding-machine tape entry and running total' groups: US-001 Add a number as a new line on the tape (5 pts, frontend-agent); US-002 See the running total update continuously (3 pts, frontend-agent); US-003 Build a tape of unlimited length (3 pts, frontend-agent); US-004 Add just two numbers (1 pt, qa-agent). Epic itself has no points and no assigned role.

**Related:** US-001, US-002, US-003, US-004

- ⚠ No development/ticket status reported for any story in this epic (not started, in progress, done).
- ⚠ No code or test evidence provided.

### EPIC-002 · approved · source: plan:EPIC-002

Epic covering correcting and managing the tape: delete, edit, clear, and copy-to-clipboard.

EPIC-002 'Correcting and managing the tape' groups: US-005 Delete a single line from the tape (3 pts, frontend-agent); US-006 Edit a line's value (5 pts, frontend-agent); US-007 Clear the tape and start again (3 pts, frontend-agent); US-008 Copy the total to the clipboard (3 pts, frontend-agent). Epic itself has no points and no assigned role.

**Related:** US-005, US-006, US-007, US-008

- ⚠ No development/ticket status reported for any story in this epic (not started, in progress, done).
- ⚠ No code or test evidence provided.

### EPIC-003 · approved · source: plan:EPIC-003

Epic covering number handling and exact decimal arithmetic.

EPIC-003 'Number handling and exact decimal arithmetic' groups: US-009 Enter whole numbers, decimals, money amounts and measurements (3 pts, frontend-agent); US-010 Subtract by entering a negative number (2 pts, frontend-agent); US-011 Have non-numeric input rejected at the point of typing (3 pts, frontend-agent); US-012 Get a total that is correct to the penny (5 pts, frontend-agent). Epic itself has no points and no assigned role.

**Related:** US-009, US-010, US-011, US-012

- ⚠ No development/ticket status reported for any story in this epic (not started, in progress, done).
- ⚠ No code or test evidence provided, including no confirmation of how penny-accurate decimal arithmetic (US-012) was implemented.

### EPIC-004 · approved · source: plan:EPIC-004

Epic covering responsive use on phone and desktop.

EPIC-004 'Works on a phone and at a desk' groups: US-013 Use the tape comfortably on any screen size (5 pts, frontend-agent); US-014 Get a numeric keypad on mobile (2 pts, frontend-agent); US-015 Drive the whole tape from the keyboard on desktop (3 pts, frontend-agent). Epic itself has no points and no assigned role.

**Related:** US-013, US-014, US-015

- ⚠ No development/ticket status reported for any story in this epic (not started, in progress, done).
- ⚠ No code or test evidence provided.

### EPIC-005 · approved · source: plan:EPIC-005

Epic covering tape continuity across browser sessions.

EPIC-005 'Tape continuity in the browser' groups: US-016 Survive an accidental refresh (5 pts, frontend-agent); US-017 Work with one tape at a time on this device (1 pt, qa-agent). Epic itself has no points and no assigned role.

**Related:** US-016, US-017

- ⚠ No development/ticket status reported for any story in this epic (not started, in progress, done).
- ⚠ No code or test evidence provided, including no confirmation of the persistence mechanism used for US-016.

### EPIC-006 · approved · source: plan:EPIC-006

Epic covering open, free, account-free, and private-by-default operation, including offline use.

EPIC-006 'Open, free and private by default' groups: US-018 Start using the app immediately with no sign-in (1 pt, qa-agent); US-019 Keep my numbers off any server (2 pts, security-agent); US-020 Keep using the app offline and from the home screen (5 pts, frontend-agent). Epic itself has no points and no assigned role.

**Related:** US-018, US-019, US-020

- ⚠ No development/ticket status reported for any story in this epic (not started, in progress, done).
- ⚠ No code or test evidence provided, including no confirmation that US-019's no-data-leaves-device guarantee has been implemented or verified.
<!-- sdlc:auto:end narrative -->
