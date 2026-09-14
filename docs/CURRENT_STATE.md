# Current State

**Last reviewed:** 2026-09-14

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
- Photo upload is currently more reliable than live camera capture. Live capture can require more than one attempt; this is retained as a stability issue rather than a release blocker.
- A valid captured ISBN can still return no title or author when the current metadata source has no record or cannot be reached. The manual-details path is the safe fallback.
- Shopkeeper remains available as a non-mutating quick-check surface, but the Product Owner has shelved it as an active workstream. Library is the canonical scan, review, add, and edit surface; do not spend milestone capacity on Shopkeeper parity or visual review unless the Product Owner reopens it.

## Open product boundaries

- Approved reference-cover enrichment is public in Version 32: a personal cover always wins, otherwise a valid ISBN may supply a clearly labeled remote Open Library reference cover, with a nonblocking fallback.
- The bounded ISBN metadata consumer is public in Version 32. Any later broadening of no-cost lookup evidence must preserve the rule that a captured identifier and provider-supplied metadata are separate evidence and requires a new bounded goal.
- Cover enrichment and ISBN enrichment were designed as separate consumers of shared read-only metadata and delivered under the one-application-writer rule.
- Tags may reuse metadata-provider responses where useful, but tag persistence, user assignment, and acceptance remain a separate product model. Provider categories must never silently become canonical user tags.
- [Milestone 9 asset lifecycle and complete cover backup](ASSET_MANAGEMENT.md#milestone-9-requirements-contract) now has a durable requirements contract. The recommended default is a downloadable versioned ZIP manifest plus personal stored-cover bytes with hashes, types, sizes, stable Book associations, and missing/orphan/duplicate reporting. Remote Open Library images remain replaceable references rather than personal backup bytes. Package scope and retention remain pending Product Owner decisions; restore is a separate later gate.
- Phase F visual items remain held for owner review before implementation: denser Bookcase spines, useful cover detail loading, and titles on missing Shelf positions.

## Orchestration and ownership

- **Planner / Product Owner interface / Site owner:** Quatre.
- **Designer:** Relena — requirements, architecture, product interpretation, acceptance criteria, durable design documentation, and release-boundary review.
- **Engineer:** Kira — inspection, implementation, remediation, tests, builds, packages, and release preparation. Kira has no Sites, credential, save, deployment, publication, or final-handoff authority.
- **Advisory roles:** Cagalli for visual design, Lacus for UX/UI usability, and Athrun for operator testing and test plans.
- All roles are direct children of Quatre and may not create subagents. Quatre assigns and reconciles work directly.
- Preserve one application-source writer at a time. `PLANNER_INBOX.md` is only for unresolved Product Owner decisions; briefs are internal durable contracts, not Product Owner transport.

## Current capacity

- **Five-hour remaining:** 14% after Version 32 publication and release reconciliation.
- **Weekly remaining:** 32% at the same check.
- **Reset credits:** 3 available and unused.
- **Floors:** target a clean stop by 10% five-hour remaining, never cross 5%; preserve 15% weekly unless the Product Owner explicitly authorizes a bounded exception.

## Current work

| Workstream | State | Next boundary |
| --- | --- | --- |
| Scanner restoration | Accepted in public Version 30 | Retain the live-capture stability note; do not reopen restoration without new evidence |
| Documentation cleanup | Reconciled through Version 32 and M9 requirements planning | Keep the TL;DR ownership footer and explicit next-action handoff in terminal workflow responses |
| Endpoint contract tests | Included in public Version 32 | Enrichment presentation checks and 167/167 full checks pass |
| Shopkeeper parity | Published in Version 31; active workstream shelved | Retain the route but spend no further milestone capacity unless the Product Owner reopens it |
| Repository maintenance | Incorporated into the Version 32 source lineage | pnpm is canonical; configured Node 24 build passes; standard wrapper remains host-blocked by its launcher/system Node 18 path |
| Reference-cover enrichment | Public in Version 32 | Product Owner may review personal-cover precedence, reference fallback, and failure handling |
| ISBN metadata enrichment | Public in Version 32 | Product Owner may review evidence hierarchy, attribution, and no-mutation behavior |
| Tags | Planned discovery | Determine which provider fields are useful; keep canonical tag decisions separate |
| M9 complete cover backup | Requirements drafted; decisions pending | Resolve personal-byte scope and retention, then authorize a bounded read-only inventory/ZIP feasibility goal; no cleanup or restore |
| Safe import/restore | Planned later | Require dry-run, validation, conflict handling, and recovery contract |
| AI Review | Planned later | Requires stable interchange and proposal/review staging |

## Next milestone

Hold new implementation near the last recorded five-hour clean-stop floor. Version 32 is public and ready for optional Product Owner enrichment review. Shopkeeper is shelved and Library is canonical. The next planning gate is Product Owner resolution of M9 personal-byte scope and retention; only then may Quatre consider a fresh-capacity, read-only feasibility goal. No backup, cleanup, restore, or held visual work is active.
