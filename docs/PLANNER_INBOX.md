# Planner Inbox

This file contains only unresolved decisions requiring Planner or product-owner input.

It is not a task backlog, technical issue tracker, Engineer progress log, changelog, roadmap, architecture document, or resolved-decision history. Designer owns this queue and removes each item after recording the accepted decision in the appropriate permanent source of truth.

## Current Decisions

### Decision 1 — Full serial-suite evidence after output/controller loss

**Context:** Focused diagnostic Attempt 2 definitively passed 17/17 under bundled Node 24 with exit 0 and clean source/process state. The subsequent full serial execution emitted test output but no final attributable summary/count, so it cannot establish fresh 93/93. Earlier unchanged-candidate evidence includes attributable 93/93, but the active release brief required a fresh full count. Build, package/boundary gates, publication, and public comparison were unrun. Controlled publication Attempt 2 remains unused at 0.

- **A — Authorize up to two additional non-mutating full-suite attribution executions with conditional continuation.** Treat the reported unattributable full-suite run as Attempt 1 of at most three. Attempt 2 may use a supported concise reporter/owned-process output-capture form under the same Node 24 runtime; Attempt 3 may isolate only the same installed local test binary from the wrapper/controller. Do not change source, tests, snapshots, dependencies, lockfiles, configuration, or runtime. On a definitive attributable 93/93 pass with clean process/source state, continue in the same run through build, package/boundary gates, controlled publication Attempt 2, and the five public markers only after definitive publication success. Stop on a real test failure, unresolved Attempt 3, drift, ambiguity, or release boundary.
- **B — Accept retained full-suite evidence for this unchanged candidate.** Treat the earlier attributable 93/93 plus current focused 17/17, Node 24 lint, exact identity, and clean-state evidence as sufficient; prepare a brief that starts with build/package/boundary revalidation and retains the unused controlled publication Attempt 2. This explicitly waives a fresh attributable full-suite count.
- **C — Park.** Preserve the exact candidate and unused publication attempt without further validation or release work.

**Designer recommendation:** `A`. It preserves the fresh full-suite gate while limiting the known output/controller diagnosis to two more non-mutating executions. Require fresh usage before brief preparation.

When several decisions are pending, number them and keep each independently understandable. Planner may respond compactly, for example `1: B; 2: A; 3: DEFER`. Do not delay urgent or high-risk decisions for batching.
