# Current State

**Last reviewed:** 2026-08-04

**Verified implementation:** v16 at commit `ead79e2`

**Assessment:** Database-first architecture review completed 2026-08-03

## Summary

The production application is a stable, private, single-user book tracker. Its Cloudflare D1 and R2 foundation can support the [Roadmap](ROADMAP.md) through additive migrations; a rewrite is not required. The current schema is suitable for the tracker but not sufficient unchanged for purchase history, advanced matching, safe interchange, AI review, reference covers, or tags.

## Current Status Dashboard

| Area | Status | Current state |
| --- | --- | --- |
| Architecture | Partial | Viable D1/R2 foundation; responsibilities must be separated incrementally |
| Database | Partial | Durable records and migrations exist; relationships are not enforced and `books` is overloaded |
| Shopping | Partial | Guidance and basic purchase confirmation exist; purchase persistence does not |
| Scanner | Partial | Live/photo ISBN scanning works; canonical same-book matching is weak |
| Bookshelf | Planned | Collection gallery/list views exist, but the roadmap bookshelf is not implemented |
| Import/Export | Partial | Immediate JSON collection import exists; export, dry run, conflicts, and backups do not |
| AI Review | Planned | No review batches, proposals, or safe interchange workflow |
| Assets | Partial | Personal cover upload and R2 serving exist; metadata, variants, and cleanup do not |
| Tags | Planned | No tag or assignment persistence |
| Analysis | Partial | Live KPIs exist; no dedicated analysis or administration area |

## Architecture maturity

- The deployed architecture uses Cloudflare D1 for structured records and R2 for cover bytes.
- Drizzle schemas and SQL migrations provide an incremental migration path.
- Owner-authorized mutations, responsive views, and product tests form a usable baseline.
- The architecture should evolve additively by preserving existing identities and moving distinct responsibilities out of `books`.
- Full title/edition/copy modeling is intentionally not required for the current roadmap.

See [Database](DATABASE.md) for verified schema details and accepted migration direction.

## Implementation maturity

The application is published and useful for current collection tracking. It supports collection selection, search, ISBN scanning, ownership and buying-state presentation, copy counts, expected CYOA positions, personal cover upload, collection import, and live KPIs. Several future workflows have interface foundations but lack the relational persistence and integrity needed for reliable expansion.

## Current strengths

- Durable D1 records and R2 cover storage.
- Stable numeric book IDs and durable collection keys.
- Live and photo-based barcode scanning with ISBN validation.
- Custom collections, search, responsive gallery/list views, and query restoration.
- Owner-only writes and save rollback tests.
- Personal guidance, copy counts, basic purchase confirmation, and CYOA expected positions.
- Existing architecture can be migrated without destructive reinterpretation.

## Current weaknesses

- `books` combines catalog, edition, ownership, copies, reading, shopping, and cover responsibilities.
- No database foreign keys are declared.
- One ISBN and one image key cannot represent alternate identifiers or asset provenance safely.
- Import writes immediately with limited validation; no export or backup workflow exists.
- Broad PATCH operations have no expected-revision concurrency check.
- Schema checks and catalog updates run during ordinary books GET requests.
- Client behavior is concentrated in one large page component, with outstanding lint issues.

## Highest risks

| Risk | Impact |
| --- | --- |
| Unenforced collection relationship | Orphaned books can be created by direct changes, restores, or future imports |
| Overloaded book record | Ownership, buying status, copy count, and identifiers can contradict one another |
| Missing stable external identity | Safe restore, cross-database import, and AI review interchange are blocked |
| Immediate imports without dry run | Conflicts or unintended writes are difficult to detect before mutation |
| Weak identifier matching | Reprint identifiers can overwrite the single ISBN or create false matches |
| Incomplete asset lifecycle | Replaced R2 objects can become unused; source and attribution are absent |

## Current production capabilities

- Collection selection, custom collections, search, filters, and responsive views.
- Live and photo-based barcode scanning and basic ISBN validation.
- Owned, Missing/Need, and Wishlist presentation with aggregate copy counts.
- Personal guidance and basic purchase confirmation.
- CYOA expected catalog positions.
- Personal cover upload, R2 storage, and cover rendering.
- Gallery and list views.
- JSON collection import.
- Live collection KPIs.
- Owner-authorized mutations, query restoration, and save rollback tests.

## Current known limitations

- No purchases, businesses, condition history, price history, or collection target-price persistence.
- No advanced same-book candidate workflow or multiple normalized identifiers.
- No roadmap bookshelf, exports, backups, or dry-run imports.
- No stable external IDs, record revisions, review batches, or proposals.
- No reference-cover enrichment, asset metadata, tags, or dedicated administration area.
- Uploaded cover replacement can leave unused R2 objects; cover upload also marks a book Owned.
- Server ISBN validation does not verify checksums, and some filters are not persisted.

## Next milestone

Implement the database integrity and Shopping Mode persistence foundation described in [Database](DATABASE.md), before redesigning Shopping Mode UI. The full sequence and blockers are maintained in the [Roadmap](ROADMAP.md).
