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

Preserve consistency across the repository, update these documents when appropriate, and prefer cross-links over duplication.

## Review Checklist

Before staging documentation, verify:

- [ ] Cross-links are valid.
- [ ] No duplicate information exists.
- [ ] `CURRENT_STATE.md` matches the latest assessment.
- [ ] `ROADMAP.md` matches accepted priorities.
- [ ] `NEXT_ACTIONS.md` reflects exactly one current sprint.
- [ ] No sensitive information exists.
- [ ] New architectural decisions are recorded.
- [ ] Documentation remains concise.
