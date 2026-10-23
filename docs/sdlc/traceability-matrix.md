# Traceability Matrix

> Maintained by QuorQ AI SDLC. Text between `sdlc:auto` markers is regenerated; anything outside them is yours and is kept.

<!-- sdlc:auto:start legend -->
Built from recorded links, not written by a model: requirement key → plan item (`source_stable_key`) → development ticket (`stable_key`) → the ticket's test steps → the last live deployment that started after the work finished.
<!-- sdlc:auto:end legend -->

<!-- sdlc:auto:start matrix -->
| Requirement | Epic | Title | Plan items | Sprint | Design | Code | Commits | Ticket | Tests | Deployed |
|---|---|---|---|---|---|---|---|---|---|---|
| US-001 | EPIC-001 | Add a number as a new line on the tape | US-001, US-001-T1, US-001-T2, US-001-T3, US-001-T4 | 1 | decimal_engine, tape, tape_line, tape_store, ui_shell | — | — | not started | not run | — |
| US-002 | EPIC-001 | See the running total update continuously | US-002, US-002-T1, US-002-T2, US-002-T3 | 1 | decimal_engine, tape, tape_line, tape_store, ui_shell | — | — | not started | not run | — |
| US-003 | EPIC-001 | Build a tape of unlimited length | US-003, US-003-T1, US-003-T2, US-003-T3 | 2 | tape, tape_line, tape_store, ui_shell | — | — | not started | not run | — |
| US-004 | EPIC-001 | Add just two numbers | US-004, US-004-T1, US-004-T2 | 2 | tape, tape_line, tape_store, ui_shell | — | — | not started | not run | — |
| US-005 | EPIC-002 | Delete a single line from the tape | US-005, US-005-T1, US-005-T2, US-005-T3, US-005-T4 | 2 | decimal_engine, tape, tape_line, tape_store, ui_shell | — | — | not started | not run | — |
| US-006 | EPIC-002 | Edit a line's value | US-006, US-006-T1, US-006-T2, US-006-T3, US-006-T4, US-006-T5 | 2 | decimal_engine, tape, tape_line, tape_store, ui_shell | — | — | not started | not run | — |
| US-007 | EPIC-002 | Clear the tape and start again | US-007, US-007-T1, US-007-T2, US-007-T3, US-007-T4 | 2 | persistence, tape, tape_line, tape_store, ui_shell | — | — | not started | not run | — |
| US-008 | EPIC-002 | Copy the total to the clipboard | US-008, US-008-T1, US-008-T2, US-008-T3, US-008-T4 | 3 | clipboard, tape, ui_shell | — | — | not started | not run | — |
| US-009 | EPIC-003 | Enter whole numbers, decimals, money amounts and measurements | US-009, US-009-T1, US-009-T2, US-009-T3 | 1 | decimal_engine, tape_line, ui_shell | — | — | not started | not run | — |
| US-010 | EPIC-003 | Subtract by entering a negative number | US-010, US-010-T1, US-010-T2, US-010-T3, US-010-T4 | 2 | decimal_engine, tape_line, ui_shell | — | — | not started | not run | — |
| US-011 | EPIC-003 | Have non-numeric input rejected at the point of typing | US-011, US-011-T1, US-011-T2, US-011-T3, US-011-T4 | 1 | tape_line, tape_store, ui_shell | — | — | not started | not run | — |
| US-012 | EPIC-003 | Get a total that is correct to the penny | US-012, US-012-T1, US-012-T2, US-012-T3, US-012-T4 | 1 | decimal_engine, tape, tape_line, tape_store | — | — | not started | not run | — |
| US-013 | EPIC-004 | Use the tape comfortably on any screen size | US-013, US-013-T1, US-013-T2, US-013-T3 | 3 | ui_shell | — | — | not started | not run | — |
| US-014 | EPIC-004 | Get a numeric keypad on mobile | US-014, US-014-T1, US-014-T2, US-014-T3, US-014-T4 | 3 | ui_shell | — | — | not started | not run | — |
| US-015 | EPIC-004 | Drive the whole tape from the keyboard on desktop | US-015, US-015-T1, US-015-T2, US-015-T3, US-015-T4 | 3 | ui_shell | — | — | not started | not run | — |
| US-016 | EPIC-005 | Survive an accidental refresh | US-016, US-016-T1, US-016-T2, US-016-T3, US-016-T4 | 3 | persistence, tape, tape_line, tape_store | — | — | not started | not run | — |
| US-017 | EPIC-005 | Work with one tape at a time on this device | US-017, US-017-T1, US-017-T2 | 3 | persistence, tape, tape_store, ui_shell | — | — | not started | not run | — |
| US-018 | EPIC-006 | Start using the app immediately with no sign-in | US-018, US-018-T1, US-018-T2 | 4 | GET /, ui_shell | — | — | not started | not run | — |
| US-019 | EPIC-006 | Keep my numbers off any server | US-019, US-019-T1, US-019-T2, US-019-T3 | 4 | GET /, static_hosting, ui_shell | — | — | not started | not run | — |
| US-020 | EPIC-006 | Keep using the app offline and from the home screen | US-020, US-020-T1, US-020-T2, US-020-T3, US-020-T4 | 4 | GET /, pwa_sw, static_hosting | — | — | not started | not run | — |
<!-- sdlc:auto:end matrix -->
