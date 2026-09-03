# Current State

**Last reviewed:** 2026-09-02

For a concise visual summary, see the [Project Dashboard](PROJECT_DASHBOARD.md). This document remains authoritative for exact operational state, gates, ownership, blockers, usage, and validation evidence.

Future Library-first presentation, Shopkeeper naming, responsive shell, testing access, write-lock UX, themes, bookcases, and optional personality layers are documented in [My Library Visual Experience](VISUAL_EXPERIENCE.md). They are planning direction only and do not alter the current queue or Site state.

Sei returned a read-only source-informed A–H estimate against exact Version 20 source. Phase A and the static Phase D foundation at `608553f`, plus older combined remediation at `80e4c61`, remain historical evidence without recoverable editable source. The Version 20-based correction candidate is complete, locally validated, source-preserved, and saved as Version 21 at `f15ea8144ec277a737f5e491e0276b60555cafb8`. Its sole publication invocation returned no definitive result. Exact deployment identity remains unavailable; a bounded public-behavior comparison is authorized without changing that identity boundary.

## Authoritative snapshot

- **Released Site:** An active live release is present, but its exact version/source identity is unverified after one ambiguous Version 21 publication invocation. The last confirmed released state before that invocation was Version 20 at `6a2191b1b506d171d576cbb6a6b160964595c051`; do not claim that Version 20 or Version 21 is currently live. Supported metadata cannot reconcile the identity without the missing deployment ID.
- **Latest saved Site:** Version 21 at exact source checkpoint `f15ea8144ec277a737f5e491e0276b60555cafb8`; its saved build archive reports 47 files. No preview is active. Its published status is unverified after the ambiguous invocation.
- **Other retained Site versions:** Version 18 migration bridge; unpublished Version 17 Shopping persistence/API foundation.
- **Production gate:** Gate 4 is complete within its defined bridge-observable verification boundary. The Version 19 surface independently reported `Shopping schema complete` and zero foreign-key issues; one later authorized read-only export matched the private Gate 2 baseline for counts, identities, Book values, ownership, copies, and cover references. The sole semantic difference was the authorized CYOA target price of 600 cents.
- **Closed operations:** Product Owner hands-on validation remains conditional on successful Version 21 publication. Broad smoke testing, corrective writes, retry/republish, rollback, restore, and destructive recovery all require later authority. Gate 3 cannot be retried. Gate 4 does not establish a D1 snapshot, R2-byte backup, restore readiness, or a complete production backup.
- **Local milestones:** M1, M3, M4, and M5 are complete. M2 Gates 0–5 are complete within their distinct evidence layers. M4's missing formal transport acceptance was closed as unverifiable and was not reconstructed.
- **Completed work:** Engineer — Sei validated, preserved, and later published the exact 24-path cumulative candidate as Version 20. The single publication succeeded with bounded root/Shopping health and no migration or production data/schema mutation; checkpoint `608553f` was excluded.

## Queue and ownership

- **Current role identities:** Planner — Quatre; Designer — Relena; Engineer — Sei.

- **Queue Mode:** `ENABLED`.
- **Throttle:** `DRAIN`; use the remaining window productively while preserving the 15% floor.
- **Engineer state:** `SEI II — RETIRED`; `SEI III — LIVE-BEHAVIOR FINGERPRINT BRIEF PREPARED / AWAITING !brief`.
- **Engineer completion:** Exact checkpoint `f15ea8144ec277a737f5e491e0276b60555cafb8` remains clean. Relative to Version 20 it contains exactly `app/page.tsx`, `app/globals.css`, and `tests/collection-behavior.test.tsx`. Lint passes with zero errors/two established warnings, focused tests pass 17/17, full serial tests pass 93/93, production build passes, desktop/mobile responsive and accessibility QA passes, focus restoration and cover-error fallback pass, and final boundary/no-data checks pass. The generated TypeScript artifact remains in private quarantine with identity preserved. Standalone type checking remains a known environment/project limitation with no candidate-page error.
- **Preservation/save result:** Sites issued the expected short-lived project-scoped credential with valid sanitized metadata. One isolated direct query returned remote `main` at exact Version 20 with exit 0; one authorized normal fast-forward push advanced configured remote `main` to exact `f15ea81`. Full pre-save revalidation and package verification then passed, and exactly one unpublished Site save created Version 21 from exact `f15ea81` with a 47-file build archive. No credential was exposed; no preview, deployment, publication, production, schema/data, migration, environment change, or save retry occurred.
- **Publication blocker:** Sei III accepted and ran the bounded brief. Site/session, Version 20 released state, Version 21 saved state, no-preview state, exact `f15ea81`, 47-file archive, clean source, three-file delta, collision exclusions, whitespace, and protected boundaries passed. Lint passed with zero errors/two established warnings. The focused collection suite then failed 3/17: two search cases timed out and one ISBN-10 search case did not find the expected book heading. Full serial tests and production build were not run after the mandatory stop. Publication attempts remain 0/1.
- **Diagnostic result:** Read-only inspection found plausible timing/test-environment sensitivity and no established source defect. Execution 1 reran the exact focused file serially and passed 17/17 with exit 0; the original series-number, title, and ISBN-10 cases all passed. Execution 2 ran those three cases alone and passed 3/3 with exit 0; 14 cases were intentionally skipped. Execution 3 was unnecessary and unrun. All three original failures are classified `EXECUTION / TEST-ENVIRONMENT BEHAVIOR` at moderate confidence because the prior timing condition was not recreated. Source remained clean; files changed and generated artifacts are none.
- **Publication result:** The resume run reconfirmed exact clean `f15ea81`, saved Version 21, the 47-file package, and the three-file Version 20 delta. Reused lint 0-error, focused 17/17, and isolated 3/3 evidence remained attributable. The remaining full serial suite passed 93/93 with exit 0, production build passed with exit 0, and package/manifest/boundary/migration/dependency/configuration/secret/no-data/write gates passed. The sole publication invocation returned a connector error without deployment identity, URL, status, or success confirmation. Post-invocation read-only state showed an active Site, latest saved Version 21, no preview, and a live release, but did not identify the published version. Bounded health checks were unrun. Files changed and generated artifacts were none.
- **Release-identity capability:** Sei III verified the starting identities but could not accept the brief. The exposed supported status lookup requires the exact opaque deployment identity missing from the ambiguous invocation; the ordinary Site metadata view does not return current published version/source/deployment fields. No qualifying one-query request can be formed. Metadata-query count remains 0/1, and no Site/source/production action occurred.
- **Planner decisions:** None pending. Product Owner selected Decision 1:A, authorizing one bounded public-content fingerprint assessment as behavior-level—not exact deployment-identity—evidence.
- **Active owner:** `ENGINEER — SEI III` — accept the prepared fingerprint brief with `!brief`; a separate `!run` remains required.
- **Blocking owner:** `NONE` for brief intake. Exact release identity remains unavailable; publication retry, health verification, and Product Owner validation remain closed.
- **Potential later owner:** `PRODUCT OWNER` — perform the separately prepared Version 21 checklist only after successful publication; supported tooling exposes no runnable unpublished checkpoint.

## Usage reserve

Product Owner recorded `!25:55`. The authorized read-only live-content fingerprint assessment is estimated at 2/4/7 points and requires a 22% operational minimum including the 15% floor. At the high estimate it finishes near 18%, preserving the floor; refresh only if a reset, other substantial work, or credible floor risk intervenes.

Workflow planning uses five-hour execution slices. One Engineer project is active per window by default. The provisional automatic stopping floor is **15%**, with a separate longer-period allowance check. The 35/50/70/85 task-class values are sizing guides; approved work may start or resume when its remaining high estimate plus the floor fits. Usage is refreshed at slice intake and thereafter only for large/high-risk work, stale/reset/intervening readings, material estimate growth, or credible floor risk. The [Engineer Execution Contract](ENGINEER_EXECUTION_CONTRACT.md) governs completion-oriented active runs and the mandatory pre-final continuation test.

## Current workstreams

| Workstream | State | Verified boundary | Next condition |
| --- | --- | --- | --- |
| Version 19 administration | Complete/retained behind Version 20 | Gate 2 status/export and Gate 3 invocation used the owner-authenticated same-origin surface | No further action currently authorized |
| Production schema activation | Gate 4 complete within bridge-observable scope | Schema-complete/zero-FK status plus one private export matched Gate 2 counts, identities, values, ownership, copies, and cover references; CYOA target is the authorized 600 cents | Keep backup/restore claims and every later release gate separate |
| Shopping UI | Last confirmed in Version 20; current release identity unverified after ambiguous Version 21 invocation | Version 20 publication evidence remains valid; Version 21 passed all local release gates, but its 1/1 publication result returned no deployment identity | Compare bounded public behavior only; no exact-identity claim, retry, or live validation |
| M3 canonical identifiers | Last confirmed in Version 20; current release identity unverified | Focused/full tests, lint, build, and Version 20 publication evidence passed | Product Owner checkpoint remains separately gated |
| M4 bounded Bookshelf | Last confirmed in Version 20; current release identity unverified | Focused/full tests, build, scoped lint, and Version 20 publication evidence passed | Compare named Version 21 public behaviors only; checkpoint remains gated; transport acceptance remains unverifiable |
| M5 catalog export foundation | Last confirmed in Version 20; current release identity unverified | Format v1, stable Book IDs, referential validation, deterministic output, no-write proof, and candidate validation passed | Complete backup/restore is not established |
| M6 downloadable export UI | Last confirmed in Version 20; current release identity unverified | 8/8 focused and cumulative publication suites, build, owner gating, no-write checks, and collision separation passed | Product Owner checkpoint remains separately gated |
| My Library Phase A shell | Complete locally; checkpoint `608553f` includes it | 94/94 current-source serial tests, targeted shell/theme suites, scoped lint, build, diff and manifest checks passed | Unsaved as a Site version; later checkpoint/release separately gated |
| My Library static Phase D themes | Complete locally; checkpoint `608553f` | Semantic conversion complete; desktop/mobile light/dark/system QA, focus, overflow, and sampled contrast passed | Admin/catalog visual routes blocked locally by sign-in; forced-colors/reduced-motion emulation and preference persistence remain later |
| Local D1 remediation | Complete | Private byte-for-byte backup; disposable-clone proof; unchanged `0004` → `0005` → `0006` applied once; preservation/integrity checks, 101/101 tests, scoped lint, and build passed | Retain backup privately; no restore or additional local write authorized |
| Confirmed validation-failure remediation | Saved Version 21 at `f15ea81`; publication invocation consumed with ambiguous result | Authoritative release metadata cannot be queried without the missing deployment ID; query count remains 0/1 | Run the authorized behavior-level public fingerprint assessment; exact identity and later gates stay closed |

## Data and export status

- Gate 2 retained a private, validated structured bridge export covering 215 Books, 4 Collections, 0 Businesses, 0 Purchases, and 17 cover references, with unique identifiers and no broken references. It is not a D1 snapshot and excludes R2 bytes.
- Gate 4 independently agrees with Gate 3 on schema-complete and zero-FK signals. Its supplemental private export matched Gate 2 counts, identities, Book values, ownership, copies, and cover references; the authorized CYOA target price is now 600 cents.
- M5 provides a validated catalog format-v1 export foundation with persisted immutable Book stable IDs. M6 adds the validated owner-only downloadable UI. Both are published in Version 20 but were not exercised during bounded publication health checks; production export and hands-on validation remain unperformed.
- No complete production backup exists. Direct D1 export and Time Travel controls remain unavailable unless Sites exposes a supported mechanism.
- Existing mutable import remains immediate and insufficiently safe; no restore or round-trip import workflow is authorized.

## Capability status

| Area | Current state |
| --- | --- |
| Database | Gate 4 complete within bridge-observable verification scope; complete backup and restore readiness remain unproven |
| Shopping | Last confirmed published in Version 20; current release identity unverified after ambiguous Version 21 invocation |
| Scanner | Existing scanning works; M3 canonical identifier foundation is complete locally |
| Bookshelf | Last confirmed published in Version 20; current release identity unverified; hands-on checkpoint gated |
| Import/Export | Bridge export completed privately at Gate 2; catalog format-v1 foundation and owner-only downloadable UI complete locally; import remains unsafe/immediate |
| AI Review | Planned; safe interchange and proposal workflow incomplete |
| Assets | Personal cover upload/R2 serving exist; metadata, variants, cleanup, and complete byte backup do not |
| Tags | Planned; persistence absent |

## Park-and-resume rule

A task-level question preserves the exact safe resume point and enters `WAITING FOR ANSWER`; unrelated eligible work may continue. The whole run pauses only for cross-cutting safety, correctness, authority, collision, exhaustion, or reserve conditions, or when no independent task remains. Answers attach to the parked task, and affected assumptions, shared files, dependencies, and remaining validation must be rechecked before resumption.

## Next milestone

The Version 20-based confirmed-failure correction remains clean, preserved, and saved as Version 21 at exact `f15ea81`. All release gates passed, but the sole 1/1 publication invocation returned no deployment identity or success result. Supported metadata requires that missing ID and exposes no current-version/history lookup; query count remains zero. Product Owner authorized one bounded public-content fingerprint as behavior-level evidence only. The brief awaits `!brief` and separate `!run`; even a match cannot establish exact deployment/source identity or open Product Owner validation automatically. Retry and every mutation remain closed.
