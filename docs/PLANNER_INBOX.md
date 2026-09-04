# Planner Inbox

This file contains only unresolved decisions requiring Planner or product-owner input.

It is not a task backlog, technical issue tracker, Engineer progress log, changelog, roadmap, architecture document, or resolved-decision history. Designer owns this queue and removes each item after recording the accepted decision in the appropriate permanent source of truth.

## Current Decisions

### Decision 1 — Unattributable focused-suite result under supported Node 24

**Context:** Bundled Node `v24.19.0` passed the supported-runtime gate and was selected process-locally without installation or persistent change. Exact candidate/Site/package Gate 1 and scoped lint passed. The focused suite started under Node 24 but returned only the Vitest startup banner with no attributable pass/fail count; 17/17 cannot be claimed. Full tests, build, remaining gates, publication, and public comparison were unrun. Source remains clean, no project-owned process remains, and controlled publication Attempt 2 is still unused at 0.

- **A — Authorize bounded diagnosis with conditional release continuation.** Prepare one brief allowing up to three distinct, non-mutating diagnostic executions under the same bundled Node 24 runtime to classify the missing result as command/output-controller behavior, a reproducible test/process failure, or unresolved. It may use explicit supported timeout/output/serial invocation forms but may not change source, tests, snapshots, dependencies, lockfiles, configuration, or runtime. If an attributable exact focused result passes 17/17 and no drift/process ambiguity remains, continue in the same accepted run through full serial tests, build, package/boundary gates, the still-unused controlled publication Attempt 2, and—only after definitive publication success—the five public markers. Stop on failed Attempt 3, any substantive test failure, ambiguity, drift, or release boundary.
- **B — Authorize diagnosis only.** Use the same bounded three-execution diagnostic scope, then return for another decision regardless of outcome; do not run full tests, build, publication, or public comparison.
- **C — Park.** Preserve exact Version 21 and the unused publication attempt without further test execution or release work.

**Designer recommendation:** `A`. It preserves strict publication gates while avoiding another handoff if the focused suite becomes definitively attributable and passes. Require a fresh usage reading and estimate before brief preparation.

When several decisions are pending, number them and keep each independently understandable. Planner may respond compactly, for example `1: B; 2: A; 3: DEFER`. Do not delay urgent or high-risk decisions for batching.
