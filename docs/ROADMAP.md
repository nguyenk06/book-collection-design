# Roadmap

The roadmap is ordered by Product Owner priority. A roadmap position is planning direction, not implementation or publication authority.

## Current baseline

Version 32 at `802db5fd9c54c79e4897cc12de86b875163f6c07` is the exact saved and public baseline. Phase 0 is closed, the Library-first shell and main-page scanner are accepted, and the first bounded ISBN/reference-cover enrichment consumer is public. Library is canonical for scan, review, add, and edit. Shopkeeper remains available but is shelved as an active workstream unless the Product Owner explicitly reopens it.

## Ordered remaining roadmap

| Order | Workstream | Effort | Entry condition |
| ---: | --- | --- | --- |
| 1 | [M9 — asset lifecycle and complete cover backup](ASSET_MANAGEMENT.md#milestone-9-requirements-contract) | Medium-large | Scope is accepted as all accessible personal covers plus owner-download-only delivery; next prove read-only inventory and ZIP feasibility; restore remains separate |
| 2 | [Tags](TAGS.md) | Medium | Define tag vocabulary, provenance, assignment, removal, and persistence; provider categories are suggestions only |
| 3 | [Safe import and restore](IMPORT_EXPORT.md) | Medium-large | Add dry-run, validation, conflict handling, rollback/recovery, and explicit confirmation after a verified backup format exists |
| 4 | [AI Review](AI_REVIEW.md) | Large | Requires stable interchange, proposals, comparison, approval, and concurrency protection |
| 5 | Expanded administration and analysis | Medium | Extend owner tools only after the underlying records and evidence are stable |

## Enrichment composition

Reference-cover enrichment and ISBN metadata enrichment may proceed as parallel design and test lanes over a shared read-only provider boundary. They remain independently promotable:

- ISBN enrichment returns normalized bibliographic evidence and source/provenance.
- Cover enrichment returns reference-image candidates and source/provenance without replacing personal covers.
- Tags may inspect the same provider responses, but provider subjects/categories remain suggestions until the separate tag model and owner workflow are approved.
- One application-source writer remains active at a time even when planning, research, fixtures, or review run in parallel.
- A provider must be no-cost for the approved use, fit Sites runtime/space limits, degrade safely, and avoid making the application dependent on a single response.

See [Enrichment Foundation](ENRICHMENT_FOUNDATION.md) for the first bounded contract.

Reference-cover and ISBN enrichment are complete through their first public Version 32 consumer. Scanner/matching changes are maintenance-only unless new Library evidence opens a bounded correction. Neither completed enrichment nor shelved Shopkeeper work consumes a current roadmap position.

## Advance decision forecast

The independent choices that can be resolved before implementation are maintained in [Planner Inbox](PLANNER_INBOX.md): initial tag intake, first tag attachment scope, initial safe-import format, AI Review submission boundary, and first expanded-administration focus. Decisions that require M9 runtime evidence or Phase F visual proposals remain intentionally deferred until those inputs exist.

## Phase F visual backlog

These items wait for Product Owner visual review before implementation:

- Denser Bookcase presentation with more visible spines.
- Useful cover loading in Book detail while preserving a safe fallback.
- Book titles, not only `Missing`, on Shelf gaps.
- Any later homepage personalization or broader visual change.

Category-based shelves and bookcases are retained. The intended aggregate view is one Library organized by collection, then series/index and author/title. Future collection reordering may add an owner-controlled collection order without removing category views.

## Completed foundations

- Durable single-user Library with D1 records and R2 personal-cover storage.
- Owner-gated administration and write paths.
- Canonical ISBN normalization/equivalence and Library-wide scanner resolution.
- Library-first responsive shell, aggregate My Library behavior, Bookcase/Shelf views, and public release identity.
- Versioned catalog export foundation and owner-only download surface.
- Main-page photo/manual/live scanner restoration accepted in Version 30.
- First bounded ISBN metadata and remote Open Library reference-cover enrichment published in Version 32.

## Release rule

Implementation, Site save, publication, production access, migration, recovery, and destructive actions remain separate gates. Quatre alone performs Site operations after explicit Product Owner authorization and validated Kira/Relena release evidence.
