# Documentation Rules

This document is the standing documentation policy for the repository.

## Repository Purpose

This repository is the permanent design authority for the Book Collection System. It documents:

- Vision
- Architecture
- Database
- Roadmap
- Decisions
- Current project state

It is not the implementation repository.

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

Planner uses permanent design documentation rather than raw handoffs or implementation chat as the primary project visibility layer:

1. [PLANNER_INBOX.md](PLANNER_INBOX.md) — what requires a decision.
2. [CURRENT_STATE.md](CURRENT_STATE.md) — what is true now.
3. [NEXT_ACTIONS.md](NEXT_ACTIONS.md) — what should happen next.
4. [CHANGELOG.md](CHANGELOG.md) — which major milestones and state transitions occurred.
5. [ROADMAP.md](ROADMAP.md) — where the project is going.

Temporary handoffs are transport and evidence. They do not replace these documents.

For each significant Engineer handoff, evaluate whether it records a major milestone transition such as local implementation, local validation, saved Site version, production migration, production verification, publication, rollback, or supersession. Update the changelog when it does, keeping each state independent. Brief acceptance and routine progress reports do not create changelog entries.

## Planner Decision Queue

[PLANNER_INBOX.md](PLANNER_INBOX.md) is the current queue for unresolved decisions that require Planner or product-owner authority. It contains no resolved history and must not duplicate the backlog, roadmap, changelog, current state, next actions, ADRs, or technical handoffs.

The queue may contain multiple independently understandable decisions. Batch non-urgent independent decisions when useful, but do not delay an urgent or high-risk gate merely to form a batch. A blocked workstream does not make the whole project blocked while another authorized independent workstream can continue.

Designer owns the queue. Engineer supplies sanitized evidence through handoffs or state reports but does not edit the queue. Planner may directly ask Designer to record a question.

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

1. Engineer evidence or Designer work identifies a genuine decision.
2. Designer confirms Planner authority is required and automatically creates or updates the queue item during intake; no separate queueing instruction is required.
3. Planner responds.
4. Designer records the accepted decision in the appropriate permanent source of truth and updates requirements, roadmap, or briefs when required.
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

Ideas that have not been accepted belong in [BACKLOG.md](BACKLOG.md). Keep them brief. Do not move speculative ideas into the roadmap until they are accepted.

## Architecture Principles

Favor:

- Incremental migrations
- Backwards compatibility
- Stable identifiers
- Preservation of user data
- Minimal schema changes
- Simple designs before generalized solutions

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
5. [HANDOFF_PROTOCOL.md](HANDOFF_PROTOCOL.md) — required for implementation handoffs.

Preserve consistency across the repository, update these documents when appropriate, and prefer cross-links over duplication.

Also read [HANDOFF_PROTOCOL.md](HANDOFF_PROTOCOL.md) before preparing or applying an implementation handoff. Use its linked templates for implementation briefs and verified Site-to-Design reports; keep detailed handoff rules there rather than duplicating them in this policy.

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
