# Planner Inbox

This file contains only unresolved decisions requiring Planner or product-owner input.

It is not a task backlog, technical issue tracker, Engineer progress log, changelog, roadmap, architecture document, or resolved-decision history. Designer owns this queue and removes each item after recording the accepted decision in the appropriate permanent source of truth.

## Current Decisions

### Decision 1 — Supported runtime alignment for controlled Version 21 republish

**Context:** Exact candidate/Site/session/package/collision Gate 1 and scoped lint passed. The focused suite failed before executing any test because the available runtime was Node `v18.18.0`, while the candidate declares Node `>=22.13.0`; Node 18 lacks the required `node:util` `styleText` export. Full tests, build, remaining package/boundary gates, publication, and public comparison were unrun. The exact candidate remains clean and controlled publication Attempt 2 remains unused at 0 invocations. No runtime, dependency, source, configuration, Site, or production change occurred.

- **A — Authorize a bounded existing-supported-runtime alignment and republish-resume brief.** Sei may inspect the already configured/available project runtimes read-only and select an existing supported Node runtime meeting `>=22.13.0`. No installation, runtime upgrade, dependency update, lockfile/configuration/source/test change, or system-wide change is permitted. If a compliant supported runtime is unavailable or ambiguous, stop. If available, rerun the complete lint/focused/full/build/package/boundary gates in that one consistent runtime and retain the previously authorized one new publication invocation only after every gate passes. Definitive success may be followed only by the same five-marker public comparison. Any failure or ambiguity stops without another attempt.
- **B — Park.** Preserve exact Version 21 and the unused publication invocation; perform no runtime or release action until a compliant supported runtime is supplied through an approved path.

**Designer recommendation:** `A`. The failure occurred before test execution and is attributable to a declared runtime mismatch, while the exact source/package boundary remains unchanged. Require a fresh usage reading before brief preparation.

When several decisions are pending, number them and keep each independently understandable. Planner may respond compactly, for example `1: B; 2: A; 3: DEFER`. Do not delay urgent or high-risk decisions for batching.
