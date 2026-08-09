# Planner Inbox

This file contains only unresolved decisions requiring Planner or product-owner input.

It is not a task backlog, technical issue tracker, Engineer progress log, changelog, roadmap, architecture document, or resolved-decision history. Designer owns this queue and removes each item after recording the accepted decision in the appropriate permanent source of truth.

## Current Decisions

### Owner-only in-Site administration boundary

- **Status:** `AWAITING PLANNER`
- **Raised by:** Designer from completed Engineer investigation
- **Decision question:** Approve a small permanent owner-only Site administration page as the operating surface for bridge schema status, private export, separately approved schema upgrade, and verification?
- **Why Planner authority is required:** This creates a durable administration/security surface and determines how production schema activation can proceed within the Sites-only operating model.
- **Option A — Approve:** Reuse the proven same-origin Site request path and existing server-side owner authorization. Require explicit staged confirmation and same-origin/CSRF protection before any schema-changing request; keep export, upgrade, verification, final Shopping publication, smoke test, and destructive recovery separately gated.
- **Option B — Reject or redirect:** Do not implement the page; production activation remains blocked until Planner selects another supported Sites-native invocation design.
- **Designer recommendation:** Option A. The investigation found normal and bridge routes share the same authorization and bindings, while direct Engineer invocation failed before application execution.
- **Impact:** Approval permits Designer to record the architecture boundary and prepare a local implementation/validation brief only. It does not authorize production access, export, migration, publication, smoke testing, restore, or destructive action.
- **Response format:** `Decision: A` or `Decision: B — <direction>`
