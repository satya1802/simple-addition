<!-- sdlc:auto:start adr -->
# ADR-0001: Use React + TypeScript (PWA) for Frontend

Status: Proposed  
Date: 2026-09-22

## Context and Problem Statement

Which Frontend technology does the project use? Decided in architecture v1.

## Considered Options

- React + TypeScript (PWA)
- Vanilla TS/Web Components
- Svelte

## Decision Outcome

Chosen option: React + TypeScript (PWA), because Approved stack. React's live-list rendering fits the tape (lines appearing, edited, deleted with the total updating instantly), and TypeScript type-checks the exact-decimal number handling before ship. A single React codebase delivers responsive phone-and-desk behaviour, the mobile numeric keypad via input attributes, Enter-to-add on desktop, and — as a PWA — offline use and install-to-home-screen.

## Consequences

React ships more baseline JS than a hand-rolled vanilla app, marginally increasing the offline cache size; negligible for an app this small and outweighed by maintainability and type safety.
<!-- sdlc:auto:end adr -->