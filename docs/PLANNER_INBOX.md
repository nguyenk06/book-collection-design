# Planner Inbox

This file contains only unresolved decisions requiring Planner or product-owner input.

It is not a task backlog, technical issue tracker, Engineer progress log, changelog, roadmap, architecture document, or resolved-decision history. Designer owns this queue and removes each item after recording the accepted decision in the appropriate permanent source of truth.

## Current Decisions

### 1. Local D1 remediation

**Decision needed:** Should Designer prepare a bounded local-only Engineer brief to repair the active Miniflare D1 by applying the already-defined ordered migrations `0004` → `0005` → `0006` after a private backup and disposable-clone proof?

- **A — Prepare the brief (recommended if data-populated local QA is next):** Require exact database identity, recoverable backup, disposable-clone validation, preservation checks, then a separate stop before active-local application unless the brief explicitly grants that local write.
- **B — Defer:** Leave the stale local database unchanged; data-populated local Shopkeeper/admin QA remains blocked, while unrelated local work may continue.

This decision grants no production, Site, source-migration, or migration-history authority.

### 2. Next Shopping release gate

**Decision needed:** With Gate 4 complete within its bridge-observable boundary, should Designer prepare the independently gated Shopping publication plan for review?

- **A — Prepare only (recommended):** Define exact candidate composition, pre-publication revalidation, publication boundary, automatic stops, and post-publication validation gates without executing any Site operation.
- **B — Hold:** Keep Version 19 published and Version 20 unpublished; prepare no release brief.

Preparation is not publication authority. Hands-on validation, smoke testing, correction, rollback, restore, and destructive recovery remain separate gates.

When several decisions are pending, number them and keep each independently understandable. Planner may respond compactly, for example `1: B; 2: A; 3: DEFER`. Do not delay urgent or high-risk decisions for batching.
