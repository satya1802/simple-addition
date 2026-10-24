<!-- sdlc:auto:start adr -->
# ADR-0002: Use FastAPI for Backend

Status: Accepted  
Date: 2026-10-24

## Context and Problem Statement

Which Backend technology does the project use? Decided in architecture v2.

## Considered Options

- FastAPI
- No backend at all

## Decision Outcome

Chosen option: FastAPI, because The product genuinely needs no server at launch: every sum happens in the browser and the tape lives in local storage. FastAPI is named as the backend of record and, if deployed at all, only as a minimal service serving the static files. It is kept in reserve for a future saved-history or sharing feature, both deliberately excluded now.

## Consequences

Carrying a backend name with nothing behind the app is deliberate — zero runtime cost today, zero provider move the day a server is wanted.
<!-- sdlc:auto:end adr -->