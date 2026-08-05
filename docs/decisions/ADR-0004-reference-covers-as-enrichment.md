# ADR-0004: Reference Covers Are Enrichment, Not Core Functionality

## Status

Accepted

## Context

Cover images aid recognition and presentation, but availability, licensing, quality, and edition accuracy vary. Core collection operations must remain reliable without them.

## Decision

Reference covers are optional enrichment. Missing, broken, or uncertain covers must not block creating, finding, or maintaining a book record.

## Consequences

- Every relevant interface needs a useful no-cover fallback.
- Asset provenance and lifecycle remain separate from canonical book identity.
- Cover matching cannot be treated as conclusive edition evidence.
- Reference cover improvements can proceed after core workflows.
