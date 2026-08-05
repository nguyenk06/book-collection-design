# Roadmap

The database-first assessment validated the priority order. Enabling foundations are delivered immediately before their consumer; feature requirements remain in their linked documents.

## Status

| Priority | Workstream | Current status | Dependencies | Estimated effort | Known blockers |
| ---: | --- | --- | --- | --- | --- |
| 0 | Database integrity and Shopping persistence design | Partial; assessment complete, migration not implemented | D1 backup, orphan audit, migration verification and rollback | Medium | No foreign keys; overloaded `books`; invariants need definition |
| 1 | [Shopping Mode](SHOPPING_MODE.md) | Partial | Purchases, normalized Businesses, collection target price, condition vocabulary, transactional confirmation | Medium-large | No purchase history; ownership derivation rule unresolved |
| 2 | [Scanner and Matching](SCANNER_AND_MATCHING.md) | Partial | `book_identifiers`, ISBN-10/13 normalization, candidate workflow | Medium | One ISBN field; weak canonical matching; overwrite risk |
| 3 | [Bookshelf](BOOKSHELF.md) | Planned | Reliable expected-series positions, missing-position rules, detail behavior | Medium | Shelf view and mobile shelf-scroll behavior absent |
| 4 | [Import and Export](IMPORT_EXPORT.md) | Partial | Stable IDs, format version, revision token, dry run, conflict policy, backup metadata | Medium-large | Import writes immediately; no export or backup infrastructure |
| 5 | [AI Review](AI_REVIEW.md) | Planned | Versioned interchange, review batches/proposals, field comparison, concurrency protection | Large | Stable interchange and review staging absent |
| 6 | Reference cover enrichment | Planned | Minimal asset metadata, personal/reference distinction, attribution, safe identifier match | Medium-large | No asset table; identifier confidence weak; personal covers need protection |
| 7 | [Asset improvements](ASSET_MANAGEMENT.md) | Partial | Asset table, variants, cleanup, broken-object fallback | Medium-large | One image key; missing metadata; orphaned R2 risk |
| 8 | [Tags](TAGS.md) | Planned | Tag and book-tag assignment tables | Medium | Persistence absent |
| 9 | Analysis and administration | Partial | Purchase data and owner-only administration routes | Medium | Only live KPIs exist; no dedicated administration area |

## Completed foundations

- Published, private single-user application.
- Durable D1 records, R2 cover storage, and SQL migration mechanism.
- Collection selection, search, scanner, responsive collection views, and owner-only writes.
- Database-first architecture assessment and roadmap validation.
- Collector-first and book-first design direction.

## Immediate milestone

Implement only the Priority 0 integrity and Shopping persistence foundation:

- Preserve existing book IDs and collection keys.
- Add Businesses, purchases, and collection target price.
- Store money in integer cents and define condition values.
- Enforce the book-to-collection relationship after audit and backup.
- Add owner-authorized purchase create/read routes and focused migration tests.
- Keep Shopping UI redesign and later roadmap features out of scope.

Details and migration order are maintained in [Database](DATABASE.md). Accepted choices are recorded in the [Decision Log](DECISIONS.md).

## Deferred

- Full edition management and an immediate title/edition/copy hierarchy.
- Offline operation and generalized media support.
- Business locations.
- Social, lending, and marketplace capabilities.
- Fully autonomous AI changes to canonical data.
