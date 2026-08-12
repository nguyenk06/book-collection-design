# Current State

**Last reviewed:** 2026-08-12

**Published Site version:** Version 18 migration bridge; deployment succeeded, but application and schema behavior remain unverified

**Verified saved implementations:** Shopping persistence/API foundation in unpublished Version 17; migration bridge published as Version 18; owner-authenticated administration surface preserved in unpublished Version 19

**Assessment:** Database-first architecture review completed 2026-08-03

**Production migration investigation:** Completed 2026-08-08; no production access or change performed

**Production backup gate:** Packet A revision 2 was authorized but automatically aborted before D1 access because no authenticated/supported production D1 operator path was available

**Workflow state:** Safe resumable pause; P2 Shopping and P3 focused validation complete locally; M1–M3 briefed serially, M4–M5 defined but not queued, and only M1 eligible after explicit `RUN`

**Queue mode:** `ENABLED` — first bounded development sprint

**Queue throttle:** `STOP`

**Usage guidance:** Product Owner reported approximately 87% usage available on 2026-08-12. Usage is shared: prefer complete validated milestones and preserve reserve for evidence and a clean stop. This does not change throttle `STOP` or authorize queue consumption.

**Engineer execution state:** `PAUSED` — replacement Engineer completed read-only `INIT`; no active workstream or queue consumption, and explicit future `RUN` is still required

## Current Engineering Workstreams

Progress is a coarse estimate toward each current objective, not validation evidence. Accepted briefs remain the authority; workstream tracking does not expand them.

| ID | Workstream | Progress | State | Authority | Blocker / next gate | Independent continuation |
| --- | --- | --- | --- | --- | --- | --- |
| `WS-ADMIN` | Owner-authenticated administration page | `[██████████] 100%` | COMPLETE | Local implementation/validation completed | Approved save execution in a future session | No further local work authorized |
| `WS-AUTH` | Same-origin authorization and security validation | `[██████████] 100%` | COMPLETE | Completed within accepted brief | Integrated validation passed | No further local work authorized |
| `WS-EXPORT` | Private export-download and validation UX | `[██████████] 100%` | COMPLETE | Completed within accepted brief | Integrated validation passed | No further local work authorized |
| `WS-CONVERGE` | Integrated admin milestone validation | `[██████████] 100%` | COMPLETE | 44/44 tests, build, and task lint pass | Approved save execution in a future session | No |
| `WS-SAVE` | Preserve validated administration source | `[██████████] 100%` | COMPLETE | Unpublished Version 19 verified | Publication remains separately gated | No |
| `WS-MIGRATION` | Production status/export and schema activation | `[░░░░░░░░░░] 0%` | BLOCKED | No production authority | Admin convergence, Site-save/publication approval, then sequential production gates | No |
| `WS-SHOP-FLOW` | Mobile Shopping search/scan/status flow | `[██████████] 100%` | COMPLETE | Implemented and validated locally | Local milestone complete | No further work required |
| `WS-SHOP-PURCHASE` | Purchase capture and history | `[██████████] 100%` | COMPLETE | Implemented and validated locally | Local milestone complete | No further work required |
| `WS-SHOP-QUALITY` | Shopping quality/accessibility convergence | `[██████████] 100%` | COMPLETE | 50/50 serial tests, focused tests, build, and task lint pass | Local convergence complete | No further work required |
| `WS-SCANNER-TESTS` | Focused scanner/identifier validation | `[██████████] 100%` | COMPLETE | 18/18 focused tests, 68/68 full serial tests, task lint, and build pass | Local validation complete | No further work required |
| `WS-PO-SHOP-ENV` | Shopping validation-environment feasibility | `[░░░░░░░░░░] 0%` | PLANNED | Read-only feasibility brief queued and unaccepted | Explicit future `RUN`, then Engineer acceptance; verify a private functional option without creating it | No while paused |
| `WS-PO-SHOP-VALIDATE` | Product Owner hands-on Shopping validation | `[░░░░░░░░░░] 0%` | PLANNED | Checkpoint required before Shopping production activation | Verify a private user-accessible environment with disposable/isolated data, then obtain separate authority to create/use it | No |

**Engineer can continue:** NO while throttle is `STOP`. Replacement Engineer initialization is complete; after usage refresh, wait for explicit `RUN` before `CB`.

**Current Planner decisions:** None. Planner accepted bounded Bookshelf (`1: A`) and export-first portability (`2: A`). Milestone 2 will separately require Product Owner preview/save authority and participation after feasibility; that future gate is not yet actionable.

**Next production gate:** None is currently executable. Product Owner hands-on Shopping validation is required before Shopping production activation; preview/save authority, publication, migration, and all production actions remain separately gated and unauthorized.

**Resume condition:** Replacement Site Engineer read-only `INIT` and stopping-point verification are complete. After usage refresh, issue explicit `RUN` when ready; until then, do not consume the queued brief. Planner and Engineer have confirmed this stopping point.

## Staged continuation

Five milestones are defined in [Staged Milestones](STAGED_MILESTONES.md). M1–M3 retain their serial briefs and gates; only M1 may become executable after explicit `RUN`. M4 bounded Bookshelf and M5 export-first portability are future definitions only, with no briefs or execution authority.

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

Planner approved a narrowly scoped permanent owner-authenticated in-Site administration surface that invokes the existing bridge APIs through the proven same-origin request path. Server-side authorization remains authoritative; schema status, private export, approved upgrade, and verification remain distinct steps, with explicit confirmation and same-origin/CSRF protection before any future schema-changing request. This surface is not an authentication bypass and must not provide owner credentials, session material, or impersonation capability to Engineer. See [ADR-0010](decisions/ADR-0010-owner-authenticated-administration-surface.md).

That surface is now implemented and validated locally. Owners receive a staged status, private export, separately approved upgrade, and verification workflow; anonymous users use the existing sign-in flow, and authenticated non-owners receive no controls or administrative data. Upgrade submission requires owner authorization, same-origin validation, JSON content type, a dedicated action header, explicit acknowledgment, and an exact confirmation phrase. Duplicate submission is disabled while active. Tests pass 44/44, build and task lint pass, and full lint retains only three pre-existing errors and one warning. At the local-completion transition, no source had yet been saved as a Site version, and no production request, export, D1/R2 operation, schema change, deployment, or publication occurred.

The exact validated administration source is now preserved as unpublished Site Version 19. Validation immediately before preservation passed 44/44 tests, build, and task lint. Version 18 remains published. Saving Version 19 did not publish, invoke the application, access production data, export, migrate, verify production, or change D1/R2.

The bounded P2 Shopping Mode UI is complete and validated in the unsaved local working copy. Mobile title/author/series/ISBN search, existing camera/photo/manual scanning, match limitations, collection status, target price when supplied, owner-only Business/Purchase history and capture, repeated-shopping navigation, ownership-independence messaging, and accessible loading/empty/error/success states are implemented. Purchase price is required and non-negative; sticker price and the other supported details remain optional, and unknown price is never converted to zero. The authoritative serial suite passes 50/50, focused Shopping tests pass 6/6, isolated collection regression tests pass 14/14, build passes, and task lint passes. Nothing was saved, published, migrated, or run against production.

P3 focused scanner/identifier validation is also complete in the unsaved local source. Focused tests pass 18/18, the authoritative full serial suite passes 68/68, task lint and build pass, and two narrow validation defects were corrected: unsupported extra characters can no longer normalize into an otherwise valid ISBN, and invalid checksums are rejected before external lookup. Physical-device validation, ISBN-10/13 conversion, canonical multi-identifier persistence, and advanced candidate matching remain deferred. No Shopping component, schema, Site version, or production state changed.

Planner added a reusable Product Owner hands-on validation checkpoint at meaningful user-facing milestones. P2 Shopping now requires this checkpoint before production activation. The current Shopping/P3 source is unsaved and not user-accessible; Version 19 does not contain Shopping. A supported private preview or unpublished saved version backed by disposable/isolated data is the preferred validation environment, but current evidence does not establish that Sites can expose one without production bindings or publication. That feasibility must be verified read-only before separate preview/save authority is requested.

Engineering then stopped at a safe resumable checkpoint for usage refresh. The replacement Engineer completed read-only `INIT`, and Planner and Engineer confirmed the stopping point. The feasibility brief remains queued and unaccepted, no workstream is active, and Queue Mode remains enabled with throttle `STOP`. No Site version contains the completed Shopping/P3 source, and no preview, production request, D1/R2 operation, migration, publication, deployment, smoke test, rollback, or destructive action occurred.

The Product Owner later reported approximately 97% weekly usage available, retiring the earlier “final 25%” constraint without resuming engineering. Planner/Designer retained the authoritative Future Improvement Catalog and knowledge-coordination rules in GitHub. Engineer completed the first-pass technical classification without implementation; its raw sandbox, source reviews, feasibility notes, classifications, license warnings, and completion handoff are preserved in the Engineer-local shared `knowledge/` workspace rather than this repository. `book-collection-design` is Designer-write-only for this workflow: Engineer reads it but communicates only through local `inbox/` and stores supporting material in local folders. No research conclusion has been promoted automatically to design, roadmap scope, or a brief.

## Current Status Dashboard

| Area | Status | Current state |
| --- | --- | --- |
| Architecture | Partial | Viable D1/R2 foundation; responsibilities must be separated incrementally |
| Database | Partial | Version 17 packages the locally validated additive migration for Businesses, Purchases, target price, and Added Date; production remains on the v16 schema and the book-to-collection relationship is not enforced |
| Shopping | Partial | Bounded search/scan/status/history/Purchase UI complete and validated locally but unsaved; production unchanged |
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
- The validated implementation requires a non-negative purchase price and allows an independently nullable sticker price; Planner accepted that contract for the current Shopping milestone.
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
- ISBN-10/13 conversion and canonical candidate handling remain incomplete; some filters are not persisted.

## Next milestone

After explicit future `RUN`, investigate the safe Shopping hands-on validation environment under the queued read-only brief. Then run the Product Owner checkpoint before any Shopping production activation. Do not begin another major product stage; preview/save creation, migration, publication, production verification, and smoke testing remain separately gated.
