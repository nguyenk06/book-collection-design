# Version 20 Confirmed-Failure Remediation Plan

**Status:** Sei III brief accepted and validation partially complete; parked for Planner Decision 1 on generated `tsconfig.tsbuildinfo` under `!99:86`
**Baseline:** exact authoritative Sites-managed Version 20 source `6a2191b1b506d171d576cbb6a6b160964595c051`  
**Candidate identity:** partial local checkpoint `47073db2fbf3a9da62bf19d9e48aa1fcbf28c73b`; it must never be called or represented as `80e4c61`

Decision 1:A's single elevated read-only inspection proved quiescence. Both formerly timed-out tests passed individually; an initial owned 17/17 focused and 93/93 full serial run, lint, and production build then completed. Standalone type checking reported two candidate-page use-before-declaration errors plus existing unrelated project typing gaps. Sei II corrected only those two references and created clean checkpoint `47073db2fbf3a9da62bf19d9e48aa1fcbf28c73b`, still limited to the approved three files. At that exact post-fix checkpoint, owned 17/17 focused and 93/93 full serial suites pass definitively. Lint attribution confirmed that the three errors do not reproduce on exact Version 20 and are candidate-activated. Sei II then consumed three narrow remediation approaches in `app/page.tsx`; the final uncommitted four-addition/four-removal diff reports zero lint errors and two warnings. The private continuity handoff, sanitized Designer report, and actual checkout state were verified, and Sei II retired. Sei III independently verified the same source, context, boundary, dirty state, and preserved attempt count, accepted the superseding brief, and ran its bounded continuation. The inherited dirty state now has definitive zero-error lint, 17/17 focused, and 93/93 full serial evidence. Standalone no-emit type checking reported no candidate-page error but generated untracked `tsconfig.tsbuildinfo`, so the run stopped at the exact candidate-boundary gate. Build, local responsive/accessibility and cover-error QA, final boundary/no-data review, checkpointing, and commit remain unrun. Planner Decision 1 is pending. This is not yet a validated candidate and has no Site or release authority.

## Purpose

Create a new, locally validated candidate that corrects only the five failures confirmed during Product Owner validation of published Version 20. Checkpoint `80e4c61` is unavailable as editable source and is historical design/test evidence only. Its code, manifest, and validation cannot be inherited or reconstructed silently.

## Confirmed scope

1. Make Shopping discoverable through visible mobile root/header navigation while preserving existing authorization and routes.
2. Make a wrapping multi-row Bookcase the primary Bookshelf presentation on desktop and mobile.
3. Retain the existing horizontal shelf as an explicit alternate view.
4. Make missing numbered positions selectable and useful using only verified available canonical number, title, and safe existing metadata; never create synthetic Book records.
5. Show the selected Book's existing personal cover when supported by verified data and route behavior, with an accessible `No cover saved` or load-error fallback.

Items 2, 3, 5, and 8 from the live checklist remain follow-up/hold where previously recorded. This plan must not turn those held scenarios into failures or broaden their validation.

## Source and composition gates

- Obtain source only through the supported authoritative Sites-managed project and require exact Version 20 baseline identity before editing.
- Do not use `book-collection-design`, the deployment-only archive, screenshots, historical diffs, or prose as source substitutes.
- Inspect actual Version 20 composition before naming files. Historical evidence suggests the root page, global styles, and collection behavior tests are shared hotspots, but those filenames are not implementation authority until verified.
- Preserve all published Shopping, M3–M6, Bookshelf, owner-only catalog download, authentication, migration, and data behavior not explicitly changed above.
- Do not restore the broader Phase A/D checkpoint, redesign the full shell, rename Shopping to Shopkeeper, or introduce theme/persistence work.

## Data and security boundary

No schema, migration, D1/R2, import/export contract, authentication, owner-mode, write-lock, purchase, or production-data change is expected or authorized. Missing positions remain presentation objects, not persisted Books. Existing cover authorization and safe fallback behavior remain authoritative.

## Proposed execution slice

- Task class: normal local implementation
- Preferred profile: GPT-5.6 Terra / Medium / Standard
- Estimated five-hour consumption: **8 / 14 / 22 percentage points** low / likely / high
- Minimum starting percentage: **70%**
- Automatic stopping percentage: **15%**
- One active Engineer project: CYOA only

Safe checkpoints:

1. Exact Version 20 source is available, clean, composition/collisions are recorded, and baseline validation passes.
2. Mobile Shopping discovery is implemented and focused validation passes.
3. The coherent Bookshelf group—multi-row primary, horizontal alternate, missing detail, selected cover/fallback—is implemented and focused validation passes.
4. Full tests, lint, build, desktop/mobile local QA, diff/manifest review, evidence, and recoverable commit complete.

If the window approaches 15%, stop at the latest completed checkpoint and report `WAITING FOR RESET`. The Bookshelf group shares state, layout, selection, style, and test surfaces and should not be split mid-convergence merely to consume capacity.

## Required validation

- Baseline and post-change focused collection/navigation tests.
- Full serial test suite, task lint, and production build.
- Desktop and narrow/mobile viewport checks for discoverability, wrapping, explicit view switching, overflow, selection, detail dismissal, focus restoration, and cover success/fallback.
- Keyboard and touch-target review; accessible names/status and no synthetic-record behavior.
- Exact changed-file manifest, clean candidate identity, collision review, and confirmation of zero schema/data/Site/production actions.

Historical `80e4c61` results guide test selection but do not count as validation of the new candidate.

## Explicit exclusions and later gates

No held validation scenarios; scan-accuracy expansion; non-ISBN matching; broad IA/theme/Shopkeeper redesign; tags; AI; assets; schema/data changes; production access; Site save/version; preview; deployment; publication; broad live smoke; retry; rollback; restore; or destructive recovery.

After local completion, Designer intake must decide whether the evidence is acceptable. Candidate preservation, Site save, publication, and Product Owner hands-on validation remain independent later decisions.
