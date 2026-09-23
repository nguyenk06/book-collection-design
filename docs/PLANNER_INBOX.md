# Planner Inbox

This file contains only unresolved decisions requiring Planner or product-owner input.

It is not a task backlog, technical issue tracker, Engineer progress log, changelog, roadmap, architecture document, or resolved-decision history. Designer owns this queue and removes each item after recording the accepted decision in the appropriate permanent source of truth.

Every item must state the available choices, the practical impact of each, the recommended choice and reason, and a compact response format. Quatre repeats those choices in the Product Owner response rather than requiring the Product Owner to open this file.

## Current Decisions

### Decision 1 — Publish the accepted Library scanner-entry cleanup?

Exact local checkpoint `d251980c15afae93663adc53a405c42c5d4b6f31` has release-boundary `PASS`. It consolidates scanner entry into one public hero action across My Library, CYOA, and Redwall, removes duplicate toolbar controls and discoverable Shopkeeper links, retains `/shopping` only as an unlinked compatibility route, and preserves scanner/auth behavior. Public production remains Version 33 at `013db3b5d747870723362ae430ffe923e32d8ba6`.

- **A — Authorize release preparation and publication (recommended):** Kira may add the next release identity and revalidate the exact release source; after clean evidence, Quatre may perform the public save/deployment. This exposes the consistent Library scanner entry for owner review. Desktop/mobile owner review should inspect hero spacing and hierarchy after publication.
- **B — Hold Version 33:** keep the accepted candidate local and make no release or Site change. The current public navigation and duplicate scanner-entry presentation remain until a later authorization.

**Why A:** the candidate is bounded to seven app/test paths, passed 14 files/182 tests plus build/lint/diff/worktree checks, and changes navigation placement without altering scanner or authentication behavior.

**Reply:** `1:A` or `1:B`.
