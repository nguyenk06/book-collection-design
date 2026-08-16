# Planner Inbox

This file contains only unresolved decisions requiring Planner or product-owner input.

It is not a task backlog, technical issue tracker, Engineer progress log, changelog, roadmap, architecture document, or resolved-decision history. Designer owns this queue and removes each item after recording the accepted decision in the appropriate permanent source of truth.

## Current Decisions

### M5 editable-source recovery disposition

- **Status:** `AWAITING PLANNER`
- **Raised by:** Designer after cross-workspace communication audit
- **Decision question:** Should the project first recover the original M5 Site editing context, or authorize a clean local reconstruction when that context cannot be recovered?
- **Why Planner authority is required:** M5 was completed only in an unsaved, uncommitted dirty Site worktree. The replacement Engineer context exposes Site/version metadata but not that working copy. Reconstructing M5 would repeat completed implementation and validation work and requires an explicit rework disposition; M6 cannot be accepted until one path supplies an inspectable cumulative M5 source.
- **Option A — Recover context first (recommended):** Product Owner reopens or assigns the original M5 Engineer/Sites chat or workspace, then Engineer verifies the six reported M5 files, source composition, tests, and collision boundaries. If the source is absent, return for Option B rather than improvising reconstruction.
- **Option B — Authorize reconstruction if unavailable:** Designer prepares a bounded local-only M5 source-reconstruction brief from the accepted contract and completion evidence. Engineer rebuilds and fully revalidates M5 before M6 intake. No Site save, publication, production access, schema activation, or release authority follows.
- **Impact:** A may clear the board with a context reassignment and no rework. B consumes additional engineering capacity but creates an inspectable supported source baseline.
- **Response:** `Decision: A` or `Decision: B`

When several decisions are pending, number them and keep each independently understandable. Planner may respond compactly, for example `1: B; 2: A; 3: DEFER`. Do not delay urgent or high-risk decisions for batching.
