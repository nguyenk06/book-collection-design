# Planner Inbox

This file contains only unresolved decisions requiring Planner or product-owner input.

It is not a task backlog, technical issue tracker, Engineer progress log, changelog, roadmap, architecture document, or resolved-decision history. Designer owns this queue and removes each item after recording the accepted decision in the appropriate permanent source of truth.

## Current Decisions

### Decision 1 — Remote endpoint execution/network-path disposition

Supported short-lived credential issuance now succeeds in Sei's established context. However, the authorized configured `main` branch-head read and a later direct owner-authorized second bounded read both failed to reach the remote endpoint and returned no SHA. No fetch, pull, push, ref update, Site save, publication, deployment, or production operation occurred. Exact `80e4c61` and its parent release remain parked.

- **A — Establish a materially different supported execution/network path:** move or reconnect the established Sei source context only through a normal supported path that can reach the configured remote endpoint. Return readiness evidence only; do not query the branch again, push, save, or publish from this decision. Designer will then prepare a new bounded evidence plan appropriate to that specific path.
- **B — Hold:** keep Version 20 live and exact `80e4c61` preserved locally. Perform no further remote or release work.

**Recommended:** A only if a genuinely different supported path is available. Otherwise B. A third identical query from the current path is not authorized.

When several decisions are pending, number them and keep each independently understandable. Planner may respond compactly, for example `1: B; 2: A; 3: DEFER`. Do not delay urgent or high-risk decisions for batching.
