# Planner Inbox

This file contains only unresolved decisions requiring Planner or product-owner input.

It is not a task backlog, technical issue tracker, Engineer progress log, changelog, roadmap, architecture document, or resolved-decision history. Designer owns this queue and removes each item after recording the accepted decision in the appropriate permanent source of truth.

## Current Decisions

### Preserve validated administration source as an unpublished Site version

- **Status:** `AWAITING PLANNER`
- **Raised by:** Designer from completed Engineer handoff
- **Decision question:** Approve preserving the exact locally validated owner-authenticated administration source as a new unpublished Site version?
- **Why Planner authority is required:** The accepted implementation brief explicitly stopped before Site-version creation; saving is a separate gate.
- **Option A — Approve:** Permit a separately scoped save of the exact validated source as an unpublished Site version, with no publication or production invocation.
- **Option B — Defer:** Leave the validated source unsaved in Sites until a later session.
- **Designer recommendation:** Option A, when the Product Owner is ready for the separate save operation; it preserves validated work without activating production behavior.
- **Impact:** Approval permits only a future narrow save brief. It does not enable Queue Mode or authorize publication, production requests, export, migration, verification, smoke testing, restore, or destructive action.
- **Response format:** `Decision: A` or `Decision: B`

When several decisions are pending, number them and keep each independently understandable. Planner may respond compactly, for example `1: B; 2: A; 3: DEFER`. Do not delay urgent or high-risk decisions for batching.
