# Next Actions

This is the active engineering queue. Long-term priorities remain in the [Roadmap](ROADMAP.md); verified schema and migration direction remain in [Database](DATABASE.md).

## Current Sprint

### Investigate Sites-Native Version 17 Activation

**Workflow state:** Active read-only investigation

**Next owner:** `ENGINEER` - process `2026-08-08-sites-native-version-17-activation-investigation-implementation-brief.md` with `CB`.

**Current objective**

Determine the safest repeatable, data-preserving way to activate Version 17 using only supported ChatGPT Sites capabilities and the existing application architecture.

**Why this is the current priority**

Planner accepted that external D1 administration is unavailable and not part of the project operating model. The next step is a read-only assessment of Sites saved versions/deployment, source packages, D1 bindings, checked-in migrations, runtime initialization such as `ensureSeeded()`, application APIs, local/disposable validation, and Sites logs/metadata. No production operation or publication is authorized. See [Database](DATABASE.md).

**Success criteria**

- Actual Sites-native capabilities and limitations are verified without production writes.
- Existing migration packaging, D1 binding use, runtime initialization, and `ensureSeeded()` behavior are traced from source and disposable validation.
- Candidate strategies are compared for preservation, repeatability, failure behavior, authorization, rollback limitations, and maintainability.
- Backup/recovery protections actually available through Sites or the application are identified without claiming unavailable export or Time Travel controls.
- A recommended Sites-native activation strategy, conflicts, and required follow-up are returned in a sanitized handoff.
- Version 16 remains published and Version 17 remains saved/unpublished; no production migration or publication occurs.

**Expected deliverables**

- Accepted Sites-native activation investigation brief.
- Source/runtime capability assessment and disposable validation evidence.
- Candidate comparison and recommended activation/recovery approach.
- Explicit unknowns and approval boundaries for any later implementation or production brief.

**Files likely affected**

- Site source, migrations, initialization paths, APIs, bindings, saved-version metadata, and disposable validation only.
- Sanitized evidence handoff; private values remain outside repository and handoff artifacts.
- [Current State](CURRENT_STATE.md), [Roadmap](ROADMAP.md), [Database](DATABASE.md), [Changelog](CHANGELOG.md), and this queue after each verified transition.

**Estimated effort**

Medium.

**Risks**

- Sites migration execution and traffic gating may remain undocumented or unobservable.
- Runtime schema upgrades could create partial-failure, concurrency, authorization, or repeatability risks if poorly designed.
- Sites-native recovery controls may be weaker than direct D1 export/Time Travel administration.
- Private backup artifacts or identifiers could leak if placed in source or handoffs.
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
