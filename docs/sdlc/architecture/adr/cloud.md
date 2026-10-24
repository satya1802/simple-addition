<!-- sdlc:auto:start adr -->
# ADR-0004: Use AWS for Cloud

Status: Accepted  
Date: 2026-10-24

## Context and Problem Statement

Which Cloud technology does the project use? Decided in architecture v2.

## Considered Options

- AWS
- Cloudflare Pages
- Netlify

## Decision Outcome

Chosen option: AWS, because The app is a bundle of static files plus offline caching — the simplest thing any host can do — covered by S3 and CloudFront with hosting pinned to an EU region to keep the privacy story clean. At well under a thousand users the cost is pennies a month, and growing a backend or database later means no provider move.

## Consequences

S3 + CloudFront needs slightly more setup than a one-click static host, but keeps the whole stack on one provider for the future.
<!-- sdlc:auto:end adr -->