# Planner Inbox

This file contains only unresolved decisions requiring Planner or product-owner input.

It is not a task backlog, technical issue tracker, Engineer progress log, changelog, roadmap, architecture document, or resolved-decision history. Designer owns this queue and removes each item after recording the accepted decision in the appropriate permanent source of truth.

## Current Decisions

### 1. M2 Gate 4 read-only production verification

- **Status:** `AWAITING PLANNER`
- **Raised by:** Designer — Relena
- **Decision:** Authorize a bounded Gate 4 read-only verification of the one-time Gate 3 activation result?
- **Why Planner authority is required:** This accesses production state through the Product Owner's owner-authenticated Version 19 administration surface, even though it permits no write.
- **A — AUTHORIZE (Designer recommendation):** Verify schema, foreign keys, target price, counts, identities, ownership, copies, covers/references, and unchanged values against Gate 2 plus the immediate Gate 3 response; stop automatically for ambiguity or mismatch.
- **B — DEFER:** Leave the Gate 3 response unverified and every later production gate closed.
- **Impact:** Estimated 3–5 usage points. No correction, retry, migration, publication, restore, rollback, or later gate is included.
- **Response:** `1: A` or `1: B`

### 2. Read-only checkpoint and source-preservation feasibility

- **Status:** `AWAITING PLANNER`
- **Raised by:** Designer — Relena
- **Decision:** Authorize a read-only investigation of supported unpublished checkpoint/preview and source-preservation options for the recovered cumulative M3–M6/Shopping/Bookshelf source?
- **Why Planner authority is required:** The investigation determines the next operational path and may expose that a later Site save, preview, or live-only checkpoint decision is necessary; it must not create any of them now.
- **A — AUTHORIZE (Designer recommendation):** Inspect Sites capabilities, exact source composition, collision boundaries, access/binding behavior, and save/preview separation; return with an exact next gate and preservation recommendation.
- **B — DEFER:** Preserve the cumulative source unchanged and keep all user-facing checkpoints paused.
- **Impact:** Estimated 5–7 usage points including the linked candidate composition/preservation assessment. No save, preview creation, deployment, publication, production access, or source change is included.
- **Response:** `2: A` or `2: B`

An exact unpublished save or supported preview requires a later separate decision after Decision 2 produces capability evidence. Product Owner hands-on validation also requires a later separate decision after an exact safe environment exists. No fallback implementation decision is queued because no mature fallback is proposed.

When several decisions are pending, number them and keep each independently understandable. Planner may respond compactly, for example `1: B; 2: A; 3: DEFER`. Do not delay urgent or high-risk decisions for batching.
