# Scanner and Matching

## Purpose

Turn a supported barcode or manual identifier into a transparent Library-wide result, optionally enriched through the existing ISBN metadata boundary when no local identifier matches, without silently changing canonical collection data.

## Accepted Phase 0 contract

The full Library scanner and simplified Shopkeeper scanner share one deterministic resolution workflow:

- Preserve the submitted value for review, normalize ISBN input, validate length and checksum, and treat equivalent ISBN-10 and ISBN-13 values consistently.
- Search the complete local canonical identifier set exactly, independent of the currently selected collection. Do not infer a local match from title, author, cover similarity, or an external provider.
- Return one explicit local outcome: invalid or unsupported input; no exact match; one exact canonical match; or conflicting/multiple canonical claims.
- For one exact match, show the canonical Book plus existing collection, ownership, and copy evidence and identify it as already tracked without mutation.
- For conflicting local claims, require Library review and never pick or merge silently.
- Only when no exact local match exists, use the existing `/api/isbn/[isbn]` boundary for optional title/author evidence. Provider evidence remains a review candidate and does not independently prove canonical identity or duplicate status.
- Metadata failure or an empty response must still end in a visible manual-review path rather than a dead end.
- Show enough normalized identifier and source evidence to explain the outcome. Never present ambiguity as a confident match.
- Do not create, merge, overwrite, or otherwise mutate a Book, identifier, collection relationship, ownership state, or Purchase during detection or lookup. A Book may be created only after explicit owner confirmation in the Library review flow, with duplicate rechecking at confirmation.

### Full Library behavior

The Library surface owns the complete review flow. It shows detailed exact/conflict/unmatched evidence, optional metadata candidate evidence, collection selection, editable prefilled fields, and a manual fallback. An unmatched ISBN and available metadata may prefill a reviewed add form, but only explicit owner confirmation may create the Book. A result may be an ephemeral review card; this contract does not establish a persistent candidate queue, reviewer record, or cross-session evidence store.

### Simplified Shopkeeper behavior

Shopkeeper uses the same validation, normalization, equivalence, complete-Library lookup, and optional metadata workflow but presents a compact acquisition result. A tracked result shows concise owned/missing/duplicate evidence and a continue-shopping action. A conflict opens `Review in Library`; an unmatched ISBN with metadata shows a short title/author preview plus `Review/add in Library`; unavailable metadata offers `Enter details in Library`. The handoff preserves the ISBN and ephemeral candidate context. Shopkeeper does not host a second mutable add form or perform relationship editing, candidate merging, automatic intake, persistent review, or automatic ownership/Purchase updates.

## Local restoration acceptance evidence

Acceptance was established at local checkpoint `75075e1e69735ac38c5afdbb7c9b7c55c12a2647` against the exact seven-path delta from Version 22 and includes:

- ISBN normalization, checksum rejection, and ISBN-10/ISBN-13 equivalence.
- Invalid, no-match, single-exact-match, and conflict/multiple-claim outcomes.
- Metadata success, empty-result, and failure outcomes through the unchanged existing ISBN API boundary.
- Reviewed Library add/manual fallback with duplicate recheck at confirmation, plus Shopkeeper context-preserving handoff to that flow.
- Proof that unconfirmed scanning and lookup do not mutate collection or purchase data.
- Distinct full Library and simplified Shopkeeper presentation, including accessible loading, result, empty, and error states at representative responsive widths.
- A source/diff collision check confirming that restoration composes with the exact Version 22 baseline and does not silently introduce excluded persistence, provider, or production scope.

## Evidence boundary

Current validation at `75075e1` passed 57/57 focused tests and 109/109 full tests, lint with zero errors and two established warnings, production build, diff/whitespace, no-unconfirmed-mutation, and protected-boundary checks. The accepted delta changes only `app/page.tsx`, `app/scanner-resolution.ts`, `app/shopping/shopping-client.tsx`, `app/shopping/shopping.css`, `tests/scanner-resolution.test.ts`, `tests/scanner-identifier.test.tsx`, and `tests/shopping-mode.test.tsx`.

The checkpoint was pushed, saved, and published as Version 23 after explicit Product Owner authorization. The single deployment returned definitive `succeeded` at the existing public CYOA URL. Physical-camera/device behavior remains unclaimed until Product Owner hands-on review.

The historical evidence does not prove a shared persistent candidate/reviewer workflow, cross-session decision storage, fuzzy scoring, physical-device behavior, provider behavior, or current Version 22 integration. Those capabilities must not be inferred.

## Restoration status

The bounded restoration is complete, Relena returned `PASS`, and exact checkpoint `75075e1` is published as Version 23. The shared resolver performs whole-Library exact/equivalent matching first, calls the existing ISBN API only when unmatched, exposes explicit conflict/metadata-empty/failure outcomes, preserves reviewed handoff context through sign-in, and rechecks duplicates before confirmed Library creation. Scanner detection and lookup do not mutate Books, identifiers, ownership, collections, or Purchases.

## Out of scope

- Persistent candidate, reviewer, diagnostic-image, or cross-session evidence storage.
- Fuzzy title/author/cover scoring, threshold tuning, duplicate merging, or cover-only identity.
- Provider redesign, new metadata or cover providers, lookup for already-exact local matches, caching, or permanent new provider dependence.
- Physical-camera/photo support claims not re-established against current source and devices.
- Automatic Book creation, automatic ISBN persistence, canonical merge, ownership/Purchase mutation, or Shopkeeper Buy/Skip/Upgrade scoring.
- Production, Site, schema, migration, or data activation.

## Dependencies

- Exact current editable Version 22 source and a goal-specific collision manifest
- [Database](DATABASE.md)
- [Asset Management](ASSET_MANAGEMENT.md)
- Canonical identity rules and an accessible review interface

## Future improvements

- Explainable composite scoring across identifier, title, author, and cover evidence.
- Explicitly designed persistent review and audit workflow if later approved.
- Feedback-driven threshold tuning.
- Duplicate and near-duplicate detection.
- Batch scanning with interruption recovery.
