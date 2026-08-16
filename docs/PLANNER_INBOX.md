# Planner Inbox

This file contains only unresolved decisions requiring Planner or product-owner input.

It is not a task backlog, technical issue tracker, Engineer progress log, changelog, roadmap, architecture document, or resolved-decision history. Designer owns this queue and removes each item after recording the accepted decision in the appropriate permanent source of truth.

## Current Decisions

### M2 Gate 3 guarded schema activation

- **Status:** `AWAITING PLANNER`
- **Raised by:** Designer after accepted M2 Gate 2 evidence
- **Decision:** May Engineer invoke the guarded additive Shopping schema activation once through the owner-authenticated Version 19 administration surface, then stop before Gate 4 verification?
- **Why Planner authority is required:** This is the first production schema/data write in the controlled live sequence. The export is validated but is not a D1 snapshot and excludes R2 bytes.
- **Option A:** Approve Gate 3 only. Reconfirm target/session, write freeze, expected pre-upgrade status, private export availability, usage reserve, exact confirmation, and security controls; invoke the guarded re-entrant upgrade once; preserve the response; then stop before verification.
- **Option B:** Decline or defer. Production remains at the expected pre-upgrade baseline; no schema/data write occurs.
- **Designer recommendation:** A, because Gate 2 verified the expected baseline, zero foreign-key issues, preservation evidence, and private export. Automatically abort for any changed prerequisite, ambiguous target, unexpected status, unavailable export/recovery posture, failed protection, partial/ambiguous result, sensitive leakage, or usage-reserve risk; never retry blindly.
- **Impact:** No post-upgrade verification beyond preserving the immediate response, Shopping save/publication, live checklist, smoke test, rollback, forward repair, restore, or destructive action is authorized.
- **Response:** `Decision: A` or `Decision: B`

When several decisions are pending, number them and keep each independently understandable. Planner may respond compactly, for example `1: B; 2: A; 3: DEFER`. Do not delay urgent or high-risk decisions for batching.
