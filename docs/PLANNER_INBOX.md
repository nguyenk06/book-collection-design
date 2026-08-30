# Planner Inbox

This file contains only unresolved decisions requiring Planner or product-owner input.

It is not a task backlog, technical issue tracker, Engineer progress log, changelog, roadmap, architecture document, or resolved-decision history. Designer owns this queue and removes each item after recording the accepted decision in the appropriate permanent source of truth.

## Current Decisions

### Decision 1 — Release candidate after exhausted source recovery

Supported remote access proves `main` is published Version 20. Sei II has no editable `80e4c61`, the retained package is deployment-only, and the authorized original-Sei locator found none of `80e4c61`, `608553f`, or Version 20 in all six available repository contexts. Exact recovery is exhausted without reconstruction.

- **A — Retire exact `80e4c61` (recommended):** preserve its evidence as historical validation, then authorize Designer planning for a new Version 20-based implementation candidate covering only the confirmed mobile navigation and Bookshelf fixes. Implementation, save, and publication remain separately gated.
- **B — Keep exact-source requirement:** leave P2 parked until the Product Owner supplies a genuine commit-containing clone/object store or independently verified editable-source package.
- **DEFER:** make no new brief or recovery attempt.

This decision does not authorize reconstruction, implementation, source modification, push, Site save, publication, deployment, migration, production mutation, or held validation.

When several decisions are pending, number them and keep each independently understandable. Planner may respond compactly, for example `1: B; 2: A; 3: DEFER`. Do not delay urgent or high-risk decisions for batching.
