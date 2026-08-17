# Planner Inbox

This file contains only unresolved decisions requiring Planner or product-owner input.

It is not a task backlog, technical issue tracker, Engineer progress log, changelog, roadmap, architecture document, or resolved-decision history. Designer owns this queue and removes each item after recording the accepted decision in the appropriate permanent source of truth.

## Current Decisions

### 1. Preserve the cumulative source as an unpublished saved version

- **Status:** `AWAITING PLANNER`
- **Raised by:** Designer — Relena
- **Decision:** Preserve the exact cumulative M3–M6/Shopping/Bookshelf source as one unpublished saved Site version, or continue relying on the dirty editable source?
- **Why Planner authority is required:** Preservation requires an exact source commit/push/package and Site save. Although saving does not deploy, publish, activate, or create a runnable checkpoint, it changes durable Site/source state.
- **A — PRESERVE (Designer recommendation):** Prepare a separately gated preservation-only brief with a fresh usage reading, exact manifest, full revalidation, commit/push/package identity, one unpublished Site save, and a mandatory stop before deployment.
- **B — CONTINUE DIRTY SOURCE:** Make no source or Site change; retain the current recovered working source and its loss/continuity risk.
- **Impact:** A improves durability but still provides no runnable preview or hands-on checkpoint. Neither option authorizes deployment, publication, activation, or production access.
- **Response:** `1: A` or `1: B`

### 2. Complete Gate 4 preservation evidence with a current private export

- **Status:** `AWAITING PLANNER`
- **Raised by:** Designer — Relena
- **Decision:** Authorize a separately bounded private read-only bridge export through the existing Version 19 owner surface to compare current counts, identities, values, and cover references with Gate 2?
- **Why Planner authority is required:** This is a new production-data export/read gate. Gate 4's existing verification path could confirm only schema-complete and zero-FK signals.
- **A — AUTHORIZE EXPORT EVIDENCE (Designer recommendation):** Prepare a read-only brief for one private structured export, offline comparison, sanitized evidence, automatic stop on mismatch/ambiguity, and no write or later gate.
- **B — ACCEPT INCOMPLETE GATE 4:** Perform no further production read; retain the independent schema/FK confirmation but keep preservation invariants unverified and later production gates closed.
- **Impact:** A may complete the missing preservation evidence using an existing supported path; it does not authorize correction, retry, migration, publication, or production mutation.
- **Response:** `2: A` or `2: B`

No hands-on-validation decision is queued yet. Sites exposes no runnable unpublished checkpoint, so any live-only checkpoint requires a separately designed sequence after preservation and production-gate decisions.

When several decisions are pending, number them and keep each independently understandable. Planner may respond compactly, for example `1: B; 2: A; 3: DEFER`. Do not delay urgent or high-risk decisions for batching.
