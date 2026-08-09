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
- Required purchase price and optional sticker price in non-negative integer cents.
- Optional purchase date and controlled condition values.
- Nullable collection target price, with CYOA configured to 600 cents locally.
- Nullable Book Added Date for new manual/imported records without fabricating historical dates.

This foundation is saved but has not been migrated to production or published; Version 18 remains live as the migration bridge, and Version 19 is an unpublished administration surface. Saving Version 17 did not execute its packaged migration or add Shopping Mode UI. Purchase creation intentionally does not update Book ownership or copy counts.

## Remaining Milestone Work

- Approve and execute production migration and verification separately from publication.
- Separately approve preservation of the completed local Shopping source if a Site save is desired.
- Define user-facing reconciliation when Purchase history and editable ownership state disagree.

## Verified Local UI Phase

This bounded phase is complete and validated against local/disposable data before production schema activation:

- Provide a mobile-first Shopping entry and fast title, author, or identifier search using existing matching capability.
- Present ownership, buying status, copy count, relevant collection target price, and existing Purchase history without implying stronger edition certainty than the data supports.
- Allow an owner to record a Purchase with optional Business, required purchase price, optional sticker price, optional date, and controlled condition through the existing owner-authorized APIs. Never fabricate an unknown price as zero.
- Keep Purchase history and editable Book ownership/copy count independent. After recording a Purchase, state clearly that ownership was not changed; do not silently reconcile or derive one from the other.
- Provide explicit navigation to the existing Book edit flow when the collector chooses to update ownership separately.
- Preserve one-handed mobile behavior, clear loading/empty/error/success states, and accessible labels/focus.

Advanced candidate matching, normalized multi-identifier persistence, offline capture, production migration, publication, and automatic ownership reconciliation remain outside this phase.

The authoritative serial suite passes 50/50, focused Shopping tests pass 6/6, isolated collection regression tests pass 14/14, build passes, and task lint passes. The Shopping source remains unsaved; Version 19 is still the latest saved version and Version 18 remains published.

## Product Owner validation checkpoint

Shopping requires hands-on Product Owner validation before production activation. The validation environment must be private and user-accessible, expose the completed Shopping source, and use disposable/isolated data without production D1/R2 mutation. The preferred path is a supported Sites preview or unpublished saved version only after read-only feasibility confirms those boundaries and separate save/preview authority is granted.

Current blocker: the completed Shopping/P3 source exists only in the Engineer's unsaved local workspace. Version 19 does not include Shopping, and current evidence does not establish whether an unpublished Sites version can be opened functionally with isolated data rather than production bindings.

Use this concise checklist:

### Desktop

1. Open Shopping from collection navigation; search by title, author, and ISBN and confirm results explain current matching limitations.
2. Open a result and verify ownership, buying status, copies, target price when present, and Purchase history are understandable and distinct.
3. As owner, record a Purchase with required price and optional Business/sticker price/date/condition; verify blank or invalid price is rejected, duplicate submission is prevented, history refreshes, and ownership/copies remain unchanged with clear guidance to edit them separately.

### Mobile

4. Repeat a one-handed search and another-book flow; confirm controls, loading/empty/error/retry/success states, focus, and labels remain usable.
5. Exercise manual ISBN plus mocked/supported live-camera or photo scan behavior available in the validation environment; confirm malformed identifiers fail clearly and no unconfirmed Book/Purchase mutation occurs.
6. Confirm owner-only Purchase details/actions are not exposed when the available validation environment supports a signed-out or non-owner view.

Return exactly one outcome with concise notes:

- `ACCEPT`
- `ACCEPT WITH FOLLOW-UP`
- `REVISE BEFORE RELEASE`

Designer records the result and routes bounded feedback before any production-activation decision. After an explicitly approved publication, repeat a short smoke review of search, status presentation, navigation, and other approved critical paths. Production writes or cleanup require their own authority.

## Future improvements

- Configurable decision cues and duplicate warnings.
- Store-session history and batch review.
- Better degraded-network capture.
- Collector-defined buying rules.
