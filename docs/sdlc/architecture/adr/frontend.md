<!-- sdlc:auto:start adr -->
# ADR-0001: Use React for Frontend

Status: Accepted  
Date: 2026-10-24

## Context and Problem Statement

Which Frontend technology does the project use? Decided in architecture v2.

## Considered Options

- React
- Svelte
- Vue

## Decision Outcome

Chosen option: React, because The whole product lives in the browser and the tape is a live list — lines appearing, being edited or deleted, the running total updating instantly — which React handles well. Written in TypeScript so exact-decimal number handling is type-checked before shipping, and a single codebase delivers the phone keypad, desktop Enter-to-add, offline-after-first-load and install-to-home-screen behaviour.

## Consequences

A SPA framework is more than a trivial calculator strictly needs, but it keeps the responsive, PWA and editable-list requirements in one maintainable codebase.
<!-- sdlc:auto:end adr -->