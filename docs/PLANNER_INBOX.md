# Planner Inbox

This file contains only unresolved decisions requiring Planner or product-owner input.

It is not a task backlog, technical issue tracker, Engineer progress log, changelog, roadmap, architecture document, or resolved-decision history. Designer owns this queue and removes each item after recording the accepted decision in the appropriate permanent source of truth.

## Current Decisions

### Decision 1 — Version 21 publication-resume revalidation

**Context:** Exact `f15ea81` remains clean and saved unpublished as Version 21; Version 20 remains live. The stopped publication brief consumed zero publication attempts. Its three focused failures did not reproduce: a later exact serial focused run passed 17/17 and the three affected cases passed 3/3 in isolation, both with exit 0. No source or generated artifact changed. All three failures are classified as execution/test-environment behavior at moderate confidence. The consumed briefs cannot be reused.

- **A — Authorize a separate bounded publication-resume brief.** Reconfirm exact Site/session/saved/source/package identities and clean boundaries; accept the completed diagnostic focused evidence while fresh and unchanged; run the remaining full serial suite, build, and required package/no-write gates; then permit exactly one Version 21 publication attempt and bounded read-only health verification only if every gate passes. Stop for any failure or ambiguity. No correction, test/source/configuration/dependency change, retry/republish, migration, production schema/data mutation, broad smoke, hands-on validation, rollback, restore, or destructive recovery.
- **B — Defer Version 21.** Keep Version 21 unpublished and Version 20 live.

**Designer recommendation:** `A`. The remaining slice is provisionally estimated at 5/8/13 five-hour points and the current `!73:62` reading exceeds the 28% operational minimum including the 15% floor.

When several decisions are pending, number them and keep each independently understandable. Planner may respond compactly, for example `1: B; 2: A; 3: DEFER`. Do not delay urgent or high-risk decisions for batching.
