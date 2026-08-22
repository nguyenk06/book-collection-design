# Planner Inbox

This file contains only unresolved decisions requiring Planner or product-owner input.

It is not a task backlog, technical issue tracker, Engineer progress log, changelog, roadmap, architecture document, or resolved-decision history. Designer owns this queue and removes each item after recording the accepted decision in the appropriate permanent source of truth.

## Current Decisions

### Decision 1 — Resume exact `80e4c61` source preservation after ambiguous push timeout

Sei completed the entire pre-save validation and exact 83-path package for checkpoint `80e4c61`, then the required push to the configured Site source branch timed out through the credential path without a success/failure result. Lingering push/remote-check processes were terminated. No Site save, publication, deployment, production request, migration, schema/data mutation, correction, retry, rollback, or restore occurred; latest saved and published remains Version 20.

- **A — Authorize bounded resume after the supported credential path is available:** first read the configured remote branch head. If it is already exact `80e4c61`, do not push again. If it is definitively not exact and the source/branch/credential identities are unambiguous, allow one push attempt for exact `80e4c61`; then revalidate affected identity/capacity gates and continue the already-authorized one-save/one-publication sequence. Automatically stop for another timeout, ambiguity, drift, collision, failed gate, or reserve risk. No correction, alternate credential workaround, force push, second retry, migration, production mutation, rollback, restore, or destructive action.
- **B — Hold:** keep the brief parked, Version 20 live, and checkpoint `80e4c61` local until a later decision.

**Recommended:** A, but only after Sei confirms a supported credential path can return a definitive remote-state result.

When several decisions are pending, number them and keep each independently understandable. Planner may respond compactly, for example `1: B; 2: A; 3: DEFER`. Do not delay urgent or high-risk decisions for batching.
