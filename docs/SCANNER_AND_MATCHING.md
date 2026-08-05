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

## Future improvements

- Explainable composite scoring across identifier, title, author, and cover evidence.
- Feedback-driven threshold tuning.
- Duplicate and near-duplicate detection.
- Batch scanning with interruption recovery.
