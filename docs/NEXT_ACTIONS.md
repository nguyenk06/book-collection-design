# Next Actions

This is the active engineering queue. Long-term priorities remain in the [Roadmap](ROADMAP.md); verified schema and migration direction remain in [Database](DATABASE.md).

## Current Sprint

### Decide the Sites-Native Administration Boundary

**Workflow state:** Investigation complete; Planner decision pending

**Next owner:** `PLANNER` - decide the owner-only in-Site administration proposal in [Planner Inbox](PLANNER_INBOX.md).

**Current objective**

Approve, reject, or redirect the proposed permanent owner-only in-Site administration surface that would invoke the existing bridge APIs through the proven same-origin Site request path.

**Why this is the current priority**

The completed investigation found that normal mutations and bridge routes share the same server-side owner helper, Site worker, and managed bindings. Normal UI calls are same-origin; the two Engineer attempts failed before application execution. A permanent narrow administration page is recommended to reuse that proven path while keeping status, export, approved upgrade, and verification separately gated. This is a material architecture/security boundary requiring Planner approval. See [Planner Inbox](PLANNER_INBOX.md), [Architecture](ARCHITECTURE.md), and [ADR-0009](decisions/ADR-0009-sites-native-migration-bridge.md).

**Success criteria**

- Planner decides whether a permanent owner-only in-Site administration surface is an acceptable operational and security boundary.
- Any approval preserves server-side owner authorization, same-origin/CSRF protection, deliberate confirmation, private export handling, and independent production gates.
- If approved, Designer records the architecture decision and prepares a local implementation/validation brief that does not authorize production operations.

**Expected deliverables**

- Planner decision recorded in permanent documentation.
- If approved, a separately scoped implementation brief.

**Files likely affected**

- [Planner Inbox](PLANNER_INBOX.md) and permanent architecture/status documents for the decision.
- No Site source changes until a separate brief is approved and accepted.

**Estimated effort**

Small decision; implementation effort is separately estimated as small-medium.

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

- Keep exactly one Current Sprint.
- Do not duplicate the [Roadmap](ROADMAP.md); link to durable requirements.
- Focus only on the next implementation horizon.
- After each milestone, move completed work to Recently Completed and promote the next ready task.
