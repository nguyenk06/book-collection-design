# Planner Inbox

This file contains only unresolved decisions requiring Planner or product-owner input.

It is not a task backlog, technical issue tracker, Engineer progress log, changelog, roadmap, architecture document, or resolved-decision history. Designer owns this queue and removes each item after recording the accepted decision in the appropriate permanent source of truth.

## Current Decisions

### Decision 1 — Classify Version 21 pre-publication focused-test failures

**Context:** Sei III's controlled publication run passed Site/session, saved/live version, source/package, clean-state, three-file delta, collision, whitespace, protected-boundary, and lint gates. The focused collection suite then reported 14/17 passing: two search tests timed out and one ISBN-10 search case did not find the expected heading. The strict brief stopped before full serial tests, build, or publication. Publication attempts remain zero; Version 20 is live and Version 21 remains saved unpublished. The failure is not yet classified as a reproducible candidate defect or an execution/test-environment issue.

- **A — Authorize bounded local diagnostic classification.** Prepare one diagnostic-only brief at exact clean `f15ea81`. Permit targeted read-only test/source inspection and up to three separately attributable, non-mutating diagnostic executions sufficient to classify each failure. Do not change source/tests/configuration/dependencies, publish, save, deploy, migrate, access or mutate production data/schema, or resume publication. Return evidence and the minimum next decision.
- **B — Defer Version 21.** Keep Version 21 unpublished and Version 20 live; do not investigate or resume the release.

**Designer recommendation:** `A`. Diagnosis is estimated at 4/7/11 five-hour points and would require a fresh reading of at least 26%, including the 15% floor.

When several decisions are pending, number them and keep each independently understandable. Planner may respond compactly, for example `1: B; 2: A; 3: DEFER`. Do not delay urgent or high-risk decisions for batching.
