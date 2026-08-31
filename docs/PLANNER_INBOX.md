# Planner Inbox

This file contains only unresolved decisions requiring Planner or product-owner input.

It is not a task backlog, technical issue tracker, Engineer progress log, changelog, roadmap, architecture document, or resolved-decision history. Designer owns this queue and removes each item after recording the accepted decision in the appropriate permanent source of truth.

## Current Decisions

### Decision 1 — Generated TypeScript artifact blocks the exact candidate boundary

**Context:** Sei III accepted the local-only Version 20 validation continuation at `!99:86` and then ran it under separate authority. The inherited source remained unchanged. Lint passed with zero errors and two warnings; focused tests passed 17/17; the full serial suite passed 93/93. Standalone no-emit type checking reported no `app/page.tsx` error but generated one untracked root file, `tsconfig.tsbuildinfo`, outside the approved three-file candidate boundary. Designer independently verified that it is untracked and not ignored, is 350,720 bytes, and has SHA-256 `62DB358B329BD636621B55FF91A488003E02AD0D16B49EAD8131636C12A7D270`. The current brief prohibits cleanup, deletion, or normalization, so Sei stopped before build, local QA, final boundary review, or checkpointing. No Site, production, schema/data, dependency/configuration, or tracked-source change occurred.

**Decision required:** How may the exact generated artifact be handled so validation can resume?

- **A — Reversible private quarantine (recommended):** Authorize one identity-checked move of the exact untracked file outside the Sites checkout into a private local quarantine location, with no overwrite. Verify afterward that only inherited `app/page.tsx` remains dirty, retain the hash and provenance privately, and resume the same local validation scope under a bounded brief addendum and fresh `!run`. Do not change `.gitignore`, TypeScript configuration, dependencies, tracked source, Site state, or production.
- **B — Exact deletion:** After rechecking filename, untracked status, size, and hash, authorize deletion of only this reproducible generated file; then verify the source boundary and resume under the same remaining gates. No wildcard, recursive cleanup, tracked-file deletion, or other normalization is allowed.
- **C — Keep parked:** Preserve the artifact untouched and leave the validation continuation parked. No further validation or checkpoint work occurs.

**Designer recommendation:** A. It restores the exact boundary without destroying the generated evidence and leaves a reversible audit trail. This is workspace authority only; it grants no source correction, fourth lint approach, push, Site save/version, preview, deployment, publication, production, schema/data, migration, rollback, or restore authority.

When several decisions are pending, number them and keep each independently understandable. Planner may respond compactly, for example `1: B; 2: A; 3: DEFER`. Do not delay urgent or high-risk decisions for batching.
