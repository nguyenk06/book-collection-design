# Enrichment Foundation

## Purpose

Create one understandable read-only evidence boundary that can support better ISBN metadata and reference-cover candidates without weakening local Library identity, personal-cover ownership, or explicit owner review.

## Current known endpoints

| Surface | Current purpose | Foundation expectation |
| --- | --- | --- |
| `/api/isbn/[isbn]` | Validate and normalize an ISBN, then request bounded attributed Open Library evidence | Keep invalid input local; expose no-result and provider failure distinctly; preserve source and cover-candidate evidence |
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

Unpublished source checkpoint `36f6b828317502eff65e45cbd7508ccaf96fbad3` covers:

- normalized ISBN request construction against the existing Open Library Search endpoint;
- bounded empty results, multiple candidates, publisher/date/subject/language/identifier normalization, record attribution, and CoverID reference candidates;
- stable unavailable behavior for provider transport and malformed JSON failures;
- stored-cover not-found behavior when a Book lacks a reference or an R2 object is absent; and
- stored-cover media metadata and public cache behavior.

The endpoint enrichment suite passes 9/9, and the full application suite passes 164/164 at pushed unpublished checkpoint `339c3bf74960171be2373f6c99d78c459bc12a2e`. That checkpoint carries bounded evidence through the shared scanner resolver and rejects unsafe candidate links. Focused lint and the configured Node 24 production build also pass. The work changes no scanner decision, Book mutation, cover persistence, tag persistence, schema, or visible UI behavior from public Version 31.

The smallest visible consumer is proposed in the [Enrichment Review Contract](ENRICHMENT_REVIEW_CONTRACT.md) and requires Product Owner visual/UX approval before implementation.

## Provider decision record

- Use the existing [Open Library Search API](https://openlibrary.org/dev/docs/api/search) as the first no-cost metadata boundary and request only bounded fields.
- Build remote candidates with the [Open Library Covers API](https://openlibrary.org/dev/docs/api/covers) by CoverID and `default=false`; link back to the Open Library record for attribution. No cover bytes are stored by this slice.
- Do not make [Google Books](https://developers.google.com/books/docs/v1/using) the default fallback: its public-data calls require an API key or OAuth identifier. Reconsider only if measured coverage gaps justify credentials and quota management.
- Do not use Open Library's legacy Books API; its own documentation identifies it as legacy and directs new work toward Search.

Future provider work must add deterministic fixtures for success, empty, malformed, timeout, partial failure, conflicting evidence, and source attribution before it is eligible for release review.

## Not yet authorized

- A new metadata or cover provider beyond the already-used Open Library service.
- Provider-result persistence or caching.
- Automatic Book, cover, or tag mutation.
- Schema, migration, authentication, dependency, or production changes.
- Site save, deployment, or publication.
