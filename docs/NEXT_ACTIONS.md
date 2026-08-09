# Next Actions

This is the active engineering queue. Long-term priorities remain in the [Roadmap](ROADMAP.md); verified schema and migration direction remain in [Database](DATABASE.md).

## Current Sprint

### Establish Authorized D1 Access and Retry Packet A

**Workflow state:** `BLOCKED-EXTERNAL`

**Next owner:** `EXTERNAL/WAIT` - Product Owner establishes an authenticated, authorized production D1 operator path privately. After that condition is met, Designer prepares or revises the next Packet A brief and Product Owner separately authorizes the execution window.

**Current objective**

Provide an authorized, authenticated D1 operator path that supports private production-target verification and backup execution, then obtain new explicit Product Owner authorization for a Packet A retry.

**Why this is the current priority**

Packet A revision 2 was authorized but automatically aborted before production D1 contact because the Engineer could not verify an authenticated/supported D1 access path. The no-write window ended. Resolving access is now the immediate prerequisite; migration, verification, publication, smoke testing, and destructive restore remain independent and unauthorized. See [Database](DATABASE.md).

Planner confirmed the operator path is not yet established. Prefer an existing Sites/Cloudflare-supported authenticated path. Do not create a new persistent migration credential unless the supported workflow requires it and is separately reviewed. No new Packet A authorization or no-write window begins before the path is established privately.

**Success criteria**

- An authorized D1 operator path is available privately through an authenticated operator session or supported connector.
- Product Owner explicitly authorizes Packet A and agrees not to change the collection until completion or abort.
- Site Engineer privately verifies the production target/access path, validates execution/results, and automatically aborts on any required stop condition.
- Version 16 remains published and Version 17 remains saved/unpublished.
- The exact production target and baseline are verified without exposing identifiers or row data.
- The current Time Travel bookmark and verified protected SQL export exist in restricted storage.
- The SQL export retention rule is recorded privately: retain through successful Version 17 migration, publication, and smoke testing until a later known-good backup exists.
- Sanitized Packet A evidence is returned; no migration or Site operation occurs.

**Expected deliverables**

- Accepted Packet A implementation brief.
- Restricted recovery bookmark and verified SQL export.
- Sanitized target, baseline, migration-ledger, invariant, and backup pass/fail report.
- Next approval request only after Packet A evidence is accepted.

**Files likely affected**

- Production target/read-only inspection, write-freeze coordination, and backup execution.
- Sanitized evidence handoff; private values remain outside repository and handoff artifacts.
- [Current State](CURRENT_STATE.md), [Roadmap](ROADMAP.md), [Database](DATABASE.md), [Changelog](CHANGELOG.md), and this queue after each verified transition.

**Estimated effort**

Medium.

**Risks**

- SQL export blocks database requests while running and may require a maintenance/write freeze.
- Ambiguous target, schema, ledger, Time Travel support, or backup output requires immediate abort.
- Private backup artifacts or identifiers could leak if placed in source or handoffs.
- Purchases and independently editable ownership state can still contradict one another.
- Publication could be mistaken for migration validation if the gates are not recorded separately.

**Out of scope**

- Shopping Mode UI redesign.
- Scanner, Bookshelf, import/export, AI review, reference covers, tags, and analysis changes.
- Full edition modeling, Business locations, and generalized media support.
- Applying any migration, changing the ledger/schema/data, or accessing R2.
- Site deployment/publication, production smoke testing, restore/import, or destructive rollback.

## Ready Next

- Complete Shopping Mode behavior on the new persistence foundation.
- Add normalized book identifiers and candidate matching before advanced scanner work.
- Apply small scanner test and validation improvements that do not change roadmap order.

## Blocked

- Bookshelf depends on completion of higher-priority Shopping and scanner milestones.
- Safe import/export depends on immutable external IDs, revision handling, format versioning, and conflict policy.
- AI Review depends on safe interchange plus review batch and proposal persistence.
- Reference-cover enrichment depends on asset metadata and safe identifier matching.
- Tags and dedicated analysis remain behind earlier roadmap priorities.

## Recently Completed

- Completed and accepted the Production Backup & Migration Execution Plan with independent backup, migration, publication, and incident-response gates.
- Completed the read-only Production Migration & Rollback Investigation; confirmed Sites execution details remain undocumented and performed no production access or change.
- Preserved the exact validated Shopping persistence/API source and migration as unpublished Site Version 17; Version 16 remains live.
- Implemented and locally validated Businesses, Purchases, collection target price, Added Date, owner-authorized APIs, and additive migration tests.
- Preserved existing Book identities and data in disposable local migration validation.
- Deferred portable Purchase identity until cross-database workflows require it.
- Completed the read-only v16 database-first architecture assessment.
- Verified the current D1/R2 architecture, schema risks, and capability maturity.
- Validated the roadmap order and accepted additive migration direction.
- Added ADRs for identity preservation, Shopping persistence, and canonical identifiers.

## Technical Debt

- No declared database foreign keys or expected-revision concurrency checks.
- Request-time schema and catalog updates in the books GET path.
- One large client page component and outstanding hook/compiler lint issues.
- Incomplete server ISBN checksum validation and scanner candidate handling.
- R2 cover replacement can leave unused objects; asset metadata is absent.
- Import writes immediately with limited validation; some query filters are not persisted.

## Queue Rules

- Keep exactly one Current Sprint.
- Do not duplicate the [Roadmap](ROADMAP.md); link to durable requirements.
- Focus only on the next implementation horizon.
- After each milestone, move completed work to Recently Completed and promote the next ready task.
