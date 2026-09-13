# Roadmap

The roadmap is ordered by Product Owner priority. A roadmap position is planning direction, not implementation or publication authority.

## Current baseline

Version 30 at `67cd49da54f55d5e03a3a3b75b55f58e8eba3fd6` is the accepted saved and public baseline. Phase 0 is closed, the Library-first Phase A shell is accepted, and the main-page scanner restoration cycle is complete with a retained live-capture stability note.

## Ordered additional roadmap

| Order | Workstream | Effort | Entry condition |
| ---: | --- | --- | --- |
| 1 | Reference-cover enrichment | Medium-large | Protect personal covers; define source, attribution, identifier confidence, fallback, and storage behavior |
| 2 | Asset lifecycle and complete cover backup | Medium-large | **NEEDS MORE INFORMATION** — define byte coverage, integrity, retention, orphan cleanup, and recovery guarantees |
| 3 | [Scanner and matching improvements](SCANNER_AND_MATCHING.md) | Medium | Begin with ISBN metadata enrichment; keep local exact/equivalent matching authoritative and provider evidence reviewable |
| 4 | [Tags](TAGS.md) | Medium | Define tag vocabulary, provenance, assignment, removal, and persistence; provider categories are suggestions only |
| 5 | [Safe import and restore](IMPORT_EXPORT.md) | Medium-large | Add dry-run, validation, conflict handling, rollback/recovery, and explicit confirmation |
| 6 | [AI Review](AI_REVIEW.md) | Large | Requires stable interchange, proposals, comparison, approval, and concurrency protection |
| 7 | Expanded administration and analysis | Medium | Extend owner tools only after the underlying records and evidence are stable |

## Enrichment composition

Reference-cover enrichment and ISBN metadata enrichment may proceed as parallel design and test lanes over a shared read-only provider boundary. They remain independently promotable:

- ISBN enrichment returns normalized bibliographic evidence and source/provenance.
- Cover enrichment returns reference-image candidates and source/provenance without replacing personal covers.
- Tags may inspect the same provider responses, but provider subjects/categories remain suggestions until the separate tag model and owner workflow are approved.
- One application-source writer remains active at a time even when planning, research, fixtures, or review run in parallel.
- A provider must be no-cost for the approved use, fit Sites runtime/space limits, degrade safely, and avoid making the application dependent on a single response.

See [Enrichment Foundation](ENRICHMENT_FOUNDATION.md) for the first bounded contract.

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

## Release rule

Implementation, Site save, publication, production access, migration, recovery, and destructive actions remain separate gates. Quatre alone performs Site operations after explicit Product Owner authorization and validated Kira/Relena release evidence.
