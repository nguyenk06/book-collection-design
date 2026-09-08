# Roadmap

The database-first assessment validated the priority order. Enabling foundations are delivered immediately before their consumer; feature requirements remain in their linked documents.

The canonical future product-shell and presentation direction is [My Library Visual Experience](VISUAL_EXPERIENCE.md). It establishes Library-first navigation and the user-facing Shopkeeper name, but does not change current implementation state, release gates, or execution authority.

## Selected next implementation priority

Product Owner Decision 1:A selected **Phase A — IA and responsive shell**. Its shell/navigation/header/view presentation is Product Owner-accepted on exact published Version 24 `4cd6eecd22e1512a87d503a2b5ceb61fdd276269`. The bounded scanner and aggregate-Library corrective phase is locally complete and Designer-accepted at exact unpublished `44a853f7430f92da37bf1c9cdef37bdfe2a6c7b2`; publication is the next separate Product Owner approval boundary. Cover loading, collection reordering, and Phase F remain later work.

## Phase 0 closure and Phase A entry

1. **Complete — source and comparison:** exact Version 22 source was located and compared with retained historical `608553f1c4d18c191582a3c418fc88a482b97045`; the historical shell/theme/Shopkeeper implementation remains superseded, non-transferable design evidence.
2. **Locally corrected; publication pending — scanner restoration:** Version 24 retains the failed public hands-on behavior; local commit `41ca4fc` restores shared reactive Library/Shopkeeper resolution, and corrective HEAD `44a853f` closes late-result race findings. Focused 61/61, full 118/118, build/lint/diff, and Relena release-boundary review pass.
3. **Published shell accepted; aggregate locally corrected — Phase A:** exact Version 24 `4cd6eec` retains the accepted responsive shell. Local `44a853f` makes My Library the aggregate base home with current collection grouping, deterministic within-group order, `Unassigned` last, and an add-target selector. Publication and public acceptance remain separate; Phase F and historical `608553f` remain excluded.

## Ordered additional roadmap

| Order | Workstream | Effort | Current boundary |
| ---: | --- | --- | --- |
| 1 | Reference-cover enrichment | Medium-large | Preserve personal covers; resolve attribution, identifier confidence, source, and fallback behavior before implementation |
| 2 | Asset lifecycle and complete cover backup | Medium-large | **NEEDS MORE INFORMATION** — distinguish metadata/lifecycle work from complete R2-byte backup and recovery guarantees |
| 3 | [Scanner and matching improvements](SCANNER_AND_MATCHING.md) | Medium | Bounded shared exact/equivalent local-first correction is locally complete at `44a853f`; publication/public acceptance and later fuzzy, provider, device, or persistent-review expansion remain separately gated |
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
| 1 | [Shopkeeper / historical Shopping Mode](SHOPPING_MODE.md) | Version 24 remains public; compact shared-resolver handoff is locally corrected at `44a853f` | Product Owner publication decision, then separately gated public acceptance | Medium | Production, broad smoke, and recovery remain gated |
| 2 | [Scanner and Matching](SCANNER_AND_MATCHING.md) | Corrective workflow locally complete and Relena-accepted at `44a853f`; public Version 24 remains unchanged | Product Owner publication decision | Medium | Protected changes remain excluded; fuzzy/provider/device/persistent expansion remains deferred |
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
- Retained historical delivery evidence for collection selection, responsive collection views, and owner-only writes; Version 24 preserves the failed scanner hands-on baseline, while exact local `44a853f` contains the release-ready correction.
- Database-first architecture assessment and roadmap validation.
- Collector-first and book-first design direction.

## Immediate milestone

The controlled Shopping release sequence and public version-label quality-of-life goal remain retained. Phase A shell presentation is accepted on exact published Version 24 `4cd6eec`. Scanner and aggregate-Library corrective work is locally complete at exact `44a853f`; Product Owner approval of the separate publication boundary is the immediate milestone. No Site goal is active without that authority.

- Retain exact Version 24 at `4cd6eecd22e1512a87d503a2b5ceb61fdd276269` as the authoritative saved and published checkpoint; Versions 21–23 remain retained release/evidence history.
- Preserve the private Gate 2 export and Gate 4 bridge-observable evidence with their documented backup and restore limitations.
- Keep the older Version 21 hands-on validation and later broad smoke parked by Decision 1:B; this does not supersede the new Version 24 scanner finding.
- Keep every correction, later publication, production/schema/data operation, migration, rollback, restore, and destructive recovery separately gated.
- Treat all later phases and roadmap capabilities as non-executable until phase-specific composition, review, capacity checks, and separate authority. Version 24 carries matching visible/accessibility `v24` labels; any remediation or later release remains separately gated.

Quatre and its direct children Relena and Kira have completed readiness initialization. This activates the Product Owner/Quatre orchestration channel but creates no product, Engineer, Site, or production authority.

Details and migration order are maintained in [Database](DATABASE.md). Accepted choices are recorded in the [Decision Log](DECISIONS.md).

Exact Version 24 at `4cd6eecd22e1512a87d503a2b5ceb61fdd276269` is definitively saved and publicly deployed at the existing public URL with matching `v24` labels and preserved audience. Version 23 remains retained scanner-release history, and Version 21's authorized anonymous correction-marker matches remain evidence for preserved feature behavior. Product Owner Decision 1:B keeps the older hands-on validation parked. The later visual/asset choices remain resolved in their canonical owners and deferred; [Planner Inbox](PLANNER_INBOX.md) has no current decision.

The completed continuation is recorded in [Staged Milestones](STAGED_MILESTONES.md). M1/M4/M5/M6 and M2 Gates 0–5 remain complete within their bounded evidence layers. M3's bounded correction is locally complete at `44a853f`; publication and public hands-on acceptance remain open. Every release and recovery gate remains sequential and separately controlled.

## Deferred

- Phase A shell presentation is published and Product Owner-accepted on Version 24; its My Library aggregate correction is locally complete at `44a853f` but unpublished. All other My Library phases remain on hold until their prerequisites and explicit authority are satisfied. B/C require storage/routing security feasibility, and G requires an exact deterministic rule/evidence contract; see [Visual Experience](VISUAL_EXPERIENCE.md).
- Full edition management and an immediate title/edition/copy hierarchy.
- Offline operation and generalized media support.
- Business locations.
- Social, lending, and marketplace capabilities.
- Fully autonomous AI changes to canonical data.
