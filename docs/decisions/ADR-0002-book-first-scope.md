# ADR-0002: Book-first Scope

## Status

Accepted

## Context

Collectors often need to record and act on a book before complete edition or copy metadata is available. Making edition precision mandatory would slow capture and leave the collection incomplete.

## Decision

Core workflows operate at book level first. Edition and copy detail may enrich a record when known, but they do not block useful collection entry or lookup.

## Consequences

- Collection capture and shopping decisions remain fast.
- The data model must distinguish absent edition detail from confirmed book-level identity.
- Edition-specific workflows may require later reconciliation.
- Interfaces must not imply precision that the evidence does not support.
