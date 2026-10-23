# Development

> Maintained by QuorQ AI SDLC. Text between `sdlc:auto` markers is regenerated; anything outside them is yours and is kept.

<!-- sdlc:auto:start narrative -->
### PLAN-OVERVIEW · approved · source: plan

Development plan is approved at version 3, organized into four sprints of capacity 20 each, covering core arithmetic entry, tape editing/scale, persistence/copy/responsive UX, and privacy/offline support.

Plan status: approved, version 3. Sprint 1 'Core arithmetic & entry' goal: establish exact-decimal engine, numeric input validation, and the core add-line/running-total loop (capacity 20). Sprint 2 'Tape editing & scale' goal: enable delete, edit, clear, negative numbers, and confirm the tape scales to long lists and the two-number case (capacity 20). Sprint 3 'Persistence, copy & responsive UX' goal: persist the tape across refresh, add copy-to-clipboard, and deliver the responsive mobile/desktop input experience (capacity 20). Sprint 4 'Privacy, zero-friction start & offline' goal: confirm no-signin zero-friction start, verify no data leaves the device, and ship offline/installable PWA support (capacity 20). Backlog is organized into 6 epics (EPIC-001 through EPIC-006) containing 20 stories (US-001 through US-020), each broken into implementation tasks assigned to frontend-agent, qa-agent, security-agent, or devops-agent roles.

**Related:** SPRINT-1, SPRINT-2, SPRINT-3, SPRINT-4

- ⚠ No explicit mapping was provided between backlog items/stories and specific sprints -- sprint goals suggest thematic groupings, but the input does not state which US-### items are scheduled in which sprint, so none is asserted here.
- ⚠ No execution/completion status (done, in progress, blocked) was given for any sprint, epic, story, or task -- only the planned scope from the approved plan is documented.

### SPRINT-1 · approved · source: plan:Sprint 1

Sprint 1 'Core arithmetic & entry' targets the exact-decimal engine, numeric input validation, and the core add-line/running-total loop.

Goal: Establish exact-decimal engine, numeric input validation, and the core add-line / running-total loop. Capacity: 20 points.

- ⚠ No items are explicitly assigned to this sprint in the input; no status of sprint progress or completion was reported.

### SPRINT-2 · approved · source: plan:Sprint 2

Sprint 2 'Tape editing & scale' targets delete, edit, clear, negative numbers, and scale/two-number verification.

Goal: Enable delete, edit, clear, negative numbers, and confirm the tape scales to long lists and the two-number case. Capacity: 20 points.

- ⚠ No items are explicitly assigned to this sprint in the input; no status of sprint progress or completion was reported.

### SPRINT-3 · approved · source: plan:Sprint 3

Sprint 3 'Persistence, copy & responsive UX' targets tape persistence across refresh, copy-to-clipboard, and responsive mobile/desktop UX.

Goal: Persist the tape across refresh, add copy-to-clipboard, and deliver the responsive mobile/desktop input experience. Capacity: 20 points.

- ⚠ No items are explicitly assigned to this sprint in the input; no status of sprint progress or completion was reported.

### SPRINT-4 · approved · source: plan:Sprint 4

Sprint 4 'Privacy, zero-friction start & offline' targets no-signin zero-friction start, confirming no data leaves the device, and offline/installable PWA support.

Goal: Confirm no-signin zero-friction start, verify no data leaves the device, and ship offline/installable PWA support. Capacity: 20 points.

- ⚠ No items are explicitly assigned to this sprint in the input; no status of sprint progress or completion was reported.

### EPIC-001 · approved · source: dev:EPIC-001

Epic covering adding-machine tape entry and the continuously updating running total.

Epic: Adding-machine tape entry and running total. No role assigned at epic level. Contains stories US-001 (add a number as a new line), US-002 (see running total update continuously), US-003 (build a tape of unlimited length), and US-004 (add just two numbers).

**Related:** US-001, US-002, US-003, US-004

- ⚠ No points or owning role recorded for the epic itself; no completion status reported.

### US-001 · approved · source: dev:US-001

Story: add a number as a new line on the tape. 5 points, owned by frontend-agent.

Planned tasks: T1 Implement addLine reducer action (frontend-agent); T2 Build entry field confirm flow (frontend-agent); T3 Parse value via decimal_engine before add (frontend-agent); T4 Empty-entry guard tests (qa-agent).

**Related:** EPIC-001, US-001-T1, US-001-T2, US-001-T3, US-001-T4

- ⚠ No completion/status or test results reported for this story or its tasks -- only planned scope from the approved plan is available.

### US-002 · approved · source: dev:US-002

Story: see the running total update continuously. 3 points, owned by frontend-agent.

Planned tasks: T1 Derived total selector (frontend-agent); T2 Sticky total display (frontend-agent); T3 Total update tests (qa-agent).

**Related:** EPIC-001, US-002-T1, US-002-T2, US-002-T3

- ⚠ No completion/status or test results reported for this story or its tasks.

### US-003 · approved · source: dev:US-003

Story: build a tape of unlimited length. 3 points, owned by frontend-agent.

Planned tasks: T1 Optimize large-list rendering (frontend-agent); T2 Auto-scroll to newest line (frontend-agent); T3 Large-tape performance test (qa-agent).

**Related:** EPIC-001, US-003-T1, US-003-T2, US-003-T3

- ⚠ No completion/status or test results reported for this story or its tasks.

### US-004 · approved · source: dev:US-004

Story: add just two numbers. 1 point, owned by qa-agent.

Planned tasks: T1 Two-entry regression test (qa-agent); T2 UX flow confirmation (frontend-agent).

**Related:** EPIC-001, US-004-T1, US-004-T2

- ⚠ No completion/status or test results reported for this story or its tasks.

### EPIC-002 · approved · source: dev:EPIC-002

Epic covering correcting and managing the tape (delete, edit, clear, copy).

Epic: Correcting and managing the tape. No role assigned at epic level. Contains stories US-005 (delete a single line), US-006 (edit a line's value), US-007 (clear the tape and start again), and US-008 (copy the total to the clipboard).

**Related:** US-005, US-006, US-007, US-008

- ⚠ No points or owning role recorded for the epic itself; no completion status reported.

### US-005 · approved · source: dev:US-005

Story: delete a single line from the tape. 3 points, owned by frontend-agent.

Planned tasks: T1 Implement deleteLine reducer action (frontend-agent); T2 Per-line delete control (frontend-agent); T3 Recalculate total on delete (frontend-agent); T4 Delete scenario tests (qa-agent).

**Related:** EPIC-002, US-005-T1, US-005-T2, US-005-T3, US-005-T4

- ⚠ No completion/status or test results reported for this story or its tasks.

### US-006 · approved · source: dev:US-006

Story: edit a line's value. 5 points, owned by frontend-agent.

Planned tasks: T1 Implement editLine reducer action (frontend-agent); T2 Inline edit UI with cancel (frontend-agent); T3 Reject invalid edits (frontend-agent); T4 Recalculate total on edit (frontend-agent); T5 Edit scenario tests (qa-agent).

**Related:** EPIC-002, US-006-T1, US-006-T2, US-006-T3, US-006-T4, US-006-T5

- ⚠ No completion/status or test results reported for this story or its tasks.

### US-007 · approved · source: dev:US-007

Story: clear the tape and start again. 3 points, owned by frontend-agent.

Planned tasks: T1 Implement clearTape reducer action (frontend-agent); T2 Confirm-before-clear dialog (frontend-agent); T3 Persist cleared state (frontend-agent); T4 Refocus entry field after clear (frontend-agent).

**Related:** EPIC-002, US-007-T1, US-007-T2, US-007-T3, US-007-T4

- ⚠ No completion/status or test results reported for this story or its tasks.
- ⚠ No dedicated QA task listed for this story, unlike most others -- unclear if clear-tape behavior has test coverage planned.

### US-008 · approved · source: dev:US-008

Story: copy the total to the clipboard. 3 points, owned by frontend-agent.

Planned tasks: T1 Clipboard write adapter (frontend-agent); T2 Copy control with confirmation (frontend-agent); T3 Fallback selectable-text path (frontend-agent); T4 Clipboard success/fallback tests (qa-agent).

**Related:** EPIC-002, US-008-T1, US-008-T2, US-008-T3, US-008-T4

- ⚠ No completion/status or test results reported for this story or its tasks.

### EPIC-003 · approved · source: dev:EPIC-003

Epic covering number handling and exact decimal arithmetic.

Epic: Number handling and exact decimal arithmetic. No role assigned at epic level. Contains stories US-009 (enter whole numbers, decimals, money amounts and measurements), US-010 (subtract via negative number), US-011 (reject non-numeric input at point of typing), and US-012 (penny-accurate total).

**Related:** US-009, US-010, US-011, US-012

- ⚠ No points or owning role recorded for the epic itself; no completion status reported.

### US-009 · approved · source: dev:US-009

Story: enter whole numbers, decimals, money amounts and measurements. 3 points, owned by frontend-agent.

Planned tasks: T1 Implement numeric format parsing (frontend-agent); T2 Wire entry field to parser (frontend-agent); T3 Format acceptance tests (qa-agent).

**Related:** EPIC-003, US-009-T1, US-009-T2, US-009-T3

- ⚠ No completion/status or test results reported for this story or its tasks.

### US-010 · approved · source: dev:US-010

Story: subtract by entering a negative number. 2 points, owned by frontend-agent.

Planned tasks: T1 Accept leading minus sign (frontend-agent); T2 Mobile sign control (frontend-agent); T3 Style negative lines distinctly (frontend-agent); T4 Negative-number tests (qa-agent).

**Related:** EPIC-003, US-010-T1, US-010-T2, US-010-T3, US-010-T4

- ⚠ No completion/status or test results reported for this story or its tasks.

### US-011 · approved · source: dev:US-011

Story: have non-numeric input rejected at the point of typing. 3 points, owned by frontend-agent.

Planned tasks: T1 Keystroke-level input filtering (frontend-agent); T2 Rejection feedback (frontend-agent); T3 Incomplete-value guard on confirm (frontend-agent); T4 Validation test suite (qa-agent).

**Related:** EPIC-003, US-011-T1, US-011-T2, US-011-T3, US-011-T4

- ⚠ No completion/status or test results reported for this story or its tasks.

### US-012 · approved · source: dev:US-012

Story: get a total that is correct to the penny. 5 points, owned by frontend-agent.

Planned tasks: T1 Integrate decimal.js/big.js wrapper (frontend-agent); T2 Wire tape_store sum to decimal_engine (frontend-agent); T3 Precision regression tests (qa-agent); T4 Document rounding rules (frontend-agent).

**Related:** EPIC-003, US-012-T1, US-012-T2, US-012-T3, US-012-T4

- ⚠ No completion/status or test results reported for this story or its tasks.
- ⚠ Task T4 'Document rounding rules' is assigned to frontend-agent but no rounding-rules document was provided as input -- content of that documentation is not available to cross-reference.

### EPIC-004 · approved · source: dev:EPIC-004

Epic covering comfortable use on both phone and desktop.

Epic: Works on a phone and at a desk. No role assigned at epic level. Contains stories US-013 (use the tape comfortably on any screen size), US-014 (numeric keypad on mobile), and US-015 (drive the whole tape from the keyboard on desktop).

**Related:** US-013, US-014, US-015

- ⚠ No points or owning role recorded for the epic itself; no completion status reported.

### US-013 · approved · source: dev:US-013

Story: use the tape comfortably on any screen size. 5 points, owned by frontend-agent.

Planned tasks: T1 Responsive layout implementation (frontend-agent); T2 Breakpoint testing (qa-agent); T3 Orientation change handling (qa-agent).

**Related:** EPIC-004, US-013-T1, US-013-T2, US-013-T3

- ⚠ No completion/status or test results reported for this story or its tasks.

### US-014 · approved · source: dev:US-014

Story: get a numeric keypad on mobile. 2 points, owned by frontend-agent.

Planned tasks: T1 Numeric inputmode configuration (frontend-agent); T2 Keep keypad open after confirm (frontend-agent); T3 Enlarge control tap targets (frontend-agent); T4 Mobile keypad tests (qa-agent).

**Related:** EPIC-004, US-014-T1, US-014-T2, US-014-T3, US-014-T4

- ⚠ No completion/status or test results reported for this story or its tasks.

### US-015 · approved · source: dev:US-015

Story: drive the whole tape from the keyboard on desktop. 3 points, owned by frontend-agent.

Planned tasks: T1 Auto-focus entry field on load (frontend-agent); T2 Enter-to-add handler (frontend-agent); T3 Full keyboard tab order and focus indicators (frontend-agent); T4 Keyboard navigation & contrast tests (qa-agent).

**Related:** EPIC-004, US-015-T1, US-015-T2, US-015-T3, US-015-T4

- ⚠ No completion/status or test results reported for this story or its tasks.

### EPIC-005 · approved · source: dev:EPIC-005

Epic covering tape continuity in the browser across refreshes, single-tape-per-device model.

Epic: Tape continuity in the browser. No role assigned at epic level. Contains stories US-016 (survive an accidental refresh) and US-017 (work with one tape at a time on this device).

**Related:** US-016, US-017

- ⚠ No points or owning role recorded for the epic itself; no completion status reported.

### US-016 · approved · source: dev:US-016

Story: survive an accidental refresh. 5 points, owned by frontend-agent.

Planned tasks: T1 localStorage read/write adapter (frontend-agent); T2 Sync tape_store on every change (frontend-agent); T3 Graceful degradation when storage unavailable (frontend-agent); T4 Persistence tests (qa-agent).

**Related:** EPIC-005, US-016-T1, US-016-T2, US-016-T3, US-016-T4

- ⚠ No completion/status or test results reported for this story or its tasks.

### US-017 · approved · source: dev:US-017

Story: work with one tape at a time on this device. 1 point, owned by qa-agent.

Planned tasks: T1 Confirm single-tape data model (frontend-agent); T2 Single-tape UX test (qa-agent).

**Related:** EPIC-005, US-017-T1, US-017-T2

- ⚠ No completion/status or test results reported for this story or its tasks.

### EPIC-006 · approved · source: dev:EPIC-006

Epic covering open, free, private-by-default access: no sign-in, no server-side data, offline/installable use.

Epic: Open, free and private by default. No role assigned at epic level. Contains stories US-018 (start using the app immediately with no sign-in), US-019 (keep numbers off any server), and US-020 (keep using the app offline and from the home screen).

**Related:** US-018, US-019, US-020

- ⚠ No points or owning role recorded for the epic itself; no completion status reported.

### US-018 · approved · source: dev:US-018

Story: start using the app immediately with no sign-in. 1 point, owned by qa-agent.

Planned tasks: T1 Verify zero-friction boot flow (frontend-agent); T2 Confirm no account UI exists (qa-agent).

**Related:** EPIC-006, US-018-T1, US-018-T2

- ⚠ No completion/status or test results reported for this story or its tasks.

### US-019 · approved · source: dev:US-019

Story: keep numbers off any server. 2 points, owned by security-agent.

Planned tasks: T1 Network traffic audit (security-agent); T2 Static-only hosting configuration (devops-agent); T3 Privacy-friendly analytics only (security-agent).

**Related:** EPIC-006, US-019-T1, US-019-T2, US-019-T3

- ⚠ No completion/status, audit results, or hosting configuration output reported for this story or its tasks.

### US-020 · approved · source: dev:US-020

Story: keep using the app offline and from the home screen. 5 points, owned by frontend-agent.

Planned tasks: T1 Configure service worker caching (frontend-agent); T2 Web app manifest (frontend-agent); T3 CloudFront caching headers (devops-agent); T4 Offline and installability tests (qa-agent).

**Related:** EPIC-006, US-020-T1, US-020-T2, US-020-T3, US-020-T4

- ⚠ No completion/status or test results reported for this story or its tasks.
<!-- sdlc:auto:end narrative -->
