# Current State

**Last reviewed:** 2026-08-31

For a concise visual summary, see the [Project Dashboard](PROJECT_DASHBOARD.md). This document remains authoritative for exact operational state, gates, ownership, blockers, usage, and validation evidence.

Future Library-first presentation, Shopkeeper naming, responsive shell, testing access, write-lock UX, themes, bookcases, and optional personality layers are documented in [My Library Visual Experience](VISUAL_EXPERIENCE.md). They are planning direction only and do not alter the current queue or Site state.

Sei returned a read-only source-informed A–H estimate against exact Version 20 source. Phase A and the static Phase D foundation at `608553f`, plus older combined remediation at `80e4c61`, remain historical evidence without recoverable editable source. The Version 20-based correction candidate is complete, locally validated, source-preserved, and saved as unpublished Version 21 at `f15ea8144ec277a737f5e491e0276b60555cafb8`; it is not previewed, deployed, or published.

## Authoritative snapshot

- **Published Site:** Version 20, the exact validated cumulative Shopping/M3–M6/Bookshelf candidate at commit `6a2191b1b506d171d576cbb6a6b160964595c051`.
- **Latest saved Site:** Unpublished Version 21 at exact source checkpoint `f15ea8144ec277a737f5e491e0276b60555cafb8`; its saved build archive reports 47 files. No preview is active. Version 20 remains the released Site.
- **Other retained Site versions:** Version 18 migration bridge; unpublished Version 17 Shopping persistence/API foundation.
- **Production gate:** Gate 4 is complete within its defined bridge-observable verification boundary. The Version 19 surface independently reported `Shopping schema complete` and zero foreign-key issues; one later authorized read-only export matched the private Gate 2 baseline for counts, identities, Book values, ownership, copies, and cover references. The sole semantic difference was the authorized CYOA target price of 600 cents.
- **Closed operations:** Product Owner live validation, broad smoke testing, corrective writes, retry/republish, rollback, restore, and destructive recovery all require later authority. Gate 3 cannot be retried. Gate 4 does not establish a D1 snapshot, R2-byte backup, restore readiness, or a complete production backup.
- **Local milestones:** M1, M3, M4, and M5 are complete. M2 Gates 0–5 are complete within their distinct evidence layers. M4's missing formal transport acceptance was closed as unverifiable and was not reconstructed.
- **Completed work:** Engineer — Sei validated, preserved, and later published the exact 24-path cumulative candidate as Version 20. The single publication succeeded with bounded root/Shopping health and no migration or production data/schema mutation; checkpoint `608553f` was excluded.

## Queue and ownership

- **Current role identities:** Planner — Quatre; Designer — Relena; Engineer — Sei.

- **Queue Mode:** `ENABLED`.
- **Throttle:** `DRAIN`; use the remaining window productively while preserving the 15% floor.
- **Engineer state:** `SEI II — RETIRED`; `SEI III — PRESERVATION/SAVE BRIEF COMPLETE / CLEAN STOP`.
- **Engineer completion:** Exact checkpoint `f15ea8144ec277a737f5e491e0276b60555cafb8` remains clean. Relative to Version 20 it contains exactly `app/page.tsx`, `app/globals.css`, and `tests/collection-behavior.test.tsx`. Lint passes with zero errors/two established warnings, focused tests pass 17/17, full serial tests pass 93/93, production build passes, desktop/mobile responsive and accessibility QA passes, focus restoration and cover-error fallback pass, and final boundary/no-data checks pass. The generated TypeScript artifact remains in private quarantine with identity preserved. Standalone type checking remains a known environment/project limitation with no candidate-page error.
- **Preservation/save result:** Sites issued the expected short-lived project-scoped credential with valid sanitized metadata. One isolated direct query returned remote `main` at exact Version 20 with exit 0; one authorized normal fast-forward push advanced configured remote `main` to exact `f15ea81`. Full pre-save revalidation and package verification then passed, and exactly one unpublished Site save created Version 21 from exact `f15ea81` with a 47-file build archive. No credential was exposed; no preview, deployment, publication, production, schema/data, migration, environment change, or save retry occurred.
- **Planner decisions:** Two independent decisions are pending: controlled publication of exact saved Version 21, and conditional Product Owner read-only live validation only after a successful publication.
- **Active owner:** `PLANNER — QUATRE` — process the two independent decisions in [`PLANNER_INBOX.md`](PLANNER_INBOX.md).
- **Blocking owner:** `EXTERNAL/WAIT` for any release execution until Product Owner authorization is recorded and a fresh usage reading supports the future brief. This is a normal gate/reset wait, not an implementation blocker.
- **Potential later owner:** Product Owner hands-on validation still requires a separately designed live-only sequence because Sites exposes no runnable unpublished checkpoint.

## Usage reserve

Sei III recorded `!20:72`: **20% five-hour** and **72% longer-period** after the Version 21 save. No Engineer work is active. Any later release brief requires a fresh reading and must preserve the 15% floor; the present state is `WAITING FOR RESET`, not `BLOCKED`.

Workflow planning uses five-hour execution slices. One Engineer project is active per window by default. The provisional automatic stopping floor is **15%**, with a separate longer-period allowance check. The 35/50/70/85 task-class values are sizing guides; approved work may start or resume when its remaining high estimate plus the floor fits. Usage is refreshed at slice intake and thereafter only for large/high-risk work, stale/reset/intervening readings, material estimate growth, or credible floor risk. The [Engineer Execution Contract](ENGINEER_EXECUTION_CONTRACT.md) governs completion-oriented active runs and the mandatory pre-final continuation test.

## Current workstreams

| Workstream | State | Verified boundary | Next condition |
| --- | --- | --- | --- |
| Version 19 administration | Complete/retained behind Version 20 | Gate 2 status/export and Gate 3 invocation used the owner-authenticated same-origin surface | No further action currently authorized |
| Production schema activation | Gate 4 complete within bridge-observable scope | Schema-complete/zero-FK status plus one private export matched Gate 2 counts, identities, values, ownership, copies, and cover references; CYOA target is the authorized 600 cents | Keep backup/restore claims and every later release gate separate |
| Shopping UI | Published in Version 20 | Exact candidate passed 92/92 saved-source, 160/160 layered, and 150/150 focused tests; one publication succeeded; bounded root/Shopping health passed | Product Owner live validation remains separately gated |
| M3 canonical identifiers | Published in Version 20; not hands-on validated | Focused/full tests, lint, build, and publication candidate validation passed | Product Owner checkpoint remains separately gated |
| M4 bounded Bookshelf | Published in Version 20; not hands-on validated | Focused/full tests, build, scoped lint, and publication candidate validation passed | Product Owner checkpoint remains separately gated; transport acceptance remains unverifiable |
| M5 catalog export foundation | Published in Version 20; not production-exercised | Format v1, stable Book IDs, referential validation, deterministic output, no-write proof, and candidate validation passed | Complete backup/restore is not established |
| M6 downloadable export UI | Published in Version 20; not hands-on validated | 8/8 focused and cumulative publication suites, build, owner gating, no-write checks, and collision separation passed | Product Owner checkpoint remains separately gated |
| My Library Phase A shell | Complete locally; checkpoint `608553f` includes it | 94/94 current-source serial tests, targeted shell/theme suites, scoped lint, build, diff and manifest checks passed | Unsaved as a Site version; later checkpoint/release separately gated |
| My Library static Phase D themes | Complete locally; checkpoint `608553f` | Semantic conversion complete; desktop/mobile light/dark/system QA, focus, overflow, and sampled contrast passed | Admin/catalog visual routes blocked locally by sign-in; forced-colors/reduced-motion emulation and preference persistence remain later |
| Local D1 remediation | Complete | Private byte-for-byte backup; disposable-clone proof; unchanged `0004` → `0005` → `0006` applied once; preservation/integrity checks, 101/101 tests, scoped lint, and build passed | Retain backup privately; no restore or additional local write authorized |
| Confirmed validation-failure remediation | Complete and saved unpublished as Version 21 at `f15ea81` | Exact three-file Version 20 delta; lint zero errors/two warnings, 17/17 focused, 93/93 full serial, build, responsive/accessibility QA, focus restoration, cover fallback, clean boundary, no-data, and saved-package checks pass | Publication and live validation remain separate closed gates |

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
| Shopping | Published in Version 20; bounded page health passed; hands-on validation pending |
| Scanner | Existing scanning works; M3 canonical identifier foundation is complete locally |
| Bookshelf | Published in Version 20; hands-on checkpoint pending |
| Import/Export | Bridge export completed privately at Gate 2; catalog format-v1 foundation and owner-only downloadable UI complete locally; import remains unsafe/immediate |
| AI Review | Planned; safe interchange and proposal workflow incomplete |
| Assets | Personal cover upload/R2 serving exist; metadata, variants, cleanup, and complete byte backup do not |
| Tags | Planned; persistence absent |

## Park-and-resume rule

A task-level question preserves the exact safe resume point and enters `WAITING FOR ANSWER`; unrelated eligible work may continue. The whole run pauses only for cross-cutting safety, correctness, authority, collision, exhaustion, or reserve conditions, or when no independent task remains. Answers attach to the parked task, and affected assumptions, shared files, dependencies, and remaining validation must be rechecked before resumption.

## Next milestone

The Version 20-based confirmed-failure correction is complete at clean checkpoint `f15ea81`, preserved on the configured source branch, and saved exactly once as unpublished Version 21. Its exact three-file composition, full local validation, package identity, and saved-version result are accepted. Version 20 remains published. Controlled Version 21 publication and conditional Product Owner live validation are independent pending decisions; neither is authorized by the save.
