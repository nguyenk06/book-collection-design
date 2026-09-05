# Roadmap

The database-first assessment validated the priority order. Enabling foundations are delivered immediately before their consumer; feature requirements remain in their linked documents.

The canonical future product-shell and presentation direction is [My Library Visual Experience](VISUAL_EXPERIENCE.md). It establishes Library-first navigation and the user-facing Shopkeeper name, but does not change current implementation state, release gates, or execution authority.

## Status

| Priority | Workstream | Current status | Dependencies | Estimated effort | Known blockers |
| ---: | --- | --- | --- | --- | --- |
| 0 | Database integrity and Shopping persistence foundation | Gate 4 complete within bridge-observable scope | Keep backup/restore guarantees separate; decide local schema remediation only if needed | Medium | Export is not a D1 snapshot, excludes R2 bytes, and does not prove restore readiness |
| 1 | [Shopkeeper / historical Shopping Mode](SHOPPING_MODE.md) | Partial; exact Version 21 published and all five anonymous correction markers match | Hands-on validation parked until Product Owner reopens it | Medium | Live validation, smoke, correction, later publication, and recovery remain gated |
| 2 | [Scanner and Matching](SCANNER_AND_MATCHING.md) | Partial; canonical identifier foundation complete locally | Future candidate workflow and user-facing matching | Medium | Production unchanged; fuzzy candidate matching deferred |
| 3 | [Bookshelf](BOOKSHELF.md) | Corrected Bookcase/Shelf release published in Version 21; anonymous markers match | Hands-on validation parked | Medium | Published but not yet hands-on validated |
| 4 | [Import and Export](IMPORT_EXPORT.md) | Partial; catalog-first export foundation and owner-only downloadable UI carried into Version 21 | Product Owner checkpoint and safe later import/restore design | Medium-large | Production download untested; no complete backup; import remains unsafe/immediate |
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

The controlled Shopping release sequence in ADR-0012 is complete through exact Version 21 publication and the five authorized anonymous marker matches. No release continuation or corrective implementation goal is active.

- Retain exact Version 21 at `f15ea81` as the authoritative saved and published checkpoint.
- Preserve the private Gate 2 export and Gate 4 bridge-observable evidence with their documented backup and restore limitations.
- Keep Product Owner hands-on validation and later smoke parked by Decision 1:B.
- Keep every correction, later publication, production/schema/data operation, migration, rollback, restore, and destructive recovery separately gated.
- Treat all future roadmap capabilities as non-executable until Quatre selects and transmits one bounded completion-oriented goal.

Quatre and its direct children Relena and Kira have completed readiness initialization. This activates the Product Owner/Quatre orchestration channel but creates no product, Engineer, Site, or production authority.

Details and migration order are maintained in [Database](DATABASE.md). Accepted choices are recorded in the [Decision Log](DECISIONS.md).

Exact Version 21 at `f15ea81` is definitively published and its five authorized anonymous correction markers match. Product Owner Decision 1:B keeps hands-on validation parked; [Planner Inbox](PLANNER_INBOX.md) currently has no unresolved decision.

The completed continuation is recorded in [Staged Milestones](STAGED_MILESTONES.md). M1/M3/M4/M5/M6 and M2 Gates 0–5 are complete within their bounded evidence layers. Version 21 is now published; every later hands-on validation, smoke, correction, and recovery gate remains sequential and separately controlled.

## Deferred

- Phased My Library visual redesign after Sei's accepted source-informed estimate; each phase remains on hold until its prerequisites and later explicit authority are satisfied. B/C require storage/routing security feasibility, and G requires an exact deterministic rule/evidence contract; see [Visual Experience](VISUAL_EXPERIENCE.md).
- Full edition management and an immediate title/edition/copy hierarchy.
- Offline operation and generalized media support.
- Business locations.
- Social, lending, and marketplace capabilities.
- Fully autonomous AI changes to canonical data.
