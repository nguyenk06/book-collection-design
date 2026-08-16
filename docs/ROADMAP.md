# Roadmap

The database-first assessment validated the priority order. Enabling foundations are delivered immediately before their consumer; feature requirements remain in their linked documents.

## Status

| Priority | Workstream | Current status | Dependencies | Estimated effort | Known blockers |
| ---: | --- | --- | --- | --- | --- |
| 0 | Database integrity and Shopping persistence foundation | Partial; Version 19 published and Gate 3 immediate activation response complete | Separately gated Gate 4 verification | Medium | Activation is not independently verified; export is not a D1 snapshot and excludes R2 bytes; book-to-collection foreign key deferred |
| 1 | [Shopping Mode](SHOPPING_MODE.md) | Partial; local UI complete; controlled live sequence stopped after Gate 3 | Gate 4 verification, Shopping publication, live validation/smoke | Medium-large | Gate 4 and every later production gate remain unexecuted |
| 2 | [Scanner and Matching](SCANNER_AND_MATCHING.md) | Partial; canonical identifier foundation complete locally | Future candidate workflow and user-facing matching | Medium | Production unchanged; fuzzy candidate matching deferred |
| 3 | [Bookshelf](BOOKSHELF.md) | Bounded first release complete locally; user checkpoint pending | Safe validation environment and Product Owner outcome before activation | Medium | Unsaved/unpublished; checkpoint environment blocked |
| 4 | [Import and Export](IMPORT_EXPORT.md) | Partial; local catalog-first export foundation complete and downloadable UI ready for brief acceptance | Local M6 UI validation/checkpoint and separately gated activation | Medium-large | Cumulative M5 source recovered and verified; no production catalog export or complete backup; import remains unsafe/immediate |
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

Continue the controlled live Shopping release sequence in ADR-0012 without a separate validation Site. Candidate isolation, administration publication, status/export, and the one-time Gate 3 invocation are complete within their evidence boundaries:

- Retain the isolated, locally validated Shopping release candidate.
- Retain published Version 19 as the owner-authenticated administration path.
- Preserve the private Gate 2 structured export and its documented limitations.
- Treat the Gate 3 immediate activation response as distinct from the still-unperformed Gate 4 verification.
- Keep Gate 4 verification and Shopping publication independently approved and evidenced.
- Run the desktop/mobile checklist and post-publication smoke review on the live Site.

Saving Version 17 does not mark Shopping released or active in production. Version 19 administration is published, status/export is complete, and Gate 3 reported activation success; Gate 4 verification and final Shopping publication remain separate closed gates.

Details and migration order are maintained in [Database](DATABASE.md). Accepted choices are recorded in the [Decision Log](DECISIONS.md).

The bounded continuation is recorded in [Staged Milestones](STAGED_MILESTONES.md). M1/M3/M4/M5 and M2 Gates 0–3 are complete within their bounded evidence layers. Gate 3 was invoked exactly once and cannot be retried; its immediate success response is not Gate 4 verification. Later gates remain sequential, closed, and unauthorized.

## Deferred

- Full edition management and an immediate title/edition/copy hierarchy.
- Offline operation and generalized media support.
- Business locations.
- Social, lending, and marketplace capabilities.
- Fully autonomous AI changes to canonical data.
