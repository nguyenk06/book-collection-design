# Planner Inbox

This file contains only unresolved decisions requiring Planner or product-owner input.

It is not a task backlog, technical issue tracker, Engineer progress log, changelog, roadmap, architecture document, or resolved-decision history. Designer owns this queue and removes each item after recording the accepted decision in the appropriate permanent source of truth.

## Current Decisions

## Authorize Production Backup Gate

**Status:** AWAITING PLANNER

**Raised by:** Engineer evidence reviewed by Designer

### Decision needed

Should Packet A be authorized to perform production target verification, read-only preflight queries, capture the current Time Travel bookmark, create and verify a protected SQL export, and enforce a maintenance/write freeze?

### Why this needs Planner

Packet A accesses production data infrastructure and can temporarily block database requests during export. Existing delegated authority covers planning only, not production access, backup execution, retention, or maintenance-window risk.

### Options

**A — Authorize Packet A after readiness details are confirmed**

Proceed only after the operator, verifier, maintenance window, secure backup location, retention period, write-freeze method, and abort authority are confirmed through the appropriate private channel. This does not authorize migration.

**B — Defer Packet A**

Keep Version 16 live and Version 17 unpublished. Production migration remains blocked.

### Designer recommendation

**A** — The verified backup is the required recovery gate before migration, while migration, publication, and destructive restore remain separately unauthorized.

### Impact

This controls the next Priority 0 operational gate. Approval permits production reads and backup creation only; it does not permit applying `0004`, publishing Version 17, smoke testing, or rollback.

### Response format

`Decision: A — authorize Packet A after readiness details are confirmed privately`

or

`Decision: B — defer Packet A`
