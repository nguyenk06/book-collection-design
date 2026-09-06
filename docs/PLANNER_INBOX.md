# Planner Inbox

This file contains only unresolved decisions requiring Planner or product-owner input.

It is not a task backlog, technical issue tracker, Engineer progress log, changelog, roadmap, architecture document, or resolved-decision history. Designer owns this queue and removes each item after recording the accepted decision in the appropriate permanent source of truth.

## Current Decisions

The following choices are required for visual-review convergence and future goal preparation. They do not authorize source changes or activate Version 21 hands-on validation.

### Decision 1 — What should “more spines” mean?

**Context:** Product Owner confirmed the Bookcase mode format is correct but expected more spines. No defect or density target is established.

- **A — Responsive density-first:** Reduce spine width/gaps within readable, keyboard, and touch-safe limits so each viewport naturally shows more spines; do not impose fixed counts.
- **B — More above the fold:** Preserve current spine width and show more rows by reducing surrounding vertical space.
- **C — Explicit viewport targets:** Product Owner supplies desired visible-spine counts for representative desktop and mobile widths.

**Designer recommendation:** `A`, because it preserves responsive behavior without inventing device-specific counts.

### Decision 2 — What should Book click do for covers?

**Context:** Clicking a Book did not load a cover during the visual review. Existing direction opens accessible Book details with stored-cover presentation and safe fallback, while reference-cover enrichment is a separate roadmap item.

- **A — Existing-cover detail:** Open the Book detail and show only the already stored personal cover when available, otherwise the safe fallback. Keep reference-cover lookup/enrichment separate.
- **B — Reference-assisted detail:** Permit a reference-cover lookup/load as part of the click path, making reference-cover enrichment a dependency before this behavior can be scoped.
- **C — Metadata-only detail:** Keep Book click focused on metadata and navigation without a cover-loading requirement.

**Designer recommendation:** `A`, preserving the current data/API boundary and avoiding silent scope combination.

### Decision 3 — Which missing-book details belong in Shelf at-a-glance view?

**Context:** Product Owner wants missing-book detail visible in Shelf mode. Current design forbids synthetic Books and must not imply unavailable metadata.

- **A — Compact existing-data summary:** Show expected position/number, known title, missing status, and any already available acquisition cue; omit unavailable fields explicitly.
- **B — Rich acquisition summary:** Require price/priority/notes and other purchasing fields, which may need a new data contract before UI work.
- **C — Minimal identity:** Show only expected position/number and known title.

**Designer recommendation:** `A`, maximizing at-a-glance utility while staying within existing data.

### Decision 4 — How should asset lifecycle and complete cover backup be bounded?

**Context:** Additional-roadmap item 2 is medium-large and marked `NEEDS MORE INFORMATION`. Existing exports exclude R2 bytes and do not prove complete cover backup or recovery readiness.

- **A — Split feasibility first:** First define and verify cover inventory, byte-backup completeness, integrity, retention, and recovery contract read-only; scope lifecycle implementation separately afterward.
- **B — One combined goal:** Treat metadata, variants, cleanup, byte backup, and recovery as one medium-large implementation goal.
- **C — Lifecycle first:** Implement metadata/variants/cleanup first and leave complete cover backup as a later independent goal.

**Designer recommendation:** `A`, because backup and recovery claims need evidence before implementation scope is safe.

Decision 1:B on 2026-09-04 continues to keep Version 21 hands-on validation parked; these new decisions do not change that boundary.

When several decisions are pending, number them and keep each independently understandable. Planner may respond compactly, for example `1: B; 2: A; 3: DEFER`. Do not delay urgent or high-risk decisions for batching.
