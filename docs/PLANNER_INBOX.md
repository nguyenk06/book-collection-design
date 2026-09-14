# Planner Inbox

This file contains only unresolved decisions requiring Planner or product-owner input.

It is not a task backlog, technical issue tracker, Engineer progress log, changelog, roadmap, architecture document, or resolved-decision history. Designer owns this queue and removes each item after recording the accepted decision in the appropriate permanent source of truth.

Every item must state the available choices, the practical impact of each, the recommended choice and reason, and a compact response format. Quatre repeats those choices in the Product Owner response rather than requiring the Product Owner to open this file.

## Current Decisions

### Decision 1 — M9 personal-cover byte scope

What must the first “complete cover backup” package contain?

- **A — All accessible personal stored-cover objects (recommended):** include Book-referenced objects and currently orphaned personal objects in separate manifest/archive classes. Treat the bytes currently stored by the application as the recoverable unit; do not claim unavailable pre-processing originals. Exclude Open Library reference-image bytes.
- **B — Referenced personal objects only:** include only personal objects currently associated with a stable Book and report orphans without placing their bytes in the ZIP.

### Decision 2 — M9 backup retention

Where should completed backup packages be retained?

- **A — Owner download only (recommended):** generate an on-demand versioned ZIP for the owner; retain no server-side backup history. Any temporary package is bounded and removed without deleting source cover objects.
- **B — Server-retained snapshots:** retain versioned backup packages and separately define duration, storage limit, owner access, and package-deletion policy before implementation.
