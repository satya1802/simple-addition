<!-- sdlc:auto:start adr -->
# ADR-0004: Use AWS (S3 + CloudFront, EU region) for Cloud

Status: Proposed  
Date: 2026-09-22

## Context and Problem Statement

Which Cloud technology does the project use? Decided in architecture v1.

## Considered Options

- AWS (S3 + CloudFront, EU region)
- Netlify/Vercel static hosting
- Cloudflare Pages

## Decision Outcome

Chosen option: AWS (S3 + CloudFront, EU region), because Approved stack. A static bundle plus offline caching is the simplest thing any host can do, and S3 + CloudFront serves it over HTTPS with the origin pinned to an EU region to keep the privacy story clean. At well under a thousand users the cost is pennies a month, and staying on AWS means no provider migration if a FastAPI backend or PostgreSQL is added later.

## Consequences

S3 + CloudFront needs slightly more setup (bucket policy, distribution, cache invalidation) than a one-click static host, but gives EU-region control and a clean upgrade path to backend services on the same provider.
<!-- sdlc:auto:end adr -->