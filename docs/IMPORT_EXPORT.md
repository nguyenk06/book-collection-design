# Import and Export

## Purpose

Make collection data portable, recoverable, and safely transferable between the application and documented external formats.

## Scope

- Versioned import and export formats.
- Parsing, normalization, validation, and error reporting.
- Preview before ambiguous or destructive changes.
- Repeatable processing and batch-level audit information.
- Complete export of user-owned core collection data.

## User workflow

1. Select a supported source or request an export.
2. Review format version, scope, and field mapping.
3. Validate an import and inspect warnings or rejected rows.
4. Confirm the proposed changes.
5. Receive a completion summary and recoverable error report.

## Data requirements

- Documented field names, types, required values, and format version.
- Stable record identifiers where safe round trips require them.
- A portable immutable Purchase identifier before Purchase records must survive Import/Export, backup/restore reconciliation, or AI Review across database boundaries; this is deferred from the current Shopping persistence foundation.
- Batch identity, source, timestamps, row outcome, and error details.
- Provenance for imported values.
- Export metadata sufficient to interpret the file independently.

## Out of scope

- Undocumented database dumps as a user-facing format.
- Silent overwrite of conflicting canonical data.
- Importing arbitrary executable or active content.
- Guaranteeing compatibility with every third-party catalog format.

## Dependencies

- [Database](DATABASE.md)
- Canonical validation and duplicate rules
- Backup and recovery procedures
- Review UI for conflicts

## Accepted export-first boundary

Planner accepted an export-first safety foundation before mutable round-trip import:

- Define a versioned, read-only export of user-owned core collection data.
- Introduce immutable external IDs only where required for stable exported identity.
- Include an attachment manifest for referenced images; do not imply that a manifest contains image bytes.
- Include sufficient metadata to identify the format, creation time, scope, and compatibility version.
- Validate export completeness and internal referential consistency against disposable/local data.
- Defer dry-run import, revision semantics, conflict handling, import mutation, restore, and rollback to a later separately approved contract.

This boundary does not authorize a production export, backup operation, schema migration, Site save, publication, or implementation. Purchase portability remains dependent on an accepted immutable Purchase identifier.

## Future improvements

- Mapping profiles for common collection tools.
- Dry-run comparison and reversible batches.
- Incremental exports and attachment manifests.
- Formal schemas and compatibility tests for every format version.
