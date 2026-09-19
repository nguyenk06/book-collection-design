# Current State

**Last reviewed:** 2026-09-19

This document is the concise operational source of truth. Release history and superseded investigations remain in the [Changelog](CHANGELOG.md).

## Product and release

- **Active project:** CYOA Collection only.
- **Public Site:** [CYOA Collection](https://cyoa-collection.znesfreak.chatgpt.site).
- **Current saved and public release:** Version 32.
- **Exact release and application source:** `802db5fd9c54c79e4897cc12de86b875163f6c07`.
- **Sites capacity:** `UNKNOWN`; no authoritative Sites meter is available.
- **Publication state:** Version 32 deployment succeeded with the existing public audience. Product Owner review of the enrichment presentation is available on the public Site.

## Accepted product state

- The Library-first shell, responsive navigation, header contents, and desktop/mobile presentation are accepted.
- My Library is the aggregate base. It keeps the category-based shelves and bookcases while also supporting the intended all-books organization by collection and then within each collection by series/index and author/title.
- The main-page scanner now reaches explicit tracked, probable-existing, new-book, unavailable-metadata, and retry outcomes. The Product Owner accepts Version 30 scanner behavior and has closed the blocking restoration cycle.
- Version 32 mobile review reopened one bounded scanner completion issue: probable ISBN-less matches correctly identify existing `Need` records but provide no direct way to confirm the match, save the ISBN, or mark the Book owned. Exact clean local candidate `b5ba8f251e37ae42474089f769f95683e2e14429` now satisfies the accepted correction: scanner capture, lookup, and results may be public; all Add/edit mutations require sign-in; sign-in and authorization-expiry context is resumable; authoritative Library state is freshly re-resolved before confirmation; and an expired Add review replaces its mutation control with an in-modal sign-in/resume action that cannot repeat the POST. Relena's final release-boundary review returned `PASS`. This candidate is not public.
- Photo upload is currently more reliable than live camera capture. Live capture can require more than one attempt; this is retained as a stability issue rather than a release blocker.
- A valid captured ISBN can still return no title or author when the current metadata source has no record or cannot be reached. The manual-details path is the safe fallback.
- Shopkeeper remains available as a non-mutating quick-check surface, but the Product Owner has shelved it as an active workstream. Library is the canonical scan, review, add, and edit surface; do not spend milestone capacity on Shopkeeper parity or visual review unless the Product Owner reopens it.

## Open product boundaries

- Approved reference-cover enrichment is public in Version 32: a personal cover always wins, otherwise a valid ISBN may supply a clearly labeled remote Open Library reference cover, with a nonblocking fallback.
- The bounded ISBN metadata consumer is public in Version 32. Any later broadening of no-cost lookup evidence must preserve the rule that a captured identifier and provider-supplied metadata are separate evidence and requires a new bounded goal.
- Cover enrichment and ISBN enrichment were designed as separate consumers of shared read-only metadata and delivered under the one-application-writer rule.
- Tags may use provider subjects/categories only as reviewable, uncommitted default suggestions; they never silently become canonical. The first attachment target is Books only, with an extensible design that does not block possible later Collection-level tags.
- AI Review is a manual portability workflow: the Product Owner exports, explicitly chooses what to provide to an external agent/chat, receives proposed filled-in catalog data, and reviews it through safe import. The application does not embed or run an AI provider, background agent, recurring review, or autonomous mutation path.
- [Milestone 9 asset lifecycle and complete cover backup](ASSET_MANAGEMENT.md#milestone-9-requirements-contract) has an accepted lower-priority boundary: include all accessible personal stored-cover bytes, including separately classified orphans, in an owner-download-only versioned ZIP with no server-retained backup history. Encryption is not required. The manifest records hashes, types, sizes, stable Book associations, and missing/orphan/duplicate reporting. Remote Open Library images remain replaceable references rather than personal backup bytes; restore is a separate later gate.
- Phase F visual items remain held for owner review before implementation: denser Bookcase spines, useful cover detail loading, and titles on missing Shelf positions.

## Orchestration and ownership

- **Planner / Product Owner interface / Site owner:** Quatre.
- **Designer:** Relena — requirements, architecture, product interpretation, acceptance criteria, durable design documentation, and release-boundary review.
- **Engineer:** Kira — inspection, implementation, remediation, tests, builds, packages, and release preparation. Kira has no Sites, credential, save, deployment, publication, or final-handoff authority.
- **Advisory roles:** Cagalli for visual design, Lacus for UX/UI usability, and Athrun for operator testing and test plans.
- All roles are direct children of Quatre and may not create subagents. Quatre assigns and reconciles work directly.
- Preserve one application-source writer at a time. `PLANNER_INBOX.md` is only for unresolved Product Owner decisions; briefs are internal durable contracts, not Product Owner transport.

## Current capacity

- **Current usage reading:** Not supplied for this documentation closure. The prior 2026-09-17 pre-reset reading is historical and must not be treated as current capacity.
- **Reset credits:** 3 available and unused.
- **Floors:** target a clean stop by 10% five-hour remaining, never cross 5%; preserve 15% weekly unless the Product Owner explicitly authorizes a bounded exception.

## Current work

| Workstream | State | Next boundary |
| --- | --- | --- |
| Scanner restoration | Accepted in public Version 30 | Retain the live-capture stability note; do not reopen restoration without new evidence |
| Probable-match completion | Exact local candidate `b5ba8f251e37ae42474089f769f95683e2e14429`; release-boundary `PASS` | Await explicit Product Owner publication authorization; Version 32 remains public |
| Documentation cleanup | Reconciled through Version 32 and M9 requirements planning | Keep the TL;DR ownership footer and explicit next-action handoff in terminal workflow responses |
| Endpoint contract tests | Included in public Version 32 | Enrichment presentation checks and 167/167 full checks pass |
| Shopkeeper parity | Published in Version 31; active workstream shelved | Retain the route but spend no further milestone capacity unless the Product Owner reopens it |
| Repository maintenance | Incorporated into the Version 32 source lineage | pnpm is canonical; configured Node 24 build passes; standard wrapper remains host-blocked by its launcher/system Node 18 path |
| Reference-cover enrichment | Public in Version 32 | Product Owner may review personal-cover precedence, reference fallback, and failure handling |
| ISBN metadata enrichment | Public in Version 32 | Product Owner may review evidence hierarchy, attribution, and no-mutation behavior |
| Tags | Priority 1 direction accepted; implementation not active | Books only; provider-seeded suggestions require review and confirmation, with later Collection extensibility preserved |
| Safe import | Priority 2 direction accepted; implementation not active | Catalog-v1 JSON only, with non-mutating validation/dry run and no cover-byte mutation; restore remains separate |
| Manual AI Review | Priority 3 workflow accepted; implementation not active | Owner manually shares explicitly selected exported data externally, then reviews proposed data through safe import |
| M9 complete cover backup | Priority 4, lower priority; requirements accepted as 1:A + 2:A | After the first three milestones, separately authorize read-only inventory/ZIP feasibility; encryption, cleanup, and restore are excluded |
| Expanded administration | Initial focus accepted; implementation not active | Prioritize data quality and backup health before collection or spending analytics |

## Next milestone

Version 32 at exact source `802db5fd9c54c79e4897cc12de86b875163f6c07` remains saved and public. Shopkeeper is shelved and Library is canonical. The local scanner authorization candidate `b5ba8f251e37ae42474089f769f95683e2e14429` is validated and release-boundary accepted, but no Site push, version change, save, deployment, or publication is authorized until the Product Owner resolves the publication decision. The advance roadmap order remains Tags, catalog-v1 Safe Import, manual AI Review, complete cover backup, then expanded administration.
