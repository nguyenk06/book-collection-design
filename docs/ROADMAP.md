# Roadmap

The database-first assessment validated the priority order. Enabling foundations are delivered immediately before their consumer; feature requirements remain in their linked documents.

## Status

| Priority | Workstream | Current status | Dependencies | Estimated effort | Known blockers |
| ---: | --- | --- | --- | --- | --- |
| 0 | Database integrity and Shopping persistence foundation | Partial; owner-authenticated administration surface preserved in unpublished Version 19 | Separately gated publication/export/upgrade/verification | Medium | Production schema remains unverified; book-to-collection foreign key deferred |
| 1 | [Shopping Mode](SHOPPING_MODE.md) | Partial; local UI complete; controlled live release/validation accepted but unexecuted | Exact release candidate, admin publication, export, schema activation/verification, Shopping publication, live validation/smoke | Medium-large | Every production gate remains unexecuted; cumulative source must be isolated |
| 2 | [Scanner and Matching](SCANNER_AND_MATCHING.md) | Partial; canonical identifier foundation complete locally | Future candidate workflow and user-facing matching | Medium | Production unchanged; fuzzy candidate matching deferred |
| 3 | [Bookshelf](BOOKSHELF.md) | Bounded first release complete locally; user checkpoint pending | Safe validation environment and Product Owner outcome before activation | Medium | Unsaved/unpublished; checkpoint environment blocked |
| 4 | [Import and Export](IMPORT_EXPORT.md) | Partial; catalog-first foundation complete locally | Future downloadable UI/checkpoint and separately gated activation | Medium-large | No production export/backup; import remains unsafe/immediate |
| 5 | [AI Review](AI_REVIEW.md) | Planned | Versioned interchange, review batches/proposals, field comparison, concurrency protection | Large | Stable interchange and review staging absent |
| 6 | Reference cover enrichment | Planned | Minimal asset metadata, personal/reference distinction, attribution, safe identifier match | Medium-large | No asset table; identifier confidence weak; personal covers need protection |
| 7 | [Asset improvements](ASSET_MANAGEMENT.md) | Partial | Asset table, variants, cleanup, broken-object fallback | Medium-large | One image key; missing metadata; orphaned R2 risk |
| 8 | [Tags](TAGS.md) | Planned | Tag and book-tag assignment tables | Medium | Persistence absent |
| 9 | Analysis and administration | Partial | Purchase data and owner-only administration routes | Medium | Only live KPIs exist; no dedicated administration area |

## Completed foundations

- Published, private single-user application.
- Durable D1 records, R2 cover storage, and SQL migration mechanism.
- Collection selection, search, scanner, responsive collection views, and owner-only writes.
- Database-first architecture assessment and roadmap validation.
- Collector-first and book-first design direction.

## Immediate milestone

Execute the controlled live Shopping release sequence in ADR-0012 without a separate validation Site:

- Isolate and validate the exact Shopping release candidate from the cumulative local worktree.
- Preserve/publish the owner-authenticated administration path through its own gate.
- Run owner-authenticated schema status, structured export, and preservation preflight before schema activation.
- Keep schema activation/verification and Shopping publication independently approved and evidenced.
- Run the desktop/mobile checklist and post-publication smoke review on the live Site.

Saving Version 17 does not mark Shopping released or active in production. Version 18 bridge is published, but schema activation and final Shopping publication remain separate gates.

Details and migration order are maintained in [Database](DATABASE.md). Accepted choices are recorded in the [Decision Log](DECISIONS.md).

The bounded continuation is recorded in [Staged Milestones](STAGED_MILESTONES.md). M1/M3/M4/M5 are complete locally. Revised M2 is queued for candidate preflight only; its production gates remain sequential and unexecuted.

## Deferred

- Full edition management and an immediate title/edition/copy hierarchy.
- Offline operation and generalized media support.
- Business locations.
- Social, lending, and marketplace capabilities.
- Fully autonomous AI changes to canonical data.
