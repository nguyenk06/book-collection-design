# Next Actions

This is the active engineering queue. Long-term priorities remain in the [Roadmap](ROADMAP.md); verified schema and migration direction remain in [Database](DATABASE.md).

## Current Sprint

### Preserve the Validated Administration Surface

**Workflow state:** Local implementation complete; unpublished Site-version approval pending

**Next owner:** `PLANNER` - approve or defer preserving the exact validated administration source as a new unpublished Site version in [Planner Inbox](PLANNER_INBOX.md).

`WS-ADMIN`, `WS-AUTH`, `WS-EXPORT`, and `WS-CONVERGE` are complete locally. Queue Mode is disabled, so no follow-on executable brief is prepared or consumed in this session. Production migration, Shopping UI, and scanner work remain unauthorized.

**Current objective**

Preserve the exact locally validated owner-authenticated administration source in a new unpublished Site version without publishing or invoking production.

**Why this is the current priority**

The administration page is implemented locally under [ADR-0010](decisions/ADR-0010-owner-authenticated-administration-surface.md). Tests pass 44/44, build and task lint pass, and no Site or production state changed. Saving the exact validated source is a separate gate and does not authorize publication or production use.

**Success criteria**

- Planner decides the unpublished save gate independently from publication and production gates.
- If approved later through a separate execution scope, the saved version must reference the exact validated source and remain unpublished.
- Saving must not invoke production APIs, export, migration, verification, smoke testing, or other production behavior.

**Expected deliverables**

- Planner decision on the unpublished Site-version preservation gate.
- A separate narrow execution brief only if approved in a future instruction.

**Files likely affected**

- [Planner Inbox](PLANNER_INBOX.md) and milestone state documents.
- No new executable brief while Queue Mode remains disabled for this session.

**Estimated effort**

Small decision; execution remains separately scoped.

**Risks**

- Sites migration execution and traffic gating may remain undocumented or unobservable.
- Runtime schema upgrades could create partial-failure, concurrency, authorization, or repeatability risks if poorly designed.
- Sites-native recovery controls may be weaker than direct D1 export/Time Travel administration.
- Private backup artifacts or identifiers could leak if placed in source or handoffs.
- A schema-changing admin action needs explicit confirmation, same-origin/CSRF protection, and serialized use in addition to owner authorization.
- Purchases and independently editable ownership state can still contradict one another.
- Publication could be mistaken for migration validation if the gates are not recorded separately.

**Out of scope**

- Shopping Mode UI redesign.
- Scanner, Bookshelf, import/export, AI review, reference covers, tags, and analysis changes.
- Full edition modeling, Business locations, and generalized media support.
- Production reads or writes, applying any migration, changing ledger/schema/data, or accessing R2.
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

- Implemented and locally validated the owner-authenticated administration surface; 44/44 tests, build, and task lint pass, with no Site save or production operation.
- Completed the read-only Site authentication/persistence-path investigation; 34/34 focused tests passed and no production or Site state changed.
- Published the exact validated Version 18 migration bridge; Sites deployment succeeded without application/API or database operations.
- Implemented and locally validated the Version 16-compatible migration bridge; saved it as unpublished Site Version 18 with packaged `0004` excluded.
- Completed and accepted the Production Backup & Migration Execution Plan with independent backup, migration, publication, and incident-response gates.
- Completed the read-only Production Migration & Rollback Investigation; confirmed Sites execution details remain undocumented and performed no production access or change.
- Preserved the exact validated Shopping persistence/API source and migration as unpublished Site Version 17; Version 18 bridge now supersedes Version 16 in production.
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

- Keep one coherent Current Sprint; it may contain multiple bounded workstreams under one or more compatible briefs.
- A blocked stream does not block unrelated authorized streams, but shared hotspots and the convergence gate must be coordinated.
- Do not duplicate the [Roadmap](ROADMAP.md); link to durable requirements.
- Focus only on the next implementation horizon.
- After each milestone, move completed work to Recently Completed and promote the next ready task.
