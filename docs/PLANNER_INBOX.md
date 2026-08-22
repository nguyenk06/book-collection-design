# Planner Inbox

This file contains only unresolved decisions requiring Planner or product-owner input.

It is not a task backlog, technical issue tracker, Engineer progress log, changelog, roadmap, architecture document, or resolved-decision history. Designer owns this queue and removes each item after recording the accepted decision in the appropriate permanent source of truth.

## Current Decisions

### 1. Product Owner live validation of published Version 20

**Decision needed:** Authorize or hold the bounded desktop/mobile hands-on validation checkpoint for the newly published exact Version 20 cumulative Shopping/M3–M6/Bookshelf candidate.

- **A — Authorize validation:** Prepare and run the concise Product Owner checklist for Shopping, visible M3 identifier behavior, Bookshelf, and catalog download. Prefer read-only scenarios; any mutation scenario must be separately named and explicitly authorized before use.
- **B — Hold:** Leave Version 20 published without beginning hands-on validation.

This decision does not authorize broad smoke testing, correction, retry/republish, migration, production data/schema mutation, rollback, restore, destructive recovery, or publication of checkpoint `608553f`. Validation must return `ACCEPT`, `ACCEPT WITH FOLLOW-UP`, or `REVISE BEFORE RELEASE` and stop.

When several decisions are pending, number them and keep each independently understandable. Planner may respond compactly, for example `1: B; 2: A; 3: DEFER`. Do not delay urgent or high-risk decisions for batching.
