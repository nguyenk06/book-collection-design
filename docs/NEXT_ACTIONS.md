# Next Actions

This is the active engineering queue. Long-term priorities remain in the [Roadmap](ROADMAP.md); verified schema and migration direction remain in [Database](DATABASE.md).

## Current Sprint

### Production Backup & Migration Execution Plan

**Current objective**

Turn the completed read-only investigation into an approval-ready operator plan for backing up and migrating production D1 before any Version 17 publication.

**Why this is the current priority**

The investigation confirmed that public Sites documentation does not define packaged D1 migration execution or traffic gating. Planner selected an operator-controlled D1 migration path rather than waiting for undocumented behavior, but has not authorized production backup, migration, publication, or rollback. See [Database](DATABASE.md).

**Success criteria**

- The execution plan enforces: backup → verify backup → inspect/list unapplied migrations → apply only `0004` → schema/data verification → publication approval → production smoke test.
- Time Travel bookmark capture and portable SQL export are distinct backup controls.
- Every gate has an operator, target check, pass/fail criteria, abort condition, evidence requirement, and approval boundary.
- Destructive Time Travel restore remains separately gated.

**Expected deliverables**

- Milestone-specific execution brief and accepted operator runbook.
- Backup and backup-verification checklist.
- Migration, schema/data verification, publication, smoke-test, abort, and rollback gates.
- Explicit approval requests for production access and each production-changing transition.

**Files likely affected**

- Production migration, backup, verification, and rollback documentation.
- Operator tooling and D1 migration-ledger inspection.
- [Current State](CURRENT_STATE.md), [Roadmap](ROADMAP.md), [Database](DATABASE.md), [Changelog](CHANGELOG.md), and this queue after each verified transition.

**Estimated effort**

Medium.

**Risks**

- Production migration could expose orphaned relationships or incomplete rollback assumptions.
- Raw `0004` is not directly idempotent and must not be replayed after an ambiguous failure.
- SQL export blocks database requests while running and may require a maintenance/write freeze.
- Purchases and independently editable ownership state can still contradict one another.
- Publication could be mistaken for migration validation if the gates are not recorded separately.

**Out of scope**

- Shopping Mode UI redesign.
- Scanner, Bookshelf, import/export, AI review, reference covers, tags, and analysis changes.
- Full edition modeling, Business locations, and generalized media support.
- Production migration or publication without explicit approval.
- Production backup/export execution or destructive restore without explicit approval.

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
