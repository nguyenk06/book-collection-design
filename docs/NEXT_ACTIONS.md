# Next Actions

This is the active engineering queue. Long-term priorities remain in the [Roadmap](ROADMAP.md); verified schema and migration direction remain in [Database](DATABASE.md).

## Current Sprint

### First Queue-Mode Sprint

**Workflow state:** Queue Mode enabled; throttle STOP; Engineer paused at a safe resumable checkpoint; P2/P3 complete locally and one read-only environment-feasibility brief remains queued and unaccepted

**Next owner:** `EXTERNAL/WAIT` - after usage refresh, start the replacement Engineer chat, run read-only `INIT`, and issue explicit `RUN` only when ready to resume.

P1 is complete in unpublished Version 19. P2 Shopping and P3 focused scanner/identifier validation are complete in unsaved local source; the authoritative full suite passes 68/68, task lint and build pass. Engineering is paused with no active workstream. The queued read-only brief remains unaccepted and cannot be consumed until explicit future `RUN`. Preview/save creation, production migration, publication, production smoke testing, and destructive actions remain unauthorized.

**Current objective**

Preserve the safe pause. After explicit future `RUN`, determine a safe functional Shopping validation environment without advancing another major product stage.

**Why this is the current priority**

Automated and Designer convergence evidence cannot substitute for hands-on usability review at a major user-facing boundary. Shopping is complete locally but remains an inaccessible black box until Product Owner can exercise realistic desktop and mobile scenarios safely. Work is intentionally paused for usage refresh; `INIT` does not resume it, and the Product Owner must explicitly restore `RUN`.

**Success criteria**

- A private user-accessible validation environment is verified without production mutation or publication.
- Product Owner completes the concise Shopping desktop/mobile checklist and returns `ACCEPT`, `ACCEPT WITH FOLLOW-UP`, or `REVISE BEFORE RELEASE`.
- Feedback is reconciled before any Shopping production-activation decision.

**Expected deliverables**

- Read-only environment feasibility evidence.
- Product Owner Shopping validation result and bounded feedback.

**Files likely affected**

- Permanent documentation and a separately authorized preview/checkpoint artifact only.
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

- After explicit future `RUN`, accept and execute the queued read-only feasibility brief for a safe Product Owner-accessible Shopping validation environment using disposable/isolated data.
- Run the Shopping hands-on checklist after separate environment/save authority is granted.
- Add normalized book identifiers and candidate matching before advanced scanner work.

## Blocked

- Bookshelf depends on completion of higher-priority Shopping and scanner milestones.
- Safe import/export depends on immutable external IDs, revision handling, format versioning, and conflict policy.
- AI Review depends on safe interchange plus review batch and proposal persistence.
- Reference-cover enrichment depends on asset metadata and safe identifier matching.
- Tags and dedicated analysis remain behind earlier roadmap priorities.

## Recently Completed

- Completed P3 focused scanner/identifier validation; 18/18 focused and 68/68 full serial tests, task lint, and build pass, with two narrow ISBN-validation defects fixed locally and no Site or production action.
- Completed and locally validated the bounded Shopping Mode UI, including required-price Purchase capture; 50/50 serial tests, 6/6 focused Shopping tests, 14/14 isolated collection tests, build, and task lint pass, with no Site save or production action.
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
