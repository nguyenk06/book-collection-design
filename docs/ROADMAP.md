# Roadmap

The database-first assessment validated the priority order. Enabling foundations are delivered immediately before their consumer; feature requirements remain in their linked documents.

The canonical future product-shell and presentation direction is [My Library Visual Experience](VISUAL_EXPERIENCE.md). It establishes Library-first navigation and the user-facing Shopkeeper name, but does not change current implementation state, release gates, or execution authority.

## Status

| Priority | Workstream | Current status | Dependencies | Estimated effort | Known blockers |
| ---: | --- | --- | --- | --- | --- |
| 0 | Database integrity and Shopping persistence foundation | Gate 4 complete within bridge-observable scope | Keep backup/restore guarantees separate; decide local schema remediation only if needed | Medium | Export is not a D1 snapshot, excludes R2 bytes, and does not prove restore readiness |
| 1 | [Shopkeeper / historical Shopping Mode](SHOPPING_MODE.md) | Partial; local Shopping UI complete; Gate 4 complete; future Shopkeeper redesign documented | Separately approved Shopping publication and live validation/smoke | Medium-large | Every later production and validation gate remains closed |
| 2 | [Scanner and Matching](SCANNER_AND_MATCHING.md) | Partial; canonical identifier foundation complete locally | Future candidate workflow and user-facing matching | Medium | Production unchanged; fuzzy candidate matching deferred |
| 3 | [Bookshelf](BOOKSHELF.md) | Bounded first release complete locally and preserved in unpublished Version 20; user checkpoint pending | Safe validation environment and Product Owner outcome before activation | Medium | No runnable unpublished preview; checkpoint environment blocked |
| 4 | [Import and Export](IMPORT_EXPORT.md) | Partial; catalog-first export foundation and owner-only downloadable UI preserved in unpublished Version 20 | Product Owner checkpoint and separately gated activation | Medium-large | No production catalog export or complete backup; import remains unsafe/immediate |
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
- Treat the Gate 3 immediate activation response as distinct from Gate 4's later independent verification and supplemental export comparison.
- Keep Gate 4 verification and Shopping publication independently approved and evidenced.
- Run the desktop/mobile checklist and post-publication smoke review on the live Site.

Saving Version 17 does not mark Shopping released or active in production. Version 19 administration is published, Gate 3 reported activation success, and Gate 4 independently confirmed schema-complete/zero-FK status plus bridge-observable preservation invariants; final Shopping publication remains a separate closed gate.

Details and migration order are maintained in [Database](DATABASE.md). Accepted choices are recorded in the [Decision Log](DECISIONS.md).

The completed continuation is recorded in [Staged Milestones](STAGED_MILESTONES.md). M1/M3/M4/M5/M6 and M2 Gates 0–4 are complete within their bounded evidence layers. Unpublished, undeployed Version 20 preserves the exact validated cumulative candidate. Every later gate remains sequential, closed, and unauthorized.

## Deferred

- Phased My Library visual redesign after Sei's accepted source-informed estimate; each phase remains on hold until its prerequisites and later explicit authority are satisfied. B/C require storage/routing security feasibility, and G requires an exact deterministic rule/evidence contract; see [Visual Experience](VISUAL_EXPERIENCE.md).
- Full edition management and an immediate title/edition/copy hierarchy.
- Offline operation and generalized media support.
- Business locations.
- Social, lending, and marketplace capabilities.
- Fully autonomous AI changes to canonical data.
