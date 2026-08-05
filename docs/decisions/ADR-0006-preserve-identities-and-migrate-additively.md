# ADR-0006: Preserve Existing Identities and Migrate Additively

## Status

Accepted

## Context

The current D1 schema is suitable as a migration starting point. Existing numeric book IDs and collection keys are stable within the deployed database, and current data can be evolved without destructive reinterpretation.

## Decision

Preserve `books.id` as the internal numeric primary key and preserve `collections.key` as the collection identifier. Evolve the schema through additive relational migrations, then gradually reduce the responsibilities held by `books`. Do not replace current identifiers or introduce a full title/edition/copy hierarchy in the first migration.

## Consequences

- Existing records and application references remain intact.
- Safe external interchange still requires a later immutable stable/public ID.
- Foreign-key enforcement requires an audit, backup, controlled table rebuild, and identifier-preservation checks.
- New responsibilities can move to related tables without a wholesale rewrite.
