# Planner Inbox

This file contains only unresolved decisions requiring Planner or product-owner input.

It is not a task backlog, technical issue tracker, Engineer progress log, changelog, roadmap, architecture document, or resolved-decision history. Designer owns this queue and removes each item after recording the accepted decision in the appropriate permanent source of truth.

Every item must state the available choices, the practical impact of each, the recommended choice and reason, and a compact response format. Quatre repeats those choices in the Product Owner response rather than requiring the Product Owner to open this file.

## Current Decisions

### Decision 1 — probable-match signed-out boundary

- **Status:** `AWAITING PLANNER`
- **Question:** Should the probable-match correction preserve the existing owner-only scanner boundary or broaden scanning and review to signed-out users?
- **A — Keep the scanner owner-only and clarify the contract (recommended):** remove the inapplicable signed-out probable-match requirement from the durable scanner contract. If authorization expires after an owner begins review, preserve the visible result, perform no write, and offer an explicit sign-in/retry path. Add focused coverage for final-confirmation conflict, failed-PATCH state preservation, cancel/no mutation, and a synchronous repeated-submit guard. This keeps the correction bounded and avoids creating a new public scanner/auth-restoration product surface. Preliminary post-reset estimate: **4–7 weekly points**.
- **B — Add signed-out probable scanning and restoration:** expose or retain scanner access for signed-out users, preserve the probable-match ISBN and matched-Book context through sign-in, and restore the full review afterward. Add the same conflict, failure, cancel, and repeated-submit safety coverage. This materially broadens authentication, navigation, persistence, and privacy behavior. Preliminary post-reset estimate: **8–13 weekly points**.
- **Why owner authority is required:** the choice determines whether scanner audience and sign-in restoration are expanded beyond the current owner-only product boundary.
- **Capacity boundary:** weekly capacity is 18% with a 15% floor and resets on **2026-09-19 at 10:24 AM PDT**. Do not implement either option before the reset. Publication remains a separate later decision.
- **Response:** `1:A` or `1:B`.
