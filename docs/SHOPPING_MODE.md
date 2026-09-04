# Shopping Mode

> **Naming transition:** Existing implementation, database, ADR, test, and release evidence uses **Shopping Mode**. The future user-facing product name is **Shopkeeper**. See [My Library Visual Experience](VISUAL_EXPERIENCE.md). Rename work is not currently authorized.

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

## Verified Foundation and Release State

Unpublished Site Version 17 preserves locally validated persistence and owner-authorized APIs for:

- Business listing and creation with normalized-name duplicate prevention.
- Purchase creation and per-Book Purchase history.
- Required purchase price and optional sticker price in non-negative integer cents.
- Optional purchase date and controlled condition values.
- Nullable collection target price, with CYOA configured to 600 cents locally.
- Nullable Book Added Date for new manual/imported records without fabricating historical dates.

Version 17 remains historical evidence for the saved persistence/API foundation; saving it did not execute its packaged migration or add Shopping Mode UI. Version 19 later supplied the owner-authenticated administration surface for Gates 2–4. Gate 3 invoked the guarded additive activation exactly once, and Gate 4 independently confirmed schema-complete and zero-FK status within its bridge-observable boundary. Exact cumulative Version 20 then published Shopping/M3–M6/Bookshelf successfully. Replacement mobile-navigation and Bookshelf corrections are now saved unpublished as Version 21 at exact `f15ea81`. Purchase creation intentionally does not update Book ownership or copy counts.

## Remaining Milestone Work

- Public fingerprinting matched visible mobile Shopping navigation but not the candidate's other four Bookshelf-related markers. Focused diagnosis passes 17/17 under Node 24, and the Product Owner accepted retained full 93/93 evidence for exact unchanged Version 21. The remaining build/package/publication brief is prepared but parked without Engineer authority; controlled publication Attempt 2 remains unused.
- After successful publication, prepare and run only the conditionally authorized read-only remediation checklist. Mutating Shopping scenarios and broad smoke remain separately gated.
- Preserve Version 20 as the current released baseline until Version 21 publication succeeds definitively.
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

The authoritative local suites passed before preservation and publication. Exact saved Version 20 later passed 92/92 saved-source, 160/160 layered, and 150/150 focused tests plus lint/build and published successfully once. Product Owner validation then confirmed a mobile Shopping-discoverability failure alongside Bookshelf failures. Replacement checkpoint `f15ea81` is saved as Version 21. Diagnostic focused tests pass 17/17, and the Product Owner accepted retained full serial 93/93 evidence for the exact unchanged candidate; the remaining build/package/publication slice is prepared but parked. The sole publication invocation returned no deployment identity or success result. An active live release exists, but its exact version is unverified; Version 20 is only the last confirmed pre-invocation baseline. Controlled Attempt 2 is unused. Read-only deployment-history reconciliation, further retry, the conditional remediation checklist, broad smoke, and all mutating Shopping scenarios remain separate gates.

## Product Owner validation checkpoint

The separate validation-Site direction is canceled. Remediation hands-on validation will occur on the live Site only after exact Version 21 publishes successfully under the controlled sequence in [ADR-0012](decisions/ADR-0012-live-shopping-validation-sequence.md). The first Version 21 checklist is read-only wherever possible and does not authorize the purchase-recording scenarios below; those mutating scenarios require another explicit Product Owner decision.

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

- Responsive Shopkeeper decision experience, collection-scoped sessions, Library-wide intake, and desktop workspace as defined in [Visual Experience](VISUAL_EXPERIENCE.md).
- Configurable decision cues and duplicate warnings.
- Store-session history and batch review.
- Better degraded-network capture.
- Collector-defined buying rules.
