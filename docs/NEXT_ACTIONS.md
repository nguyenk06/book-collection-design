# Next Actions

This document contains the current execution horizon. Long-term priorities remain in the [Roadmap](ROADMAP.md); verified current truth remains in [Current State](CURRENT_STATE.md).

## Current sprint

- **Workflow state:** M1/M3/M4/M5 and M2 Gates 0–3 are complete within bounded evidence. M4 transport closure is permanently unverifiable. M6 is parked before acceptance.
- **Queue Mode:** `ENABLED`.
- **Throttle:** `RUN`.
- **Engineer state:** `BLOCKED`; no independently eligible approved task remains.
- **Next owner:** `EXTERNAL/WAIT` — Product Owner reopens or assigns the original M5 Engineer/Sites context for read-only recovery inspection.
- **Usage:** Last reported reading was approximately 80% before the bounded cycle; 30% remaining is the protected stopping reserve. Obtain a fresh reading before resumed implementation when available.

Gate 3 was invoked exactly once. Its immediate response reported Shopping schema completion and zero foreign-key issues. The sequence stopped before Gate 4, so production schema and preservation invariants remain unverified. Gate 3 cannot be retried.

## Ready when source is available

Planner selected recovery first. Reopen or assign the original M5 Engineer/Sites chat or workspace, because M5 completion evidence states that its six changed files existed only in an unsaved, uncommitted dirty Site worktree. Engineer then verifies `app/catalog-export.ts`, `db/schema.ts`, `db/bridge-schema.ts`, `app/api/books/route.ts`, `shopping-migrations/0006_book_stable_ids.sql`, and `tests/catalog-export.test.ts`; confirms source composition, prior test reproducibility, and collision separation from Version 19 and the isolated Shopping candidate; and reports the result without changing source. If any required source is unavailable, stop and return for an explicit reconstruction decision. Reconstruction is not currently authorized.

Resume M6 at its recorded safe pre-`!brief` boundary:

1. Identify the exact cumulative editable M5 source in the supported Sites context.
2. Verify its composition and collision separation from Version 19 and the isolated Shopping candidate.
3. Revalidate M5 tests, dependencies, usage reserve, and clean-stop capacity.
4. Run `!brief` and accept M6 only if all eligibility checks pass.
5. Implement and validate only the local/disposable, owner-only downloadable catalog format-v1 UI described by the existing brief.

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
