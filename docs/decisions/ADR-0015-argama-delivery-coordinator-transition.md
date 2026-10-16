# ADR-0015: Separate ChatGPT Product Planning from Codex Delivery Coordination

**Status:** Accepted
**Date:** 2026-10-15
**Supersedes:** [ADR-0013](ADR-0013-quatre-one-level-subagent-pilot.md) for current parent identity and routing only

## Context

ADR-0013 established a successful one-level CYOA Codex pilot under the name Quatre. The same name later came to identify the separate ChatGPT CYOA Product Planner. Using Quatre for both product planning and Codex delivery coordination obscured which role owned product direction, Codex children, execution routing, usage governance, and Sites operations.

The project remains at public Version 34 with its release identity, pending Product Owner review, accepted roadmap, evidence, attempts, checkpoints, and child-agent continuity intact. The correction is an identity and responsibility clarification, not a reset or product milestone.

## Decision

Separate the two layers permanently:

- **ChatGPT Product Planner — Quatre** is external to the Codex hierarchy. Quatre owns product planning, strategy, roadmap interpretation, decision framing, scope refinement, release-closure recommendations, and preparation of Product Owner-approved delivery goals. Quatre does not manage Codex children, modify application source, operate Sites, deploy, or publish.
- **Codex Delivery Coordinator — Argama** is the persistent one-level Codex parent, Product Owner execution interface, usage governor, goal and queue manager, evidence reconciler, Site-owning agent, and final release-handoff coordinator.
- **Relena, Kira, Athrun, Lacus, and Cagalli** remain direct non-delegating children of Argama. Their existing context, evidence, authority boundaries, attempts, and checkpoints continue unchanged.
- The Product Owner remains the boundary between ChatGPT product planning and Codex delivery. The Product Owner sends Product Owner-approved goals from Quatre to Argama and receives one consolidated delivery result from Argama. The Product Owner does not transport routine briefs, reports, or messages among Argama's children.
- Kira remains the sole application-source writer when activated. Only Argama may perform a later explicitly Product-Owner-authorized Sites operation after validated Kira evidence and Relena release-boundary confirmation.

`PLANNER_INBOX.md` remains reserved for genuine unresolved Product Owner decisions. If delivery evidence reveals a material product choice, Argama presents the choices and consequences to the Product Owner; the Product Owner may take the finding to ChatGPT Quatre for product planning.

## Consequences

- Current workflow documents, startup prompts, briefs, handoffs, footers, usage governance, and routing name Argama as the Codex parent and Site owner.
- Child terminal reports use `NEXT OWNER: DELIVERY COORDINATOR — ARGAMA`.
- Argama's consolidated terminal reports use `NEXT OWNER: PRODUCT OWNER`, or the established parallel-owner form when independent Codex responsibilities remain active.
- Historical records continue to attribute earlier Codex parent work to Quatre. This decision does not imply that Argama performed past work.
- The public Version 34 state, roadmap order, held Phase F boundary, shelved Shopkeeper state, production gates, and all existing evidence remain unchanged.

## Operational reference

See [CYOA One-Level Codex Subagent Pilot](../ONE_LEVEL_SUBAGENT_PILOT.md) and [Delivery Coordinator startup](../../templates/DELIVERY_COORDINATOR_STARTUP.md).
