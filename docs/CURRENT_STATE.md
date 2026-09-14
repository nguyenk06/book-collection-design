# Current State

**Last reviewed:** 2026-09-13

This document is the concise operational source of truth. Release history and superseded investigations remain in the [Changelog](CHANGELOG.md).

## Product and release

- **Active project:** CYOA Collection only.
- **Public Site:** [CYOA Collection](https://cyoa-collection.znesfreak.chatgpt.site).
- **Current saved and public release:** Version 31.
- **Exact release and application source:** `d9d83bb4c964c2de9af8c0affdcb1a44ed5e6792`.
- **Sites capacity:** `UNKNOWN`; no authoritative Sites meter is available.
- **Publication state:** Version 31 deployment succeeded. Product Owner review is parked by request while nonvisual work continues. No later source checkpoint has been saved, deployed, or published.

## Accepted product state

- The Library-first shell, responsive navigation, header contents, and desktop/mobile presentation are accepted.
- My Library is the aggregate base. It keeps the category-based shelves and bookcases while also supporting the intended all-books organization by collection and then within each collection by series/index and author/title.
- The main-page scanner now reaches explicit tracked, probable-existing, new-book, unavailable-metadata, and retry outcomes. The Product Owner accepts Version 30 scanner behavior and has closed the blocking restoration cycle.
- Photo upload is currently more reliable than live camera capture. Live capture can require more than one attempt; this is retained as a stability issue rather than a release blocker.
- A valid captured ISBN can still return no title or author when the current metadata source has no record or cannot be reached. The manual-details path is the safe fallback.
- Shopkeeper now uses the same resolution outcomes as Library and adds live UPC printed-text retry plus photo barcode/OCR fallback. It remains a non-mutating quick-check surface; adding or editing a Book continues in Library. Version 31 visual and mobile acceptance is parked, not accepted or rejected.

## Open product boundaries

- Selecting a Book does not yet reliably load a useful cover. Reference-cover enrichment is the next ordered product workstream.
- ISBN metadata enrichment should broaden no-cost lookup evidence without changing the rule that a captured identifier and provider-supplied metadata are separate evidence.
- Cover enrichment and ISBN enrichment may be designed and validated in parallel because both consume read-only metadata, but application-source writing remains one writer at a time.
- Tags may reuse metadata-provider responses where useful, but tag persistence, user assignment, and acceptance remain a separate product model. Provider categories must never silently become canonical user tags.
- Asset lifecycle and complete cover backup remain `NEEDS MORE INFORMATION`; metadata enrichment is not a complete R2-byte backup or restore guarantee.
- Phase F visual items remain held for owner review before implementation: denser Bookcase spines, useful cover detail loading, and titles on missing Shelf positions.

## Orchestration and ownership

- **Planner / Product Owner interface / Site owner:** Quatre.
- **Designer:** Relena — requirements, architecture, product interpretation, acceptance criteria, durable design documentation, and release-boundary review.
- **Engineer:** Kira — inspection, implementation, remediation, tests, builds, packages, and release preparation. Kira has no Sites, credential, save, deployment, publication, or final-handoff authority.
- **Advisory roles:** Cagalli for visual design, Lacus for UX/UI usability, and Athrun for operator testing and test plans.
- All roles are direct children of Quatre and may not create subagents. Quatre assigns and reconciles work directly.
- Preserve one application-source writer at a time. `PLANNER_INBOX.md` is only for unresolved Product Owner decisions; briefs are internal durable contracts, not Product Owner transport.

## Current capacity

- **Five-hour remaining:** 85% after the natural reset and resolver-evidence checkpoint.
- **Weekly remaining:** 43% at the same check.
- **Reset credits:** 3 available and unused.
- **Floors:** target a clean stop by 10% five-hour remaining, never cross 5%; preserve 15% weekly unless the Product Owner explicitly authorizes a bounded exception.

## Current work

| Workstream | State | Next boundary |
| --- | --- | --- |
| Scanner restoration | Accepted in public Version 30 | Retain the live-capture stability note; do not reopen restoration without new evidence |
| Documentation cleanup | Reconciled through Version 31 | Keep the TL;DR ownership footer and explicit next-action handoff in terminal workflow responses |
| Endpoint contract tests | Expanded in pushed unpublished source | Resolver/enrichment checks and 164/164 full checks pass |
| Shopkeeper parity | Published in Version 31; owner review parked | Resume mobile/desktop review only when the Product Owner is ready |
| Repository maintenance | Complete in unpublished `4763cb1026911d4829b2dcb426e342d6f66dfa79` | pnpm is canonical; configured Node 24 build passes; standard wrapper remains host-blocked by its launcher/system Node 18 path |
| Reference-cover enrichment | Read-only evidence reaches the scanner resolver in unpublished `339c3bf74960171be2373f6c99d78c459bc12a2e` | Review the proposed personal-first reference-cover fallback before visible implementation |
| ISBN metadata enrichment | Attributed evidence reaches the scanner resolver in unpublished `339c3bf74960171be2373f6c99d78c459bc12a2e` | Review the proposed compact evidence block before visible implementation |
| Tags | Planned discovery | Determine which provider fields are useful; keep canonical tag decisions separate |
| Complete cover backup | Needs more information | Define inventory, byte coverage, integrity, retention, and recovery claims before implementation |
| Safe import/restore | Planned later | Require dry-run, validation, conflict handling, and recovery contract |
| AI Review | Planned later | Requires stable interchange and proposal/review staging |

## Next milestone

Keep Version 31 owner review parked. Review the [Enrichment Review Contract](ENRICHMENT_REVIEW_CONTRACT.md) before visible implementation. The proposed slice uses the existing Add dialog and a personal-cover-first Book detail fallback; it must not persist a provider cover, silently change a Book, or convert provider subjects into canonical tags.
