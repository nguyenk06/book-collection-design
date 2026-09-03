# Planner Inbox

This file contains only unresolved decisions requiring Planner or product-owner input.

It is not a task backlog, technical issue tracker, Engineer progress log, changelog, roadmap, architecture document, or resolved-decision history. Designer owns this queue and removes each item after recording the accepted decision in the appropriate permanent source of truth.

## Current Decisions

### Decision 1 — Reconcile ambiguous Version 21 publication identity

**Context:** Exact Version 21 at clean `f15ea81` passed all remaining release gates: reused lint/focused evidence stayed attributable, full serial tests passed 93/93, build passed, and final package/no-write/boundary checks passed. The sole 1/1 publication invocation returned a connector error without deployment identity, URL, status, or success confirmation. A post-invocation read-only view showed an active Site, Version 21 latest saved, no preview, and a live release, but not which version is live. Version 20 is the last confirmed pre-invocation baseline. No retry or health check occurred.

- **A — Authorize one bounded read-only deployment-history/status verification.** Query only supported Site release metadata sufficient to establish exact current published version, source checkpoint, deployment identity/status, and invocation outcome. Do not publish, retry, republish, save, preview, deploy, run health checks or hands-on validation, change source, migrate, mutate schema/data, roll back, restore, or use an alternate path. If exact Version 21 is definitively live, return evidence for Designer acceptance and conditional checklist preparation. If Version 20 is definitively live, return for a separate retry decision. If identity remains ambiguous, stop parked.
- **B — Defer reconciliation.** Record current live-version identity as unknown and perform no release or validation work.

**Designer recommendation:** `A`. Estimated usage is 2/4/7 five-hour points; obtain a fresh reading of at least 22%, including the 15% floor, before any Engineer brief/run.

When several decisions are pending, number them and keep each independently understandable. Planner may respond compactly, for example `1: B; 2: A; 3: DEFER`. Do not delay urgent or high-risk decisions for batching.
