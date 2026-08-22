# Planner Inbox

This file contains only unresolved decisions requiring Planner or product-owner input.

It is not a task backlog, technical issue tracker, Engineer progress log, changelog, roadmap, architecture document, or resolved-decision history. Designer owns this queue and removes each item after recording the accepted decision in the appropriate permanent source of truth.

## Current Decisions

### 1. Controlled Shopping publication candidate and gate

**Verified starting state**

- Published/live Site is Version 19, the owner-authenticated administration surface.
- Saved Version 20 is unpublished, undeployed, and preserves the validated cumulative Shopping/M3–M6/Bookshelf candidate.
- Gate 4 is complete within its bridge-observable boundary. This is not a D1 snapshot, R2-byte backup, restore-readiness proof, or complete backup.
- Local visual checkpoint `608553f` is later than Version 20 and must not enter a publication candidate implicitly.

**Decision needed:** Which exact candidate should Designer use when preparing the separately gated Shopping publication brief?

- **A — Shopping-only candidate:** Isolate the approved administration/migration path, Shopping UI, and accepted validation fixes. Stop if this requires unsafe reconstruction or cannot preserve verified shared behavior.
- **B — Cumulative Version 20 candidate:** Explicitly accept publishing Shopping together with the named M3–M6/Bookshelf features after full cumulative revalidation.
- **C — Hold:** Keep Version 19 published and Version 20 unpublished; prepare no publication brief.

**Proposed gate after an A or B decision**

1. Reconfirm Engineer identity, authoritative Site, owner session, published Version 19, saved Version 20, and no unintended preview/deployment.
2. Verify the exact included/excluded manifest, migration set, clean source boundary, and source/package identity. Exclude later local Phase A/D work and unrelated changes.
3. Run focused tests, the authoritative serial suite, lint, production build, diff/whitespace, migration-order, and packaging checks for the selected candidate.
4. Reconfirm Gate 4 evidence and stop if publication could perform an unapproved schema/data operation.
5. Under a later explicit publication approval, publish exactly the approved candidate once, verify deployment identity and basic application health, then stop and return sanitized evidence.

Automatically stop for ambiguous Site/session/version/candidate/package identity, unexpected dirty state, failed validation, missing preservation evidence, or unexpected production behavior. Do not correct, republish, retry migration, restore, roll back, mutate data, or continue into hands-on validation or smoke testing.

Selecting A or B authorizes Designer to prepare the publication brief only. It does not authorize a Site operation or publication. Publication, Product Owner hands-on validation, post-publication smoke review, correction, rollback, restore, and destructive recovery remain independent gates.

When several decisions are pending, number them and keep each independently understandable. Planner may respond compactly, for example `1: B; 2: A; 3: DEFER`. Do not delay urgent or high-risk decisions for batching.
