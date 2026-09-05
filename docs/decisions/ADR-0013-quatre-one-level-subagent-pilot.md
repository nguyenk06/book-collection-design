# ADR-0013: Use Quatre as the One-Level CYOA Parent and Site Owner

**Status:** Accepted pilot
**Date:** 2026-09-04

## Context

The separate-chat workflow required the Product Owner to carry commands, briefs, and reports between Planner, Designer, and Engineer contexts. It also allowed Engineer work and final Sites operations to occur in the same role context, increasing coordination, continuity, and authority-boundary overhead.

Version 21 is definitively published, its five anonymous correction markers match, and Product Owner hands-on validation is parked. This clean release boundary is suitable for a CYOA-only workflow pilot.

## Decision

Use Planner — Quatre as the persistent parent, orchestrator, usage governor, and Site-owning agent. Designer — Relena and successor Engineer — Kira are direct Quatre children and may not spawn. Any temporary test/review agent is also a direct Quatre child.

The Product Owner communicates only with Quatre. Quatre routes completion-oriented goals, durable briefs, evidence, and results internally. `PLANNER_INBOX.md` remains only for genuine Product Owner decisions.

Only one application-source writer may be active at a time. Kira may inspect, implement, test, build, package, and prepare a release packet, but cannot invoke Sites tools, obtain Sites credentials, save, preview, deploy, publish, or perform the final Site handoff. Quatre may perform an explicitly authorized Site operation only after Kira supplies a validated release packet and Relena confirms the product/release boundary.

Preserve the 15% five-hour floor, separate longer-period capacity check, `UNKNOWN` Sites capacity when no meter exists, CYOA-only project scope, and explicit Product Owner gates for publication, production/schema/data mutation, migration, credentials, destructive recovery, rollback, restore, and external sharing.

## Consequences

- The Product Owner has one operational interface and no longer transports `!inbox`, `!brief`, reports, briefs, or role prompts.
- Quatre owns convergence and the final Site operation; Kira owns only source-through-release-packet work.
- Routine micro-briefs become completion-oriented goals with durable briefs only where scope/authority persistence is useful.
- Subagent reports return to Quatre and never direct the Product Owner to another agent.
- One-level topology prevents uncontrolled delegation and simplifies ownership.
- Parallel application writers require isolated worktrees and explicit collision review.
- The pilot may be revised or retired after observed use; doing so requires a later documented decision.

## Operational reference

See [CYOA One-Level Codex Subagent Pilot](../ONE_LEVEL_SUBAGENT_PILOT.md).
