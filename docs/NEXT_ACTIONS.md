# Next Actions

This is the active engineering queue. Long-term priorities remain in the [Roadmap](ROADMAP.md); verified schema and migration direction remain in [Database](DATABASE.md).

## Current Sprint

### First Queue-Mode Sprint

**Workflow state:** Queue Mode enabled; throttle RUN; P2 continuation active and one P3 quality brief queued

**Next owner:** `ENGINEER` - complete active P2 convergence, then use `CB` for the P3 scanner-test brief if still eligible and no `DRAIN`/`STOP` is active.

P1 is complete in unpublished Version 19. The P2 continuation is accepted: `WS-SHOP-PURCHASE` is active at 40% and `WS-SHOP-QUALITY` remains 70% pending convergence. One P3 focused scanner/identifier test brief is queued behind a collision check. Production migration, another Site save, publication, production smoke testing, and destructive actions remain unauthorized.

**Current objective**

Prove Queue Mode with two coherent milestones: first preserve the exact validated administration source as an unpublished Site version, then implement and locally validate a bounded Shopping Mode UI against local/disposable data.

**Why this is the current priority**

Planner approved the unpublished save and this bounded sprint. Shopping Mode is the highest product priority after the database foundation; safe local UI progress does not require production schema activation. The Product Owner monitors usage externally and may issue `DRAIN` or `STOP`; project roles must not infer precise usage.

**Success criteria**

- Purchase capture and quality/accessibility streams converge coherently.
- Required purchase-price validation is clear and zero is never substituted for unknown data.
- At sprint convergence, permanent state distinguishes local, saved, published, migrated, and production-verified status.

**Expected deliverables**

- Final P2 local implementation/validation handoff.
- P3 focused scanner/identifier validation evidence if it becomes eligible and is accepted before `DRAIN`/`STOP`.
- Mobile-readable sprint review at `DRAIN`, `STOP`, or sprint completion.

**Files likely affected**

- Site source and disposable tests for P2 only.
- Permanent documentation through normal CI processing.

**Estimated effort**

Bounded sprint; Product Owner intends approximately 20 percentage points of externally monitored weekly usage, but project roles do not calculate or claim usage.

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

- Preserved the exact validated owner-authenticated administration source as unpublished Site Version 19; Version 18 remains published and production was untouched.
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
