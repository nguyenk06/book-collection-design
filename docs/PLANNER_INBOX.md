# Planner Inbox

This file contains only unresolved decisions requiring Planner or product-owner input.

It is not a task backlog, technical issue tracker, Engineer progress log, changelog, roadmap, architecture document, or resolved-decision history. Designer owns this queue and removes each item after recording the accepted decision in the appropriate permanent source of truth.

## Current Decisions

### M2 Gate 1 administration publication

- **Status:** `AWAITING PLANNER`
- **Raised by:** Designer after accepted M2 Gate 0 evidence
- **Decision:** May Engineer publish only the existing Version 19 owner-authenticated administration surface as Gate 1?
- **Why Planner authority is required:** This changes the live Site deployment and is an independently gated production-risk action under ADR-0012.
- **Option A:** Approve Gate 1 only. Engineer revalidates and publishes exact Version 19, verifies deployment/minimal availability, confirms Shopping remains unpublished and schema/data unchanged, then stops before Gate 2.
- **Option B:** Decline or defer. Version 18 remains published and M2 stays stopped at Gate 1.
- **Designer recommendation:** A. Gate 0 cleanly isolated the later Shopping candidate, and Gate 1 publishes only the already validated administration surface needed for the owner-authenticated bridge path.
- **Impact:** No export, schema activation, Shopping publication, live checklist, smoke test, rollback, or destructive action is authorized.
- **Response:** `Decision: A` or `Decision: B`

When several decisions are pending, number them and keep each independently understandable. Planner may respond compactly, for example `1: B; 2: A; 3: DEFER`. Do not delay urgent or high-risk decisions for batching.
