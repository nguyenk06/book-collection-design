# Planner Inbox

This file contains only unresolved decisions requiring Planner or product-owner input.

It is not a task backlog, technical issue tracker, Engineer progress log, changelog, roadmap, architecture document, or resolved-decision history. Designer owns this queue and removes each item after recording the accepted decision in the appropriate permanent source of truth.

## Current Decisions

### Decision 1 — Exact `80e4c61` source-recovery direction

P1 definitively confirmed the authoritative Sites-managed repository, supported credentials, and remote `main` at published Version 20 SHA `6a2191b1b506d171d576cbb6a6b160964595c051`. Sei II has no editable checkout of exact candidate `80e4c61`. The retained exact-hash package contains generated `dist/` output, not the 83-path editable source, so it cannot satisfy the release source gate.

- **A — Read-only original-Sei source locator (recommended):** authorize preparation of one diagnostic brief that inspects the continuing original Sei repository/working context for the actual clean `80e4c61` commit/tree and a supported preservation path. No copy, push, source change, Site operation, or release continuation.
- **B — Retire exact `80e4c61`:** stop recovery and require a separately designed Version 20-based remediation implementation; do not reconstruct silently.
- **DEFER — Keep P2 parked:** make no new source-recovery or remediation brief.

None of these choices authorizes P2 release execution, source transfer, push, Site save, publication, deployment, migration, or production mutation.

When several decisions are pending, number them and keep each independently understandable. Planner may respond compactly, for example `1: B; 2: A; 3: DEFER`. Do not delay urgent or high-risk decisions for batching.
