# Roadmap

The database-first assessment validated the priority order. Enabling foundations are delivered immediately before their consumer; feature requirements remain in their linked documents.

## Status

| Priority | Workstream | Current status | Dependencies | Estimated effort | Known blockers |
| ---: | --- | --- | --- | --- | --- |
| 0 | Database integrity and Shopping persistence foundation | Partial; Gate 4 independently confirmed schema-complete and zero-FK signals | Complete preservation evidence through a separately approved read-only path | Medium | Target price/counts/identities/preservation remain unverified; export is not a D1 snapshot and excludes R2 bytes |
| 1 | [Shopping Mode](SHOPPING_MODE.md) | Partial; local UI complete; controlled live sequence stopped at incomplete Gate 4 | Preservation evidence, Shopping publication, live validation/smoke | Medium-large | Gate 4 preservation evidence and every later production gate remain incomplete/unexecuted |
| 2 | [Scanner and Matching](SCANNER_AND_MATCHING.md) | Partial; canonical identifier foundation complete locally | Future candidate workflow and user-facing matching | Medium | Production unchanged; fuzzy candidate matching deferred |
| 3 | [Bookshelf](BOOKSHELF.md) | Bounded first release complete locally; user checkpoint pending | Safe validation environment and Product Owner outcome before activation | Medium | Unsaved/unpublished; checkpoint environment blocked |
| 4 | [Import and Export](IMPORT_EXPORT.md) | Partial; catalog-first export foundation and owner-only downloadable UI complete locally | Product Owner checkpoint and separately gated activation | Medium-large | Unsaved/unpublished; no production catalog export or complete backup; import remains unsafe/immediate |
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
- Treat the Gate 3 immediate activation response as distinct from Gate 4's later independent but incomplete verification.
- Keep Gate 4 verification and Shopping publication independently approved and evidenced.
- Run the desktop/mobile checklist and post-publication smoke review on the live Site.

Saving Version 17 does not mark Shopping released or active in production. Version 19 administration is published, Gate 3 reported activation success, and Gate 4 independently confirmed schema-complete/zero-FK signals but not preservation invariants; final Shopping publication remains a separate closed gate.

Details and migration order are maintained in [Database](DATABASE.md). Accepted choices are recorded in the [Decision Log](DECISIONS.md).

The completed continuation is recorded in [Staged Milestones](STAGED_MILESTONES.md). M1/M3/M4/M5/M6 and M2 Gates 0–3 are complete within their bounded evidence layers. Gate 4 is independently confirmed only for schema-complete/zero-FK signals and remains incomplete for preservation evidence. Product Owner approved preparation of cumulative preservation-only save and private-export evidence briefs; both remain drained pending fresh usage, Designer estimate, and explicit `!run`. Every later gate remains sequential, closed, and unauthorized.

## Deferred

- Full edition management and an immediate title/edition/copy hierarchy.
- Offline operation and generalized media support.
- Business locations.
- Social, lending, and marketplace capabilities.
- Fully autonomous AI changes to canonical data.
