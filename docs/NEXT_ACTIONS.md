# Next Actions

This is the active engineering queue. Long-term priorities remain in the [Roadmap](ROADMAP.md); verified schema and migration direction remain in [Database](DATABASE.md).

## Current Sprint

### First Queue-Mode Sprint

**Workflow state:** M1/M3/M4/M5 and M2 Gates 0–2 complete; Gate 3 authorized; M4 transport closure pending; M6 local export-download UI queued independently

**Next owner:** `ENGINEER` - run `CB` for Gate 3, invoke the guarded activation no more than once, report, and stop before Gate 4.

Gate 2 succeeded through the owner-authenticated Version 19 administration surface: production reported the expected pre-upgrade baseline with zero foreign-key issues, and a validated structured export is retained privately. No production write occurred. M4's separate acceptance report remains missing.

**Current objective**

Execute the approved Gate 3/M4/M6 Engineer batch under `RUN`. The Shopping candidate remains unauthorized for saving or publication.

**Why this is the current priority**

Automated and Designer convergence evidence cannot substitute for hands-on usability review at a major user-facing boundary. Shopping is complete locally but remains an inaccessible black box until Product Owner can exercise realistic desktop and mobile scenarios safely. The prior usage pause is complete; `RUN` now permits M1 intake but does not satisfy M2’s Product Owner checkpoint conditions.

**Success criteria**

- Engineer cleanly accepts the Gate 3 brief and reconfirms target/session, write freeze, unchanged expected baseline, private export availability, security controls, exact confirmation, and usage boundary.
- The guarded upgrade is invoked no more than once and Engineer stops before Gate 4 regardless of result.
- Proposed batch: Gate 3 once (with existing safeguards), factual M4 acceptance/transport closure, then bounded M6 local export-download UI implementation and full validation.
- Estimated usage: Gate 3 intake/action/report 4–7 points; M4 existing-evidence closure 1–2; M6 intake, implementation, ordinary remediation, full validation, and transport 19–29; total 24–38. Expected remaining usage is approximately 42–56% from the reported 80%, preserving at least a 12-point cushion above the protected reserve.
- Expected completion range: Gate 3 completion/abort and M4 closure should finish; M6 should reach validated completion across one coherent run, or a clean partial handoff if unexpected remediation pushes the forecast toward reserve.
- After `RUN`, Engineer may choose the practical order within dependencies, remediate and validate within accepted scope, and move past an independently blocked stream. Gate 3 must still precede M6 intake and the production sequence must stop before Gate 4.
- If a task needs clarification, preserve it at a precise safe resume point, record the minimum question and assumptions not made, mark it `WAITING FOR ANSWER`, and continue another independent task. Attach the authoritative answer and revalidate affected assumptions/shared files before resuming; report material rework impact first.

**Expected deliverables**

- Gate 3 brief-acceptance report.
- Sanitized Gate 3 completion/abort report separating the immediate response from later verification.
- M4 acceptance/transport report only if existing local evidence proves it; otherwise a concise inability-to-verify report.
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

- Obtain the missing M4 brief-acceptance report; do not recreate or infer it in GitHub.
- Accept and execute/abort only M2 Gate 3, report, and stop the production sequence before Gate 4.
- Complete the M4 transport check from existing evidence only; do not recreate or infer acceptance.
- Engineer: run `CB` for Gate 3, preserve its completion/abort report, stop that production sequence before Gate 4, close M4 transport factually, then continue eligible M6 local work.
- M6 is local/disposable only: no Site save, publication, production export, migration, schema/data change, or activation.

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
