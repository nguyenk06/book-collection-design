# Planner Inbox

This file contains only unresolved decisions requiring Planner or product-owner input.

It is not a task backlog, technical issue tracker, Engineer progress log, changelog, roadmap, architecture document, or resolved-decision history. Designer owns this queue and removes each item after recording the accepted decision in the appropriate permanent source of truth.

## Current Decisions

### Decision 1 — Activate P1 after the five-hour reset?

The Product Owner authorized preparation, but not execution, of a diagnostic-only credential and branch-head brief. Current five-hour capacity is below the stopping floor. After reset and a fresh reading of at least 35%, may Sei II accept P1 with `!brief` and then execute it only after a separate `!run`?

- **A — Authorize P1 after reset:** supported authoritative Sites-managed context only; exactly one read-only query for `refs/heads/main`; automatic stop for ambiguity or unsupported access; no push, source change, Site operation, or release continuation.
- **B — Keep P1 parked:** prepare no Engineer activation until a later Product Owner instruction.
- **DEFER:** leave the decision open.

This decision cannot authorize P2 release resumption or P3 live validation.

When several decisions are pending, number them and keep each independently understandable. Planner may respond compactly, for example `1: B; 2: A; 3: DEFER`. Do not delay urgent or high-risk decisions for batching.
