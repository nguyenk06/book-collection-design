# Book Collection System Design

This repository is the permanent source of truth for the Book Collection System's design, architecture, roadmap, and major decisions. It is a lightweight, Markdown-first documentation project; it is not the application.

## Relationship to the application

The application is maintained in a separate implementation repository. This repository describes intended behavior and architectural direction. Implementation-specific details belong here only when they clarify the current state or constrain future design.

## Status

Site Version 16 remains published and live. The validated Shopping persistence foundation is saved as unpublished Version 17; production has not been migrated or verified, and Version 17 has not been published. The immediate work is the gated Production Backup & Migration Execution Plan. See [Current State](docs/CURRENT_STATE.md) and [Next Actions](docs/NEXT_ACTIONS.md).

## Start here

Planner should read, in order:

1. [Planner Inbox](docs/PLANNER_INBOX.md)
2. [Current State](docs/CURRENT_STATE.md)
3. [Next Actions](docs/NEXT_ACTIONS.md)
4. [Changelog](docs/CHANGELOG.md)
5. [Roadmap](docs/ROADMAP.md)

Temporary handoffs are evidence and transport; Planner should not normally need to read them.

## Contributor reading

New contributors should read, in order:

1. [Project Vision](docs/PROJECT_VISION.md)
2. [Current State](docs/CURRENT_STATE.md)
3. [Roadmap](docs/ROADMAP.md)
4. [Architecture](docs/ARCHITECTURE.md)
5. [Decision Log](docs/DECISIONS.md)
6. [Design and Site Handoff Protocol](docs/HANDOFF_PROTOCOL.md)

Implementation changes should be made in the application repository. Major architectural or product decisions should be reflected here.

## Documentation

| Area | Document |
| --- | --- |
| Direction | [Planner Inbox](docs/PLANNER_INBOX.md) · [Project Vision](docs/PROJECT_VISION.md) |
| Delivery | [Roadmap](docs/ROADMAP.md) · [Next Actions](docs/NEXT_ACTIONS.md) · [Backlog](docs/BACKLOG.md) · [Current State](docs/CURRENT_STATE.md) · [Changelog](docs/CHANGELOG.md) |
| Architecture | [Architecture](docs/ARCHITECTURE.md) · [Database](docs/DATABASE.md) |
| Core workflows | [Shopping Mode](docs/SHOPPING_MODE.md) · [Scanner and Matching](docs/SCANNER_AND_MATCHING.md) · [Bookshelf](docs/BOOKSHELF.md) |
| Data workflows | [Import and Export](docs/IMPORT_EXPORT.md) · [AI Review](docs/AI_REVIEW.md) · [Asset Management](docs/ASSET_MANAGEMENT.md) · [Tags](docs/TAGS.md) |
| Governance | [Decision Log](docs/DECISIONS.md) · [Documentation Rules](docs/DOCUMENTATION_RULES.md) · [Contributing](docs/CONTRIBUTING.md) |
| Handoffs | [Protocol](docs/HANDOFF_PROTOCOL.md) · [Implementation Brief template](templates/IMPLEMENTATION_BRIEF.md) · [Design Handoff template](templates/DESIGN_HANDOFF.md) |

## GitHub Pages

The `docs/` directory includes a minimal Jekyll configuration and landing page. GitHub Pages can publish it by selecting **Deploy from a branch**, the default branch, and the `/docs` folder in repository settings. Markdown remains the source of truth.
