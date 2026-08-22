# ADR-0012: Validate Shopping Through a Controlled Live Release

## Status

Accepted

## Context

M1 found no supported validation environment that was simultaneously Product Owner-accessible, private, isolated, runnable, and non-production. A separate validation Site would add another Site, bindings, access policy, lifecycle, and cleanup burden. The Product Owner canceled that direction and accepted controlled validation on the live Site using existing collection data.

## Decision

Do not create a separate validation Site. Validate Shopping only after a controlled live release whose gates remain independently observable and sequential:

1. Assemble and locally validate an exact Shopping release candidate without unintentionally including later M3–M5 work.
2. Preserve/publish the owner-authenticated administration surface required for the proven same-origin bridge path.
3. In an owner session, verify schema status and create/privately retain the versioned structured export; record preservation invariants.
4. After explicit schema-activation authority, run the guarded additive Shopping upgrade and verify schema, foreign keys, target price, counts, identities, ownership, copies, covers/references, and unchanged existing values.
5. After explicit Shopping-publication authority, publish the exact validated Shopping release candidate and verify deployment/application health.
6. Run the Product Owner live desktop/mobile Shopping checklist and record `ACCEPT`, `ACCEPT WITH FOLLOW-UP`, or `REVISE BEFORE RELEASE`.
7. Perform the post-publication critical-path smoke review. Any corrective write, cleanup, rollback, or destructive recovery requires its own authority.

## Consequences

- Existing production collection data is the validation dataset; no production data is copied to a second environment.
- Book IDs, collection keys/data, covers/references, ownership, and copy counts must be preserved and verified.
- The bridge structured export is required but is not a D1 snapshot or R2-byte backup. Its limitation must be recorded before schema activation.
- Additive schema activation and code rollback remain distinct. Prefer forward repair; destructive restore remains separately authorized.
- This decision defines the sequence. It is not evidence that a candidate was saved, the administration surface was published, an export occurred, schema changed, Shopping was published, or validation/smoke testing passed.
- The need to isolate Shopping from cumulative M3–M5 work is a release-packaging correction, not a preferred future workflow. Future parallel work should remain independently promotable and must not become interconnected merely because it shares a working copy.

## Implementation status

Gates 0–4 are complete within their documented evidence boundaries. Gate 3 was invoked exactly once. Gate 4 independently confirmed schema-complete and zero-foreign-key status, and a separately authorized read-only bridge export matched the Gate 2 baseline for counts, identities, Book values, ownership, copies, and cover references; the sole semantic difference was the authorized CYOA target price of 600 cents. This status does not convert the export into a D1 snapshot, include R2 bytes, prove restore readiness, or establish a complete production backup. Gate 5 Shopping publication and every later validation, smoke, correction, rollback, or recovery step remain closed pending separate authority.
