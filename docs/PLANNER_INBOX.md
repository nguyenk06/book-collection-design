# Planner Inbox

This file contains only unresolved decisions requiring Planner or product-owner input.

It is not a task backlog, technical issue tracker, Engineer progress log, changelog, roadmap, architecture document, or resolved-decision history. Designer owns this queue and removes each item after recording the accepted decision in the appropriate permanent source of truth.

## Current Decisions

### Decision 1 — Permit one materially different read-only remote-head query

**Context:** Product Owner previously authorized exact source preservation for clean local checkpoint `f15ea81`, followed conditionally by one unpublished Site save. Sei III accepted the brief at `!61:78` and ran Stage 1 at `!58:77`. The single authorized configured-branch query reached provider detection but returned no definitive SHA before its controller result ended. No push, ref update, package action, Site save, or source/Site/production mutation occurred. Designer reconfirmed local `main` remains clean at exact `f15ea81`, with the exact three-file Version 20 delta. The local remote-tracking reference remains exact Version 20 `6a2191b1b506d171d576cbb6a6b160964595c051`, but this cached reference is not proof of current remote state. Stage 2 remains blocked.

- **A — Authorize one different supported read-only query (recommended):** Permit exactly one additional remote `refs/heads/main` query through a materially different supported project-scoped method while retaining the configured remote and existing credential identity. No alternate credential workaround, elevated access, push, or Site action occurs during the query. If the result is exact `f15ea81`, preservation is already satisfied. If it is exact Version 20 `6a2191b...`, the previously authorized single normal fast-forward push remains eligible. Any other SHA, timeout, missing SHA, credential ambiguity, or collision stops Stage 1 again; do not try a third query.
- **B — Defer:** Keep the candidate only in its clean local checkout. Do not query, push, or enter Stage 2.

**Remaining estimate:** 5 / 9 / 15 five-hour points including the conditional push/save work; operational minimum 30% with the 15% floor. Current recorded usage is `!58:77`.

When several decisions are pending, number them and keep each independently understandable. Planner may respond compactly, for example `1: B; 2: A; 3: DEFER`. Do not delay urgent or high-risk decisions for batching.
