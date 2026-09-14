# ADR-0014: Owner-Download Complete Cover Backup

## Status

Accepted

## Context

Personal cover bytes are stored separately from Book metadata. Book references alone cannot preserve or even identify every personal object when interrupted writes or earlier inconsistencies leave orphaned objects. Retaining generated backup snapshots on the server would add another storage lifecycle, access boundary, cost surface, and deletion policy before basic recoverability has been proven.

## Decision

- Include every accessible personal stored-cover object in the first complete-cover-backup scope.
- Classify Book-referenced and orphaned objects separately; never silently discard or relink an orphan.
- Treat currently stored bytes as the recoverable unit without claiming unavailable pre-processing originals.
- Exclude remote Open Library reference-image bytes.
- Deliver each completed backup as an authenticated owner-download-only versioned ZIP with a verifiable manifest.
- Retain no server-side backup history. Any temporary package is bounded and removed without deleting source cover objects.
- Require a separately authorized read-only feasibility run before implementation. If complete enumeration cannot be proven, stop and request a new explicit scope decision rather than silently narrowing the package.

## Consequences

- The preferred scope provides stronger preservation than a Book-reference-only export and can expose orphaned assets safely.
- Complete paginated storage enumeration, stable Book associations, runtime limits, and projected package size must be proven before implementation.
- Owner-download-only delivery avoids snapshot retention, storage-growth, expiry, and server-side package-deletion policy.
- Backup generation does not authorize cleanup, deletion, relinking, restore, production inspection, implementation, or Site operations.
- Restore remains a separate later design and authorization gate.
