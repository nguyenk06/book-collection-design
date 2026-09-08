# Scanner and Matching

## Purpose

Turn a supported barcode or manual identifier into a transparent Library-wide result, optionally enriched through the existing ISBN metadata boundary when no local identifier matches, without silently changing canonical collection data.

## Version 25 corrective acceptance contract — Steps 2–3

Both camera-decoded and manually entered ISBNs on the full Library scanner and simplified Shopkeeper scanner must enter one shared deterministic resolution workflow:

- Preserve the submitted value for review, normalize ISBN input, validate length and checksum, and treat equivalent ISBN-10 and ISBN-13 values consistently.
- Search the complete local canonical identifier set exactly, independent of the currently selected collection. Do not infer a local match from title, author, cover similarity, or an external provider.
- Return one explicit local outcome: invalid or unsupported input; no exact match; one exact canonical match; or conflicting/multiple canonical claims.
- For one exact match, show the canonical Book plus existing collection, ownership, and copy evidence and identify it as already tracked without mutation.
- For conflicting local claims, require Library review and never pick or merge silently.
- Only when no exact local match exists, use the existing `/api/isbn/[isbn]` boundary for optional title/author evidence. Provider evidence remains a review candidate and does not independently prove canonical identity or duplicate status.
- Metadata failure or an empty response must still end in a visible manual-review path rather than a dead end.
- Show enough normalized identifier and source evidence to explain the outcome. Never present ambiguity as a confident match.
- Do not create, merge, overwrite, or otherwise mutate a Book, identifier, collection relationship, ownership state, or Purchase during detection or lookup. A Book may be created only after explicit owner confirmation in the Library review flow, with duplicate rechecking at confirmation.
- After any tracked, conflict, unmatched, metadata-empty, metadata-error, or handoff result, a repeat scan/reset returns both entry surfaces to a usable initial state without retaining a misleading prior outcome.

### Full Library behavior

The Library surface owns the complete review flow. It shows detailed exact/conflict/unmatched evidence, optional metadata candidate evidence, collection selection, editable prefilled fields, and a manual fallback. An unmatched ISBN and available metadata may prefill a reviewed add form, but only explicit owner confirmation may create the Book. A result may be an ephemeral review card; this contract does not establish a persistent candidate queue, reviewer record, or cross-session evidence store.

### Simplified Shopkeeper behavior

Shopkeeper uses the same validation, normalization, equivalence, complete-Library lookup, and optional metadata workflow but presents a compact acquisition result. A tracked result shows concise owned/missing/duplicate evidence and a continue-shopping action. A conflict opens `Review in Library`; an unmatched ISBN with metadata shows a short title/author preview plus `Review/add in Library`; unavailable metadata offers `Enter details in Library`. The handoff preserves the ISBN and ephemeral candidate context. Shopkeeper does not host a second mutable add form or perform relationship editing, candidate merging, automatic intake, persistent review, or automatic ownership/Purchase updates.

## Version 23 implementation and test evidence

Implementation and automated-test evidence was established at local checkpoint `75075e1e69735ac38c5afdbb7c9b7c55c12a2647` against the exact seven-path delta from Version 22 and includes:

- ISBN normalization, checksum rejection, and ISBN-10/ISBN-13 equivalence.
- Invalid, no-match, single-exact-match, and conflict/multiple-claim outcomes.
- Metadata success, empty-result, and failure outcomes through the unchanged existing ISBN API boundary.
- Reviewed Library add/manual fallback with duplicate recheck at confirmation, plus Shopkeeper context-preserving handoff to that flow.
- Proof that unconfirmed scanning and lookup do not mutate collection or purchase data.
- Distinct full Library and simplified Shopkeeper presentation, including accessible loading, result, empty, and error states at representative responsive widths.
- A source/diff collision check confirming that restoration composes with the exact Version 22 baseline and does not silently introduce excluded persistence, provider, or production scope.

## Evidence boundary and Product Owner result

Current validation at `75075e1` passed 57/57 focused tests and 109/109 full tests, lint with zero errors and two established warnings, production build, diff/whitespace, no-unconfirmed-mutation, and protected-boundary checks. The accepted delta changes only `app/page.tsx`, `app/scanner-resolution.ts`, `app/shopping/shopping-client.tsx`, `app/shopping/shopping.css`, `tests/scanner-resolution.test.ts`, `tests/scanner-identifier.test.tsx`, and `tests/shopping-mode.test.tsx`.

The checkpoint was pushed, saved, and published as Version 23 after explicit Product Owner authorization. The single deployment returned definitive `succeeded` at the existing public CYOA URL. Those implementation, automated-test, build, and publication results remain valid evidence, but they do not establish public hands-on acceptance.

On published Version 24, the Product Owner observed that both Library and Shopkeeper decode and display an ISBN but do not continue through Library-wide duplicate identification, metadata lookup outcome, review/add or manual continuation, or comparison. Scanner restoration therefore failed Product Owner public hands-on acceptance despite the earlier local and automated evidence.

The historical evidence does not prove a shared persistent candidate/reviewer workflow, cross-session decision storage, fuzzy scoring, physical-device behavior beyond the reported decode, provider behavior, or correct downstream runtime handoff on Version 24. Those capabilities must not be inferred.

## Version 25 corrective result

Exact Version 25 source `738acc07f3093bc74434dba2a32d62b94e6cfe06` publishes Kira's scanner commit `41ca4fc` plus aggregate/corrections HEAD `44a853f7430f92da37bf1c9cdef37bdfe2a6c7b2` and the Version 25 identity commit. Library and Shopkeeper share reactive scan submission/resolution, late or replaced results cannot reopen the flow, and aggregate My Library semantics no longer narrow matching or presentation to the add-target collection.

The exact baseline-to-HEAD boundary is eight UI/test paths: `app/globals.css`, `app/page.tsx`, `app/shopping/shopping-client.tsx`, `app/shopping/shopping.css`, `app/use-isbn-scanner-submission.ts`, `tests/collection-behavior.test.tsx`, `tests/scanner-identifier.test.tsx`, and `tests/shopping-mode.test.tsx`. Focused affected suites passed 61/61, the full serial suite passed 118/118, production build passed, lint reported zero errors and one established `no-img-element` warning, diff-check was clean, and Relena's final read-only release-boundary review returned `PASS`.

Version 25 was saved and successfully deployed at the existing public URL with the public audience preserved. Product Owner hands-on acceptance remains pending through the [Version 25 Product Owner Review](VERSION_25_OWNER_REVIEW.md). A canceled pending Library lookup can leave its `Checking ISBN…` notice visible until another action clears it; this is a non-blocking next-release follow-up if this area is touched and does not reopen the flow or mutate data.

## Out of scope

- Persistent candidate, reviewer, diagnostic-image, or cross-session evidence storage.
- Fuzzy title/author/cover scoring, threshold tuning, duplicate merging, or cover-only identity.
- Provider redesign, new metadata or cover providers, lookup for already-exact local matches, caching, or permanent new provider dependence.
- Physical-camera/photo support claims not re-established against current source and devices.
- Automatic Book creation, automatic ISBN persistence, canonical merge, ownership/Purchase mutation, or Shopkeeper Buy/Skip/Upgrade scoring.
- My Library aggregate semantics are outside the scanner contract and were completed separately in aggregate/corrections commit `44a853f`; cover loading/remediation or reference-cover enrichment, Shelf missing-title presentation, Phase F, and later releases remain out of scope and do not fail Version 25 acceptance.
- Production data access, Sites or credentials, deployment, schema/migration/authentication/API/provider/dependency/lockfile change, or data activation. If diagnosis shows that any protected change is necessary, stop and return for a Product Owner decision rather than expanding the corrective slice.

## Dependencies

- Exact Version 25 `738acc07` release identity, corrective `44a853f` source, and its eight-path collision manifest
- [Database](DATABASE.md)
- [Asset Management](ASSET_MANAGEMENT.md)
- Canonical identity rules and an accessible review interface

## Future improvements

- Explainable composite scoring across identifier, title, author, and cover evidence.
- Explicitly designed persistent review and audit workflow if later approved.
- Feedback-driven threshold tuning.
- Duplicate and near-duplicate detection.
- Batch scanning with interruption recovery.
