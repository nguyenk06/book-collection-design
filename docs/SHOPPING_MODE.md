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

## Verified Saved Foundation

Unpublished Site Version 17 preserves locally validated persistence and owner-authorized APIs for:

- Business listing and creation with normalized-name duplicate prevention.
- Purchase creation and per-Book Purchase history.
- Independent purchase and sticker prices in non-negative integer cents.
- Optional purchase date and controlled condition values.
- Nullable collection target price, with CYOA configured to 600 cents locally.
- Nullable Book Added Date for new manual/imported records without fabricating historical dates.

This foundation is saved but has not been migrated to production or published; Version 18 remains live as the migration bridge, and Version 19 is an unpublished administration surface. Saving Version 17 did not execute its packaged migration or add Shopping Mode UI. Purchase creation intentionally does not update Book ownership or copy counts.

## Remaining Milestone Work

- Approve and execute production migration and verification separately from publication.
- Complete Shopping Mode UI on the persistence foundation.
- Define user-facing reconciliation when Purchase history and editable ownership state disagree.

## Accepted Local UI Phase

This bounded phase may proceed against local/disposable data before production schema activation:

- Provide a mobile-first Shopping entry and fast title, author, or identifier search using existing matching capability.
- Present ownership, buying status, copy count, relevant collection target price, and existing Purchase history without implying stronger edition certainty than the data supports.
- Allow an owner to record a Purchase with optional Business, independent purchase/sticker prices, optional date, and controlled condition through the existing owner-authorized APIs.
- Keep Purchase history and editable Book ownership/copy count independent. After recording a Purchase, state clearly that ownership was not changed; do not silently reconcile or derive one from the other.
- Provide explicit navigation to the existing Book edit flow when the collector chooses to update ownership separately.
- Preserve one-handed mobile behavior, clear loading/empty/error/success states, and accessible labels/focus.

Advanced candidate matching, normalized multi-identifier persistence, offline capture, production migration, publication, and automatic ownership reconciliation remain outside this phase.

## Future improvements

- Configurable decision cues and duplicate warnings.
- Store-session history and batch review.
- Better degraded-network capture.
- Collector-defined buying rules.
