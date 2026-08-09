# Current State

**Last reviewed:** 2026-08-08

**Verified production implementation:** Site Version 16

**Verified saved implementation:** Shopping persistence/API foundation in unpublished Site Version 17; not migrated to production or published

**Assessment:** Database-first architecture review completed 2026-08-03

**Production migration investigation:** Completed 2026-08-08; no production access or change performed

**Production execution planning:** Complete; Packet A backup gate authorized after private readiness confirmation, not yet executed

## Summary

The production application remains a stable, private, single-user book tracker on Site Version 16. The validated Shopping persistence/API foundation is preserved in Site version history as unpublished Version 17 but has not been migrated to production or published. Its additive approach remains compatible with the [Roadmap](ROADMAP.md); a rewrite is not required.

The read-only migration investigation found no public Sites contract establishing when packaged D1 migrations execute or whether migration success gates production traffic. The accepted operational direction is therefore to prepare an operator-controlled D1 migration, not publish Version 17 or wait indefinitely for undocumented Sites behavior.

The operator runbook and independent approval packets are complete. Planner authorized Packet A for production target verification, read-only preflight, current Time Travel bookmark retrieval, protected SQL export, and a maintenance/write freeze only after the operator, verifier, window, secure storage, retention, freeze method, and abort authority are confirmed privately. No Packet A operation has occurred.

## Current Status Dashboard

| Area | Status | Current state |
| --- | --- | --- |
| Architecture | Partial | Viable D1/R2 foundation; responsibilities must be separated incrementally |
| Database | Partial | Version 17 packages the locally validated additive migration for Businesses, Purchases, target price, and Added Date; production remains on the v16 schema and the book-to-collection relationship is not enforced |
| Shopping | Partial | Persistence and owner-authorized APIs are saved in unpublished Version 17; production and Shopping UI remain unchanged |
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

Unpublished Site Version 17 preserves validated Business and Purchase persistence, collection target price, nullable Book Added Date, and owner-authorized Business/Purchase APIs. It is not a production capability: saving the version did not run the packaged migration or deploy the Site. No Shopping Mode UI was added, and Purchase creation does not alter Book ownership or copy counts.

### Saved, unpublished Shopping foundation

- Businesses use cleaned display names and unique normalized names.
- Purchases preserve transaction history separately from Book identity, ownership, and copy counts.
- Purchase and sticker prices use independent, nullable, non-negative integer cents.
- Purchase condition is limited to New, Like New, Very Good, Good, Fair, Poor, or Unknown.
- Collection target price is nullable; the CYOA target is 600 cents in the local migration.
- Existing Books retain unknown Added Dates as `NULL`; newly created or imported Books receive an Added Date.
- Local migration tests preserved Book IDs, collection keys, records, ownership, copies, ISBNs, cover references, and timestamps.
- Focused tests and the local production build pass. Full-project lint retains unrelated pre-existing failures.
- Version 17 references the exact validated source state and contains the Shopping migration in its saved package.

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
- Version 17 is saved but unpublished; Version 16 remains live.
- Production migration, rollback, and production behavior remain unverified.
- Sites migration trigger, executor, tracking, retry behavior, atomicity, and traffic sequencing remain unknown from public documentation.
- Raw migration `0004` applies once locally but is not directly idempotent; safe execution depends on the D1 migration ledger and controlled operator sequencing.
- The production D1 target, access, migration ledger, Time Travel eligibility, and backup artifacts remain unverified until Packet A executes.
- The book-to-collection foreign key and historical Added Date backfill remain deferred; unknown historical dates must not be fabricated.
- No advanced same-book candidate workflow or multiple normalized identifiers.
- No roadmap bookshelf, exports, backups, or dry-run imports.
- No stable external IDs, record revisions, review batches, or proposals.
- No reference-cover enrichment, asset metadata, tags, or dedicated administration area.
- Uploaded cover replacement can leave unused R2 objects; cover upload also marks a book Owned.
- Server ISBN validation does not verify checksums, and some filters are not persisted.

## Next milestone

Execute only the conditionally authorized Packet A production backup gate after private readiness confirmation. Stop after target/preflight evidence, Time Travel bookmark retrieval, protected SQL export, and backup verification. Migration, publication, smoke testing, and rollback remain unauthorized.
