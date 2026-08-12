# Planner Inbox

This file contains only unresolved decisions requiring Planner or product-owner input.

It is not a task backlog, technical issue tracker, Engineer progress log, changelog, roadmap, architecture document, or resolved-decision history. Designer owns this queue and removes each item after recording the accepted decision in the appropriate permanent source of truth.

## Current Decisions

### Shopping validation-environment direction

- **Status:** `AWAITING PLANNER`
- **Raised by:** Designer from accepted M1 feasibility evidence
- **Decision question:** Should Designer define a separately isolated validation Site for future approval, or defer Shopping hands-on validation until Sites exposes a supported safe preview?
- **Why Planner authority is required:** A separate Site adds architecture, access-policy, binding-isolation, setup, and maintenance scope; the existing Site exposes no verified private, isolated, non-production runnable option.
- **Option A — Define separate validation Site:** Designer specifies a distinct non-production Site, isolated bindings/data, owner-only access, lifecycle, and cleanup boundaries. This decision authorizes design only; creation still requires a later explicit action gate.
- **Option B — Defer validation environment:** Keep M2 blocked and prohibit Shopping activation until Sites provides a supported safe preview or Planner revisits the architecture.
- **Designer recommendation:** A, if near-term Shopping hands-on validation remains a priority; otherwise B avoids new operational scope.
- **Impact:** M2 and Shopping activation remain blocked either until the separate environment is designed and separately authorized or until a supported platform option exists. M3 continues independently.
- **Response:** `Decision: A` or `Decision: B`

When several decisions are pending, number them and keep each independently understandable. Planner may respond compactly, for example `1: B; 2: A; 3: DEFER`. Do not delay urgent or high-risk decisions for batching.
