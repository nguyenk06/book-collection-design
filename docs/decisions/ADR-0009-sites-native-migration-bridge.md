# ADR-0009: Sites-Native Migration Bridge for Shopping Schema Activation

## Status

Accepted

## Context

Version 17 contains locally validated Shopping persistence code and packaged migration `0004`, but Sites does not expose a verified packaged-migration execution, ordering, atomicity, retry, or traffic-gating contract. Direct D1 administration is outside the project operating model. Runtime `ensureSeeded()` creates and repairs only the Version 16-era schema, while ordinary Version 17 access expects the new Shopping columns and tables.

Direct publication could therefore serve Version 17 code against an unmigrated schema. Sites-native recovery controls are also limited: no direct D1 snapshot, export, Time Travel, query, or restore control is exposed to the Site Engineer.

## Decision

Use a temporary Version 16-compatible migration bridge before final Shopping activation.

The bridge will:

- Keep ordinary application traffic compatible with the Version 16 schema.
- Expose owner-authorized API boundaries for schema status, versioned structured JSON export, explicit re-entrant Shopping-schema upgrade, and post-upgrade verification.
- Implement guarded additive reconciliation that inspects state, tolerates repeat invocation and partial prior progress, preserves accepted identities/data, and records completion only after verification.
- Keep migration business logic in testable server modules rather than route handlers, UI components, startup, page load, or ordinary GET paths.
- Isolate Sites-specific authentication from upgrade business logic and keep D1/R2 behind API/server boundaries.
- Exclude packaged `0004` from independently executable bridge deployment content when the Sites packaging mechanism could otherwise execute it unpredictably.

Bridge implementation, saving an unpublished Site version, bridge publication, production JSON export, production schema upgrade, final Shopping publication, smoke testing, and destructive recovery remain separate scopes or approval gates. This decision approves only the architecture; the current implementation brief may authorize local implementation/validation and saving a new unpublished Site version.

## Consequences

- Direct Version 17 publication remains prohibited until the bridge workflow is implemented, validated, separately published, executed, and verified through approved gates.
- Application-level JSON export is a portable recovery artifact but is not equivalent to a D1 snapshot and does not include R2 object bytes by default.
- Additive schema and Version 16 application compatibility provide rollback protection; Site code rollback does not reverse database changes.
- Forward repair is preferred; no destructive down-migration is introduced.
- The bridge adds temporary implementation complexity but avoids undocumented Sites behavior as the sole data-preservation mechanism.
- Portability is preserved through explicit HTTP/JSON APIs, portable schema definitions, isolated authentication, server-side persistence boundaries, and testable business logic without building a generalized adapter framework now.
