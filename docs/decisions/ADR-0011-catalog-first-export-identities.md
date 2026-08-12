# ADR-0011: Catalog-First Export Identities

## Status

Accepted

## Context

The first portable export needs identities that remain meaningful outside one database. Existing numeric `books.id` values are stable internally but are not portable. Existing `collections.key` values are generated once and survive rename. Businesses and Purchases do not yet have accepted portable identities.

## Decision

Format version 1 is catalog-first:

- Include Collections, Books, canonical Book identifiers, collection state, and an image-reference manifest.
- Exclude Businesses and Purchases explicitly.
- Use existing `collections.key` as the Collection external ID.
- Add a non-null, globally unique, immutable Book `stable_id` generated once and persisted additively. Never derive it from mutable metadata or expose the internal numeric ID as portable identity.
- Reference Books from identifier and manifest records by `stable_id`.
- Preserve internal numeric IDs only as implementation details and never require them for interpretation or future matching.

## Consequences

- M5 may implement and validate the additive Book `stable_id` locally after normal brief acceptance.
- Existing Book IDs, collection keys, relationships, and user data must remain unchanged.
- A future format revision may add Businesses and Purchases only after their immutable identity and compatibility contracts are accepted.
- Format v1 is not a complete transaction-history backup and must say so clearly.
- This decision does not authorize production migration, production export, Site saving, publication, import, restore, or rollback.
