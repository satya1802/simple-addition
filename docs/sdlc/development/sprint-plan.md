# Sprint Plan

> Maintained by QuorQ AI SDLC. Text between `sdlc:auto` markers is regenerated; anything outside them is yours and is kept.

<!-- sdlc:auto:start sprints -->
## Sprint 1: Sprint 1 - Core arithmetic & entry

Establish exact-decimal engine, numeric input validation, and the core add-line / running-total loop

Capacity: 20 points · Committed: 19

| Key | Type | Title | Points | Role | Depends on |
|---|---|---|---|---|---|
| US-001 | Story | Add a number as a new line on the tape | 5 | frontend-agent | US-009, US-011, US-012 |
| ↳ US-001-T1 | Task | Implement addLine reducer action | — | frontend-agent | — |
| ↳ US-001-T2 | Task | Build entry field confirm flow | — | frontend-agent | — |
| ↳ US-001-T3 | Task | Parse value via decimal_engine before add | — | frontend-agent | — |
| ↳ US-001-T4 | Task | Empty-entry guard tests | — | qa-agent | — |
| US-002 | Story | See the running total update continuously | 3 | frontend-agent | US-001, US-012 |
| ↳ US-002-T1 | Task | Derived total selector | — | frontend-agent | — |
| ↳ US-002-T2 | Task | Sticky total display | — | frontend-agent | — |
| ↳ US-002-T3 | Task | Total update tests | — | qa-agent | — |
| US-009 | Story | Enter whole numbers, decimals, money amounts and measurements | 3 | frontend-agent | — |
| ↳ US-009-T1 | Task | Implement numeric format parsing | — | frontend-agent | — |
| ↳ US-009-T2 | Task | Wire entry field to parser | — | frontend-agent | — |
| ↳ US-009-T3 | Task | Format acceptance tests | — | qa-agent | — |
| US-011 | Story | Have non-numeric input rejected at the point of typing | 3 | frontend-agent | US-009 |
| ↳ US-011-T1 | Task | Keystroke-level input filtering | — | frontend-agent | — |
| ↳ US-011-T2 | Task | Rejection feedback | — | frontend-agent | — |
| ↳ US-011-T3 | Task | Incomplete-value guard on confirm | — | frontend-agent | — |
| ↳ US-011-T4 | Task | Validation test suite | — | qa-agent | — |
| US-012 | Story | Get a total that is correct to the penny | 5 | frontend-agent | — |
| ↳ US-012-T1 | Task | Integrate decimal.js/big.js wrapper | — | frontend-agent | — |
| ↳ US-012-T2 | Task | Wire tape_store sum to decimal_engine | — | frontend-agent | — |
| ↳ US-012-T3 | Task | Precision regression tests | — | qa-agent | — |
| ↳ US-012-T4 | Task | Document rounding rules | — | frontend-agent | — |

## Sprint 2: Sprint 2 - Tape editing & scale

Enable delete, edit, clear, negative numbers, and confirm the tape scales to long lists and the two-number case

Capacity: 20 points · Committed: 17

| Key | Type | Title | Points | Role | Depends on |
|---|---|---|---|---|---|
| US-003 | Story | Build a tape of unlimited length | 3 | frontend-agent | US-001, US-002 |
| ↳ US-003-T1 | Task | Optimize large-list rendering | — | frontend-agent | — |
| ↳ US-003-T2 | Task | Auto-scroll to newest line | — | frontend-agent | — |
| ↳ US-003-T3 | Task | Large-tape performance test | — | qa-agent | — |
| US-004 | Story | Add just two numbers | 1 | qa-agent | US-001, US-002 |
| ↳ US-004-T1 | Task | Two-entry regression test | — | qa-agent | — |
| ↳ US-004-T2 | Task | UX flow confirmation | — | frontend-agent | — |
| US-005 | Story | Delete a single line from the tape | 3 | frontend-agent | US-001, US-002 |
| ↳ US-005-T1 | Task | Implement deleteLine reducer action | — | frontend-agent | — |
| ↳ US-005-T2 | Task | Per-line delete control | — | frontend-agent | — |
| ↳ US-005-T3 | Task | Recalculate total on delete | — | frontend-agent | — |
| ↳ US-005-T4 | Task | Delete scenario tests | — | qa-agent | — |
| US-006 | Story | Edit a line's value | 5 | frontend-agent | US-001, US-002, US-011 |
| ↳ US-006-T1 | Task | Implement editLine reducer action | — | frontend-agent | — |
| ↳ US-006-T2 | Task | Inline edit UI with cancel | — | frontend-agent | — |
| ↳ US-006-T3 | Task | Reject invalid edits | — | frontend-agent | — |
| ↳ US-006-T4 | Task | Recalculate total on edit | — | frontend-agent | — |
| ↳ US-006-T5 | Task | Edit scenario tests | — | qa-agent | — |
| US-007 | Story | Clear the tape and start again | 3 | frontend-agent | US-001 |
| ↳ US-007-T1 | Task | Implement clearTape reducer action | — | frontend-agent | — |
| ↳ US-007-T2 | Task | Confirm-before-clear dialog | — | frontend-agent | — |
| ↳ US-007-T3 | Task | Persist cleared state | — | frontend-agent | — |
| ↳ US-007-T4 | Task | Refocus entry field after clear | — | frontend-agent | — |
| US-010 | Story | Subtract by entering a negative number | 2 | frontend-agent | US-009, US-001 |
| ↳ US-010-T1 | Task | Accept leading minus sign | — | frontend-agent | — |
| ↳ US-010-T2 | Task | Mobile sign control | — | frontend-agent | — |
| ↳ US-010-T3 | Task | Style negative lines distinctly | — | frontend-agent | — |
| ↳ US-010-T4 | Task | Negative-number tests | — | qa-agent | — |

## Sprint 3: Sprint 3 - Persistence, copy & responsive UX

Persist the tape across refresh, add copy-to-clipboard, and deliver the responsive mobile/desktop input experience

Capacity: 20 points · Committed: 19

| Key | Type | Title | Points | Role | Depends on |
|---|---|---|---|---|---|
| US-008 | Story | Copy the total to the clipboard | 3 | frontend-agent | US-002 |
| ↳ US-008-T1 | Task | Clipboard write adapter | — | frontend-agent | — |
| ↳ US-008-T2 | Task | Copy control with confirmation | — | frontend-agent | — |
| ↳ US-008-T3 | Task | Fallback selectable-text path | — | frontend-agent | — |
| ↳ US-008-T4 | Task | Clipboard success/fallback tests | — | qa-agent | — |
| US-013 | Story | Use the tape comfortably on any screen size | 5 | frontend-agent | US-001, US-002 |
| ↳ US-013-T1 | Task | Responsive layout implementation | — | frontend-agent | — |
| ↳ US-013-T2 | Task | Breakpoint testing | — | qa-agent | — |
| ↳ US-013-T3 | Task | Orientation change handling | — | qa-agent | — |
| US-014 | Story | Get a numeric keypad on mobile | 2 | frontend-agent | US-001 |
| ↳ US-014-T1 | Task | Numeric inputmode configuration | — | frontend-agent | — |
| ↳ US-014-T2 | Task | Keep keypad open after confirm | — | frontend-agent | — |
| ↳ US-014-T3 | Task | Enlarge control tap targets | — | frontend-agent | — |
| ↳ US-014-T4 | Task | Mobile keypad tests | — | qa-agent | — |
| US-015 | Story | Drive the whole tape from the keyboard on desktop | 3 | frontend-agent | US-001 |
| ↳ US-015-T1 | Task | Auto-focus entry field on load | — | frontend-agent | — |
| ↳ US-015-T2 | Task | Enter-to-add handler | — | frontend-agent | — |
| ↳ US-015-T3 | Task | Full keyboard tab order and focus indicators | — | frontend-agent | — |
| ↳ US-015-T4 | Task | Keyboard navigation & contrast tests | — | qa-agent | — |
| US-016 | Story | Survive an accidental refresh | 5 | frontend-agent | US-001, US-007 |
| ↳ US-016-T1 | Task | localStorage read/write adapter | — | frontend-agent | — |
| ↳ US-016-T2 | Task | Sync tape_store on every change | — | frontend-agent | — |
| ↳ US-016-T3 | Task | Graceful degradation when storage unavailable | — | frontend-agent | — |
| ↳ US-016-T4 | Task | Persistence tests | — | qa-agent | — |
| US-017 | Story | Work with one tape at a time on this device | 1 | qa-agent | US-016 |
| ↳ US-017-T1 | Task | Confirm single-tape data model | — | frontend-agent | — |
| ↳ US-017-T2 | Task | Single-tape UX test | — | qa-agent | — |

## Sprint 4: Sprint 4 - Privacy, zero-friction start & offline

Confirm no-signin zero-friction start, verify no data leaves the device, and ship offline/installable PWA support

Capacity: 20 points · Committed: 8

| Key | Type | Title | Points | Role | Depends on |
|---|---|---|---|---|---|
| US-018 | Story | Start using the app immediately with no sign-in | 1 | qa-agent | US-001 |
| ↳ US-018-T1 | Task | Verify zero-friction boot flow | — | frontend-agent | — |
| ↳ US-018-T2 | Task | Confirm no account UI exists | — | qa-agent | — |
| US-019 | Story | Keep my numbers off any server | 2 | security-agent | — |
| ↳ US-019-T1 | Task | Network traffic audit | — | security-agent | — |
| ↳ US-019-T2 | Task | Static-only hosting configuration | — | devops-agent | — |
| ↳ US-019-T3 | Task | Privacy-friendly analytics only | — | security-agent | — |
| US-020 | Story | Keep using the app offline and from the home screen | 5 | frontend-agent | US-016 |
| ↳ US-020-T1 | Task | Configure service worker caching | — | frontend-agent | — |
| ↳ US-020-T2 | Task | Web app manifest | — | frontend-agent | — |
| ↳ US-020-T3 | Task | CloudFront caching headers | — | devops-agent | — |
| ↳ US-020-T4 | Task | Offline and installability tests | — | qa-agent | — |

## Unscheduled

_Nothing unscheduled._
<!-- sdlc:auto:end sprints -->
