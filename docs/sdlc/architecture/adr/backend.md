<!-- sdlc:auto:start adr -->
# ADR-0002: Use FastAPI (reserved, nothing deployed at launch) for Backend

Status: Proposed  
Date: 2026-09-22

## Context and Problem Statement

Which Backend technology does the project use? Decided in architecture v1.

## Considered Options

- FastAPI (reserved, nothing deployed at launch)
- No backend at all
- Node/Express (if a server is ever needed)

## Decision Outcome

Chosen option: FastAPI (reserved, nothing deployed at launch), because Approved stack and named as the choice of record. This design deploys nothing behind the app: every sum happens in the browser and the tape lives in local storage, so no API is needed now. FastAPI is kept in reserve to serve static files or to power future saved-history/sharing features.

## Consequences

Naming a backend that isn't deployed adds no runtime cost or attack surface today; the trade-off is simply that any future server work must build the API from scratch, which is intentional given those features are out of scope.
<!-- sdlc:auto:end adr -->