# Next Actions

This is the active engineering queue. Long-term priorities remain in the [Roadmap](ROADMAP.md); verified schema and migration direction remain in [Database](DATABASE.md).

## Current Sprint

### Database integrity and Shopping persistence foundation

**Current objective**

Add the minimum relational foundation required to represent purchases safely while preserving every existing book and collection identifier.

**Why this is the current priority**

Shopping Mode is the highest-priority user workflow. Persistence and relational integrity must exist before its interface is expanded. See [ADR-0003](decisions/ADR-0003-shopping-mode-priority.md) and [ADR-0007](decisions/ADR-0007-shopping-persistence-foundation.md).

**Success criteria**

- Existing book IDs, collection keys, ownership data, and production records remain intact.
- Businesses, purchases, and collection target price have validated persistence.
- The book-to-collection relationship is enforced after an orphan audit and backup.
- Money uses integer cents; purchase condition values are defined.
- Owner-authorized purchase create/read behavior is tested.
- Migration verification and rollback procedures are documented.

**Expected deliverables**

- Additive schema migration and rollback documentation.
- Purchase and Business persistence with collection target price.
- Owner-authorized purchase create/read routes.
- Constraint, validation, preservation, and migration tests.
- Updated design documentation after implementation verification.

**Files likely affected**

- Implementation database schema and migrations.
- Books, collections, purchase, and Business API modules.
- Database and API tests.
- [Current State](CURRENT_STATE.md), [Roadmap](ROADMAP.md), [Database](DATABASE.md), [Changelog](CHANGELOG.md), and this queue after completion.

**Estimated effort**

Medium.

**Risks**

- Orphaned collection references or identifier changes during table rebuild.
- Contradictions between purchases and independently editable ownership state.
- Incorrect money or condition validation.
- Incomplete rollback or production-data preservation checks.

**Out of scope**

- Shopping Mode UI redesign.
- Scanner, Bookshelf, import/export, AI review, reference covers, tags, and analysis changes.
- Full edition modeling, Business locations, and generalized media support.

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
