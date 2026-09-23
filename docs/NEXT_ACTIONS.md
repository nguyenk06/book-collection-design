# Next Actions

This document contains the current execution horizon. Long-term ordering is in the [Roadmap](ROADMAP.md); exact operational truth is in [Current State](CURRENT_STATE.md).

## Product Owner review — public Version 34

Exact source `14775b498dedcf71d54c4641ee457b0d64395f49` is saved and publicly deployed as Version 34. It provides one public hero-level **Scan ISBN** action across My Library, CYOA, and Redwall; removes the duplicate collection-toolbar scanner controls and discoverable Shopkeeper navigation links; retains Library and How it works; and keeps `/shopping` only as an unlinked shelved compatibility route with its mode label. Scanner resolution and public-scan/authenticated-mutation behavior are unchanged.

Exact-source evidence is release-boundary `PASS`, 14 files/182 tests passed, production build passed, lint reported zero errors and three established warnings, and diff/worktree checks were clean. Sites saved Version 34 and its deployment succeeded with the existing public audience.

Review and report `PASS` or `FAIL` with browser/device, viewport, Library state, and the last visible issue:

1. Inspect hero scanner spacing and hierarchy at desktop width.
2. Inspect the responsive shell and hero at the `<=1100px` wrap boundary.
3. Inspect the hero action at `<=720px` and representative mobile widths, including touch readability.
4. Check My Library, CYOA, and Redwall across their available Library states and confirm exactly one hero-level **Scan ISBN** action with no toolbar duplicate.
5. Confirm Library and How it works remain discoverable and no Shopkeeper link appears in header, primary navigation, mobile navigation, or other routine Library discovery.

This bounded review does not reopen broader held visual work or Shopkeeper as an active workstream.

## Probable-match release — published in Version 33

Version 32 mobile evidence confirms that Outcast of Redwall and The Bellmaker reach the correct ISBN-less `Need` records, but the result offers only **View Library record** and no usable edit surface. The Product Owner selected **Option A — confirm and update the existing record**.

Exact release source `013db3b5d747870723362ae430ffe923e32d8ba6` publishes the accepted public-scan/authenticated-mutation boundary. Public scanner capture, lookup, and explicit results remain non-mutating. **Save ISBN**, **Mark owned**, final **Add**, and every other Book edit require authentication. Sign-in and authorization-expiry flows preserve resumable review context, refresh and re-resolve authoritative Library state, and require confirmation before writing. After an Add receives 403, the active modal preserves the edited values, replaces **Add item** with **Sign in and resume review**, and cannot repeat the POST.

Final validation on the exact source passed the Node 24 serial suite at 14 files/181 tests, focused version checks at 2/2, lint with zero errors and three established image warnings, the production build, diff check, and clean-worktree check. Relena's final read-only release-boundary review returned `PASS`. Version 33 was saved and deployed successfully with the existing public audience; Product Owner testing is now the next gate.

## Accepted advance roadmap package

The Product Owner selected reviewable provider-seeded tag suggestions with canonical owner control, Book-only first tag attachment with an extensible later Collection path, catalog-v1 JSON as the only first safe-import format, manual external-agent review of explicitly selected exported data followed by safe reimport, and data quality plus backup health as the first expanded-administration focus. These are durable direction choices only; they do not activate implementation, external data transfer, or override later feasibility, privacy, cost, release, production, or held visual gates.

## Completed release maintenance

- Checkpoint `4763cb1026911d4829b2dcb426e342d6f66dfa79`, now incorporated into the public Version 32 source lineage, made pnpm canonical, removed the stale npm lockfile, and made the package scripts portable.
- The configured Node 24 direct Vinext build passes. The standard Site wrapper still fails on this host because its launcher reaches the system Node 18 path; that host/tooling limitation is separate from application correctness.

## Completed foundation and shelved Shopkeeper pass

1. Reconcile the durable documentation from the rejected Version 26 state through accepted public Version 30.
2. Preserve the scanner stability note: photo upload is more reliable, while live capture may require retries.
3. Add focused unit coverage for the known read-only ISBN metadata and stored-cover retrieval endpoints.
4. Record ISBN and reference-cover enrichment as parallel design/test lanes over shared provider boundaries.
5. Record tags as a possible consumer of provider categories while keeping canonical tag persistence and owner decisions separate.

The original endpoint foundation passed 7/7 in Version 31 lineage. Its bounded evidence propagation and safety checks are now included in public Version 32.

## Completed implementation milestone — enrichment presentation

The Product Owner approved the four recommended presentation choices. Their bounded visible consumer is now included in public Version 32 exact source `802db5fd9c54c79e4897cc12de86b875163f6c07`.

The delivered enrichment milestone used a provider-neutral, read-only boundary divided into independently reviewable slices:

### Slice A — provider and evidence contract — public in Version 32

- Existing Open Library lookup now returns bounded title, author, publisher, publication-date, first-year, subject, language, identifier, record-link, and CoverID evidence with explicit provider attribution.
- Transport and malformed-response failures return the existing stable unavailable outcome; empty results remain valid and manual fallback remains intact.
- Reference covers use CoverID URLs with `default=false`, remain remote candidates only, and do not consume Site storage.
- No additional provider, key, schema, persistence, tag, or UI behavior was added.

### Slice B — ISBN enrichment consumer — public in Version 32

- The existing Add item dialog now shows a secondary read-only evidence block with publisher, publication date/year, language, attributed source link, and one reference thumbnail when available.
- Consider another no-cost source only after measured Open Library gaps justify it; Google Books is not the default because public-data calls require an API key or OAuth identifier.
- Preserve exact/equivalent local matching before external lookup.
- Return reviewable title, author, edition/date, and source evidence when available.
- Never create, merge, overwrite, or relabel a Book without explicit owner confirmation.

### Slice C — reference-cover consumer — public in Version 32

- Consume the Open Library CoverID candidate already returned by the shared endpoint; prefer record/CoverID attribution over ISBN cover routing.
- Uploaded personal covers retain precedence; a reference image appears only when no personal cover exists and is explicitly labeled as Open Library evidence.
- Define attribution, caching/storage limits, broken-link fallback, and replacement rules before enabling persistence.

### Slice D — tag discovery only

- Provider subjects/categories may seed reviewable, uncommitted default suggestions, but never silently create canonical tags or assignments.
- The first tag attachment target is Books only. Preserve a future extension path for Collection-level tags without presenting that scope as implemented.

Slices B and C may be researched, specified, and tested in parallel. Application-source edits remain sequential under the one-writer rule, and each slice must remain independently promotable.

The approved bounded slice is recorded in the [Enrichment Review Contract](ENRICHMENT_REVIEW_CONTRACT.md). Validation passed 71/71 focused checks, 167/167 full checks, lint with zero errors, a production build, and diff integrity. Changing the reviewed ISBN clears evidence from the previous scan. Subjects remain hidden and no provider data or remote cover is persisted automatically.

## Version 32 release gate — complete

Exact source `802db5fd9c54c79e4897cc12de86b875163f6c07` was validated, saved as Site Version 32, and deployed with the existing public audience. Product Owner review is optional and uses the checklist above.

## Deferred lower-priority boundary — Milestone 9 cover backup

The durable [M9 requirements contract](ASSET_MANAGEMENT.md#milestone-9-requirements-contract) proposes a downloadable versioned ZIP manifest plus personal stored-cover bytes. It requires stable Book associations, SHA-256 hashes, byte sizes, media types, missing/orphan/duplicate reporting, no automatic source-object deletion, a read-only dry run, and independent archive verification. Open Library reference images are excluded as replaceable remote evidence, and restore remains a separate later gate.

The Product Owner selected **1:A + 2:A**: all accessible personal cover objects, including separately classified orphans, with owner-download-only delivery and no server-retained backup history. Encryption is not required. This milestone now follows Tags, Safe Import, and manual AI Review. When it eventually reaches its own fresh-capacity and separate-goal gate, begin with read-only feasibility only: inventory the selected scope, reconcile associations/counts, measure total bytes/projected ZIP size, and identify platform limits. Stop before implementation if enumeration, byte access, stable identity, or runtime limits are unresolved; stop immediately if a production write, cleanup, schema change, restore, or destructive action appears necessary.

## Later ordered work

1. Design Books-only tags with reviewable provider suggestions and later Collection extensibility.
2. Design catalog-v1-JSON-only safe import with no cover-byte mutation; keep restore separate.
3. Define the manual AI Review portability flow: owner-controlled export sharing, external proposals, review, and safe reimport.
4. Later, separately authorize read-only cover inventory and ZIP feasibility for accepted boundary 1:A + 2:A; encryption is not required.
5. Expand administration first around data quality and backup health.

## Held visual work

Do not implement denser spines, cover-detail presentation, Shelf missing-title presentation, or other visual changes until the Product Owner reviews the proposed change. Keep category-based shelves/bookcases and the aggregate collection-grouped Library.

## Resume and stopping rules

- Check current five-hour and weekly capacity before a project or large milestone.
- Keep a 10% five-hour clean-stop target, 5% hard lower boundary, and 15% weekly floor unless explicitly overridden.
- Preserve one active application-source writer.
- Stop for a genuine Product Owner decision, release/publication gate, capacity problem, material scope expansion, or validation failure.
- Keep `PLANNER_INBOX.md` empty unless an unresolved Product Owner decision genuinely blocks the next safe step.

## Repository hygiene before the next release

- Keep pnpm as the sole lockfile workflow.
- Use the configured Node 24 runtime for validation until the standard Site wrapper's Windows launcher/runtime selection is corrected.
- Do not mix that host-tooling repair into the next visible feature release unless it is independently verified.
