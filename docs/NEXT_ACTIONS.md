# Next Actions

This document contains the current execution horizon. Long-term priorities remain in the [Roadmap](ROADMAP.md); verified current truth remains in [Current State](CURRENT_STATE.md).

## Current sprint

- **Workflow state:** M1/M3/M4/M5 and M2 Gates 0–3 are complete within bounded evidence. M4 transport closure is permanently unverifiable. Engineer — Sei completed the P1 source-recovery inspection; M6 is ready for brief acceptance.
- **Queue Mode:** `ENABLED`.
- **Throttle:** `RUN`.
- **Engineer state:** `AVAILABLE` for M6 at its safe pre-`!brief` boundary.
- **Next owner:** `ENGINEER` — in the continuing source-bearing Engineer — Sei context, revalidate the M6 acceptance conditions and run `!brief`.
- **Usage:** Last reported reading was approximately 80% before the bounded cycle; 30% remaining is the protected stopping reserve. Obtain a fresh reading before resumed implementation when available.

Gate 3 was invoked exactly once. Its immediate response reported Shopping schema completion and zero foreign-key issues. The sequence stopped before Gate 4, so production schema and preservation invariants remain unverified. Gate 3 cannot be retried.

## Ready for M6 brief acceptance

The read-only recovery inspection found all six reported M5 files in the original cumulative editable working source. Current focused, layered, and full serial tests, task lint, build, `git diff --check`, and no-write evidence passed. Published and saved Version 19 remains the clean base; cumulative M3–M5, Bookshelf, and Shopping work remains unsaved/unpublished and separate from the saved Version 17 Shopping foundation. No source transfer or reconstruction is required.

Resume M6 at its recorded safe pre-`!brief` boundary:

1. Continue in the verified source-bearing Engineer — Sei context.
2. Revalidate source composition, collision separation, dependencies, usage reserve, and clean-stop capacity.
3. Run `!brief` and accept M6 only if all eligibility checks pass.
4. Implement and validate only the local/disposable, owner-only downloadable catalog format-v1 UI described by the existing brief.

M6 excludes Site save/publication, production access/export, bridge-export replacement, schema or migration changes, import/restore, image bytes, Businesses/Purchases, Shopping changes, and backup claims. A later user checkpoint and any activation remain separately gated.

## Closed production gate

Gate 4 verification requires separate explicit Product Owner approval. It is not part of M6 or the active continuation. No verification, correction, retry, Shopping publication, live checklist, smoke test, rollback, restore, or destructive recovery is currently authorized.

## Other workstreams

- M4 bounded Bookshelf is complete locally, not planned implementation work. It remains unsaved/unpublished and requires a Product Owner checkpoint before activation.
- M5 catalog export foundation is complete locally. The private Gate 2 bridge export and local M5 catalog export are useful but neither is a complete production backup; both exclude R2 bytes.
- Mutable import, AI Review, reference-cover enrichment, Tags, and dedicated analysis remain behind their accepted dependencies and are not current queue work.

## Resume and stopping rules

- A parked task resumes without reinitialization solely for the resolved condition, but affected assumptions, source, dependencies, collisions, usage, and tests must be revalidated.
- A blocked task does not stop unrelated eligible work. In the current batch, no unrelated eligible task remains.
- Stop for missing authority, source ambiguity, collision risk, failed validation, private-data leakage, mutation, production access, or approach to the protected reserve.
- Unprefixed words and abbreviations are normal conversation and do not trigger workflow behavior.
