<!-- sdlc:auto:start adr -->
# ADR-0003: Use PostgreSQL for Database

Status: Accepted  
Date: 2026-10-24

## Context and Problem Statement

Which Database technology does the project use? Decided in architecture v2.

## Considered Options

- PostgreSQL
- No database

## Decision Outcome

Chosen option: PostgreSQL, because Nothing is kept on a server at launch, so there is no database to run: the current tape sits in browser local storage with no accounts, cross-device sync or history. PostgreSQL is the right name for later because it stores exact decimal money values natively without rounding drift, which matters given penny accuracy is a hard requirement.

## Consequences

No operational database cost now; if saved tapes or accounts arrive later, the exact-decimal column type is already the correct home for the values.
<!-- sdlc:auto:end adr -->