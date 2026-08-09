# Current State

**Last reviewed:** 2026-08-09

**Published Site version:** Version 18 migration bridge; deployment succeeded, but application and schema behavior remain unverified

**Verified saved implementations:** Shopping persistence/API foundation in unpublished Version 17; migration bridge source preserved in Version 18 and now published

**Assessment:** Database-first architecture review completed 2026-08-03

**Production migration investigation:** Completed 2026-08-08; no production access or change performed

**Production backup gate:** Packet A revision 2 was authorized but automatically aborted before D1 access because no authenticated/supported production D1 operator path was available

**Workflow state:** Authentication/persistence-path investigation complete; owner-only in-Site administration architecture awaits Planner approval

## Summary

The published Site is now Version 18, a temporary migration bridge whose ordinary data paths remain compatible with the Version 16 schema. The validated Shopping persistence/API foundation remains preserved as unpublished Version 17 and has not been activated in production. Version 18 publication is verified from Sites deployment status only; application and schema behavior are not yet verified.

The read-only migration investigation found no public Sites contract establishing when packaged D1 migrations execute or whether migration success gates production traffic. That behavior remains unknown and must not be assumed.

The operator runbook and private-project readiness model are complete. The Product Owner explicitly authorized Packet A revision 2 and observed the no-write window, but the Engineer could not authenticate a direct D1 operator path, find a supported D1 connector, or use an existing authenticated Cloudflare session. The required ambiguous-target/access abort fired before any production D1 query or backup operation. The no-write window ended after abort.

Planner accepted external D1 administration as unavailable and outside the intended operating model. The project must use only supported capabilities exposed through ChatGPT Sites. External Cloudflare sessions, Wrangler authentication, API credentials/tokens, direct D1 console access, and another deployment platform are not project requirements. Version 17 activation now requires a read-only Sites-native architecture investigation; no production operation or publication is authorized.

The completed investigation found that migration packaging proves inclusion but not execution, ordering, atomicity, retry, or traffic gating. Runtime `ensureSeeded()` writes and repairs only the Version 16-era schema, while Version 17 ordinary queries and writes expect the new Shopping columns/tables; direct Version 17 publication is therefore unsafe on current evidence. Disposable validation showed that a guarded additive reconciler can repeat and resume from a partial state while preserving Book identity and collection data. Planner approved the temporary Version 16-compatible migration bridge architecture for local implementation/validation and an unpublished Site save only. No Site or production operation has occurred from that approval.

The bridge is implemented and locally validated. Its preserved Version 18 archive contains migrations `0000` through `0003` and excludes independently executable `0004`. The bridge provides Version 16-compatible ordinary data access plus owner-only schema status, versioned JSON export, explicit re-entrant Shopping upgrade, and read-only upgrade verification APIs. Full tests pass 37/37, build and bridge/task lint pass, and full lint retains only three pre-existing errors and one warning in the main page. Version 18 is now published; Version 17 remains unpublished.

Sites reported the exact saved Version 18 deployment succeeded. Version 18 is now published and Version 16 is superseded but retained in version history. Publication did not invoke the application or bridge APIs and does not establish application health, database schema state, packaged migration execution, or data preservation. No export, D1/R2 operation, schema upgrade, verification, final Shopping publication, smoke test, restore/import, or destructive action occurred.

Planner approved the next isolated read-only gate: owner-authenticated production schema status and versioned structured JSON export with private storage and sanitized verification evidence. Approval is not execution evidence and does not authorize the schema-upgrade POST, D1/R2 writes, ordinary application smoke testing, final Shopping publication, restore/import, rollback, or destructive action.

The first preflight/export attempt automatically aborted at the authentication prerequisite. The available Site browser context was signed out and no alternate signed-in context was available. The schema-status endpoint returned no application response, no export was requested or created, and the no-write window ended. One read-only Site root load occurred during troubleshooting outside the brief's strict two-endpoint scope; no interaction or mutation followed.

The Product Owner subsequently reported owner mode, but the second attempt still could not access an owner-authenticated Site tab in the Engineer browser session. Direct navigation to schema status was blocked before an application response. No production read succeeded, no export was produced, and no write or D1/R2 change occurred. Version 18 remains published, but its application health and schema state remain unverified. Repeating the same external/direct invocation is no longer the next action.

The completed read-only authentication/persistence-path investigation established that normal owner mutations and the Version 18 bridge use the same server-side owner authorization helper, Site worker, and managed D1 binding; cover operations additionally use the managed R2 binding. Normal signed-in UI operations originate as same-origin browser requests, while the two Engineer attempts failed before application route execution. Focused disposable validation passed 34/34. No source, production request, data/schema operation, Site version, deployment, or publication changed.

The recommended next architecture is a narrowly scoped permanent owner-only in-Site administration surface that invokes the existing bridge APIs through the proven same-origin request path. Server-side authorization remains authoritative; schema status, private export, approved upgrade, and verification remain distinct steps, with explicit confirmation and same-origin/CSRF protection before any future schema-changing request. This recommendation is not yet accepted and requires Planner approval before implementation.

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
- Version 17 is saved but unpublished; Version 18 bridge is published, and Version 16 is retained as superseded history.
- Production migration, rollback, and production behavior remain unverified.
- Sites migration trigger, executor, tracking, retry behavior, atomicity, and traffic sequencing remain unknown from public documentation.
- Raw migration `0004` applies once locally but is not directly idempotent; safe execution depends on the D1 migration ledger and controlled operator sequencing.
- The production D1 target, access, migration ledger, Time Travel eligibility, and backup artifacts remain unverified until Packet A executes.
- Direct operator-controlled production D1 migration, export, and Time Travel controls are unavailable unless Sites itself exposes a supported mechanism.
- Sites exposes saved versions, deployment/status controls, worker logs, hosted access controls, and managed logical D1/R2 bindings, but no standalone D1 migration/query/export/Time Travel control was found.
- `ensureSeeded()` performs legacy runtime writes but does not create Shopping schema; it cannot safely prepare an unmigrated database for direct Version 17 traffic.
- Version 18 is the saved migration bridge. Its duplicate-request guard is runtime-local rather than distributed, and schema inspection remains the durable source of truth.
- The bridge JSON export is portable structured data with R2 references, not a D1 snapshot, R2-byte backup, or restore facility.
- The book-to-collection foreign key and historical Added Date backfill remain deferred; unknown historical dates must not be fabricated.
- No advanced same-book candidate workflow or multiple normalized identifiers.
- No roadmap bookshelf, exports, backups, or dry-run imports.
- No stable external IDs, record revisions, review batches, or proposals.
- No reference-cover enrichment, asset metadata, tags, or dedicated administration area.
- Direct Engineer invocation of owner-only endpoints is not an established operational path; the failure boundary occurred before application execution.
- Uploaded cover replacement can leave unused R2 objects; cover upload also marks a book Owned.
- Server ISBN validation does not verify checksums, and some filters are not persisted.

## Next milestone

Obtain Planner approval or rejection of the proposed permanent owner-only in-Site administration surface and its security/operational boundary. If approved, prepare a separately scoped local implementation/validation brief; no production operation is authorized by the investigation.
