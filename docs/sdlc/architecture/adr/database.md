<!-- sdlc:auto:start adr -->
# ADR-0003: Use PostgreSQL (reserved, no database at launch) for Database

Status: Proposed  
Date: 2026-09-22

## Context and Problem Statement

Which Database technology does the project use? Decided in architecture v1.

## Considered Options

- PostgreSQL (reserved, no database at launch)
- No database (current design)
- SQLite (if a lightweight later store suffices)

## Decision Outcome

Chosen option: PostgreSQL (reserved, no database at launch), because Approved stack. Nothing is kept on a server, so no database runs at launch — the current tape sits in browser local storage. PostgreSQL is the right name for later: its native numeric type stores exact decimal money values without rounding drift, matching the penny-accuracy requirement if saved tapes or accounts are ever added.

## Consequences

Deferring the database keeps launch operationally free and privacy-clean; the trade-off is no cross-device or long-term history, which is a deliberate scope exclusion.
<!-- sdlc:auto:end adr -->