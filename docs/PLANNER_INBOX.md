# Planner Inbox

This file contains only unresolved decisions requiring Planner or product-owner input.

It is not a task backlog, technical issue tracker, Engineer progress log, changelog, roadmap, architecture document, or resolved-decision history. Designer owns this queue and removes each item after recording the accepted decision in the appropriate permanent source of truth.

## Current Decisions

### 1. Execute the prepared cumulative Version 20 publication brief

Product Owner selected the exact cumulative Version 20 Shopping/M3–M6/Bookshelf candidate (`1:B`) and excluded later local Phase A/D checkpoint `608553f`. Designer prepared a held publication brief with an estimated 8–13 usage-point envelope, including intake, identity/composition checks, full revalidation, one publication attempt, bounded health verification, evidence, ordinary non-mutating remediation, and clean stop.

**Decision needed:** Authorize or hold execution of that exact publication brief.

- **A — Authorize publication:** Permit Sei to revalidate and publish the exact saved Version 20 candidate once, then verify deployment identity and bounded application health and stop.
- **B — Hold:** Keep Version 19 published and Version 20 unpublished. The prepared brief remains non-executable.

Neither option authorizes migration, production data/schema mutation, live Product Owner validation, broad smoke testing, correction, retry, republish, rollback, restore, or destructive recovery. An A decision still requires explicit `!run`, successful `!brief` acceptance, a fresh usage reading, and preservation of the standing 30% reserve.

When several decisions are pending, number them and keep each independently understandable. Planner may respond compactly, for example `1: B; 2: A; 3: DEFER`. Do not delay urgent or high-risk decisions for batching.
