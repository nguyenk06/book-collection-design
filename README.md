# My Library Design

This repository is the permanent source of truth for My Library's design, architecture, roadmap, and major decisions. It is a lightweight, Markdown-first documentation project; it is not the application.

> [📊 View the Project Dashboard](docs/PROJECT_DASHBOARD.md) — concise visual progress, milestone status, and remaining release path.

## Relationship to the application

The application is maintained in the CYOA Collection ChatGPT Site implementation workspace. This repository describes intended behavior and architectural direction. Implementation-specific details belong here only when they clarify verified current state or constrain future design.

## Status

Site Version 19 is the published owner-authenticated administration surface. Unpublished, undeployed Version 20 preserves the exact validated cumulative Shopping/M3–M6/Bookshelf source; it is not a runnable preview and saving it did not execute migrations. Gate 4 is complete within its bridge-observable verification boundary; this does not establish a D1 snapshot, R2-byte backup, restore readiness, or complete production backup. See [Current State](docs/CURRENT_STATE.md) and [Next Actions](docs/NEXT_ACTIONS.md).

## Start here

Planner should read, in order:

1. [Planner Inbox](docs/PLANNER_INBOX.md)
2. [Project Dashboard](docs/PROJECT_DASHBOARD.md)
3. [Current State](docs/CURRENT_STATE.md)
4. [Next Actions](docs/NEXT_ACTIONS.md)
5. [Changelog](docs/CHANGELOG.md)
6. [Roadmap](docs/ROADMAP.md)

Temporary briefs and Engineer reports are stored only in the external local `briefs/` and `inbox/` transport; they are never GitHub content. `docs/PLANNER_INBOX.md` is the separate Quatre/Product Owner decision queue. Planner replies with ordinary decision text such as `Decision 1:A`; `!inbox` is Relena's command for processing Engineer transport and is not a Planner command.

The concise current workstream view in [Current State](docs/CURRENT_STATE.md) shows what is active, blocked, able to continue, and approaching a production gate. Progress estimates are informational; briefs and validation evidence remain authoritative.

## Contributor reading

New contributors should read, in order:

1. [Project Vision](docs/PROJECT_VISION.md)
2. [Current State](docs/CURRENT_STATE.md)
3. [Roadmap](docs/ROADMAP.md)
4. [Architecture](docs/ARCHITECTURE.md)
5. [Decision Log](docs/DECISIONS.md)
6. [Design and Site Handoff Protocol](docs/HANDOFF_PROTOCOL.md)

Implementation changes should be made in the Site implementation workspace. Major architectural or product decisions should be reflected here.

## Documentation

| Area | Document |
| --- | --- |
| Direction | [Planner Inbox](docs/PLANNER_INBOX.md) · [Project Vision](docs/PROJECT_VISION.md) |
| Delivery | [Project Dashboard](docs/PROJECT_DASHBOARD.md) · [Roadmap](docs/ROADMAP.md) · [Staged Milestones](docs/STAGED_MILESTONES.md) · [Next Actions](docs/NEXT_ACTIONS.md) · [Backlog](docs/BACKLOG.md) · [Current State](docs/CURRENT_STATE.md) · [Changelog](docs/CHANGELOG.md) |
| Architecture | [Architecture](docs/ARCHITECTURE.md) · [Database](docs/DATABASE.md) |
| Visual experience | [My Library Visual Experience](docs/VISUAL_EXPERIENCE.md) |
| Core workflows | [Shopkeeper / historical Shopping Mode](docs/SHOPPING_MODE.md) · [Scanner and Matching](docs/SCANNER_AND_MATCHING.md) · [Bookshelf](docs/BOOKSHELF.md) |
| Data workflows | [Import and Export](docs/IMPORT_EXPORT.md) · [AI Review](docs/AI_REVIEW.md) · [Asset Management](docs/ASSET_MANAGEMENT.md) · [Tags](docs/TAGS.md) |
| Knowledge | [Knowledge Ownership Index](docs/KNOWLEDGE_INDEX.md) · [Future Improvement Catalog](docs/FUTURE_IMPROVEMENT_CATALOG.md) |
| Governance | [Decision Log](docs/DECISIONS.md) · [Documentation Rules](docs/DOCUMENTATION_RULES.md) · [Contributing](docs/CONTRIBUTING.md) |
| Handoffs | [Protocol](docs/HANDOFF_PROTOCOL.md) · [Implementation Brief template](templates/IMPLEMENTATION_BRIEF.md) · [Design Handoff template](templates/DESIGN_HANDOFF.md) |
| Role startup | [Designer](templates/DESIGNER_STARTUP.md) · [Site Engineer](templates/ENGINEER_STARTUP.md) · [Planner](templates/PLANNER_STARTUP.md) |
| Engineer handoffs | [Implementation brief](templates/IMPLEMENTATION_BRIEF.md) · [Estimation brief](templates/ESTIMATION_BRIEF.md) |

## GitHub Pages

The `docs/` directory includes a minimal Jekyll configuration and landing page. GitHub Pages can publish it by selecting **Deploy from a branch**, the default branch, and the `/docs` folder in repository settings. Markdown remains the source of truth.
