# Planner Inbox

This file contains only unresolved decisions requiring Planner or product-owner input.

It is not a task backlog, technical issue tracker, Engineer progress log, changelog, roadmap, architecture document, or resolved-decision history. Designer owns this queue and removes each item after recording the accepted decision in the appropriate permanent source of truth.

## Current Decisions

### Approve Sites-Native Migration Bridge

**Status:** AWAITING PLANNER / PRODUCT OWNER

**Decision needed:** Approve, revise, or reject a temporary Version 16-compatible migration bridge as the architecture for safely activating the Version 17 Shopping schema within ChatGPT Sites.

**Verified basis:** The read-only investigation found no established packaged-migration execution contract and confirmed that `ensureSeeded()` does not create the Shopping schema required by ordinary Version 17 access. A guarded additive reconciler passed disposable first-run, repeat-run, and partial-state recovery validation while preserving sample identities and state. No Site or production operation occurred.

**Proposed bridge:** owner-only schema-status, versioned JSON-export, explicit re-entrant Shopping-upgrade, and verification APIs; Version 16-compatible ordinary traffic; no independent packaged `0004` execution; final Shopping publication remains separate.

**Designer recommendation:** Approve the architecture for local implementation/validation and creation of a new unpublished saved Site version only. Require separate explicit approval for bridge publication, production export, schema upgrade, final Shopping publication, smoke testing, or destructive action.

**Response format:** `Migration bridge: APPROVED for local implementation/validation and unpublished Site save only`, or provide the requested revision/rejection.
