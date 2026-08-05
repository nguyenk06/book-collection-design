# ADR-0008: Canonical Books with Related Identifiers

## Status

Accepted

## Context

The scanner needs to determine whether a scanned item is the same book despite equivalent or alternate ISBNs. A parallel `AltBooks` table would duplicate ownership, search, covers, purchases, tags, review, interchange, and rendering behavior.

## Decision

Do not create an `AltBooks` table. Relate multiple normalized identifiers to a canonical book through `book_identifiers`, with uniqueness on identifier type and normalized value. A small aliases relationship may be considered later only if title aliases become necessary.

## Consequences

- Search and collection behavior continue to use one canonical book record.
- Scanner work requires identifier normalization, evidence-based candidates, and tests that prevent overwrite.
- Existing alternate-numbering CYOA rows can remain book records initially.
- Alias support remains a future idea rather than part of the first identifier migration.
