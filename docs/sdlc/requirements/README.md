# Product Requirements

> Maintained by QuorQ AI SDLC. Text between `sdlc:auto` markers is regenerated; anything outside them is yours and is kept.

<!-- sdlc:auto:start narrative -->
## Summary

### REQ-EPIC-001 · draft · source: requirements:EPIC-001

Core capability: enter an unbounded sequence of numbers as tape lines with a continuously updating running total; plain two-number addition is a special case, not a separate mode.

Scope notes: no limit on line count; lines carry a number only (no labels/notes - flagged as the assumption most likely wrong for expenses/stock-taking use); only addition is supported (no x, /, or full calculator).
- US-001 [critical] Add a number as a new line: typed number appears as new line, entry field clears (AC-001); appended below existing lines in order, no alteration of prior lines (AC-002); empty entry confirmed adds nothing (AC-003).
- US-002 [critical] Continuously updating total: empty tape shows 0 (AC-004); total updates immediately on add with no equals button (AC-005); example 10.50+4.25-2.75=12.00 (AC-006); total stays visible while list scrolls (AC-007).
- US-003 [high] Unlimited length: tape of ~500 lines still accepts new lines, recalculates correctly, stays responsive (AC-008); list auto-scrolls to newest line (AC-009).
- US-004 [medium] Two numbers only: two sequential entries both appear as lines with correct sum, no extra 'equals' step (AC-010).

**Related:** US-001, US-002, US-003, US-004

- ⚠ Assumption that lines carry number only (no labels) is flagged in the input as the most likely-to-be-wrong assumption if real use is expenses or stock-taking - not yet confirmed.

### REQ-EPIC-002 · draft · source: requirements:EPIC-002

Practical tape correction and management: delete a line, edit a line's value with recalculation, clear the whole tape, and copy the total to clipboard.

Open assumption: this full editing set is assumed necessary for v1; could be trimmed to clear-only if real use shows otherwise. Explicitly out of scope for this version: export to file, print view, sharing a tape with others.
- US-005 [high] Delete a line: removing a line preserves order of remaining lines and recalculates total (AC-011); deleting last line empties tape, total 0 (AC-012); delete control on phone is single-tap, large target (AC-013).
- US-006 [high] Edit a line's value: editing updates value in place, position unchanged, total recalculates (AC-014); invalid edit value rejected with visible indication, line keeps prior value (AC-015); cancel leaves line and total unchanged (AC-016).
- US-007 [high] Clear the tape: confirmed clear removes all lines, resets total to 0, refocuses entry field (AC-017); un-confirmed clear leaves tape/total unchanged (AC-018); cleared state persists across reload (AC-019).
- US-008 [medium] Copy total to clipboard: exact value copied as plain text with no currency decoration (AC-020); success shows brief confirmation (AC-021); if clipboard blocked/unsupported, clear message shown and total remains manually selectable (AC-022).

**Related:** US-005, US-006, US-007, US-008

- ⚠ Editing feature set (delete/edit/clear/copy) is an explicit assumption for v1 scope, not a confirmed requirement - may be trimmed later.

### REQ-EPIC-003 · draft · source: requirements:EPIC-003

Accepts whole numbers, decimals, money amounts and measurements with no currency display, computes with exact decimal arithmetic (no floating-point drift), rejects non-numeric input at entry, and supports negative numbers as the only subtraction mechanism.

Open assumptions: exact decimal arithmetic required because money is in scope, yet no currency symbols/selection shown anywhere; non-numeric input rejected at point of entry rather than silently dropped; negatives are the only way to subtract (no minus/x/divide operators).
- US-009 [critical] Accept numeric formats: whole numbers (AC-023), decimals preserving entered decimal places e.g. 3.75/0.125 (AC-024), money-style amounts with no symbol required (AC-025); no currency symbol or selector shown anywhere (AC-026).
- US-010 [high] Subtract via negative number: -30 line is visibly distinct and reduces total correctly, e.g. 100 -> 70 (AC-027); minus enterable via mobile keypad or explicit sign control (AC-028); no subtract/multiply/divide operator offered (AC-029).
- US-011 [high] Reject non-numeric input at typing: invalid characters refused as typed with visible indication (AC-030); second decimal point refused (AC-031); incomplete values (lone '-' or '.') rejected on confirm with a message, no line added (AC-032).
- US-012 [critical] Penny-accurate total: 0.1+0.2 = exactly 0.3, not 0.30000000000000004 (AC-033); 0.01 x100 = exactly 1.00 (AC-034); mixed precision 1+2.5+3.125 = exactly 6.625 (AC-035); recalculation after delete/edit remains an exact decimal sum (AC-036).

**Related:** US-009, US-010, US-011, US-012

### REQ-EPIC-004 · draft · source: requirements:EPIC-004

Single responsive web app usable equally on phone and desktop: mobile gets a numeric keypad with large tap targets, desktop supports full keyboard-only operation with Enter-to-add.

Open assumption: basic accessibility (contrast, large tap targets, full keyboard operability) is assumed in scope for v1; no formal accessibility audit or conformance certification included.
- US-013 [critical] Comfortable on any screen: usable without horizontal scroll/zoom at 375px width (AC-037); desktop layout adapts while keeping entry/total prominent (AC-038); orientation rotation preserves content/layout without data loss (AC-039).
- US-014 [high] Mobile numeric keypad: tapping entry field brings up numeric keypad incl. decimal separator and minus entry (AC-040); keypad stays open after confirming a line (AC-041); all controls (add/delete/clear/copy) have thumb-sized tap targets (AC-042).
- US-015 [high] Desktop keyboard-only operation: focus auto-lands in entry field on load (AC-043); Enter adds line, updates total, keeps focus in cleared field (AC-044); full Tab/Shift+Tab/Enter navigation reaches every control incl. per-line delete/edit, clear, copy, with visible focus indicator (AC-045); sufficient text/control contrast on any supported device (AC-046).

**Related:** US-013, US-014, US-015

- ⚠ No formal accessibility audit or conformance certification is in scope for v1 - only basic expectations assumed; not verified by any input provided.

### REQ-EPIC-005 · draft · source: requirements:EPIC-005

The current tape is held only in the browser so an accidental refresh or tab switch does not lose work; nothing is stored on a server, and only one tape exists at a time per device.

Open assumptions: local storage holds only the current tape - no history of past tapes, no cross-device sync, no long-term record; one tape at a time for a single anonymous user per device, no way to keep two tapes side by side.
- US-016 [high] Survive accidental refresh: refresh or tab reopen restores same lines/order/total (AC-047); every add/edit/delete persists immediately to storage (AC-048); if local storage is unavailable/blocked, tape still works for the session without blocking errors (AC-049).
- US-017 [medium] One tape at a time: interface shows exactly one tape, no create/name/switch/reopen options (AC-050); a different device/browser starts empty, no sync (AC-051); cleared tape offers no recovery/history (AC-052).

**Related:** US-016, US-017

### REQ-EPIC-006 · draft · source: requirements:EPIC-006

Anyone can open the app and use it instantly: no accounts, sign-in, payment or adverts; all arithmetic happens client-side with no personal data collected; app works offline after first load and is installable to a home screen.

Open assumptions: free with no payments/subscriptions/adverts; no analytics beyond privacy-friendly aggregate page counts, no personal data, minimal GDPR exposure; client-side-only static site on EU hosting, no backend/database, traffic assumed well under 1,000 users so no capacity planning done; offline use and install-to-home-screen assumed in scope, first candidates to defer if costly.
- US-018 [critical] Immediate use, no sign-in: first visit presents a usable empty tape with no sign-up/onboarding/consent step (AC-053); no login/registration/profile/account settings anywhere (AC-054); no payment/subscription/upgrade/advert at any point (AC-055).
- US-019 [high] Numbers stay off any server: no line values/totals transmitted after initial load, verified via network inspection (AC-056); deployed app is client-side-only static site, no backend/database holding user data, hosted in EU (AC-057); any instrumentation limited to privacy-friendly aggregate page counts, no tracking cookies or individual identification (AC-058).
- US-020 [medium] Offline and installable: reopening with no network still allows tape, entry, editing, clear, copy to work (AC-059); installable to home screen with name/icon, opens directly into tape (AC-060); offline-added lines remain unchanged on reconnect with no sync/upload attempted (AC-061).

**Related:** US-018, US-019, US-020

- ⚠ Analytics tool/vendor for 'privacy-friendly aggregate page counts' is not specified in any input.
<!-- sdlc:auto:end narrative -->

<!-- sdlc:auto:start summary -->
**Requirements version:** v1  
**Delivery scope:** lightweight  
**Approved:** 2026-09-22

**Capabilities in scope:** Adding-machine tape entry of an unbounded sequence of numbers, Continuously updating running total, Visible list of entered lines, Delete a line from the tape, Edit a line's value with the total recalculating, Clear the tape and start again, Copy the total to the clipboard, Acceptance of whole numbers, decimals, money amounts and measurements, Rejection of non-numeric entries at the point of typing, Responsive tape that works on a phone and at a desk, Numeric keypad entry on mobile, Keyboard-only entry on desktop with Enter to add a line, Current tape retained in the browser across an accidental refresh, Penny-accurate decimal arithmetic with no floating-point drift, No currency symbol or currency selection shown, Negative numbers accepted as the only way to subtract, No labels or notes on individual lines, One tape at a time for a single anonymous user per device, No accounts, sign-in or user identity of any kind, Free to use, with no payments, subscriptions or adverts, Current tape held only in the browser, never on a server

**Approved technology stack:**

| Layer | Choice | Rationale |
|---|---|---|
| backend | FastAPI | Your product genuinely needs no server: every sum happens in the browser and the tape lives in local storage. FastAPI is the only backend on the list, so I name it as the choice of record, with the honest recommendation that you deploy nothing behind the app for now — a minimal FastAPI service only serving the static files, or none at all. Keep it in reserve for the day you want saved history or sharing, both of which you have deliberately excluded. |
| cloud | AWS | The app is a bundle of static files plus offline caching, which is the simplest thing any host can do, and AWS covers it with S3 and CloudFront. It lets you pin hosting to an EU region as assumed, which keeps the privacy story clean, and at well under a thousand users the cost will be pennies a month. It also means that if the product later grows a backend or a database, you are not moving providers. |
| database | PostgreSQL | You confirmed nothing is kept on a server: the current tape sits in the browser's local storage and there is no cross-device or long-term history, no accounts and no personal data. So there is no data to store and no database to run at launch. PostgreSQL is the only option available, and it is the right one to name for later — if you ever add saved tapes or accounts, it handles exact decimal money values natively without rounding drift, which matters given penny accuracy is a hard requirement. |
| frontend | React | This matches the starting point already agreed: the whole product lives in the browser. The tape — lines appearing, a line being edited or deleted, the running total updating instantly — is exactly the kind of live list React handles well, and with TypeScript the number handling and exact-decimal arithmetic are checked before anything ships. It also gives you the phone-and-desk behaviour, numeric keypad on mobile, Enter-to-add on desktop, offline use after first load and install-to-home-screen, without a second codebase. |
<!-- sdlc:auto:end summary -->

<!-- sdlc:auto:start epics -->
## EPIC-001: Adding-machine tape entry and running total

The core of the product: the user enters an unbounded sequence of numbers, each appearing as a line in a visible list, with a running total that updates continuously. This replaces a two-box "A + B" form; plain two-number addition is covered as a special case of the tape.

Scope notes and open assumptions:
- There is no limit on the number of lines in a tape.
- Lines carry a number only. Labels or notes on individual lines are assumed out of scope; this is the assumption most likely to be wrong if the real use turns out to be expenses or stock-taking.
- Only addition is supported. Other operators (x, /) and a full calculator are excluded.

### US-001: Add a number as a new line on the tape

**Priority:** critical

> As a person adding up a series of numbers, I want to type a number and add it to the tape as a new line, so that I can build up a list of the numbers I am adding without losing sight of any of them.

| ID | Given | When | Then |
|---|---|---|---|
| AC-001 | the app is open with an empty tape | the user types a valid number into the entry field and confirms it | the number appears as the first line of the visible tape list and the entry field is cleared and ready for the next number |
| AC-002 | a tape that already contains one or more lines | the user adds another number | the new number is appended as the next line below the existing lines, in the order it was entered, and no existing line is altered |
| AC-003 | the entry field is empty | the user attempts to confirm the entry | no line is added to the tape and the tape and total are unchanged |

### US-002: See the running total update continuously

**Priority:** critical

> As a person adding up a series of numbers, I want a total that updates the moment a line is added, so that I always know where I am without pressing an equals button.

| ID | Given | When | Then |
|---|---|---|---|
| AC-004 | an empty tape | the user opens the app | the running total is displayed as 0 |
| AC-005 | a tape showing a running total | the user adds a new line | the displayed total is immediately updated to the sum of all lines on the tape, with no further action required from the user |
| AC-006 | a tape of lines 10.50, 4.25 and -2.75 | the user views the total | the total displayed is 12.00 |
| AC-007 | a tape with many lines so that the list scrolls | the user scrolls the list of lines | the running total remains visible on screen at all times |

### US-003: Build a tape of unlimited length

**Priority:** high

> As a person adding a long list of numbers, I want to keep adding lines with no cap on how many, so that I am never forced to split a long job across two sessions.

| ID | Given | When | Then |
|---|---|---|---|
| AC-008 | a tape that already contains a large number of lines (for example 500) | the user adds a further line | the line is accepted, the total is recalculated correctly, and the app remains responsive to further entry |
| AC-009 | a tape longer than fits on one screen | the user adds a new line | the list scrolls so that the newest line is visible |

### US-004: Add just two numbers

**Priority:** medium

> As a person who only needs a quick sum of two numbers, I want the tape to work just as well for two entries as for fifty, so that the simplest case is not made harder by the tape design.

| ID | Given | When | Then |
|---|---|---|---|
| AC-010 | an empty tape | the user enters two numbers one after another | both appear as lines and the total shows their sum, with no extra step such as pressing equals |

## EPIC-002: Correcting and managing the tape

Practical tape handling so a mistake does not force the user to start over: delete a line, edit a line's value with the total recalculating, clear the whole tape, and copy the total to the clipboard.

Open assumption: this editing set (delete, edit, clear, copy) is assumed necessary for the first version. If real use shows the user only ever adds lines and starts again, this epic could be trimmed to clear-only.

Out of scope for this version: export to a file, a print view, and sharing a tape with anyone else.

### US-005: Delete a single line from the tape

**Priority:** high

> As a person who has keyed a number in error, I want to remove one line from the tape, so that I can fix the mistake without rekeying everything.

| ID | Given | When | Then |
|---|---|---|---|
| AC-011 | a tape containing three lines | the user deletes the second line | that line is removed from the list, the remaining lines keep their original order, and the total is immediately recalculated as the sum of the remaining lines |
| AC-012 | a tape with a single line | the user deletes it | the tape is empty and the total shows 0 |
| AC-013 | the tape is displayed on a phone | the user looks at any line | a delete control for that line is reachable with a single tap on a target large enough to hit accurately |

### US-006: Edit a line's value

**Priority:** high

> As a person who mistyped a figure, I want to change the value of an existing line, so that the total is corrected without deleting and re-adding the line.

| ID | Given | When | Then |
|---|---|---|---|
| AC-014 | a tape containing the lines 10, 20 and 30 with a total of 60 | the user edits the second line to 25 | the line displays 25, its position in the list is unchanged, and the total updates to 65 |
| AC-015 | a line is being edited | the user enters a value that is not a valid number | the change is rejected with a visible indication and the line keeps its previous value |
| AC-016 | a line is being edited | the user cancels the edit | the line retains its original value and the total is unchanged |

### US-007: Clear the tape and start again

**Priority:** high

> As a person starting a new set of numbers, I want to clear the whole tape in one action, so that I can begin a fresh calculation without deleting lines one at a time.

| ID | Given | When | Then |
|---|---|---|---|
| AC-017 | a tape containing one or more lines | the user chooses to clear the tape and confirms | all lines are removed, the total returns to 0, and the entry field is focused and ready for the first number |
| AC-018 | a tape containing one or more lines | the user triggers clear but does not confirm | the tape and total are left exactly as they were |
| AC-019 | the tape has been cleared | the user reloads the page | the tape is still empty, confirming the cleared state was persisted rather than the old tape being restored |

### US-008: Copy the total to the clipboard

**Priority:** medium

> As a person who needs the answer somewhere else, I want to copy the running total with one action, so that I can paste it into another app without retyping and risking an error.

| ID | Given | When | Then |
|---|---|---|---|
| AC-020 | a tape with a total of 1234.56 | the user activates the copy control | the exact value 1234.56 is placed on the device clipboard as plain text, with no currency symbol or other decoration |
| AC-021 | the user has activated the copy control | the copy succeeds | a brief visible confirmation is shown so the user knows the value was copied |
| AC-022 | a browser that blocks or does not support clipboard access | the user activates the copy control | the user is shown a clear message and the total remains selectable so it can be copied manually |

## EPIC-003: Number handling and exact decimal arithmetic

The app accepts any number the user needs - whole numbers, decimals, money amounts and measurements - and is not tied to a currency. Totals are computed with exact decimal arithmetic so money is penny-accurate with no floating-point drift.

Open assumptions:
- Exact decimal arithmetic is assumed necessary because money is in scope; no currency symbols or currency selection are shown anywhere.
- Non-numeric input is rejected at the point of entry rather than silently ignored.
- Negative numbers are accepted and are the only way to subtract; there is no minus operator, and no x or / operators.

### US-009: Enter whole numbers, decimals, money amounts and measurements

**Priority:** critical

> As a person adding up anything from receipts to measurements, I want the app to accept any ordinary number I type, so that I do not have to reformat my figures to suit the app.

| ID | Given | When | Then |
|---|---|---|---|
| AC-023 | the entry field | the user enters a whole number such as 42 | it is accepted and added as a line showing 42 |
| AC-024 | the entry field | the user enters a decimal such as 3.75 or 0.125 | it is accepted and added as a line preserving the decimal places as entered |
| AC-025 | the entry field | the user enters a money-style amount such as 19.99 | it is accepted as a plain number with no currency symbol added or required |
| AC-026 | the tape and total display | the user views any line or the total | no currency symbol is shown and no currency selection option exists anywhere in the app |

### US-010: Subtract by entering a negative number

**Priority:** high

> As a person who needs to take a figure off the total, I want to enter a negative number as a line, so that I can subtract without needing a separate operator.

| ID | Given | When | Then |
|---|---|---|---|
| AC-027 | a tape with a total of 100 | the user adds the line -30 | the line is displayed as -30, visibly distinguishable from a positive line, and the total becomes 70 |
| AC-028 | the user is entering a number on a phone | the numeric entry is shown | a minus sign can be entered from the on-screen keypad or an explicit sign control |
| AC-029 | the app interface | the user looks for arithmetic controls | no subtract, multiply or divide operator is offered, as only addition of signed numbers is in scope |

### US-011: Have non-numeric input rejected at the point of typing

**Priority:** high

> As a person keying numbers quickly, I want invalid characters to be refused as I type rather than quietly dropped, so that I can trust that what I see on the tape is what I meant to enter.

| ID | Given | When | Then |
|---|---|---|---|
| AC-030 | the entry field | the user types a letter or a symbol that cannot form part of a number | the character does not appear in the field and the user is given an immediate visible indication that it was refused |
| AC-031 | the entry field already contains a decimal point | the user types a second decimal point | the second point is refused and the field keeps a single valid decimal number |
| AC-032 | the entry field contains an incomplete value such as a lone minus sign or decimal point | the user confirms the entry | no line is added and the user is told the value is not a valid number |

### US-012: Get a total that is correct to the penny

**Priority:** critical

> As a person adding up money, I want the total computed with exact decimal arithmetic, so that the answer never drifts by a fraction of a penny the way binary floating point does.

| ID | Given | When | Then |
|---|---|---|---|
| AC-033 | an empty tape | the user adds the lines 0.1 and 0.2 | the total displayed is exactly 0.3 and never 0.30000000000000004 |
| AC-034 | an empty tape | the user adds 0.01 one hundred times | the total displayed is exactly 1.00 |
| AC-035 | a tape mixing values of differing decimal precision such as 1, 2.5 and 3.125 | the total is calculated | the total is exactly 6.625 with no rounding or truncation of the entered values |
| AC-036 | a line is deleted or edited | the total is recalculated | the recalculated total is exactly equal to the decimal sum of the remaining line values |

## EPIC-004: Works on a phone and at a desk

A single responsive web app that is equally usable on a phone and on a desktop from day one: mobile brings up a numeric keypad with large tap targets, desktop supports keyboard-only entry with Enter to add a line.

Open assumption: basic accessibility expectations (readable contrast, large tap targets, full keyboard operation) are assumed to be part of this first version; no formal accessibility audit or conformance certification is in scope.

### US-013: Use the tape comfortably on any screen size

**Priority:** critical

> As a user switching between my phone and my desk, I want the same app to lay out sensibly on either screen, so that I do not need a separate app or a pinch-and-zoom struggle on mobile.

| ID | Given | When | Then |
|---|---|---|---|
| AC-037 | a phone-sized viewport (for example 375px wide) | the app is opened | the entry field, the list of lines and the running total are all usable without horizontal scrolling or zooming |
| AC-038 | a desktop-sized viewport | the app is opened | the layout adapts to the wider screen while keeping the entry field and running total prominent |
| AC-039 | the app open on a phone | the user rotates the device between portrait and landscape | the tape content and total remain intact and the layout reflows without loss of data |

### US-014: Get a numeric keypad on mobile

**Priority:** high

> As a phone user, I want the numeric keypad to appear when I tap the entry field, so that I can key numbers quickly without hunting through a full alphabetic keyboard.

| ID | Given | When | Then |
|---|---|---|---|
| AC-040 | the app open on a mobile device | the user taps the number entry field | the device shows a numeric keypad including the decimal separator and a way to enter a minus sign |
| AC-041 | the mobile keypad is open | the user confirms a line | the line is added, the field is cleared and the keypad stays open so the next number can be keyed straight away |
| AC-042 | the app displayed on a phone | the user taps any control such as add, delete, clear or copy | the control has a tap target large enough to be activated reliably with a thumb |

### US-015: Drive the whole tape from the keyboard on desktop

**Priority:** high

> As a desktop user keying a long list, I want to add, correct and clear lines without touching the mouse, so that I can enter numbers at speed the way I would on an adding machine.

| ID | Given | When | Then |
|---|---|---|---|
| AC-043 | the app open on a desktop browser | the page finishes loading | keyboard focus is already in the number entry field |
| AC-044 | focus is in the entry field with a valid number typed | the user presses Enter | the number is added as a line, the total updates and focus stays in the now-empty entry field |
| AC-045 | the app open on a desktop browser | the user navigates using only Tab, Shift+Tab and Enter | every interactive control including each line's delete and edit controls, clear and copy can be reached and activated, with a clearly visible focus indicator |
| AC-046 | the app rendered on any supported device | text and controls are inspected against their backgrounds | contrast is sufficient for the total and line values to be read comfortably |

## EPIC-005: Tape continuity in the browser

The current tape is held in the browser so an accidental refresh or tab switch does not wipe it. Nothing is stored on a server.

Open assumptions:
- Browser local storage holds only the current tape. There is no history of past tapes, no cross-device sync and no long-term record.
- One tape at a time for a single anonymous user per device; there is no way to keep two tapes side by side.

### US-016: Survive an accidental refresh

**Priority:** high

> As a person mid-way through a long tape, I want my lines and total to still be there after an accidental refresh or tab switch, so that a stray keystroke does not cost me all my work.

| ID | Given | When | Then |
|---|---|---|---|
| AC-047 | a tape containing several lines | the user refreshes the page or closes and reopens the tab in the same browser | the same lines appear in the same order and the same total is shown |
| AC-048 | a tape containing several lines | the user adds, edits or deletes a line | the change is persisted to browser storage immediately so a refresh at any point restores the latest state |
| AC-049 | a browser where local storage is unavailable or blocked | the user uses the app | the tape still works normally for the duration of the session and the user is not blocked by an error |

### US-017: Work with one tape at a time on this device

**Priority:** medium

> As a single anonymous user of the app, I want one clear current tape rather than a set of saved ones, so that the app stays as simple as an adding machine.

| ID | Given | When | Then |
|---|---|---|---|
| AC-050 | the app is open | the user looks at the interface | exactly one tape is shown and there is no option to create, name, switch between or reopen other tapes |
| AC-051 | a tape built on one device | the user opens the app on a different device or browser | that device starts with an empty tape, as no history is synced between devices |
| AC-052 | a tape has been cleared | the user looks for a way to recover it | no past-tape history is offered, consistent with the decision that saved history is out of scope for this version |

## EPIC-006: Open, free and private by default

Anyone can open the app and start using it instantly: no accounts, no sign-in, no payment and no adverts. All arithmetic happens in the browser, no personal data is collected, and the app remains usable offline after first load.

Open assumptions:
- Free with no payments, subscriptions or adverts of any kind.
- No analytics beyond basic privacy-friendly page counts; no personal data collected, keeping GDPR exposure minimal.
- Client-side-only static site on EU hosting with no backend or database; traffic is assumed to be low (well under a thousand users) so no capacity planning has been done.
- Offline use after first load and installation to a phone home screen are assumed in scope for this version; if that adds cost, they are the first candidates to defer.

### US-018: Start using the app immediately with no sign-in

**Priority:** critical

> As a first-time visitor, I want to open the app and start typing numbers straight away, so that nothing stands between me and the sum I need.

| ID | Given | When | Then |
|---|---|---|---|
| AC-053 | a user who has never visited before | they open the app URL | a usable empty tape is presented with no sign-up, sign-in, onboarding or consent step of any kind |
| AC-054 | the app interface | the user inspects it for account features | there is no login, registration, profile, or account settings option anywhere |
| AC-055 | the app interface | the user uses any feature | no payment, subscription, upgrade prompt or advert is presented at any point |

### US-019: Keep my numbers off any server

**Priority:** high

> As a privacy-conscious user, I want my figures to stay on my own device, so that nothing I add up is ever transmitted or stored elsewhere.

| ID | Given | When | Then |
|---|---|---|---|
| AC-056 | the app is in use with a tape of numbers | network traffic is inspected after the initial page load | no line values or totals are transmitted to any server |
| AC-057 | the deployed app | its architecture is reviewed | it is a client-side-only static site with no backend service and no database holding user data, hosted in the EU |
| AC-058 | the app is instrumented at all | measurement is reviewed | it is limited to privacy-friendly aggregate page counts with no personal data, cookies for tracking, or identification of individual users |

### US-020: Keep using the app offline and from the home screen

**Priority:** medium

> As a user with a poor or absent connection, I want the app to keep working after the first load and to be installable to my home screen, so that I can add up numbers anywhere, such as in a stockroom or on a train.

| ID | Given | When | Then |
|---|---|---|---|
| AC-059 | the user has loaded the app once | they reopen it with no network connection | the app loads and the tape, entry, editing, clear and copy features all work as normal |
| AC-060 | a supported mobile browser | the user chooses to install or add the app to their home screen | it installs with a name and icon and opens directly into the tape when launched |
| AC-061 | an offline session in which lines were added | the device comes back online | the tape is unchanged and no synchronisation or upload is attempted, since nothing is stored on a server |
<!-- sdlc:auto:end epics -->
