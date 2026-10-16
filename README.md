# My Library Design

This repository is the permanent source of truth for My Library's design, architecture, roadmap, and major decisions. It is a lightweight, Markdown-first documentation project; it is not the application.

> [📊 View the Project Dashboard](docs/PROJECT_DASHBOARD.md) — concise visual progress, milestone status, and remaining release path.

## Relationship to the application

The application is maintained in the CYOA Collection ChatGPT Site implementation workspace. This repository describes intended behavior and architectural direction. Implementation-specific details belong here only when they clarify verified current state or constrain future design.

## Status

Site Version 34 at exact `14775b498dedcf71d54c4641ee457b0d64395f49` is the saved public release and is pending bounded Product Owner review. It provides one canonical hero-level **Scan ISBN** entry across My Library, CYOA, and Redwall, removes duplicate collection-toolbar scanner controls, and removes discoverable Shopkeeper navigation while retaining its unlinked compatibility route. See [Current State](docs/CURRENT_STATE.md) and [Next Actions](docs/NEXT_ACTIONS.md) for the authoritative release and review state.

## Start here

Delivery Coordinator should read, in order:

1. [CYOA One-Level Subagent Pilot](docs/ONE_LEVEL_SUBAGENT_PILOT.md)
2. [Planner Inbox](docs/PLANNER_INBOX.md)
3. [Project Dashboard](docs/PROJECT_DASHBOARD.md)
4. [Current State](docs/CURRENT_STATE.md)
5. [Next Actions](docs/NEXT_ACTIONS.md)
6. [Changelog](docs/CHANGELOG.md)
7. [Roadmap](docs/ROADMAP.md)

The active pilot is operational: ChatGPT Product Planner Quatre owns external product planning, while Delivery Coordinator Argama is the initialized persistent Codex parent, usage governor, evidence reconciler, and Site owner. Relena, Kira, Athrun, Lacus, and Cagalli remain ready direct non-delegating Argama children; no implementation goal is active. Sei III and the old separate-chat workflow are retired, and Kira inherits no Sei state or authority and has no Sites rights. The Product Owner carries only approved goals into Argama and consolidated results back to Quatre when further planning is needed—not routine briefs, reports, `!inbox`, or `!brief` among Codex children. Temporary artifacts remain internal/local and never become GitHub content. `docs/PLANNER_INBOX.md` is reserved for genuine Product Owner decisions.

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
| Data workflows | [Enrichment Foundation](docs/ENRICHMENT_FOUNDATION.md) · [Enrichment Review Contract](docs/ENRICHMENT_REVIEW_CONTRACT.md) · [Import and Export](docs/IMPORT_EXPORT.md) · [AI Review](docs/AI_REVIEW.md) · [Asset Management](docs/ASSET_MANAGEMENT.md) · [Tags](docs/TAGS.md) |
| Knowledge | [Knowledge Ownership Index](docs/KNOWLEDGE_INDEX.md) · [Future Improvement Catalog](docs/FUTURE_IMPROVEMENT_CATALOG.md) |
| Governance | [CYOA One-Level Subagent Pilot](docs/ONE_LEVEL_SUBAGENT_PILOT.md) · [Decision Log](docs/DECISIONS.md) · [Documentation Rules](docs/DOCUMENTATION_RULES.md) · [Engineer Execution Contract](docs/ENGINEER_EXECUTION_CONTRACT.md) · [Contributing](docs/CONTRIBUTING.md) |
| Handoffs | [Protocol](docs/HANDOFF_PROTOCOL.md) · [Engineer Execution Contract](docs/ENGINEER_EXECUTION_CONTRACT.md) · [Implementation Brief template](templates/IMPLEMENTATION_BRIEF.md) · [Design Handoff template](templates/DESIGN_HANDOFF.md) |
| Role startup | [Argama Delivery Coordinator](templates/DELIVERY_COORDINATOR_STARTUP.md) · [deprecated former parent path](templates/PLANNER_STARTUP.md) · [Relena direct child](templates/DESIGNER_STARTUP.md) · [Kira direct child](templates/ENGINEER_STARTUP.md) |
| Engineer handoffs | [Implementation brief](templates/IMPLEMENTATION_BRIEF.md) · [Estimation brief](templates/ESTIMATION_BRIEF.md) |

## GitHub Pages

The `docs/` directory includes a minimal Jekyll configuration and landing page. GitHub Pages can publish it by selecting **Deploy from a branch**, the default branch, and the `/docs` folder in repository settings. Markdown remains the source of truth.
