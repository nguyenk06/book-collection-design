# Current State

**Last reviewed:** 2026-08-31

For a concise visual summary, see the [Project Dashboard](PROJECT_DASHBOARD.md). This document remains authoritative for exact operational state, gates, ownership, blockers, usage, and validation evidence.

Future Library-first presentation, Shopkeeper naming, responsive shell, testing access, write-lock UX, themes, bookcases, and optional personality layers are documented in [My Library Visual Experience](VISUAL_EXPERIENCE.md). They are planning direction only and do not alter the current queue or Site state.

Sei returned a read-only source-informed A–H estimate against exact Version 20 source. Phase A and the static Phase D foundation at `608553f`, plus older combined remediation at `80e4c61`, remain historical evidence without recoverable editable source. A new Version 20-based correction candidate is now complete and locally validated at `f15ea8144ec277a737f5e491e0276b60555cafb8`; it is not saved, pushed, or published.

## Authoritative snapshot

- **Published Site:** Version 20, the exact validated cumulative Shopping/M3–M6/Bookshelf candidate at commit `6a2191b1b506d171d576cbb6a6b160964595c051`.
- **Latest saved Site:** Version 20; its identity-matched Sites package reported 47 files and the authorized Version 19→20 delta contains exactly 24 paths.
- **Other retained Site versions:** Version 18 migration bridge; unpublished Version 17 Shopping persistence/API foundation.
- **Production gate:** Gate 4 is complete within its defined bridge-observable verification boundary. The Version 19 surface independently reported `Shopping schema complete` and zero foreign-key issues; one later authorized read-only export matched the private Gate 2 baseline for counts, identities, Book values, ownership, copies, and cover references. The sole semantic difference was the authorized CYOA target price of 600 cents.
- **Closed operations:** Product Owner live validation, broad smoke testing, corrective writes, retry/republish, rollback, restore, and destructive recovery all require later authority. Gate 3 cannot be retried. Gate 4 does not establish a D1 snapshot, R2-byte backup, restore readiness, or a complete production backup.
- **Local milestones:** M1, M3, M4, and M5 are complete. M2 Gates 0–5 are complete within their distinct evidence layers. M4's missing formal transport acceptance was closed as unverifiable and was not reconstructed.
- **Completed work:** Engineer — Sei validated, preserved, and later published the exact 24-path cumulative candidate as Version 20. The single publication succeeded with bounded root/Shopping health and no migration or production data/schema mutation; checkpoint `608553f` was excluded.

## Queue and ownership

- **Current role identities:** Planner — Quatre; Designer — Relena; Engineer — Sei.

- **Queue Mode:** `ENABLED`.
- **Throttle:** `DRAIN`; use the remaining window productively while preserving the 15% floor.
- **Engineer state:** `SEI II — RETIRED`; `SEI III — LOCAL IMPLEMENTATION COMPLETE / CLEAN STOP`. No Engineer brief or `!run` is active.
- **Engineer completion:** Exact local checkpoint `f15ea8144ec277a737f5e491e0276b60555cafb8` is clean and four commits ahead of its configured remote-tracking baseline. Relative to Version 20 it contains exactly `app/page.tsx`, `app/globals.css`, and `tests/collection-behavior.test.tsx`; the final checkpoint changes only `app/page.tsx`. Lint passes with zero errors/two established warnings, focused tests pass 17/17, full serial tests pass 93/93, production build passes, desktop/mobile responsive and accessibility QA passes, focus restoration and cover-error fallback pass, and final boundary/no-data checks pass. The generated TypeScript artifact was moved once into private quarantine with identity preserved. Standalone type checking remains a known environment/project limitation with no candidate-page error. No push, Site save/version, preview, publication, production, schema/data, dependency, or configuration action occurred.
- **Planner decisions:** None pending. Product Owner selected Decisions 1:A and 2:A: exact source preservation, then one conditional unpublished Site save as a separate stage. Publication remains closed.
- **Active owner:** `PRODUCT OWNER` — send Sei III `!brief` for the queued preservation/save brief. A separate `!run` remains required after clean acceptance.
- **Blocking owner:** `NONE`; the Site save remains conditionally blocked until exact source preservation and package/identity revalidation succeed.
- **Potential later owner:** Product Owner hands-on validation still requires a separately designed live-only sequence because Sites exposes no runnable unpublished checkpoint.

## Usage reserve

Product Owner supplied `!89:82`: **89% five-hour** and **82% longer-period**. Exact source preservation is estimated at 2/4/7 points; the separate conditional unpublished-save stage adds 3/5/8 points. Their combined 5/9/15-point envelope requires a 30% operational minimum including the 15% floor and is authorized for brief intake while this reading remains fresh.

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
| Confirmed validation-failure remediation | Complete locally at `f15ea81`; unsaved and unpublished | Exact three-file Version 20 delta; lint zero errors/two warnings, 17/17 focused, 93/93 full serial, build, responsive/accessibility QA, focus restoration, cover fallback, clean boundary, and no-data checks pass | Decide source preservation and unpublished save separately; publication remains closed |

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

The Version 20-based confirmed-failure correction is complete locally at clean checkpoint `f15ea81`. Its exact three-file composition and full local validation are accepted. It has not been pushed to the configured source branch or saved as a Site version. Planner Decisions 1 and 2 govern those operations independently; publication and held live validation remain closed.
