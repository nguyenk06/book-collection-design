# Planner Inbox

This file contains only unresolved decisions requiring Planner or product-owner input.

It is not a task backlog, technical issue tracker, Engineer progress log, changelog, roadmap, architecture document, or resolved-decision history. Designer owns this queue and removes each item after recording the accepted decision in the appropriate permanent source of truth.

## Current Decisions

### Authorize Version 18 Bridge Publication

**Status:** AWAITING PLANNER / PRODUCT OWNER

**Decision needed:** Approve or defer deployment/publication of saved Site Version 18 as the temporary Version 16-compatible migration bridge.

**Verified basis:** The bridge is implemented and locally validated; 37/37 tests pass, build and bridge/task lint pass, and the exact saved archive contains migrations `0000` through `0003` but not `0004`. Version 18 is unpublished, Version 16 remains published, and no production operation occurred.

**Scope if approved:** Publish/deploy Version 18 only. Do not invoke production admin APIs, export production data, upgrade schema, publish final Shopping behavior, perform smoke testing, restore/import, or take destructive action without separate approval.

**Designer recommendation:** Approve Version 18 bridge publication as the next isolated gate because its ordinary paths remain Version 16-compatible and its package does not independently contain `0004`. Require completion evidence before considering the production export gate.

**Response format:** `Version 18 bridge publication: APPROVED`, or `Version 18 bridge publication: DEFERRED`.
