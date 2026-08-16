# Next Actions

This is the active engineering queue. Long-term priorities remain in the [Roadmap](ROADMAP.md); verified schema and migration direction remain in [Database](DATABASE.md).

## Current Sprint

### First Queue-Mode Sprint

**Workflow state:** M1/M3/M4/M5 and M2 Gates 0–1 complete; Gate 2 awaits separate Product Owner authority; M4 transport closure awaits acceptance report

**Next owner:** `PLANNER` - approve or decline M2 Gate 2 owner-authenticated schema status, private export, and preservation preflight.

The Product Owner canceled the separate validation Site. Gate 1 published only Version 19 successfully, but application rendering was not independently observed and no production endpoint or database operation occurred. Gate 2 remains a distinct production read/export decision. M4's separate acceptance report remains missing.

**Current objective**

Decide whether Engineer may execute Gate 2 through an owner-authenticated Version 19 session: inspect schema status, create and privately retain the structured export, and verify preservation preflight evidence. The later Shopping candidate remains unauthorized for saving or publication.

**Why this is the current priority**

Automated and Designer convergence evidence cannot substitute for hands-on usability review at a major user-facing boundary. Shopping is complete locally but remains an inaccessible black box until Product Owner can exercise realistic desktop and mobile scenarios safely. The prior usage pause is complete; `RUN` now permits M1 intake but does not satisfy M2’s Product Owner checkpoint conditions.

**Success criteria**

- Product Owner explicitly approves or declines Gate 2 after reviewing Gate 1 and its application-rendering limitation.
- If approved, target/session, write freeze, expected schema baseline, private export storage, export integrity/limitations, and preservation invariants are verified with sanitized evidence.
- Engineer stops before schema activation; Shopping remains unpublished and no production write occurs.

**Expected deliverables**

- Explicit Gate 2 decision.
- If approved and executed, a sanitized Gate 2 report separating schema-status observation, private export validation, preservation evidence, and explicit no-write state.

**Files likely affected**

- Permanent documentation and private local export/evidence locations only.
- Permanent documentation through normal CI processing.

**Estimated effort**

Engineer estimates up to approximately 50% usage for M1–M3 through existing blockers. This is a ceiling; preserve reserve for convergence, evidence, and a clean stop.

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
- Production writes, applying any migration, changing ledger/schema/data, or accessing R2 bytes.
- Site deployment/publication, Shopping activation, production smoke testing, restore/import, or destructive rollback.

## Ready Next

- Obtain the missing M4 brief-acceptance report; do not recreate or infer it in GitHub.
- After explicit approval, execute only M2 Gate 2 owner status/private export/preservation preflight and stop before schema activation.
- M5 requires no further local implementation; any downloadable UI, Site save, production export, migration, or activation needs a new brief and separate gates.
- M4 is complete locally. Do not start M5 until the Planner entity-scope decision is recorded, its local brief is revised/confirmed eligible, and usage safely clears reserve.

## Blocked

- Bookshelf depends on completion of higher-priority Shopping and scanner milestones.
- Safe import/export depends on immutable external IDs, revision handling, format versioning, and conflict policy.
- AI Review depends on safe interchange plus review batch and proposal persistence.
- Reference-cover enrichment depends on asset metadata and safe identifier matching.
- Tags and dedicated analysis remain behind earlier roadmap priorities.

## Recently Completed

- Published only the existing Version 19 owner-authenticated administration source; Sites deployment succeeded, Shopping/M3–M5 remained excluded, application rendering was not independently observed, and no API/data/schema operation occurred.
- Completed P3 focused scanner/identifier validation; 18/18 focused and 68/68 full serial tests, task lint, and build pass, with two narrow ISBN-validation defects fixed locally and no Site or production action.
- Completed and locally validated the bounded Shopping Mode UI, including required-price Purchase capture; 50/50 serial tests, 6/6 focused Shopping tests, 14/14 isolated collection tests, build, and task lint pass, with no Site save or production action.
- Preserved the exact validated owner-authenticated administration source as Site Version 19 before its later separately authorized publication; preservation itself left production untouched.
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
- ISBN-10/13 conversion and canonical scanner candidate handling remain incomplete.
- R2 cover replacement can leave unused objects; asset metadata is absent.
- Import writes immediately with limited validation; some query filters are not persisted.

## Queue Rules

- Keep one coherent Current Sprint; it may contain multiple bounded workstreams under one or more compatible briefs.
- A blocked stream does not block unrelated authorized streams, but shared hotspots and the convergence gate must be coordinated.
- Do not duplicate the [Roadmap](ROADMAP.md); link to durable requirements.
- Focus only on the next implementation horizon.
- After each milestone, move completed work to Recently Completed and promote the next ready task.
