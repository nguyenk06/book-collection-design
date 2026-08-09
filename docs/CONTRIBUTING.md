# Contributing

This repository documents the Book Collection System's product direction, architecture, and major decisions. Application implementation happens in a separate repository.

## Before changing documentation

- Read [Project Vision](PROJECT_VISION.md), [Current State](CURRENT_STATE.md), and [Roadmap](ROADMAP.md).
- Verify implementation claims against the actual Site implementation workspace and saved/deployed Site evidence.
- Keep current behavior separate from proposed behavior.
- Avoid duplicating roadmap status inside feature documents.

## Documentation standards

- Prefer concise headings, lists, tables, diagrams, and cross-links.
- Use plain language and define system-specific terms.
- Mark unknowns explicitly; do not infer deployed behavior.
- Keep filenames stable and links relative.
- Use Mermaid for diagrams that materially clarify relationships or workflows.
- Update the **Last reviewed** date only when [Current State](CURRENT_STATE.md) is actually reconciled.

## Architectural decisions

Create an ADR when a decision:

- Establishes a durable system boundary or product principle.
- Selects a significant data, integration, or operational approach.
- Has meaningful tradeoffs future contributors need to understand.
- Supersedes an accepted decision.

Add the ADR to the [Decision Log](DECISIONS.md). Do not rewrite accepted ADR history; supersede it with a new record.

## Keeping repositories aligned

When a major implementation milestone or architectural decision is completed:

1. Update [Current State](CURRENT_STATE.md).
2. Update roadmap status without copying feature requirements.
3. Reconcile affected architecture, database, and feature documents.
4. Add a changelog entry.
5. Add or supersede an ADR when the decision is durable.

Pull requests should state which implementation evidence was reviewed and identify any remaining unknowns.
