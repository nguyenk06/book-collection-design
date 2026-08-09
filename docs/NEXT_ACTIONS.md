# Next Actions

This is the active engineering queue. Long-term priorities remain in the [Roadmap](ROADMAP.md); verified schema and migration direction remain in [Database](DATABASE.md).

## Current Sprint

### Save and prepare the Shopping persistence foundation

**Current objective**

Move the locally validated Shopping persistence/API foundation into Site version history and prepare a safe, explicitly approved production migration and publication path.

**Why this is the current priority**

Shopping persistence and owner-authorized APIs are implemented and validated locally, but the work is not saved as a Site version, migrated to production, or published. Preserving that evidence and planning production activation are the immediate prerequisites to UI work. See [Database](DATABASE.md) and [ADR-0007](decisions/ADR-0007-shopping-persistence-foundation.md).

**Success criteria**

- The exact validated source is committed and pushed so a Site version can be saved.
- A new Site version records the foundation without implying publication.
- Production migration verification, rollback, backup, and authorization steps are documented.
- The deferred book-to-collection foreign key has an explicit implementation sequence.
- Production migration and publication occur only with separate explicit approval.

**Expected deliverables**

- Committed and pushed validated Site source.
- Saved, unpublished Site version.
- Production migration and rollback plan, including identifier and record preservation checks.
- Explicit decision point for production migration and later publication.

**Files likely affected**

- Site source/version workflow.
- Production migration, backup, verification, and rollback documentation.
- Book-to-collection foreign-key migration work when scheduled.
- [Current State](CURRENT_STATE.md), [Roadmap](ROADMAP.md), [Database](DATABASE.md), [Changelog](CHANGELOG.md), and this queue after each verified transition.

**Estimated effort**

Medium.

**Risks**

- Unsaved local work cannot be promoted through the Sites version workflow.
- Production migration could expose orphaned relationships or incomplete rollback assumptions.
- Purchases and independently editable ownership state can still contradict one another.
- Publication could be mistaken for migration validation if the gates are not recorded separately.

**Out of scope**

- Shopping Mode UI redesign.
- Scanner, Bookshelf, import/export, AI review, reference covers, tags, and analysis changes.
- Full edition modeling, Business locations, and generalized media support.
- Production migration or publication without explicit approval.

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
