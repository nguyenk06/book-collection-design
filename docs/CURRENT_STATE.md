# Current State

**Last reviewed:** 2026-08-08

**Verified production implementation:** Site Version 16

**Verified local implementation:** Shopping persistence/API foundation; validated locally, not saved as a Site version, migrated to production, or published

**Assessment:** Database-first architecture review completed 2026-08-03

## Summary

The production application remains a stable, private, single-user book tracker on Site Version 16. A locally implemented Shopping persistence/API foundation has been validated but has not been saved in Site version history, migrated to production, or published. Its additive approach remains compatible with the [Roadmap](ROADMAP.md); a rewrite is not required.

## Current Status Dashboard

| Area | Status | Current state |
| --- | --- | --- |
| Architecture | Partial | Viable D1/R2 foundation; responsibilities must be separated incrementally |
| Database | Partial | Local additive schema and migration validation cover Businesses, Purchases, target price, and Added Date; production remains on the v16 schema and the book-to-collection relationship is not enforced |
| Shopping | Partial | Persistence and owner-authorized APIs are locally validated but unsaved and unpublished; Shopping UI remains unchanged |
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

The published application remains useful for current collection tracking. It supports collection selection, search, ISBN scanning, ownership and buying-state presentation, copy counts, expected CYOA positions, personal cover upload, collection import, and live KPIs.

The local Site working copy additionally contains validated Business and Purchase persistence, collection target price, nullable Book Added Date, and owner-authorized Business/Purchase APIs. This work is not a saved Site version or a production capability. No Shopping Mode UI was added, and Purchase creation does not alter Book ownership or copy counts.

### Locally validated Shopping foundation

- Businesses use cleaned display names and unique normalized names.
- Purchases preserve transaction history separately from Book identity, ownership, and copy counts.
- Purchase and sticker prices use independent, nullable, non-negative integer cents.
- Purchase condition is limited to New, Like New, Very Good, Good, Fair, Poor, or Unknown.
- Collection target price is nullable; the CYOA target is 600 cents in the local migration.
- Existing Books retain unknown Added Dates as `NULL`; newly created or imported Books receive an Added Date.
- Local migration tests preserved Book IDs, collection keys, records, ownership, copies, ISBNs, cover references, and timestamps.
- Focused tests and the local production build pass. Full-project lint retains unrelated pre-existing failures.

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

- Production has no Businesses, Purchases, condition history, price history, collection target price, or Added Date migration.
- The locally validated Shopping foundation is not saved in Site version history or published.
- Production migration, rollback, and production behavior remain unverified.
- The book-to-collection foreign key and historical Added Date backfill remain deferred; unknown historical dates must not be fabricated.
- No advanced same-book candidate workflow or multiple normalized identifiers.
- No roadmap bookshelf, exports, backups, or dry-run imports.
- No stable external IDs, record revisions, review batches, or proposals.
- No reference-cover enrichment, asset metadata, tags, or dedicated administration area.
- Uploaded cover replacement can leave unused R2 objects; cover upload also marks a book Owned.
- Server ISBN validation does not verify checksums, and some filters are not persisted.

## Next milestone

Save the locally validated Shopping persistence/API foundation as a Site version, complete production migration and rollback planning, and retain explicit approval gates before migration or publication. The full sequence and blockers are maintained in the [Roadmap](ROADMAP.md).
