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

## Accepted format version 1 contract

Planner selected a catalog-first format. Version 1 includes:

- Format metadata: contract name, version `1`, generated timestamp, application/schema compatibility marker, and explicit included/excluded entity lists.
- Collections: immutable `collections.key`, display name, system/custom marker, and collection-level settings present in the accepted schema.
- Books: a new persisted immutable globally unique `stable_id`; collection reference by `collections.key`; bibliographic fields; series position; ownership, buying, copy, reading, notes/guidance, Added Date, and timestamps without fabricating unknown values.
- Canonical identifiers: identifier type/value associated by Book `stable_id`.
- Image manifest: Book `stable_id` plus existing image reference and explicit `bytes_included: false`; no image bytes or claim of complete media backup.

Version 1 explicitly excludes Businesses, Purchases, secrets, internal numeric Book IDs as portable identity, raw database structures, and R2 bytes. Unknown/null values remain null. The export must be read-only, self-describing, referentially consistent, and deterministic except for documented generation metadata.

The additive Book `stable_id` must be generated once, persisted, globally unique, immutable, and unrelated to mutable title/author/ISBN data. Existing `collections.key` remains the Collection external ID. See [ADR-0011](decisions/ADR-0011-catalog-first-export-identities.md).

## Future improvements

- Mapping profiles for common collection tools.
- Dry-run comparison and reversible batches.
- Incremental exports and attachment manifests.
- Formal schemas and compatibility tests for every format version.
