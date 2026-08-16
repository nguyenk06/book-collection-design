# Next Actions

This is the active engineering queue. Long-term priorities remain in the [Roadmap](ROADMAP.md); verified schema and migration direction remain in [Database](DATABASE.md).

## Current Sprint

### First Queue-Mode Sprint

**Workflow state:** M1/M3/M4/M5 and M2 Gates 0–3 complete within bounded evidence; M4 transport gap closed as unverifiable; M6 parked before acceptance on source availability

**Next owner:** `EXTERNAL/WAIT` - materialize the correct cumulative editable M5 source in the supported Sites editing context without contaminating Version 19 or the isolated Shopping candidate.

Gate 3 was invoked exactly once through the owner-authenticated Version 19 administration surface. Its immediate response reported Shopping schema completion and zero foreign-key issues; this is not Gate 4 verification. The production sequence stopped before Gate 4. M4's formal acceptance transition could not be verified and was not reconstructed.

**Current objective**

Resume M6 from its safe pre-`CB` boundary when the correct cumulative editable M5 source becomes available. Keep Gate 4 and the Shopping candidate closed.

**Why this is the current priority**

Automated and Designer convergence evidence cannot substitute for hands-on usability review at a major user-facing boundary. Shopping is complete locally but remains an inaccessible black box until Product Owner can exercise realistic desktop and mobile scenarios safely. The prior usage pause is complete; `RUN` now permits M1 intake but does not satisfy M2’s Product Owner checkpoint conditions.

**Success criteria**

- Materialize and identify the cumulative editable M5 source through the supported Sites workflow.
- Before M6 acceptance, verify its exact composition and collision separation from published Version 19 and the isolated Shopping candidate.
- Resume M6 without reinitialization solely for this parked condition; revalidate dependencies, shared files, usage, and remaining tests first.
- Preserve the 30% remaining reserve and the existing park-and-resume behavior.

**Expected deliverables**

- M6 acceptance and completion/blocker evidence for a local/disposable downloadable catalog-export UI.

**Files likely affected**

- Permanent documentation and a separately authorized Gate 3 report only; the private Gate 2 export remains outside GitHub and handoff transport.
- Permanent documentation through normal CI processing.

**Estimated effort**

Product Owner reports approximately 80% remaining. Engineer may continue until 30% remains. The 30% value is a protected reserve and mandatory stopping threshold, not a usage grant or target. Stop earlier when no eligible work remains or safe handoff requires it, and reserve enough usage for validation, evidence, transport, and a clean stop.

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
- Scanner, Bookshelf implementation, mutable import, AI review, reference covers, tags, and analysis changes. The separately queued bounded M6 read-only export-download UI is allowed only after the Gate 3/M4 transition.
- Full edition modeling, Business locations, and generalized media support.
- Raw SQL, migration-ledger edits, direct packaged migration execution, corrective writes, or R2-byte access.
- Site deployment/publication, Shopping activation, production smoke testing, restore/import, or destructive rollback.

## Ready Next

- External/source owner: make the correct cumulative editable M5 source available in the supported Sites context.
- Engineer after source availability: revalidate composition/collisions and run `CB` for M6.
- M6 remains local/disposable only: no Site save, publication, production export, migration, schema/data change, or activation.
- Gate 4 verification requires a new explicit Product Owner approval and is not part of this continuation.

## Blocked

- Bookshelf depends on completion of higher-priority Shopping and scanner milestones.
- Safe import/export depends on immutable external IDs, revision handling, format versioning, and conflict policy.
- AI Review depends on safe interchange plus review batch and proposal persistence.
- Reference-cover enrichment depends on asset metadata and safe identifier matching.
- Tags and dedicated analysis remain behind earlier roadmap priorities.

## Recently Completed

- Completed Gate 2 owner status/private export preflight: expected pre-upgrade baseline, zero foreign-key issues, and a privately retained validated structured export; no production write or schema activation occurred.
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
