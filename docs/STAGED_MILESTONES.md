# Staged Milestone Sequence

**Reviewed:** 2026-09-14

Milestones are independently reviewable and do not bundle implementation, Site save, publication, production access, or recovery authority.

## Completed sequence

| Milestone | State |
| --- | --- |
| Phase 0 — source, workflow, and scanner baseline | Closed |
| Phase A — Library-first responsive shell | Accepted from public Version 24 |
| Aggregate My Library correction | Published from Version 25 |
| Main-page scanner restoration | Accepted in public Version 30; live retry stability note retained |
| Shopkeeper scanner parity and visual cleanup | Published in Version 31; further work shelved by Product Owner |
| M1 — Shopping validation feasibility | Complete within recorded boundary |
| M2 — controlled Shopping release and schema gates | Complete within recorded bridge-observable boundary |
| M3 — canonical Book identifiers | Complete for exact/equivalent ISBN resolution |
| M4 — bounded Bookshelf | Implemented; later Phase F visual refinements remain held |
| M5 — export-first portability foundation | Complete |
| M6 — downloadable catalog export UI | Complete and published; broader restore is not established |

Historical evidence and exact prior release details remain in the [Changelog](CHANGELOG.md).

## Milestone 7 — enrichment foundation

**State:** Foundation complete; first visible consumers published in Version 32.

- Reconcile current documentation through accepted Version 30.
- Test the known ISBN metadata and stored-cover retrieval contracts.
- Define a provider-neutral evidence boundary shared by ISBN and reference-cover consumers.
- Preserve personal covers, local canonical identity, no-result/manual fallback, source attribution, and no-mutation behavior.
- Treat tags only as a possible future consumer of provider suggestions.

The initial test-only checkpoint remains in history. Its provider/evidence boundary now underpins the bounded ISBN and reference-cover presentation published in exact Version 32 source `802db5fd9c54c79e4897cc12de86b875163f6c07`. The public consumer preserves local-first matching, attribution, personal-cover precedence, manual fallback, and no automatic persistence.

## Milestone 7A — Shopkeeper parity release

**State:** Published as Version 31; further parity and visual review shelved by Product Owner.

- Preserve Shopkeeper as a compact, non-mutating quick-check surface.
- Match Library scanner outcomes for duplicates, probable ISBN-less matches, conflicts, new metadata, unavailable metadata, and manual review.
- Add live retail-UPC printed-text recognition and explicit retry.
- Add uploaded-photo barcode preprocessing and OCR fallback.
- Keep all Book creation and editing in Library.

The implementation passed 15/15 focused Shopkeeper checks, 161/161 full application checks, 37/37 focused release-identity checks, lint, and a production build. Exact public source is `d9d83bb4c964c2de9af8c0affdcb1a44ed5e6792`.

## Milestone 8A — reference-cover enrichment

**State:** First bounded consumer published in Version 32.

- Select approved no-cost sources.
- Define candidate confidence, attribution, personal/reference distinction, fallback, and storage/caching limits.
- Keep remote candidates read-only until the owner explicitly chooses a cover or an approved policy exists.
- Do not claim complete backup or recovery from metadata or cached references.

## Milestone 8B — ISBN metadata enrichment

**State:** First bounded consumer published in Version 32.

- Add approved fallback evidence for valid ISBNs that lack useful current metadata.
- Normalize but do not silently merge conflicting titles, authors, editions, dates, or subjects.
- Keep exact/equivalent local Library matching ahead of provider lookup.
- Preserve manual entry when all sources fail.

## Milestone 8C — tag discovery

**State:** Planned discovery only.

- Evaluate provider subjects/categories for usefulness and noise.
- Define canonical tag vocabulary, provenance, assignment, removal, and owner control separately.
- Do not turn provider categories into stored tags by default.

## Milestone 9 — asset lifecycle and complete cover backup

**State:** Requirements boundary accepted as 1:A + 2:A; no feasibility run or implementation is active.

The durable contract is [Asset Management — Milestone 9 requirements contract](ASSET_MANAGEMENT.md#milestone-9-requirements-contract). The recommended package is a downloadable versioned ZIP containing a manifest and the selected scope of personal stored-cover bytes. It records hashes, media types, byte sizes, and stable Book associations; reports missing, orphaned, and duplicate objects; never deletes source objects; and requires a read-only dry run plus independent archive verification. Remote Open Library images remain replaceable references, not backed-up personal assets. Restore is a separate later milestone and authority gate.

The accepted scope includes all accessible personal cover objects, including separately classified orphans, and uses owner-download-only delivery with no server-retained backup history. Entry to the next step requires a fresh capacity check and separate authorization of a bounded read-only feasibility goal. Stop if required objects cannot be enumerated safely, stable associations cannot be proven, the ZIP exceeds supported runtime limits, or any production write, cleanup, schema change, restore, or destructive action appears necessary.

## Later milestones

1. Tags implementation.
2. Safe import and restore.
3. AI Review.
4. Expanded administration and analysis.
5. Phase F visual refinements after Product Owner review.

## Shared controls

- Quatre is the sole Product Owner interface and Site owner.
- Relena owns product contract and release-boundary review; Kira is the sole application writer when activated.
- Planning, fixtures, and review may run in parallel; application-source writing does not.
- Validate each slice independently and name its included/excluded boundaries.
- Check account capacity before each project or large milestone and preserve the established five-hour and weekly floors.
- Publication, production access, migration, restore, rollback, and destructive cleanup always require their own authority.
