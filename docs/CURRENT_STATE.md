# Current State

**Last reviewed:** 2026-08-04

**Maturity:** Published, actively designed, implementation baseline pending review

## Summary

A published Book Collection System site exists in a separate implementation repository. This repository now provides the durable design baseline. The exact production schema, feature completeness, and operational constraints have not yet been recorded here and must be verified during the database review.

## Current strengths

- A working, published product surface exists.
- Product direction is explicitly collector-first and book-first.
- Shopping, scanning, bookshelf, review, and portability workflows have defined design boundaries.
- Architecture decisions can now be recorded independently of implementation churn.

## Known limitations

- The current database inventory and relationships are not yet verified here.
- Feature maturity and known implementation defects are not yet mapped to the design documents.
- Data provenance, match confidence, and asset ownership rules need implementation review.
- Import, export, backup, and recovery guarantees need validation.
- Operational analysis and administrative workflows remain later priorities.

## Major upcoming work

1. Complete the database review and update [Database](DATABASE.md).
2. Capture verified implementation behavior in this document and [Architecture](ARCHITECTURE.md).
3. Advance [Shopping Mode](SHOPPING_MODE.md).
4. Improve [Scanner and Matching](SCANNER_AND_MATCHING.md).
5. Establish milestone-level acceptance criteria in the implementation repository.

## Milestone update checklist

- Change the review date and maturity statement.
- Move roadmap workstreams to the correct status.
- Record newly verified capabilities and limitations.
- Update architecture and database facts.
- Add material changes to the [Changelog](CHANGELOG.md).
- Create an ADR when a durable decision has been made.
