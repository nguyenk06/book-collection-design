# Planner Inbox

This file contains only unresolved decisions requiring Planner or product-owner input.

It is not a task backlog, technical issue tracker, Engineer progress log, changelog, roadmap, architecture document, or resolved-decision history. Designer owns this queue and removes each item after recording the accepted decision in the appropriate permanent source of truth.

## Current Decisions

### Authorize Version 18 Production Preflight and JSON Export

**Status:** AWAITING PLANNER / PRODUCT OWNER

**Decision needed:** Approve or defer an owner-only production bridge operation limited to read-only schema status and a versioned structured JSON export.

**Verified basis:** Version 18 publication succeeded. No application/API request or database operation has occurred, so production schema state and bridge behavior remain unverified. The bridge was locally validated for pre-upgrade readability, owner authorization, export, and preservation.

**Scope if approved:** Invoke only `GET /api/admin/schema-status` and `GET /api/admin/export`; store the export privately; verify its format/version, parseability, expected record categories, sanitized counts/identity invariants, and R2 references; return sanitized evidence and stop.

**Still unauthorized:** Schema-upgrade POST, D1/R2 writes, final Shopping publication, ordinary UI/API smoke testing, restore/import, rollback, destructive action, or exposing the export or private identifiers.

**Designer recommendation:** Approve this read-only backup gate. Require accepted preflight/export evidence before considering the schema-upgrade gate.

**Response format:** `Version 18 production preflight/export: APPROVED`, or `Version 18 production preflight/export: DEFERRED`.
