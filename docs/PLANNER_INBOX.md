# Planner Inbox

This file contains only unresolved decisions requiring Planner or product-owner input.

It is not a task backlog, technical issue tracker, Engineer progress log, changelog, roadmap, architecture document, or resolved-decision history. Designer owns this queue and removes each item after recording the accepted decision in the appropriate permanent source of truth.

## Current Decisions

### 1. Approve the proposed Engineer batch and issue `RUN`?

**Context:** Product Owner reports approximately 80% usage remaining. The protected reserve is 30% remaining. Designer proposes a bounded batch estimated to consume 24–38 percentage points and finish with approximately 42–56% remaining:

1. M2 Gate 3: one already approved guarded schema-activation invocation, with its existing abort safeguards; preserve the immediate response and stop the production sequence before Gate 4.
2. M4: close the missing acceptance/transport lifecycle only from factual existing evidence; report inability to verify rather than recreating or inferring evidence.
3. M6: implement, remediate, fully validate, and report the local owner-only catalog format-v1 download UI. No Site, production, schema, import, or publication authority.

Gate 3 and M6 do not share a source-editing window: Gate 3 must report and stop before local M6 intake. M6 must preserve the published Version 19 administration surface and isolated Shopping candidate. If one stream blocks, Engineer reports it and moves to the next independently eligible, non-conflicting stream. Gate 4 and every later production action remain closed.

- **A — Approve and issue `RUN` for this batch.** Engineer may autonomously order and complete the three priorities within their briefs and recorded gates, stopping before 30% remaining or earlier for a safe handoff.
- **B — Revise or defer.** Keep throttle `STOP` and state the desired change.

**Designer recommendation:** A. The high estimate leaves a 12-point cushion above the protected reserve, and M6 supplies useful independent local work after the production sequence stops.

**Estimate basis and fallback:** Gate 3 is 4–7 points, factual M4 closure 1–2, and M6 implementation/remediation/full validation/transport 19–29. Gate 3 completion or automatic abort supplies the transition report; either way, the production sequence stops before Gate 4 and Engineer can move to M4/M6. If M6 blocks, Engineer preserves the blocker and may perform only another independently eligible, non-conflicting brief already inside this approved batch; none currently follows M6, so the safe outcome is a clean handoff rather than speculative work.

Approval also activates the documented park-and-resume rule: a task-level question is recorded as `WAITING FOR ANSWER` and does not interrupt other eligible batch work. It does not weaken any production or risk gate.

When several decisions are pending, number them and keep each independently understandable. Planner may respond compactly, for example `1: B; 2: A; 3: DEFER`. Do not delay urgent or high-risk decisions for batching.
