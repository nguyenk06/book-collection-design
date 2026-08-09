# Shopping Mode

## Purpose

Help a collector decide quickly whether to buy, skip, or investigate a book while shopping.

## Scope

- Fast barcode scan or text search.
- Clear owned, wanted, and uncertain states.
- Candidate selection when matching is ambiguous.
- Minimal actions suitable for one-handed, mobile use.
- Optional capture for later review.

## User workflow

1. Open Shopping Mode.
2. Scan a barcode or search by title, author, or identifier.
3. Review the best local collection match and its confidence.
4. See ownership, wanted status, and relevant copy or edition detail.
5. Add, update, dismiss, or defer the item.
6. Continue without navigating through the full catalog.

## Data requirements

- Normalized identifiers and searchable title/creator data.
- Collection status and, if supported, edition or copy detail.
- Match evidence, confidence, and alternate candidates.
- Timestamp and provenance for shopping actions.
- Offline or degraded behavior defined by implementation constraints.

## Out of scope

- Price comparison and retailer integrations.
- General collection administration.
- Requiring perfect edition metadata before a decision.
- Fully automatic purchasing decisions.

## Dependencies

- [Database](DATABASE.md)
- [Scanner and Matching](SCANNER_AND_MATCHING.md)
- Reliable mobile application behavior
- Collection search and status rules

## Verified Local Foundation

The Site working copy has locally validated persistence and owner-authorized APIs for:

- Business listing and creation with normalized-name duplicate prevention.
- Purchase creation and per-Book Purchase history.
- Independent purchase and sticker prices in non-negative integer cents.
- Optional purchase date and controlled condition values.
- Nullable collection target price, with CYOA configured to 600 cents locally.
- Nullable Book Added Date for new manual/imported records without fabricating historical dates.

This foundation is not saved as a Site version, migrated to production, or published. It adds no Shopping Mode UI. Purchase creation intentionally does not update Book ownership or copy counts.

## Remaining Milestone Work

- Save the validated source as an unpublished Site version.
- Approve and execute production migration and verification separately from publication.
- Complete Shopping Mode UI on the persistence foundation.
- Define user-facing reconciliation when Purchase history and editable ownership state disagree.

## Future improvements

- Configurable decision cues and duplicate warnings.
- Store-session history and batch review.
- Better degraded-network capture.
- Collector-defined buying rules.
