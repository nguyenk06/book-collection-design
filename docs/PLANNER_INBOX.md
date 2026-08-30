# Planner Inbox

This file contains only unresolved decisions requiring Planner or product-owner input.

It is not a task backlog, technical issue tracker, Engineer progress log, changelog, roadmap, architecture document, or resolved-decision history. Designer owns this queue and removes each item after recording the accepted decision in the appropriate permanent source of truth.

## Current Decisions

### Decision 1 — Authorize the new Version 20-based remediation brief?

Product Owner Decision 1:A retired exact `80e4c61` as an executable candidate while preserving its historical evidence. Designer prepared [Version 20 Confirmed-Failure Remediation Plan](VERSION20_CONFIRMED_FAILURE_REMEDIATION_PLAN.md), limited to the five confirmed mobile-navigation and Bookshelf failures. The new candidate must start from exact Sites-managed Version 20 source and receive a new identity and full validation.

- **A — Authorize brief preparation (recommended):** Relena may create one local-only implementation brief for Sei II using the documented scope, 8/14/22 estimate, 70% minimum start, and 15% stop floor. Implementation still requires `!brief` then separate `!run`.
- **B — Revise planning:** keep implementation parked and return the minimum requested change.
- **DEFER:** keep the plan documented with no executable brief.

This decision cannot authorize source work now, Site save/version, preview, publication, deployment, production access/mutation, migration, held validation, retry, rollback, restore, or destructive recovery.

When several decisions are pending, number them and keep each independently understandable. Planner may respond compactly, for example `1: B; 2: A; 3: DEFER`. Do not delay urgent or high-risk decisions for batching.
