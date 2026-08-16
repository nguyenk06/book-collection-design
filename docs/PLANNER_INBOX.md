# Planner Inbox

This file contains only unresolved decisions requiring Planner or product-owner input.

It is not a task backlog, technical issue tracker, Engineer progress log, changelog, roadmap, architecture document, or resolved-decision history. Designer owns this queue and removes each item after recording the accepted decision in the appropriate permanent source of truth.

## Current Decisions

### M2 Gate 2 owner status and private export

- **Status:** `AWAITING PLANNER`
- **Raised by:** Designer after accepted M2 Gate 1 publication evidence
- **Decision:** May Engineer execute Gate 2 through an owner-authenticated Version 19 session: inspect schema status, create and privately retain the versioned structured export, and verify preservation preflight evidence?
- **Why Planner authority is required:** This is a bounded production read/export gate involving private production data and the recovery posture required before any schema activation.
- **Option A:** Approve Gate 2 only. Enforce the write freeze, verify target/session and expected baseline, inspect schema status, create and privately retain/validate the structured export, record sanitized preservation evidence and export limitations, then stop before schema activation.
- **Option B:** Decline or defer. Version 19 remains published; no production endpoint, export, schema, or data operation occurs.
- **Designer recommendation:** A, with automatic abort for unavailable owner session, ambiguous target, unexpected schema, failed/private-storage export, preservation mismatch, or inadequate recovery posture.
- **Impact:** No schema-upgrade POST, D1/R2 write, migration, Shopping publication, live checklist, smoke test, rollback, restore, or destructive action is authorized.
- **Response:** `Decision: A` or `Decision: B`

When several decisions are pending, number them and keep each independently understandable. Planner may respond compactly, for example `1: B; 2: A; 3: DEFER`. Do not delay urgent or high-risk decisions for batching.
