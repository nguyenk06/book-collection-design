# Planner Inbox

This file contains only unresolved decisions requiring Planner or product-owner input.

It is not a task backlog, technical issue tracker, Engineer progress log, changelog, roadmap, architecture document, or resolved-decision history. Designer owns this queue and removes each item after recording the accepted decision in the appropriate permanent source of truth.

Every item must state the available choices, the practical impact of each, the recommended choice and reason, and a compact response format. Quatre repeats those choices in the Product Owner response rather than requiring the Product Owner to open this file.

## Current Decisions

### Decision 1 — Publish the accepted scanner authorization correction?

Exact clean local checkpoint `b5ba8f251e37ae42474089f769f95683e2e14429` passed the final release boundary and validation. Public production remains Version 32 at `802db5fd9c54c79e4897cc12de86b875163f6c07`.

- **A — Authorize release preparation and publication (recommended):** permit the bounded next release identity/preparation step, required final revalidation, and Quatre-owned Site save/deploy/publication of this accepted correction. This makes public scanning available while retaining authentication for every Add/edit mutation.
- **B — Hold Version 32:** keep the accepted candidate local and make no application or Site change. The public scanner retains the Version 32 probable-match dead end until a later authorization.

**Recommended:** A, because the candidate closes the Product Owner-reported workflow gap within the accepted boundary and has complete local release evidence. Publication remains unstarted until this decision is answered.

**Response:** `1:A` or `1:B`.
