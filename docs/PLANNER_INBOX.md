# Planner Inbox

This file contains only unresolved decisions requiring Planner or product-owner input.

It is not a task backlog, technical issue tracker, Engineer progress log, changelog, roadmap, architecture document, or resolved-decision history. Designer owns this queue and removes each item after recording the accepted decision in the appropriate permanent source of truth.

## Current Decisions

### Decision 1 — Preserve exact local correction candidate on the configured source branch

**Context:** Sei III completed and locally validated clean checkpoint `f15ea8144ec277a737f5e491e0276b60555cafb8`, exactly four commits ahead of the configured remote-tracking baseline. Relative to published/saved Version 20 it contains exactly `app/page.tsx`, `app/globals.css`, and `tests/collection-behavior.test.tsx`. Full local validation passes; no push or Site operation has occurred.

- **A — Authorize bounded source preservation (recommended):** Reconfirm checkout, remote, branch, HEAD, clean state, Version 20 ancestry, exact three-file manifest, validation recency, credential path, and remote branch head. If the remote is already exact `f15ea81`, do not push. If it definitively differs only by the expected ancestor state and all identities are unambiguous, permit one normal push of exact `f15ea81`. Stop for drift, collision, timeout, ambiguous result, unsupported credentials, failed revalidation, or floor risk. No force push, retry, source correction, Site save, publication, production, migration, rollback, or restore.
- **B — Defer:** Keep the candidate only in its current clean local checkout. Do not query or push the configured remote.

**Estimate:** 2 / 4 / 7 five-hour points.

### Decision 2 — Create one unpublished saved Site version after preservation

**Context:** A saved Site version would preserve the exact candidate in Sites but is not runnable and provides no unpublished preview. Published and latest saved Site state remains Version 20. This decision is independent from publication and becomes executable only after Decision 1:A succeeds and source/package identity is reconfirmed.

- **A — Authorize one conditional unpublished save:** After successful exact source preservation, verify Site/project/session identity, source commit/package identity, exact three-file delta, collision and migration invariants, full required revalidation, and usage. Permit exactly one Site save. Stop before preview, deployment, publication, live validation, production access/mutation, correction, retry, rollback, or restore.
- **B — Defer (recommended if preservation alone is sufficient):** Keep Version 20 as latest saved/published and do not create a Site version.

**Estimate:** additional 3 / 5 / 8 five-hour points after Decision 1:A; combined preservation-plus-save envelope 5 / 9 / 15.

When several decisions are pending, number them and keep each independently understandable. Planner may respond compactly, for example `1: B; 2: A; 3: DEFER`. Do not delay urgent or high-risk decisions for batching.
