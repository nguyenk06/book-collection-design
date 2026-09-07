# Roadmap

The database-first assessment validated the priority order. Enabling foundations are delivered immediately before their consumer; feature requirements remain in their linked documents.

The canonical future product-shell and presentation direction is [My Library Visual Experience](VISUAL_EXPERIENCE.md). It establishes Library-first navigation and the user-facing Shopkeeper name, but does not change current implementation state, release gates, or execution authority.

## Selected next implementation priority

Product Owner Decision 1:A selected **Phase A — IA and responsive shell**. It is implemented, fully validated, Designer-accepted, saved, and publicly deployed as exact Version 24 checkpoint `4cd6eecd22e1512a87d503a2b5ceb61fdd276269`, composed from Version 23 without importing historical `608553f`. Product Owner visual review on the published Site is the active acceptance gate. Bookcase/detail choices remain deferred to Phase F.

## Phase 0 closure and Phase A entry

1. **Complete — source and comparison:** exact Version 22 source was located and compared with retained historical `608553f1c4d18c191582a3c418fc88a482b97045`; the historical shell/theme/Shopkeeper implementation remains superseded, non-transferable design evidence.
2. **Complete — scanner restoration and release:** the shared local-first Library/Shopkeeper scanner workflow passed its bounded acceptance gates and was saved and published as exact Version 23 at `75075e1e69735ac38c5afdbb7c9b7c55c12a2647`.
3. **Published — Phase A:** exact Version 24 `4cd6eec` makes Library the base/home, preserves the same primary destinations across Library/Shopkeeper and responsive layouts, exposes title/current collection/view/admin/version context, and keeps search in the collection area. Focused 60/60, full 112/112, lint/build/boundary checks, Designer acceptance, save, and public deployment pass. Phase F choices and historical `608553f` remain excluded; Product Owner visual acceptance is pending.

## Ordered additional roadmap

| Order | Workstream | Effort | Current boundary |
| ---: | --- | --- | --- |
| 1 | Reference-cover enrichment | Medium-large | Preserve personal covers; resolve attribution, identifier confidence, source, and fallback behavior before implementation |
| 2 | Asset lifecycle and complete cover backup | Medium-large | **NEEDS MORE INFORMATION** — distinguish metadata/lifecycle work from complete R2-byte backup and recovery guarantees |
| 3 | [Scanner and matching improvements](SCANNER_AND_MATCHING.md) | Medium | Shared exact/equivalent local matching, metadata fallback, and reviewed Library handoff are published in Version 23; later fuzzy, provider, device, and persistent candidate/review improvements remain separately unverified and excluded |
| 4 | [Tags](TAGS.md) | Medium | Persistence and assignment model are absent |
| 5 | [Safe import and restore](IMPORT_EXPORT.md) | Medium-large | Existing import mutates immediately; dry-run, validation, conflict, and recovery contracts are absent |
| 6 | [AI Review](AI_REVIEW.md) | Large | Requires stable interchange, proposal/review staging, and concurrency protection |
| 7 | Expanded administration and analysis | Medium | Owner administration exists for bounded operations; dedicated analysis remains later scope |

None of these ordered items is an executable queue entry or authority to combine workstreams.

## Delivery status

The sequence numbers below are retained historical delivery positions; the selected Phase A priority and ordered additional roadmap above control future planning.

| Historical position | Workstream | Current status | Dependencies | Estimated effort | Known blockers |
| ---: | --- | --- | --- | --- | --- |
| 0 | Database integrity and Shopping persistence foundation | Gate 4 complete within bridge-observable scope | Keep backup/restore guarantees separate; decide local schema remediation only if needed | Medium | Export is not a D1 snapshot, excludes R2 bytes, and does not prove restore readiness |
| 1 | [Shopkeeper / historical Shopping Mode](SHOPPING_MODE.md) | Partial; published in exact Version 23, with Version 21's five-marker evidence retained and scanner continuity restored | Hands-on validation parked until Product Owner reopens it | Medium | Live validation, smoke, correction, later publication, and recovery remain gated |
| 2 | [Scanner and Matching](SCANNER_AND_MATCHING.md) | Shared local-first Library/Shopkeeper restoration accepted and published in exact Version 23 | Keep advanced improvements separately scoped and estimated | Medium | Persistent candidate workflow, fuzzy matching, device/provider claims, and production remain unverified/deferred |
| 3 | [Bookshelf](BOOKSHELF.md) | Corrected Bookcase/Shelf behavior is carried into Version 23; prior anonymous markers remain retained evidence | Hands-on validation parked | Medium | Published but not yet hands-on validated |
| 4 | [Import and Export](IMPORT_EXPORT.md) | Partial; catalog-first export foundation and owner-only downloadable UI are carried into Version 23 | Product Owner checkpoint and safe later import/restore design | Medium-large | Production download untested; no complete backup; import remains unsafe/immediate |
| 5 | [AI Review](AI_REVIEW.md) | Planned | Versioned interchange, review batches/proposals, field comparison, concurrency protection | Large | Stable interchange and review staging absent |
| 6 | Reference cover enrichment | Planned | Minimal asset metadata, personal/reference distinction, attribution, safe identifier match | Medium-large | No asset table; identifier confidence weak; personal covers need protection |
| 7 | [Asset improvements](ASSET_MANAGEMENT.md) | Partial; additional-roadmap item 2 is **NEEDS MORE INFORMATION** | Asset table, variants, cleanup, broken-object fallback, complete cover-byte backup boundary | Medium-large | One image key; missing metadata; orphaned R2 risk; backup and recovery scope unresolved |
| 8 | [Tags](TAGS.md) | Planned | Tag and book-tag assignment tables | Medium | Persistence absent |
| 9 | Analysis and administration | Partial | Purchase data and owner-only administration routes | Medium | Only live KPIs exist; no dedicated administration area |

## Completed foundations

- Published, private single-user application.
- Durable D1 records, R2 cover storage, and SQL migration mechanism.
- Retained historical delivery evidence for collection selection, responsive collection views, and owner-only writes; shared Library/Shopkeeper scanner continuity is restored, validated, saved, and published in exact Version 23.
- Database-first architecture assessment and roadmap validation.
- Collector-first and book-first design direction.

## Immediate milestone

The controlled Shopping release sequence, public version-label quality-of-life goal, and shared scanner restoration remain retained through Version 23. Phase 0 is closed. Phase A is saved and publicly deployed as exact Version 24 `4cd6eec`; Product Owner visual review on the published Site is the active acceptance gate, and no implementation or Site goal is active.

- Retain exact Version 24 at `4cd6eecd22e1512a87d503a2b5ceb61fdd276269` as the authoritative saved and published checkpoint; Versions 21–23 remain retained release/evidence history.
- Preserve the private Gate 2 export and Gate 4 bridge-observable evidence with their documented backup and restore limitations.
- Keep Product Owner hands-on validation and later smoke parked by Decision 1:B.
- Keep every correction, later publication, production/schema/data operation, migration, rollback, restore, and destructive recovery separately gated.
- Treat all later phases and roadmap capabilities as non-executable until phase-specific composition, review, capacity checks, and separate authority. Version 24 carries matching visible/accessibility `v24` labels; any remediation or later release remains separately gated.

Quatre and its direct children Relena and Kira have completed readiness initialization. This activates the Product Owner/Quatre orchestration channel but creates no product, Engineer, Site, or production authority.

Details and migration order are maintained in [Database](DATABASE.md). Accepted choices are recorded in the [Decision Log](DECISIONS.md).

Exact Version 24 at `4cd6eecd22e1512a87d503a2b5ceb61fdd276269` is definitively saved and publicly deployed at the existing public URL with matching `v24` labels and preserved audience. Version 23 remains retained scanner-release history, and Version 21's authorized anonymous correction-marker matches remain evidence for preserved feature behavior. Product Owner Decision 1:B keeps the older hands-on validation parked. The later visual/asset choices remain resolved in their canonical owners and deferred; [Planner Inbox](PLANNER_INBOX.md) has no current decision.

The completed continuation is recorded in [Staged Milestones](STAGED_MILESTONES.md). M1/M3/M4/M5/M6 and M2 Gates 0–5 are complete within their bounded evidence layers and carried into Version 23; the scanner-only Version 23 delta changes M3/entry-point continuity without reopening other milestones. Every later hands-on validation, smoke, correction, release, and recovery gate remains sequential and separately controlled.

## Deferred

- Phase A is published as Version 24 and awaits Product Owner visual acceptance on the public Site. All other My Library phases remain on hold until their prerequisites and explicit authority are satisfied. B/C require storage/routing security feasibility, and G requires an exact deterministic rule/evidence contract; see [Visual Experience](VISUAL_EXPERIENCE.md).
- Full edition management and an immediate title/edition/copy hierarchy.
- Offline operation and generalized media support.
- Business locations.
- Social, lending, and marketplace capabilities.
- Fully autonomous AI changes to canonical data.
