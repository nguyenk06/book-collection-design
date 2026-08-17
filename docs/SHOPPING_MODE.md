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

This foundation is saved but has not been published as Shopping UI; Version 19 is live as the owner-authenticated administration surface, while Version 18 is retained in Site history. Gate 2 observed the pre-upgrade baseline and retained a validated structured export privately. Gate 3 later invoked the guarded additive activation exactly once. Gate 4 independently confirmed schema-complete and zero-FK signals but stopped incomplete because the existing surface could not expose target-price, count, identity, or preservation comparisons. Saving Version 17 itself did not execute its packaged migration or add Shopping Mode UI. Purchase creation intentionally does not update Book ownership or copy counts.

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

The authoritative serial suite passes 50/50, focused Shopping tests pass 6/6, isolated collection regression tests pass 14/14, build passes, and task lint passes. The Shopping source remains unsaved; Version 19 is the latest saved and published administration version, but contains no Shopping UI.

## Product Owner validation checkpoint

The separate validation-Site direction is canceled. Shopping hands-on validation will occur on the live Site using existing collection data only after the controlled sequence in [ADR-0012](decisions/ADR-0012-live-shopping-validation-sequence.md) reaches publication successfully.

The sequence does not weaken data preservation because the database is lightweight or correctable. Before schema activation, create and privately retain the bridge structured export, record preservation invariants, and acknowledge that the artifact excludes R2 bytes and is not a D1 snapshot. Preserve and verify Book IDs, collection keys/data, covers/references, ownership, copy counts, and existing values. Keep schema activation, verification, Shopping publication, hands-on validation, post-publication smoke testing, code rollback, forward repair, and destructive recovery as separate gates.

The Shopping release candidate must not accidentally include later M3–M5 work from the cumulative unsaved working copy. Engineer must establish an exact source baseline containing only the approved administration/migration path, Shopping UI, and P3 validation fixes. Stop before Site action if that candidate cannot be isolated and validated safely.

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

Designer records the live result and routes bounded feedback. `REVISE BEFORE RELEASE` in this live sequence means stop further use where practical, assess code rollback to the last compatible version, and require a corrective brief; it does not authorize destructive database recovery. After publication, repeat a short smoke review of search, status presentation, navigation, ownership/copies, cover rendering, and other approved critical paths. Production writes or cleanup require their own authority.

## Future improvements

- Configurable decision cues and duplicate warnings.
- Store-session history and batch review.
- Better degraded-network capture.
- Collector-defined buying rules.
