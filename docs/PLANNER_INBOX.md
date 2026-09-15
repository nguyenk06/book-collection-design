# Planner Inbox

This file contains only unresolved decisions requiring Planner or product-owner input.

It is not a task backlog, technical issue tracker, Engineer progress log, changelog, roadmap, architecture document, or resolved-decision history. Designer owns this queue and removes each item after recording the accepted decision in the appropriate permanent source of truth.

Every item must state the available choices, the practical impact of each, the recommended choice and reason, and a compact response format. Quatre repeats those choices in the Product Owner response rather than requiring the Product Owner to open this file.

## Current Decisions

### Decision 1 — initial tag intake

- **Status:** `AWAITING PLANNER`
- **Question:** How should tags enter the first tag workflow?
- **A — Manual tags plus reviewable provider suggestions (recommended):** collectors create canonical tags; provider subjects may be offered as uncommitted suggestions that require confirmation. Reuses enrichment evidence without surrendering vocabulary control.
- **B — Manual tags only:** simplest and most private initial release, but discards useful provider assistance and requires more typing.
- **Why owner authority is required:** changes the product's automation and provenance boundary.
- **Response:** `1:A` or `1:B`.

### Decision 2 — initial tag attachment scope

- **Status:** `AWAITING PLANNER`
- **Question:** What can receive tags in the first release?
- **A — Books only (recommended):** one understandable relationship and smaller persistence/import/filter surface.
- **B — Books and collections:** supports collection-level organization immediately but adds semantics, UI, export, and conflict rules.
- **Why owner authority is required:** materially changes the first tag data model and user workflow.
- **Response:** `2:A` or `2:B`.

### Decision 3 — first safe-import format

- **Status:** `AWAITING PLANNER`
- **Question:** Which input format should the first dry-run import support?
- **A — My Library catalog-v1 JSON only (recommended):** provides one versioned, deterministic round-trip contract before third-party mappings.
- **B — Catalog JSON and generic CSV together:** helps manual spreadsheets sooner but adds column mapping, encoding, ambiguity, and broader validation work.
- **Why owner authority is required:** sets the size and interoperability promise of the first safe-import milestone.
- **Response:** `3:A` or `3:B`.

### Decision 4 — AI Review submission boundary

- **Status:** `AWAITING PLANNER`
- **Question:** What Library data may a future AI Review send for analysis?
- **A — Explicitly selected records only (recommended):** each review session shows the fields being sent and requires confirmation; strongest privacy and cost control.
- **B — Explicit whole-Library batch sessions:** enables broader anomaly detection but sends more personal collection data and requires stronger retention, cost, progress, and cancellation controls.
- **Why owner authority is required:** establishes the privacy and external-processing boundary.
- **Response:** `4:A` or `4:B`.

### Decision 5 — first expanded-administration focus

- **Status:** `AWAITING PLANNER`
- **Question:** Which analysis should expanded administration prioritize first?
- **A — Data quality and backup health (recommended):** missing identifiers, covers, orphan/missing assets, and export/backup readiness; reinforces M9 and safe restore.
- **B — Collection completion analytics:** gaps, series progress, duplicates, and collection comparisons; more collector-facing insight.
- **C — Spending and purchase analytics:** price history, businesses, and acquisition patterns; depends more heavily on the shelved Shopkeeper/purchase workflow.
- **Why owner authority is required:** sets the first analysis milestone's product value and dependencies.
- **Response:** `5:A`, `5:B`, or `5:C`.
