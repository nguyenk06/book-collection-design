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

## Future improvements

- Mapping profiles for common collection tools.
- Dry-run comparison and reversible batches.
- Incremental exports and attachment manifests.
- Formal schemas and compatibility tests for every format version.
