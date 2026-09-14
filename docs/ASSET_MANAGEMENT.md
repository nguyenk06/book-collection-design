# Asset Management

**Current milestone:** M9 requirements planning; no implementation or production access is authorized.

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

## Accepted backup/lifecycle boundary

Product Owner Decision 4:A splits complete cover backup feasibility from asset-lifecycle implementation. The first future goal, when separately authorized, is read-only contract and evidence work: inventory personal cover references and stored bytes; define completeness and integrity checks; distinguish manifests from byte backups; document retention and recovery expectations; and identify unsupported or inaccessible storage boundaries. Only after that evidence is accepted may metadata, variants, cleanup, orphan handling, backup execution, or recovery implementation be scoped.

This direction does not establish that a complete cover backup exists, authorize R2 or production access, combine lifecycle and recovery into one goal, or change the existing catalog export's `bytes_included: false` boundary.

## Milestone 9 requirements contract

### Outcome

Provide an owner-downloadable, independently verifiable backup of personal stored-cover bytes and their stable Book associations without changing Books, cover objects, preferred-cover state, or remote reference-cover behavior. The package proves only what it actually contains. It is not a database backup, hosted retention guarantee, or restore implementation.

### Recommended package

- One ZIP per completed export, named with a format version and generation timestamp.
- A versioned `manifest.json` plus personal cover files under safe archive-relative paths.
- Manifest-level format version, generation time, exact application/release identity when available, scope declaration, totals, and verification result.
- One entry per personal cover object with stable Book ID when associated, non-secret storage/object identity, archive path, SHA-256 hash, byte size, detected media type, and optional dimensions.
- Remote Open Library images remain replaceable reference evidence. Their provider attribution or URL may be listed with `bytes_included: false`, but their bytes are not personal assets and are not included in the backup.
- The existing catalog export remains a separate metadata artifact until a later composition contract explicitly binds catalog and cover-package identities.

### Inventory and reporting

The dry run and completed package must separately report:

- referenced personal objects whose bytes are present and verified;
- Book cover references whose object is missing or unreadable;
- orphaned personal objects with no proven Book association;
- duplicate-content objects identified by equal cryptographic hash, without assuming which object is preferred;
- unsupported media types, invalid sizes, hash/read failures, and records lacking a stable Book association;
- excluded remote reference covers and any inaccessible storage boundary.

No inventory, duplicate, orphan, or missing-object finding authorizes automatic deletion, relinking, metadata repair, cover replacement, or Book mutation. Cleanup is a later proposal-and-confirmation workflow after a verified backup exists.

### Dry run and verification

1. A separately authorized read-only dry run enumerates the chosen object scope, resolves stable Book associations, reads only the bytes needed for type/size/hash evidence, and produces a sanitized inventory report without creating a backup or changing source state.
2. The dry run reconciles Book cover-reference counts, accessible object counts, missing/orphan/duplicate classifications, total bytes, and projected ZIP size. Any unexplained count or unsupported runtime/size boundary stops the milestone.
3. A later separately authorized export generates the ZIP from the accepted inventory boundary. Partial archives or failed reads must be labeled incomplete and must never be reported as a complete backup.
4. An independent offline verifier reopens the ZIP, validates its safe paths and manifest version, recomputes every included file's SHA-256 and byte size, checks declared media types, and reconciles every manifest entry and total.
5. Acceptance requires zero unexplained included-file/manifest mismatches, an explicit report for every exclusion or failure, and before/after proof that no Book, cover reference, stored cover object, or production setting changed.

### Operator and QA acceptance plan

The primary evaluation baseline is **1A + 2A**: every accessible personal stored-cover object is in scope, orphans are separately classified, and the completed package is available only as an authenticated owner download with no retained backup history. A later authorized dry run must first prove complete paginated listing, the intended storage key/prefix boundary, stable Book IDs, reconciled counts and bytes, and an acceptable projected runtime. If that proof fails, stop rather than silently narrowing scope. The fallback **1B + 2A** (currently referenced objects only, owner download only) requires an explicit recorded scope decision before implementation or retest.

Evidence is collected in three distinct gates; success at one gate does not stand in for another:

1. **Automated fixture tests:** use synthetic local records and objects only. Cover a referenced object, a missing referenced object, an orphan, two references or objects with equal content, unsafe and colliding source names, an unsupported or mismatched media type, a zero-byte or unreadable object, and enough objects to require multiple listing pages.
2. **Authorized non-mutating runtime feasibility:** in a separately authorized environment, record storage namespace and prefix, page count and continuation behavior, unique keys, stable Book-ID availability, classification counts, total and readable bytes, failures, elapsed time, projected ZIP size, and before/after state evidence. No archive is generated at this gate.
3. **Product Owner download and offline verification:** after separate implementation and publication authorization, the authenticated owner downloads the package, confirms no backup is retained or exposed to another session, disconnects from the application, reopens the ZIP offline, and runs or reviews the independent verification result.

Use `PASS`, `PARTIAL`, `FAIL`, or `NOT RUN` for each check. `PARTIAL` must identify every omitted object and its count/bytes/reason in both the report and package; it can never satisfy complete-backup acceptance.

| Check | Automated fixture proof | Authorized runtime proof | Product Owner proof |
| --- | --- | --- | --- |
| Inventory and pagination | Every page is consumed once; repeated tokens/pages and duplicate keys fail | Listed unique-object total reconciles to page totals within the declared prefix | Download summary shows the accepted scope and totals |
| Classification | Referenced, missing, orphan, duplicate-content, unsupported, and unreadable cases are mutually explicit | Every reference and listed object reaches a named class; unexplained records fail | Exclusions and incompleteness are understandable before download |
| Deterministic manifest | Reordered input produces identical normalized entry order and serialization apart from declared run metadata | Repeated dry runs over unchanged state reconcile classifications, paths, counts, and bytes | Manifest scope/version and completion status are visible |
| Safe archive paths | Reject absolute paths, traversal, control characters, reserved names, and post-normalization collisions | Proposed path set is unique and archive-relative | ZIP opens without path warnings or extraction outside the chosen folder |
| Integrity and type | Recomputed SHA-256, byte size, detected type, and manifest totals match; mismatches fail | Readable bytes have recorded size/hash/type; missing or failed reads are explicit | Offline verification recomputes each included file and reconciles totals |
| Owner-only and no-store | Authorization failures disclose no inventory or archive; responses use the required no-store behavior | Owner identity and cache/retention evidence are recorded without secrets | Another session cannot obtain the package; no server-side history remains |
| Failure handling | Interrupted listing/read/package cases remain `PARTIAL` or `FAIL`, never complete | Timeouts, access limits, and inaccessible boundaries preserve exact progress and omissions | A partial or corrupt download is visibly rejected |
| No mutation | Test doubles reject object writes/deletes/copies and Book/reference writes | Before/after evidence shows unchanged Books, references, objects, preferred-cover state, and settings | No library or cover change appears after download and offline verification |

Stop and return evidence to Quatre when pagination is unavailable or non-terminating; the key/prefix scope or owner boundary is ambiguous; stable Book IDs cannot be resolved; counts or bytes do not reconcile; an archive path collides or is unsafe; an object cannot be read or verified; projected memory, size, or runtime exceeds the accepted bound; authentication or no-store behavior fails; unexpected mutation occurs; secrets appear in output; or any incomplete result lacks explicit `PARTIAL`/`FAIL` labeling. No stopped run authorizes cleanup, archive generation, scope fallback, or source changes.

### Restore and lifecycle boundary

- Restore remains a separate later gate under [Import and Export](IMPORT_EXPORT.md). M9 does not write objects back, attach covers, merge Books, overwrite preferred assets, or prove rollback/recovery readiness.
- A future restore contract must define dry run, target identity, conflict handling, missing Book behavior, hash verification, owner confirmation, rollback, and partial-failure recovery before any write is authorized.
- Source personal-cover deletion, orphan cleanup, duplicate consolidation, format conversion, and retention automation are not part of backup generation and require separate Product Owner authority.

### Accepted Product Owner boundary

The Product Owner selected **1:A + 2:A** on 2026-09-14:

- Include every accessible personal stored-cover object. Book-referenced objects and orphaned objects remain separate manifest/archive classes. Treat the bytes currently stored by the application as the recoverable unit; do not claim unavailable pre-processing originals. Exclude Open Library reference-image bytes.
- Deliver the completed package as an authenticated owner download with no retained server-side backup history. Any temporary package must be bounded and removed without deleting source cover objects.

This decision makes M9 requirements-ready for a separately authorized read-only feasibility goal; it does not activate that goal or authorize implementation, production access, archive generation, cleanup, restore, or Site operations. If complete enumeration cannot be proven, stop and return a new explicit scope choice rather than silently falling back to referenced objects only. Archive encryption, splitting, or alternate delivery becomes a Product Owner question only if feasibility evidence shows it is necessary.

## Future improvements

- Perceptual duplicate detection.
- Automated format and size optimization.
- Broken-link monitoring and repair queues.
- Asset manifests for portable backups.
