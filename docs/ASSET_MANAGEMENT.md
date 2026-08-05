# Asset Management

## Purpose

Manage covers and supporting media as reliable, replaceable enrichment linked to canonical collection records.

## Scope

- Asset references, storage keys, and provenance.
- Preferred cover selection and deterministic fallbacks.
- Validation, deduplication, and lifecycle state.
- Reference-cover enrichment from permitted sources.
- Export and recovery expectations for user-owned assets.

## User workflow

1. View the current preferred asset and its source.
2. Upload, select, replace, or remove a preferred asset.
3. Review reference-cover candidates when useful.
4. Continue using the book record even when no asset exists.

## Data requirements

- Stable link to the relevant book or edition.
- Source, ownership/license notes, retrieval timestamp, and content type.
- Storage location, checksum, dimensions, and lifecycle status where applicable.
- Preferred/fallback selection state.
- Clear distinction between user-owned and remotely referenced content.

## Out of scope

- Making a cover mandatory for a valid book record.
- Assuming a cover proves edition identity.
- Indefinite caching without source and rights policy.
- Embedding large binary assets directly in core records.

## Dependencies

- [Database](DATABASE.md)
- Storage and delivery infrastructure
- [Import and Export](IMPORT_EXPORT.md)
- Source terms and retention policy

## Future improvements

- Perceptual duplicate detection.
- Automated format and size optimization.
- Broken-link monitoring and repair queues.
- Asset manifests for portable backups.
