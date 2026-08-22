# Controlled Shopping Publication Plan

**Status:** Prepared for Planner/Product Owner review; not authorized for execution  
**Prepared:** 2026-08-21

This plan defines the next independent gate after M2 Gate 4. It does not authorize a Site save, deployment, publication, production request, write, validation run, correction, rollback, restore, or destructive action.

## Verified starting state

- Published/live Site is Version 19, the owner-authenticated administration surface.
- Saved Version 20 is unpublished, undeployed, and preserves the exact validated cumulative Shopping/M3–M6/Bookshelf candidate.
- Gate 4 is complete within its bridge-observable boundary. The supplemental export matched Gate 2 counts, identities, Book values, ownership, copies, and cover references; the authorized CYOA target price is 600 cents.
- The bridge export is not a D1 snapshot, excludes R2 bytes, and does not prove restore readiness or complete backup.
- Local visual work at checkpoint `608553f` is later than Version 20 and must not enter a Shopping publication candidate implicitly.

## Candidate decision required before publication authority

Version 20 is cumulative, while ADR-0012 originally requires an exact Shopping release candidate that does not accidentally include later M3–M6/Bookshelf work. Before any publication brief, Engineer must perform a read-only source-composition and Sites-capability check and Planner/Product Owner must approve one exact candidate:

1. **Shopping-only candidate:** isolate the approved administration/migration path, Shopping UI, and accepted validation fixes without reconstructing or weakening validated shared surfaces; or
2. **Cumulative Version 20 candidate:** explicitly accept publishing Shopping together with the named M3–M6/Bookshelf features after full cumulative revalidation.

Stop if supported tooling cannot produce the chosen candidate exactly, if isolation would require unsafe reconstruction, or if saved/source/package identity is ambiguous.

## Proposed publication gate

After a separate explicit publication decision:

1. Reconfirm Engineer identity, authoritative Site, owner session, published Version 19, latest saved Version 20, and absence of an unintended preview/deployment.
2. Verify the exact included/excluded file and migration manifest and confirm no unreviewed local Phase A/D work, generated files, dependencies, secrets, or unrelated changes are included.
3. Re-run the candidate's focused tests, authoritative serial suite, task lint, production build, diff/whitespace checks, migration-order checks, and source/package identity checks.
4. Reconfirm Gate 4 evidence, current production-read compatibility, and the automatic-stop conditions below. Do not rerun Gate 3 or perform a corrective write.
5. Publish exactly the approved candidate once through the supported Sites workflow.
6. Verify only deployment identity and basic application health authorized by the publication gate, then stop and return sanitized evidence.

## Automatic stops

Stop before publication for a wrong or ambiguous Site, owner session, live/saved version, candidate manifest, package identity, migration set, source composition, unexpected dirty state, failed validation, missing private preservation artifact, or any indication that publication would perform an unapproved schema/data operation.

After publication, stop for failed or ambiguous deployment identity, application health, or unexpected state. Do not correct, republish, retry migration, restore, roll back, mutate data, or proceed to hands-on validation or smoke testing without the applicable separate authority.

## Later independent gates

- Product Owner desktop/mobile Shopping hands-on validation.
- Post-publication critical-path smoke review.
- Any corrective source/data write or forward repair.
- Code rollback, data restore, or destructive recovery.

Each remains separately approved and evidenced under [ADR-0012](decisions/ADR-0012-live-shopping-validation-sequence.md).

## Review output

Planner/Product Owner review must select the exact candidate composition and either authorize a publication brief or hold. Approval of this planning document alone is not execution authority.
