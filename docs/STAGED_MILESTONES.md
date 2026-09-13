# Staged Milestone Sequence

**Reviewed:** 2026-09-12

Milestones are independently reviewable and do not bundle implementation, Site save, publication, production access, or recovery authority.

## Completed sequence

| Milestone | State |
| --- | --- |
| Phase 0 — source, workflow, and scanner baseline | Closed |
| Phase A — Library-first responsive shell | Accepted from public Version 24 |
| Aggregate My Library correction | Published from Version 25 |
| Main-page scanner restoration | Accepted in public Version 30; live retry stability note retained |
| M1 — Shopping validation feasibility | Complete within recorded boundary |
| M2 — controlled Shopping release and schema gates | Complete within recorded bridge-observable boundary |
| M3 — canonical Book identifiers | Complete for exact/equivalent ISBN resolution |
| M4 — bounded Bookshelf | Implemented; later Phase F visual refinements remain held |
| M5 — export-first portability foundation | Complete |
| M6 — downloadable catalog export UI | Complete and published; broader restore is not established |

Historical evidence and exact prior release details remain in the [Changelog](CHANGELOG.md).

## Milestone 7 — enrichment foundation

**State:** Complete locally; no product behavior change.

- Reconcile current documentation through accepted Version 30.
- Test the known ISBN metadata and stored-cover retrieval contracts.
- Define a provider-neutral evidence boundary shared by ISBN and reference-cover consumers.
- Preserve personal covers, local canonical identity, no-result/manual fallback, source attribution, and no-mutation behavior.
- Treat tags only as a possible future consumer of provider suggestions.

Focused endpoint tests pass 7/7 and the full application suite passes 159/159. Test-only source checkpoint `d3a39e346065a866271a12682f66941ce863d144` is pushed. Documentation links are reconciled, and no Site version or production state changed.

## Milestone 8A — reference-cover enrichment

**State:** Planned; first ordered feature workstream.

- Select approved no-cost sources.
- Define candidate confidence, attribution, personal/reference distinction, fallback, and storage/caching limits.
- Keep remote candidates read-only until the owner explicitly chooses a cover or an approved policy exists.
- Do not claim complete backup or recovery from metadata or cached references.

## Milestone 8B — ISBN metadata enrichment

**State:** Planned; may run alongside 8A in design, fixture, and review work.

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

**State:** `NEEDS MORE INFORMATION`.

Before implementation, define inventory scope, R2 byte inclusion, integrity verification, personal/reference retention, orphan cleanup, restore order, failure handling, and the exact recovery claim.

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
