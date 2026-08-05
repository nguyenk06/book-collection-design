# Book Collection System Design

This repository is the permanent source of truth for the Book Collection System's design, architecture, roadmap, and major decisions. It is a lightweight, Markdown-first documentation project; it is not the application.

## Relationship to the application

The application is maintained in a separate implementation repository. This repository describes intended behavior and architectural direction. Implementation-specific details belong here only when they clarify the current state or constrain future design.

## Status

The system has a published site and an established collection workflow. The immediate work is to review the database and then improve collection completion workflows, beginning with Shopping Mode. See [Current State](docs/CURRENT_STATE.md) and the [Roadmap](docs/ROADMAP.md).

## Start here

New contributors should read, in order:

1. [Project Vision](docs/PROJECT_VISION.md)
2. [Current State](docs/CURRENT_STATE.md)
3. [Roadmap](docs/ROADMAP.md)
4. [Architecture](docs/ARCHITECTURE.md)
5. [Decision Log](docs/DECISIONS.md)

Implementation changes should be made in the application repository. Major architectural or product decisions should be reflected here.

## Documentation

| Area | Document |
| --- | --- |
| Direction | [Project Vision](docs/PROJECT_VISION.md) |
| Delivery | [Roadmap](docs/ROADMAP.md) · [Current State](docs/CURRENT_STATE.md) · [Changelog](docs/CHANGELOG.md) |
| Architecture | [Architecture](docs/ARCHITECTURE.md) · [Database](docs/DATABASE.md) |
| Core workflows | [Shopping Mode](docs/SHOPPING_MODE.md) · [Scanner and Matching](docs/SCANNER_AND_MATCHING.md) · [Bookshelf](docs/BOOKSHELF.md) |
| Data workflows | [Import and Export](docs/IMPORT_EXPORT.md) · [AI Review](docs/AI_REVIEW.md) · [Asset Management](docs/ASSET_MANAGEMENT.md) · [Tags](docs/TAGS.md) |
| Governance | [Decision Log](docs/DECISIONS.md) · [Contributing](docs/CONTRIBUTING.md) |

## GitHub Pages

The `docs/` directory includes a minimal Jekyll configuration and landing page. GitHub Pages can publish it by selecting **Deploy from a branch**, the default branch, and the `/docs` folder in repository settings. Markdown remains the source of truth.
