# Planner Inbox

This file contains only unresolved decisions requiring Planner or product-owner input.

It is not a task backlog, technical issue tracker, Engineer progress log, changelog, roadmap, architecture document, or resolved-decision history. Designer owns this queue and removes each item after recording the accepted decision in the appropriate permanent source of truth.

## Current Decisions

### 1. Interim remediation assessment while live validation is held

Product Owner validation has confirmed three related UI failures:

- Mobile users cannot discover Shopping from the visible root/header navigation.
- Desktop and mobile Bookshelf provide only the horizontal shelf; Product Owner requires a primary multi-row bookcase while retaining horizontal as an alternate.
- Missing slots lack useful/selectable book information, and selected-book cover presentation is absent or requires source/data verification.

Items 2, 3, 5, and 8 remain follow-up/on hold; those held tests are not failures and must not be converted into speculative implementation. The final checkpoint conclusion is still pending.

**Decision needed:** May Designer prepare a bounded read-only Engineer source/collision assessment for the confirmed failed items while held validation waits?

- **A — Assess now (recommended):** Compare exact published Version 20 with later local checkpoint `608553f`; determine whether mobile Shopping navigation is already addressed, verify Bookshelf layout/detail/cover composition and data availability, identify shared-file collisions, and return an implementation estimate/recommended baseline. No source change or Site operation.
- **B — Hold all remediation work:** Wait for the remaining Product Owner tests and final checkpoint conclusion before asking Sei to inspect source.

An A decision authorizes assessment/estimation only. It does not select Version 20 or `608553f` as the remediation baseline, authorize implementation, treat held checks as failures, change source/data/schema, create a Site version, publish, correct production, retry, roll back, restore, or perform destructive recovery.

When several decisions are pending, number them and keep each independently understandable. Planner may respond compactly, for example `1: B; 2: A; 3: DEFER`. Do not delay urgent or high-risk decisions for batching.
