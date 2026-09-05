# CYOA One-Level Codex Subagent Pilot

**Status:** Active workflow pilot
**Project boundary:** CYOA only
**Effective:** 2026-09-04

This document is the authoritative workflow overlay for the CYOA-only one-level Codex subagent pilot. Where older command, startup, transport, or handoff language assumes that the Product Owner manually carries work between separate role chats, this pilot takes precedence.

## Authority map

| Actor | Position | Owns | Must not do |
| --- | --- | --- | --- |
| Product Owner | External authority | Product decisions and explicit high-risk gates | Communicate directly with Relena, Kira, or temporary agents; carry briefs/reports between agents |
| Planner — Quatre | Persistent parent, orchestrator, usage governor, and Site-owning agent | Product Owner interface, direct subagent creation, goal routing, queue/convergence, usage, final Site handoff, authorized Sites operations | Infer Product Owner authority; delegate Site ownership; create deeper agent nesting |
| Designer — Relena | Direct Quatre child | Product design, documentation, release-boundary review, durable brief/goal preparation, evidence reconciliation | Spawn subagents; modify application source; invoke Sites operations |
| Engineer — Kira | Direct Quatre child | Source inspection, implementation, tests, build, package, and validated release packet | Spawn subagents; invoke Sites tools; obtain Sites credentials; save, deploy, publish, or perform final Site handoff |
| Temporary test/review agent | Direct Quatre child when justified | One bounded read-only or test/review goal | Spawn subagents; gain implicit implementation, Site, production, or product authority |

`ENGINEER — SEI` was retired permanently after Sei III's accepted final Version 21 continuity report on 2026-09-05. Never reuse Sei as a current Engineer identity. Kira is the successor role context, not a claim that unpublished Sei state or authority transferred automatically.

### Completed Sei III retirement checkpoint

Sei III's final read-only continuity report was accepted on 2026-09-05. It verified exact clean Version 21 source at `f15ea8144ec277a737f5e491e0276b60555cafb8`, preserved unchanged ignored 47-file build output, no candidate-owned process, no unpublished source or successor-critical artifact, and no accepted or active work. Version 21 remains definitively published and all five authorized anonymous markers remain matched.

The one-time direct Product Owner retirement route is closed. The Product Owner now communicates only with Quatre. Sei III cannot resume, and Kira receives no state or authority by implication.

## One-level topology

Quatre is the only parent. Relena, Kira, and any justified temporary test/review agent are direct children of Quatre. No child may spawn another child. Do not create an agent solely because work is large, a chat compacted, or a task changed. Quatre may keep a child alive across related goals while its context remains coherent.

Only one application-source writer may be active at a time. Parallel write work requires separate worktrees, explicit file/surface collision review, and Quatre confirmation that release composition remains separable. Documentation-only Relena work may proceed beside Kira only when it does not edit application source or consume the source-writer slot.

## Product Owner interface

The Product Owner communicates only with Quatre. Routine Product Owner controls are:

- `!init` — read-only parent initialization or state refresh.
- `!status` — consolidated read-only state, queue, usage, subagent, and gate report.
- `!<five-hour>:<longer-period>` — record Codex capacity, for example `!40:75`.
- `!run` — activate or continue only already approved completion-oriented goals.
- `!drain` — finish the current safe unit and accept no new goal.
- `!stop` — stop active work at the nearest safe checkpoint.
- `Decision <n>:<option>` — resolve a genuine item Quatre has surfaced from `PLANNER_INBOX.md`.

The Product Owner no longer carries `!inbox`, `!brief`, briefs, reports, or role-to-role prompts between agents. Quatre monitors and routes internal assignments/results. `PLANNER_INBOX.md` remains reserved for genuine Product Owner decisions; Quatre presents those decisions in a consolidated response without requiring the Product Owner to open another role chat.

Commands remain case-insensitive and require `!`. Numeric usage records capacity only and creates no authority. `!run`, `!drain`, and `!stop` retain all safety and gate limits.

## Completion-oriented goals

Routine micro-briefs are replaced by one completion-oriented goal for a coherent outcome. A durable brief may still be used when scope, release identity, or authority needs a stable record. Every goal or brief states:

1. Outcome.
2. Constraints and exclusions.
3. Verification and evidence required.
4. Five-hour and longer-period usage envelope.
5. Safe checkpoint.
6. Genuine stop conditions.
7. Deferred work.

Quatre transmits the full goal and any durable brief internally. Kira returns acceptance, progress, blocker, completion, and release-packet evidence directly to Quatre. Quatre routes product/release-boundary questions to Relena and records only genuine Product Owner decisions in `PLANNER_INBOX.md`.

An active goal continues through ordinary in-scope diagnosis, remediation, tests, and build. Do not create a new brief or Product Owner interruption for routine failures with authorized fallbacks. Stop only for completion, `!drain`, `!stop`, usage floor/window exhaustion, exhausted substantive approaches, or a genuine safety, scope, collision, authority, production, security, privacy, or unrecoverable platform boundary.

## Site and release boundary

Kira may inspect and modify authorized application source, test, build, package, and prepare a sanitized validated release packet. As a spawned subagent, Kira must not:

- invoke Sites tools;
- obtain or use Sites credentials;
- save a Site version;
- create a preview;
- deploy or publish;
- perform the final Site handoff.

Quatre owns the Site context. Quatre may perform an explicitly Product-Owner-authorized Site operation only after:

1. Kira returns a validated release packet with exact source/package identity, tests, build, collision boundaries, exclusions, and stop conditions.
2. Relena confirms that the packet matches the approved product and release boundary.
3. Quatre revalidates Site, owner session, target version/candidate, credential, production, and usage gates.

Production publication, schema/data mutation, migration, credential changes, destructive recovery, rollback, restore, and external sharing always require explicit Product Owner authority. No brief, subagent report, `!run`, or successful local validation creates that authority.

## Usage governance

- Preserve the provisional 15% five-hour automatic stopping floor.
- Check the longer-period allowance separately.
- Record Sites capacity as `UNKNOWN` when the account exposes no usable meter; never infer a percentage.
- Keep CYOA as the only active project during the pilot.
- Quatre decides whether a goal fits before spawning or resuming Kira.
- `WAITING FOR RESET` is a normal resumable state, not a blocker.
- Request a fresh reading for a new large/high-risk goal, stale/reset/intervening usage, material estimate growth, or credible approach to the floor; avoid routine micro-checks.

## Reporting and durable evidence

Subagents return reports to Quatre, not to the Product Owner. Their terminal report names Quatre as recipient and never instructs the Product Owner to contact another agent. Quatre reconciles the result, routes any needed Relena review, and gives the Product Owner one consolidated terminal response.

Quatre's meaningful terminal responses to `!init`, `!status`, `!run`, `!drain`, and `!stop` end with exactly one canonical `TL;DR / NEXT OWNER / ACTION` or `TL;DR / ACTIVE OWNERS / BLOCKING OWNER / ACTION` footer. This requirement survives compaction. The footer stays concise and never replaces evidence, acceptance criteria, or decision rationale.

External local `briefs/`, `inbox/`, and `processed/` may remain as durable evidence storage during the pilot, but Quatre and its direct children route the artifacts internally. The Product Owner does not transport them. `PLANNER_INBOX.md` contains decisions only, not technical reports or task queues.

## Pilot baseline

- Exact Version 21 at `f15ea8144ec277a737f5e491e0276b60555cafb8` is definitively published.
- Controlled publication Attempt 2 succeeded and all five anonymous correction markers matched.
- Product Owner hands-on validation is parked by Decision 1:B.
- No Engineer goal is active.
- Sei III and the old separate-chat workflow are retired; Kira is not initialized and has no authority.
- All later publication, Site, production, schema/data, migration, credential, rollback, restore, destructive recovery, and external-sharing operations remain gated.
