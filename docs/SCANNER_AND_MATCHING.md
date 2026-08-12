# Scanner and Matching

## Purpose

Convert a barcode, cover, or text capture into a transparent, reviewable candidate for an existing or new book record.

## Scope

- Barcode and supported image/text capture.
- Identifier and text normalization.
- Local-first candidate lookup with optional external enrichment.
- Evidence-based scoring and confidence thresholds.
- Manual resolution of ambiguous or conflicting matches.

## User workflow

1. Capture a barcode or supported image.
2. Review the recognized identifier or text when necessary.
3. Receive a likely match or a short candidate list.
4. Confirm, choose another candidate, create a minimal record, or defer.
5. Preserve the decision and relevant evidence.

## Data requirements

- Raw capture reference or safely retained diagnostic data.
- Normalized ISBNs and searchable bibliographic fields.
- Candidate source, evidence, score, and model/rule version.
- Match decision, reviewer, and timestamp.
- Clear link to canonical book or edition identity.

## Out of scope

- Treating a cover image alone as conclusive identity.
- Silent merging of conflicting records.
- Permanent dependence on a single external metadata provider.
- Edition-perfect matching when a book-level decision is sufficient.

## Dependencies

- [Database](DATABASE.md)
- [Asset Management](ASSET_MANAGEMENT.md)
- External metadata adapters, where used
- Review interface and canonical identity rules

## Verified focused validation

The current local implementation has deterministic coverage for ISBN normalization, checksums, invalid inputs, manual scan handling, mocked live-camera/photo results, lookup success/failure, and absence of unconfirmed Book/Purchase mutation. Focused tests pass 18/18; the authoritative full serial suite passes 68/68; task lint and build pass.

Two narrow defects were corrected without expanding architecture: unsupported extra characters no longer normalize into a valid ISBN, and invalid checksums are rejected before external lookup. Physical-device testing, ISBN-10/13 conversion, canonical multi-identifier persistence, candidate scoring, duplicate merging, and external-provider redesign remain deferred.

The subsequent local canonical identifier foundation completed additive `book_identifiers` persistence, deterministic ISBN-10/13 conversion/equivalence, conservative conflict-aware backfill planning, and exact canonical lookup without merge or overwrite. Focused tests pass 29/29 and the full serial suite passes 79/79; lint and build pass. Fuzzy scoring, physical-device claims, provider redesign, and production/Site activation remain deferred.

## Future improvements

- Explainable composite scoring across identifier, title, author, and cover evidence.
- Feedback-driven threshold tuning.
- Duplicate and near-duplicate detection.
- Batch scanning with interruption recovery.
