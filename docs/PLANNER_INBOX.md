# Planner Inbox

This file contains only unresolved decisions requiring Planner or product-owner input.

It is not a task backlog, technical issue tracker, Engineer progress log, changelog, roadmap, architecture document, or resolved-decision history. Designer owns this queue and removes each item after recording the accepted decision in the appropriate permanent source of truth.

## Current Decisions

### Purchase price contract

- **Status:** `AWAITING PLANNER`
- **Raised by:** Designer from P2 Shopping contract blocker
- **Decision question:** Should Purchase price remain required for current Shopping capture, or should persistence/API be changed to allow an unknown price?
- **Why Planner authority is required:** Accepted documentation described purchase and sticker prices as independently nullable, but the validated migration/API require purchase price. Resolving this changes either product requirements or the persistence/API contract.
- **Option A — Require purchase price:** Align UI and permanent design to the validated implementation. Purchase creation cannot be submitted without a non-negative price.
- **Option B — Allow unknown purchase price:** Preserve the earlier accepted nullable direction and authorize a separately validated local schema/API/bridge adjustment before Purchase capture converges.
- **Designer recommendation:** Option A for this bounded sprint. It avoids widening schema/migration scope and reaches a coherent UI milestone sooner; zero must never represent unknown.
- **Impact:** Option A permits a narrow UI continuation brief. Option B requires broader persistence/API and migration-bridge work before UI convergence. Neither option authorizes production or Site saving/publication.
- **Response format:** `Decision: A` or `Decision: B`

When several decisions are pending, number them and keep each independently understandable. Planner may respond compactly, for example `1: B; 2: A; 3: DEFER`. Do not delay urgent or high-risk decisions for batching.
