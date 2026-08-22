# Planner Inbox

This file contains only unresolved decisions requiring Planner or product-owner input.

It is not a task backlog, technical issue tracker, Engineer progress log, changelog, roadmap, architecture document, or resolved-decision history. Designer owns this queue and removes each item after recording the accepted decision in the appropriate permanent source of truth.

## Current Decisions

### Decision 1 — Configured Site source credential-path disposition

The exact `80e4c61` candidate remains clean, validated, and locally packaged. Its initial configured-source push timed out, and a separately authorized read-only branch-head check then timed out again through the same credential path. Both operations stopped cleanly with no definitive remote SHA, no resumed push attempt, and zero Site save/publication/deployment attempts. Version 20 remains latest saved and published.

- **A — Establish the supported path, then reassess:** Product Owner makes the configured Site source remote readable through a supported noninteractive credential path in Sei's established context. Return only evidence that a definitive branch-head read is available; do not push, save, or publish from this decision. Designer then prepares a fresh bounded resume estimate/authority using the observed remote state.
- **B — Hold:** keep exact `80e4c61` local and Version 20 live. Do not perform further credential, remote, Site, or release work.

**Recommended:** A if the supported credential setup can be completed normally; otherwise B. Do not repeat the same timed-out operation or improvise an alternate credential workaround.

When several decisions are pending, number them and keep each independently understandable. Planner may respond compactly, for example `1: B; 2: A; 3: DEFER`. Do not delay urgent or high-risk decisions for batching.
