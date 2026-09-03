# Version 20 Confirmed-Failure Remediation Plan

**Status:** Complete and saved as Version 21 at `f15ea8144ec277a737f5e491e0276b60555cafb8`; public fingerprint mismatched four markers; controlled republish stopped before tests on unsupported Node 18; new invocation unused
**Baseline:** exact authoritative Sites-managed Version 20 source `6a2191b1b506d171d576cbb6a6b160964595c051`  
**Candidate identity:** final local checkpoint `f15ea8144ec277a737f5e491e0276b60555cafb8`; it must never be called or represented as `80e4c61`

Sei II and Sei III completed the Version 20-based correction through one preserved replacement handoff and bounded recovery sequence. Final checkpoint `f15ea81` remains clean with exactly `app/page.tsx`, `app/globals.css`, and `tests/collection-behavior.test.tsx` relative to Version 20. The first publication invocation returned no deployment identity or success result, and a later public fingerprint retained legacy Gallery/List/Bookshelf behavior rather than the candidate Bookcase/Shelf surfaces. The controlled republish reverified the exact boundary and passed lint, then stopped before focused test execution because Node 18 did not meet the declared Node 22.13+ requirement. Exact live identity remains unknown; the new invocation remains unused and runtime alignment requires a separate decision.

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
