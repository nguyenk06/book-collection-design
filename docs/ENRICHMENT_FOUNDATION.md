# Enrichment Foundation

## Purpose

Create one understandable read-only evidence boundary that can support better ISBN metadata and reference-cover candidates without weakening local Library identity, personal-cover ownership, or explicit owner review.

## Current known endpoints

| Surface | Current purpose | Foundation expectation |
| --- | --- | --- |
| `/api/isbn/[isbn]` | Validate and normalize an ISBN, then request bounded title/author evidence | Keep invalid input local; expose no-result and provider failure distinctly; preserve source evidence when expanded |
| `/api/covers/[id]` | Retrieve the stored personal cover for a Book | Return a safe not-found result for missing references or bytes; preserve media metadata and bounded caching |
| `/api/books/[id]/cover` | Owner-only personal-cover upload/removal | Remains separate from reference-cover discovery and is not changed by enrichment planning |

Administration, catalog export, authentication, Books, Collections, Businesses, and Purchases have existing focused contract coverage and are outside this enrichment slice.

## Shared contract

- Local exact/equivalent identifier matches remain authoritative over external metadata.
- A captured ISBN is observed evidence; a provider title, author, subject, or image is supplied evidence. Store and display their provenance separately.
- Multiple candidates and conflicts remain visible. Do not silently select, merge, or overwrite.
- Timeouts, provider errors, empty results, and partial results must end in a useful manual or retry path.
- Provider use must be no-cost for the approved scope and compatible with hosted runtime and storage limits.
- Reference-cover candidates must never overwrite a personal cover automatically.
- Provider subjects/categories may inform later tag suggestions but are not canonical tags.

## Parallel work boundary

ISBN enrichment and cover enrichment may share provider requests, normalized source records, fixtures, and error handling. They must still be independently testable and releasable. Tag discovery may inspect the same sanitized fixtures without adding persistence.

Parallel research or review does not relax the one-writer rule for application source.

## Test foundation

The current source suite covers:

- normalized ISBN request construction against the known metadata endpoint;
- bounded empty results and multiple candidate normalization;
- stored-cover not-found behavior when a Book lacks a reference or an R2 object is absent; and
- stored-cover media metadata and public cache behavior.

The focused enrichment suite passes 7/7, and the full application suite passes 159/159 against the accepted Version 30 source plus this source-only test addition.

Future provider work must add deterministic fixtures for success, empty, malformed, timeout, partial failure, conflicting evidence, and source attribution before it is eligible for release review.

## Not yet authorized

- A new metadata or cover provider.
- Provider-result persistence or caching.
- Automatic Book, cover, or tag mutation.
- Schema, migration, authentication, dependency, or production changes.
- Site save, deployment, or publication.
