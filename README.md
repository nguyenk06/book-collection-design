# My Library Design

This repository is the permanent source of truth for My Library's design, architecture, roadmap, and major decisions. It is a lightweight, Markdown-first documentation project; it is not the application.

> [📊 View the Project Dashboard](docs/PROJECT_DASHBOARD.md) — concise visual progress, milestone status, and remaining release path.

## Relationship to the application

The application is maintained in the CYOA Collection ChatGPT Site implementation workspace. This repository describes intended behavior and architectural direction. Implementation-specific details belong here only when they clarify verified current state or constrain future design.

## Status

Site Version 21 at exact `f15ea81` is definitively published; all five authorized anonymous correction markers matched. Product Owner hands-on validation is parked. Later local Phase A/D checkpoint `608553f` remains excluded. See [Current State](docs/CURRENT_STATE.md) and [Next Actions](docs/NEXT_ACTIONS.md).

## Start here

Planner should read, in order:

1. [CYOA One-Level Subagent Pilot](docs/ONE_LEVEL_SUBAGENT_PILOT.md)
2. [Planner Inbox](docs/PLANNER_INBOX.md)
3. [Project Dashboard](docs/PROJECT_DASHBOARD.md)
4. [Current State](docs/CURRENT_STATE.md)
5. [Next Actions](docs/NEXT_ACTIONS.md)
6. [Changelog](docs/CHANGELOG.md)
7. [Roadmap](docs/ROADMAP.md)

The active pilot uses Quatre as persistent parent, orchestrator, usage governor, and Site owner. Relena and successor Engineer Kira are direct non-delegating Quatre children. The Product Owner communicates only with Quatre and does not carry briefs, reports, `!inbox`, or `!brief` between agents. Temporary artifacts remain internal/local and never become GitHub content. `docs/PLANNER_INBOX.md` is reserved for genuine Product Owner decisions.

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
| Governance | [CYOA One-Level Subagent Pilot](docs/ONE_LEVEL_SUBAGENT_PILOT.md) · [Decision Log](docs/DECISIONS.md) · [Documentation Rules](docs/DOCUMENTATION_RULES.md) · [Engineer Execution Contract](docs/ENGINEER_EXECUTION_CONTRACT.md) · [Contributing](docs/CONTRIBUTING.md) |
| Handoffs | [Protocol](docs/HANDOFF_PROTOCOL.md) · [Engineer Execution Contract](docs/ENGINEER_EXECUTION_CONTRACT.md) · [Implementation Brief template](templates/IMPLEMENTATION_BRIEF.md) · [Design Handoff template](templates/DESIGN_HANDOFF.md) |
| Role startup | [Quatre parent](templates/PLANNER_STARTUP.md) · [Relena direct subagent](templates/DESIGNER_STARTUP.md) · [Kira direct subagent](templates/ENGINEER_STARTUP.md) |
| Engineer handoffs | [Implementation brief](templates/IMPLEMENTATION_BRIEF.md) · [Estimation brief](templates/ESTIMATION_BRIEF.md) |

## GitHub Pages

The `docs/` directory includes a minimal Jekyll configuration and landing page. GitHub Pages can publish it by selecting **Deploy from a branch**, the default branch, and the `/docs` folder in repository settings. Markdown remains the source of truth.
