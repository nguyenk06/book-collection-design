# Staged Milestone Sequence

**Prepared:** 2026-08-12

**Execution budget:** Fresh post-reset reading 90%; the temporary pre-reset exception is closed and the standing 30% protected reserve is restored. Primary private-export evidence remains estimated at 3–5 points; fallback local schema diagnosis is bounded and read-only.

**Queue state:** Throttle `DRAIN` until explicit `!run`; the reactivated P2 private-export evidence task is primary and mutation-free local `stable_id` drift diagnosis is the independent fallback. Later Site and production gates remain closed.

**Usage state:** Version 20 preserves the exact validated cumulative source. Reassess P2 after reset; accept it only when the full envelope preserves the cushion and clean-stop capacity. See [Next Batch Plan](NEXT_BATCH_PLAN.md).

This sequence stages only work supported by the approved roadmap and permanent decisions. Engineer Research Sandbox review, engineering-knowledge validation, external-project research, Future Improvement Catalog review/ranking, and new ideas are excluded.

The queue is ordered, but blockers and questions are per milestone rather than global. Park a task requiring clarification as `WAITING FOR ANSWER` with its minimum question, assumptions deliberately not made, safe resume point, conflicts, and remaining validation. Then continue the next independently eligible brief. Attach the authoritative answer and revalidate affected assumptions/shared files before resuming; report material rework impact first. A parked blocker remains unresolved and still gates its own user-facing or production outcome. Technical validation, Designer convergence, Product Owner hands-on validation, and production approval remain separate gates.

Future parallel milestones should remain independently promotable. Completion in one cumulative working copy does not authorize bundling: each saved or published candidate must name its exact included/excluded source and migration set. If independent promotion is not technically possible, stop before release and request an explicit convergence decision.

## Milestone 1 — Shopping validation-environment feasibility

- **Roadmap authority:** [Roadmap priority 1 and Immediate milestone](ROADMAP.md#immediate-milestone); [Shopping checkpoint](SHOPPING_MODE.md#product-owner-validation-checkpoint).
- **Objective/user outcome:** Determine, without mutation, whether a private, runnable, Product Owner-accessible environment can expose the completed Shopping/P3 source with disposable or isolated data. This milestone creates no environment.
- **Included:** Verify actual Sites-native preview/version options, runnability, privacy, authentication, binding isolation, source baseline, access steps, and the narrow next approval request.
- **Excluded:** Source changes; preview/version creation; save, deployment, publication, production requests, D1/R2 access, migration, smoke testing, credentials/session transfer, external platforms, research review, and destructive action.
- **Starting state:** Verify published Version 18; unpublished Version 19 latest saved; completed P2 Shopping plus P3 fixes in the unsaved local copy; prior 68/68 serial tests, 18/18 focused scanner tests, task lint, and build passing; no Site version containing P2/P3; explicit `!run` before `!brief`.
- **Acceptance/tests/evidence:** Classify supported options for runnability, privacy, authentication, and D1/R2 isolation; report one safe option and exact access steps, or the blocker and simplest supported alternatives; provide sanitized capability evidence, baseline verification, and explicit no-change confirmation.
- **Data/rollback:** No data access or mutation; rollback not applicable. Any unexpected mutation ends the milestone.
- **User validation:** Not performed; this prepares the checkpoint.
- **Stop/escalate:** Required mutation, unverified isolation, authentication bypass, credential/session request, missing source, ambiguous identity, unsupported assumption, or production invocation.
- **Completion/handoff:** Local `inbox/` acceptance and completion/blocker reports followed by a fresh queue scan. M2 uses accepted M1 evidence; if M1 or M2 cannot proceed, evaluate independent M3 rather than stopping the whole cycle.

## Milestone 2 — Controlled live Shopping release and Product Owner checkpoint

- **Roadmap authority:** [Roadmap priority 1 and Immediate milestone](ROADMAP.md#immediate-milestone); [Shopping checkpoint](SHOPPING_MODE.md#product-owner-validation-checkpoint); [Handoff Protocol checkpoint](HANDOFF_PROTOCOL.md#product-owner-hands-on-validation-checkpoint).
- **Objective/user outcome:** Release the exact approved Shopping candidate through controlled live gates, then let Product Owner validate desktop/mobile behavior against the existing collection.
- **Included:** Candidate isolation/local validation; separately approved administration-surface publication; owner schema status and private structured export; separately approved guarded schema activation and verification; separately approved Shopping publication; live checklist; smoke review; sanitized evidence after every gate.
- **Excluded:** Separate validation Site, accidental M3–M5 publication, unapproved schema/source changes, destructive restore, silent data correction, external platform, credentials/session transfer, and research review.
- **Dependencies/starting state:** Exact cumulative source and Site/version identity verified; Shopping-only release candidate can be isolated; Product Owner is available; each production gate receives its required explicit authority before execution.
- **Acceptance/tests/evidence:** Preserve Book IDs, collections, covers/references, ownership, copies, and existing values; verify structured export and its limitations; schema/foreign-key/target/count checks pass; exact candidate deploys; checklist returns one allowed outcome; critical smoke paths pass.
- **Data/rollback:** Use live data. Retain export privately; keep compatible prior Site versions; prefer forward repair after additive migration. Code rollback and destructive data recovery remain separate decisions.
- **User validation:** Required live after schema verification and Shopping publication.
- **Stop/escalate:** Candidate contamination, failed backup/export, unexpected schema, preservation mismatch, partial upgrade, failed deployment/health, failed checklist/smoke, unavailable owner session, missing authority, or any destructive recovery need.
- **Completion/handoff:** One local report per gate plus a final outcome; never combine gate approvals or infer success from this definition.

## Milestone 3 — Canonical book-identifier foundation

- **Roadmap authority:** [Roadmap priority 2](ROADMAP.md); [Database accepted direction, step 5](DATABASE.md#accepted-direction); [ADR-0008](decisions/ADR-0008-canonical-books-and-identifiers.md); [Scanner and Matching](SCANNER_AND_MATCHING.md).
- **Objective/user outcome:** Local/disposable search and scan paths resolve validated equivalent ISBN-10/ISBN-13 identifiers to one canonical Book without silent overwrite or duplicate creation.
- **Included:** Additive local `book_identifiers` model/migration; type, normalized value, canonical Book relation, global type/value uniqueness; deterministic normalization/conversion; conservative valid-ISBN backfill; exact lookup; explicit conflict reporting; minimal integration needed for canonical results.
- **Excluded:** Production migration/data; Site save/publication; fuzzy scoring; silent merges; edition/copy hierarchy; `AltBooks`; provider redesign; physical-device claims; batch scanning; Bookshelf; Import/Export; research review.
- **Dependencies/starting state:** M1 has reached a reported completion or blocker transition; exact P2/P3 baseline is preserved; baseline suite, focused tests, lint, and build pass; no unresolved Shopping issue collides with scanner/search surfaces. M2 acceptance is not required for this local foundation.
- **Acceptance:** Preserve Book IDs and collection state in disposable migration tests; backfill valid ISBNs conservatively; invalid/conflicting values never overwrite/merge; uniqueness prevents duplicate claims; ISBN-10/13 equivalents resolve to one Book; scanning alone causes no Book/Purchase mutation; legacy `books.isbn` remains compatible.
- **Tests/evidence:** Representative migration, failure behavior, normalization/checksum/conversion vectors, uniqueness/conflicts, exact lookup, no-mutation scanner tests, full serial/focused suites, task lint, and build. Report counts, not private data.
- **Data/rollback:** Local/disposable only and additive. Preserve `books.id`, `collections.key`, ownership, copies, purchases, covers, and timestamps. Retain pre-migration fixture and prove clean failure without partial reassignment. No production rollback authority.
- **User validation:** Designer convergence required. Product Owner checkpoint only if a material new resolution flow is introduced; this does not authorize activation.
- **Stop/escalate:** ADR conflict; unsafe backfill/uniqueness; ambiguity; proposed merge/overwrite; undocumented product/architecture decision; persistent regression; missing source/data/access; or Site/production need.
- **Completion/handoff:** Local `inbox/` acceptance and final handoff separate implementation, local migration evidence, save, publication, and production states.

## Milestone 4 — Bounded collection Bookshelf

- **Roadmap authority:** [Roadmap priority 3](ROADMAP.md); Planner decision `1: A`; [Bookshelf accepted bounded first release](BOOKSHELF.md#accepted-bounded-first-release).
- **Objective/user outcome:** Browse one collection in existing series order, see explicit missing-position gaps, open a real Book, and return without losing browsing context.
- **Included:** Existing collection selection and series positions; real Book cover/text fallbacks; non-book gap indicators; existing detail/edit navigation; return-context preservation; responsive keyboard/mobile behavior.
- **Excluded:** Physical shelf locations, saved views, tags, bulk actions, synthetic Books for gaps, new identity/schema models, enrichment, analysis, and production actions.
- **Dependencies/starting state:** M3 accepted by Designer; canonical identifier changes converged without regression; existing collection/series-position rules verified; local brief accepted through `!brief`.
- **Acceptance:** Stable ordering; gaps never mutate or masquerade as Books; real Books open existing detail/edit; return restores collection and browsing context; missing covers/metadata degrade safely; existing collection behavior remains intact.
- **Tests/evidence:** Ordering/gap fixtures, navigation/return tests, cover/metadata fallback, keyboard/accessibility, responsive viewport coverage, full regression suite, build, and task lint.
- **Data/rollback:** No schema change expected. Preserve all Book/collection identities and state. Local UI changes must be revertible without data cleanup.
- **User validation:** Required at this user-facing boundary using desktop and mobile browse/gap/detail/return scenarios in a separately authorized safe environment.
- **Stop/escalate:** Required schema or identity change; ambiguous expected-position rule; synthetic record proposal; context cannot be preserved safely; persistent regression; or any save/production need.
- **Completion/handoff:** Future local acceptance/completion reports and Designer convergence; separate Product Owner outcome before any activation.

## Milestone 5 — Export-first portability foundation

- **Roadmap authority:** [Roadmap priority 4](ROADMAP.md); Planner decision `2: A`; [Import/Export accepted export-first boundary](IMPORT_EXPORT.md#accepted-export-first-boundary).
- **Objective/user outcome:** Produce a locally validated, versioned read-only export whose identity, scope, and referenced-image manifest can be understood independently.
- **Included:** Format/version metadata; immutable external IDs required for exported identity; core collection export; referential validation; attachment-reference manifest; deterministic serialization where practical; local/disposable export validation.
- **Excluded:** Import mutation, dry-run import, revisions/conflicts, restore, rollback, raw database dump as user format, image-byte backup unless separately designed, production export, migration, Site save/publication, and research review.
- **Dependencies/starting state:** M4 accepted by Designer; M3 identifier foundation stable; Designer-approved external-ID contract for every exported entity—including Purchases if included; export field/scope schema documented; local brief accepted through `!brief`.
- **Acceptance:** Versioned contract is self-describing; stable IDs and references are unique/consistent; required core records are complete; manifest distinguishes references from bytes; unknown/null values are preserved; repeated export of unchanged fixture is equivalent; no mutation occurs.
- **Tests/evidence:** Contract/schema validation, representative complete/empty/null fixtures, referential and uniqueness checks, deterministic comparison, malformed-state failure, no-write verification, full regressions, build, and task lint.
- **Data/rollback:** Read-only local/disposable execution. No production data or backup claim. No rollback needed because export must not mutate; any observed mutation stops work.
- **User validation:** Required only when a safe downloadable user-facing export experience is later implemented; validate understandable scope, filename/metadata, and image-manifest limitation before activation.
- **Stop/escalate:** Missing external-ID contract; Purchase portability ambiguity; pressure to omit required data silently; mutation/restore requirement; sensitive leakage; integrity mismatch; schema migration; or production access.
- **Completion/handoff:** Future local reports separate format implementation, validation, artifact handling, Site state, and production state. Import remains a later decision and brief.

M4 and M5 are complete locally. M2 Gate 0 isolated the exact candidate, Gate 1 published only Version 19 administration, and Gate 2 verified the expected pre-upgrade baseline, zero foreign-key issues, and a privately retained structured export without a production write. Gate 3 was invoked exactly once. Gate 4 independently confirmed schema-complete and zero-FK signals, then stopped incomplete because the authorized surface could not expose preservation invariants. Every later gate remains closed. M4's missing formal acceptance transition was factually closed as unverifiable rather than inferred or recreated.

## Milestone 6 — Local downloadable catalog export UI

**State:** Complete and validated locally; preserved in unpublished, undeployed Version 20; Product Owner checkpoint remains separately gated.

- **Roadmap authority:** [Roadmap priority 4](ROADMAP.md); [Import/Export accepted export-first boundary and format v1](IMPORT_EXPORT.md#accepted-format-version-1-contract); completed M5 foundation.
- **Objective/user outcome:** An owner can locally request and download the approved catalog format-v1 export with understandable scope and limitations.
- **Included:** Owner-only local UI/route integration over the existing catalog export service; safe filename and format metadata; explicit included/excluded entities; `bytes_included: false` limitation; loading, success, error, retry, and accessibility states; no-mutation verification.
- **Excluded:** Import, restore, production export, bridge-export replacement, schema/migration changes, image bytes, Businesses/Purchases, Shopping changes, Version 19 administration changes, Site save/publication, production access, and research review.
- **Dependencies/eligibility:** Batch throttle is `RUN` after the authorized `!run`; Gate 3/M4 transitions and the production stop before Gate 4 are satisfied. The exact cumulative editable M5 source, collision boundaries, and current validation are verified. Before acceptance, Engineer must revalidate source composition, dependencies, usage safely above the protected reserve, and clean-stop capacity.
- **Acceptance/tests/evidence:** Downloaded format-v1 artifact matches the accepted contract; owner-only behavior; understandable filename/scope/limitations; deterministic payload except documented metadata; empty/error/retry/accessibility coverage; explicit no-write checks; focused/full serial tests, task lint, and build.
- **Data/rollback:** Local/disposable and read-only. No production data, save, publication, backup claim, import, restore, or rollback authority.
- **User validation:** A later separately authorized checkpoint is required before activation; no Site operation follows from local completion.
- **Stop/escalate:** Source collision with Version 19 or the isolated Shopping candidate, need for schema/product expansion, private leakage, mutation, failed validation, unavailable source, or reserve risk.
- **Completion/handoff:** Local brief acceptance and completion/blocker reports, followed by a fresh queue scan. Keep release composition independent.

## Shared controls

- Finish and validate the current milestone before starting another; reserve usage for tests, evidence, and a clean stop.
- If one workstream blocks, report it and continue the next independently eligible, non-conflicting workstream. Waiting for a production gate does not idle authorized local work.
- A task-level question causes `WAITING FOR ANSWER`, not a global stop, unless it affects all eligible work, crosses a risk gate, threatens shared architecture/correctness, leaves no independent task, or usage approaches reserve.
- New instructions queue behind safe active work unless they explicitly invoke `!stop`, say `HOLD`, or invalidate work in progress.
- Stop for undocumented product/architecture choices, destructive or irreversible actions, ungated publication/activation, unauthorized migration, material expansion, bypassed criteria, missing source/data/credentials/access, failed validation, or unresolved integrity risk.
- Designer alone writes GitHub documentation. Engineer communicates through local `inbox/`; technical material remains local.
- Migration, publication, activation, production smoke testing, rollback, and destructive cleanup remain separately gated.
