# Documentation Rules

This document is the standing documentation policy for the repository.

The active [CYOA One-Level Codex Subagent Pilot](ONE_LEVEL_SUBAGENT_PILOT.md) governs role topology and routing. Quatre is the persistent parent and Site owner; Relena and Kira are direct non-delegating children. The Product Owner communicates only with Quatre.

## Repository Purpose

This repository is the permanent design authority for the Book Collection System. It documents:

- Vision
- Architecture
- Database
- Roadmap
- Decisions
- Current project state

It is not the implementation repository.

It is also not a role-to-role transport workspace. GitHub contains durable high-level product documentation, architecture, roadmap/milestones, accepted decisions, workflow run rules, and the Designer-maintained Planner Inbox. Engineer goals, briefs, reports, acceptance records, release packets, and handoffs remain internal/local artifacts routed by Quatre; the Product Owner does not carry them.

## Documentation Philosophy

Documents should explain why a decision exists, what it establishes, and when it applies. Prefer architecture over code and omit implementation detail that does not clarify a durable constraint.

## Source of Truth

- Current implementation describes current behavior.
- Design documents describe intended direction.
- If implementation and design disagree, document the discrepancy; do not silently change the design.

## Documentation Style

Prefer:

- Headings
- Tables
- Bullet lists
- Mermaid diagrams
- Cross-links
- Architecture Decision Records

Avoid unnecessary narrative. Keep documents concise and link to existing explanations instead of repeating them.

## Current vs Future

Always distinguish:

- **Verified Current State:** Observed in the reviewed implementation or production system.
- **Accepted Direction:** Approved architecture or product direction not necessarily implemented.
- **Future Proposal:** Unaccepted or exploratory work.

Never present planned work as implemented.

## Sanitization

Before committing documentation, verify that it contains no sensitive information.

Never publish:

- API keys, tokens, passwords, secrets, or cookies.
- Environment variables or connection strings.
- Internal account identifiers.
- Private bucket names.
- Machine-specific paths or personal information.
- Operational deployment details not required for architecture.
- Exact production URLs unless intentionally documented.
- Exact commit hashes unless required for historical reference.

Generalize operational details whenever practical.

## Roadmap Rules

[ROADMAP.md](ROADMAP.md) represents long-term product priorities.

- Do not reorder items merely because implementation would be easier.
- Recommend changes only with explicit architectural or product justification.
- Keep completed milestones visible.
- Keep immediately actionable work in [NEXT_ACTIONS.md](NEXT_ACTIONS.md).

## Planner Visibility

Quatre uses permanent design documentation plus internally routed subagent evidence as the primary project visibility layer:

1. [PLANNER_INBOX.md](PLANNER_INBOX.md) — what requires a decision.
2. [PROJECT_DASHBOARD.md](PROJECT_DASHBOARD.md) — concise derived visual progress; coarse estimates only.
3. [CURRENT_STATE.md](CURRENT_STATE.md) — what is true now and the exact operational authority.
4. [NEXT_ACTIONS.md](NEXT_ACTIONS.md) — what should happen next.
5. [CHANGELOG.md](CHANGELOG.md) — which major milestones and state transitions occurred.
6. [ROADMAP.md](ROADMAP.md) — where the project is going.

The dashboard never replaces Current State, evidence, briefs, or gate reports. Designer updates it after accepting Engineer completion evidence, changing a milestone state, or changing roadmap scope, without deriving false precision from task counts.

Temporary handoffs are local transport and evidence. They must not be committed to this repository and do not replace these documents.

The public [Engineer Execution Contract](ENGINEER_EXECUTION_CONTRACT.md) is the concise authority for Kira's active-goal continuation and terminal stopping conditions. The [pilot](ONE_LEVEL_SUBAGENT_PILOT.md) governs topology and Site ownership. Keep detailed evidence mechanics in [HANDOFF_PROTOCOL.md](HANDOFF_PROTOCOL.md), and require Kira startup and goal templates to link to both.

Kira replacement uses two distinct internally routed artifacts:

- A sanitized `DESIGN_HANDOFF.md` report returned to Quatre for any required Relena review.
- A private local-only `ENGINEER_CONTINUITY_HANDOFF.md` artifact for successor continuity. It may contain the exact local source path and machine-specific state needed for recovery, but must remain outside GitHub and must never contain credentials, tokens, owner identity, secrets, or private production data.

Never copy the private continuity artifact into this repository, a public issue, a public handoff, or permanent documentation. Quatre routes it internally; the Product Owner does not transport it. Permanent documents record only sanitized conclusions and authoritative candidate identity.

For each significant Engineer handoff, evaluate whether it records a major milestone transition such as local implementation, local validation, saved Site version, production migration, production verification, publication, rollback, or supersession. Update the changelog when it does, keeping each state independent. Brief acceptance and routine progress reports do not create changelog entries.

## Planner Decision Queue

[PLANNER_INBOX.md](PLANNER_INBOX.md) is the current queue for unresolved decisions that require Planner or product-owner authority. It contains no resolved history and must not duplicate the backlog, roadmap, changelog, current state, next actions, ADRs, or technical handoffs.

The queue may contain multiple independently understandable decisions. Batch non-urgent independent decisions when useful, but do not delay an urgent or high-risk gate merely to form a batch. A blocked workstream does not make the whole project blocked while another authorized independent workstream can continue.

Relena maintains the queue under Quatre orchestration. Kira supplies sanitized evidence directly to Quatre but does not edit the queue. Quatre routes only genuine Product Owner decisions to Relena for recording.

Create an item only when delegated authority cannot safely resolve a genuine choice involving:

- Product direction, user experience, or meaningful prioritization
- Scope expansion or reduction, or conflicting accepted requirements
- Architecture with material product consequences
- Release or production risk requiring owner acceptance
- Destructive operations
- Cost or external-service commitments
- Privacy or public-data implications

Do not escalate routine implementation choices, ordinary brief acceptance, fixable test failures, documentation housekeeping, delegated engineering details, or questions answerable from accepted direction. An unknown alone is not a Planner decision; first determine whether it blocks authorized work or can be resolved through further authorized investigation.

Each pending item uses this concise structure:

- Short decision title
- Status: `AWAITING PLANNER`
- Raised by
- One clear decision question
- Why Planner authority is required
- Two concise options when possible, with consequences
- Designer recommendation, or `NONE`
- Impact
- Short response format such as `Decision: A`

Include only the minimum sanitized technical context required to decide. Link to permanent repository documents for detail; never link to local handoff paths.

Decision lifecycle:

1. Kira evidence, Relena work, or Quatre orchestration identifies a genuine Product Owner decision.
2. Quatre asks Relena to confirm and record the minimum decision item; routine implementation and internal routing never enter the queue.
3. Quatre presents the decision to the Product Owner and receives the response.
4. Quatre routes the answer to Relena, which records it in the permanent source of truth and updates requirements, roadmap, or goals when required.
5. Designer updates the changelog for a material milestone consequence and creates or supersedes an ADR when warranted.
6. Designer removes the resolved queue item. Git history and permanent design documents retain the durable record.

## Architecture Decision Records

Every major architectural decision should become an ADR containing:

- Status
- Context
- Decision
- Consequences
- Future considerations

Never rewrite historical ADRs. Supersede or clarify them with a new record and update the [Decision Log](DECISIONS.md).

## Current State Updates

Whenever architecture changes, update:

- [CURRENT_STATE.md](CURRENT_STATE.md)
- [ROADMAP.md](ROADMAP.md)
- [CHANGELOG.md](CHANGELOG.md)
- [NEXT_ACTIONS.md](NEXT_ACTIONS.md)

Create or supersede ADRs when required.

## Backlog

Unstructured internal ideas that have not been accepted belong in [BACKLOG.md](BACKLOG.md). Comparable-application product/UX findings belong in the [Future Improvement Catalog](FUTURE_IMPROVEMENT_CATALOG.md), where they remain ranked candidates rather than roadmap commitments. Keep both concise. Do not move speculative ideas into the roadmap until they are accepted.

## Knowledge Spaces

Use the [Knowledge Index](KNOWLEDGE_INDEX.md) to keep four authority levels distinct:

- [Future Improvement Catalog](FUTURE_IMPROVEMENT_CATALOG.md) — Planner/Designer-ranked product and UX opportunities from comparable applications. Entries are candidates, not roadmap commitments.
- Engineer Research Sandbox — Engineer-local technical feasibility, patterns, risks, experiments, and options stored in the shared handoff workspace's `knowledge/` area. Raw entries do not belong in this repository and do not authorize implementation.
- Kira goal/brief — approved implementation scope only, transmitted internally by Quatre.
- Tester knowledge — coverage strategy, regression knowledge, and evidence conventions only; it does not define product behavior or implementation scope.

Relena owns promotion from research into accepted product direction or a Kira goal/brief under Quatre orchestration. Product Owner participation occurs only through Quatre when a material escalation changes behavior, priority, cost, risk, or scope. Preserve rejected/superseded records briefly so research is not repeatedly rediscovered.

Kira records source URL, review date/status, license warning, revisit trigger, and explicit confirmation that no code was copied in local knowledge. Kira has read-only access to `book-collection-design`, returns evidence directly to Quatre, and must not create or modify any Design-repository or GitHub artifact. Relena alone may incorporate an approved conclusion into authoritative documentation. Do not present observed patterns as verified CYOA implementation facts.

## Architecture Principles

Favor:

- Incremental migrations
- Backwards compatibility
- Stable identifiers
- Preservation of user data
- Minimal schema changes
- Simple designs before generalized solutions
- Independently promotable workstreams and release candidates where platform capabilities permit

Parallel implementation must not create accidental release coupling. Record genuine dependencies and shared hotspots, but keep unrelated source, migrations, validation evidence, Site saves, and publication authority separable. When separation is technically impossible, document the coupling and require an explicit convergence decision before release.

Avoid complexity before the roadmap requires it.

## Project Scope

The product is a private-use Book Collection System focused on:

- Books and book series
- Shopping workflow
- Scanner
- Bookshelf
- AI-assisted review

Future media types may influence architecture but must not expand the current scope.

## Repository Memory

For every future documentation task, read these authorities first:

1. [DOCUMENTATION_RULES.md](DOCUMENTATION_RULES.md) — standing documentation policy.
2. [PROJECT_VISION.md](PROJECT_VISION.md) — product authority.
3. [ROADMAP.md](ROADMAP.md) — long-term plan.
4. [NEXT_ACTIONS.md](NEXT_ACTIONS.md) — active engineering queue.
5. [ENGINEER_EXECUTION_CONTRACT.md](ENGINEER_EXECUTION_CONTRACT.md) — active-run continuation and terminal-response authority.
6. [HANDOFF_PROTOCOL.md](HANDOFF_PROTOCOL.md) — required for implementation handoffs.
7. [KNOWLEDGE_INDEX.md](KNOWLEDGE_INDEX.md) — research/catalog routing when the task involves external findings or future ideas.

Preserve consistency across the repository, update these documents when appropriate, and prefer cross-links over duplication.

Also read the [pilot](ONE_LEVEL_SUBAGENT_PILOT.md) and [HANDOFF_PROTOCOL.md](HANDOFF_PROTOCOL.md) before preparing or applying a Kira goal, release packet, or evidence handoff. Use the linked templates and keep detailed mechanics there rather than duplicating them in this policy.

## Review Checklist

Before staging documentation, verify:

- [ ] Cross-links are valid.
- [ ] No duplicate information exists.
- [ ] `CURRENT_STATE.md` matches the latest assessment.
- [ ] `ROADMAP.md` matches accepted priorities.
- [ ] `NEXT_ACTIONS.md` reflects one coherent current execution horizon, which may contain multiple bounded workstreams.
- [ ] No sensitive information exists.
- [ ] New architectural decisions are recorded.
- [ ] Documentation remains concise.
