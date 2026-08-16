# Next Actions

This document contains the current execution horizon. Long-term priorities remain in the [Roadmap](ROADMAP.md); verified current truth remains in [Current State](CURRENT_STATE.md).

## Current sprint

- **Workflow state:** M1/M3/M4/M5/M6 and M2 Gates 0–3 are complete within bounded evidence. M4 transport closure is permanently unverifiable. M6 is locally validated, unsaved, and unpublished.
- **Queue Mode:** `ENABLED`.
- **Throttle:** `DRAIN`; the completed cycle is preserved and no new intake is allowed before authorization.
- **Engineer state:** `PAUSED`; the approved local batch is complete and no eligible brief remains.
- **Next owner:** `EXTERNAL/WAIT` — Product Owner may issue `!run` to activate the approved P1/P2 read-only batch.
- **Usage:** Approximately 50% remains. The proposed 8–12 point batch expects 38–42% remaining; 30% is the protected floor, not a consumption target.

Gate 3 was invoked exactly once. Its immediate response reported Shopping schema completion and zero foreign-key issues. The sequence stopped before Gate 4, so production schema and preservation invariants remain unverified. Gate 3 cannot be retried.

## M6 locally complete

Engineer added an isolated owner-only `/catalog-download` route and read-only `/api/catalog-export` endpoint over M5, with contract validation, safe download behavior, explicit scope/backup limitations, and accessible loading, success, empty, error, retry, focus, and announcement states. Five M6 files were added without changing Version 19 administration, Shopping, M3–M5 services, schema, migrations, import, or dependencies.

Validation passed:

- 8/8 focused M6 tests and 160/160 full serial tests.
- Task lint, production build, and diff/whitespace checks.
- Anonymous and non-owner API denial, owner page gating, read-only query evidence, duplicate-click protection, safe filenames, and accessible state behavior.

M6 remains in the cumulative dirty local source. Saved and published Site versions remain Version 19. A later Product Owner checkpoint and any preview/save/activation remain separately gated.

## Proposed next batch

See [Approved Next Execution Batch](NEXT_BATCH_PLAN.md). Final priority is:

1. P1 M2 Gate 4 read-only production verification: 3–5 points.
2. P2 read-only Sites checkpoint/preview feasibility plus candidate composition/preservation assessment: 5–7 points.

Shared overhead yields an estimated 8–12 points total. No fallback implementation is proposed. Both briefs are queued but ineligible under `DRAIN`; only explicit `!run` activates intake. P2 follows P1's completion or automatic-stop report unless P1 identifies a cross-cutting safety or identity conflict.

## Closed production gate

Gate 4 verification requires separate explicit Product Owner approval. It is not part of M6 or the active continuation. No verification, correction, retry, Shopping publication, live checklist, smoke test, rollback, restore, or destructive recovery is currently authorized.

## Other workstreams

- M4 bounded Bookshelf is complete locally, not planned implementation work. It remains unsaved/unpublished and requires a Product Owner checkpoint before activation.
- M5 catalog export foundation is complete locally. The private Gate 2 bridge export and local M5 catalog export are useful but neither is a complete production backup; both exclude R2 bytes.
- Mutable import, AI Review, reference-cover enrichment, Tags, and dedicated analysis remain behind their accepted dependencies and are not current queue work.

## Resume and stopping rules

- A parked task resumes without reinitialization solely for the resolved condition, but affected assumptions, source, dependencies, collisions, usage, and tests must be revalidated.
- A blocked task does not stop unrelated eligible work. The current approved batch is complete and no unrelated eligible task remains.
- Stop for missing authority, source ambiguity, collision risk, failed validation, private-data leakage, mutation, production access, or approach to the protected reserve.
- Unprefixed words and abbreviations are normal conversation and do not trigger workflow behavior.
