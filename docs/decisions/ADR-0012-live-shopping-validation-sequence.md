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

Gates 0–5 are complete within their documented evidence boundaries. Replacement `f15ea81` was saved as Version 21 and passed all local release gates. Its first publication invocation returned no deployment identity or success confirmation. A bounded public fingerprint then matched visible mobile Shopping navigation but not the candidate's four Bookcase-related markers. Product Owner authorized one controlled republish, but it stopped before focused test execution because the available Node 18 runtime did not meet the declared Node 22.13+ requirement. The new publication invocation remains unused. Exact live identity remains unverified; supported runtime alignment, health verification, and the Product Owner checklist remain separate gates.
