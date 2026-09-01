# Planner Inbox

This file contains only unresolved decisions requiring Planner or product-owner input.

It is not a task backlog, technical issue tracker, Engineer progress log, changelog, roadmap, architecture document, or resolved-decision history. Designer owns this queue and removes each item after recording the accepted decision in the appropriate permanent source of truth.

## Current Decisions

### Decision 1 — Controlled publication of exact saved Version 21

**Context:** Exact correction checkpoint `f15ea8144ec277a737f5e491e0276b60555cafb8` is clean, source-preserved, fully revalidated, package-verified, and saved exactly once as unpublished Site Version 21 with a 47-file archive. Version 20 remains published and no preview is active. Publication was not authorized by the preservation/save brief.

- **A — Authorize a bounded publication brief.** Permit exact Site/session/saved-version/source/package identity checks, full required pre-publication revalidation, one publication attempt for exact saved Version 21, bounded application-health verification, sanitized evidence, and a clean stop. Automatically stop for ambiguity, drift, collision, failed validation, or usage-floor risk. Do not authorize correction, retry, republish, migration, production schema/data mutation, broad smoke testing, Product Owner hands-on validation, rollback, restore, or destructive recovery.
- **B — Defer publication.** Keep Version 21 unpublished and Version 20 live.

**Designer recommendation:** `A`, after a fresh usage reading supports the eventual brief.

### Decision 2 — Conditional Product Owner read-only live validation

**Context:** The five confirmed Version 20 failures have accepted local validation in exact Version 21, but Product Owner hands-on validation can occur only after a separately authorized successful publication because supported tooling exposes no runnable unpublished preview.

- **A — Authorize checklist preparation conditionally after successful publication.** Prepare a concise desktop/mobile, read-only-where-possible checklist for mobile Shopping discovery, primary multi-row Bookcase, horizontal Shelf alternate, missing-position selection/details, selected-book cover/fallback, and basic navigation. Keep every mutation scenario separately gated.
- **B — Defer hands-on validation.** Preserve the prior held state.

**Designer recommendation:** `A`. This decision does not authorize publication or any mutation.

When several decisions are pending, number them and keep each independently understandable. Planner may respond compactly, for example `1: B; 2: A; 3: DEFER`. Do not delay urgent or high-risk decisions for batching.
