# Next Actions

This document contains the current execution horizon. Long-term ordering is in the [Roadmap](ROADMAP.md); exact operational truth is in [Current State](CURRENT_STATE.md).

## Parked Product Owner review — public Version 31

1. Open Shopkeeper on mobile first, then desktop, and confirm the compact scan/search surface is visually usable.
2. Scan a known Library ISBN and confirm the duplicate/ownership result is explicit.
3. Present a retail UPC, confirm printed-ISBN recognition starts, and use **Retry text scan** when needed.
4. Upload a barcode photo and confirm either a recognized ISBN for confirmation or a clear manual fallback.
5. Check one new ISBN and one metadata-unavailable ISBN; confirm both hand off to Library without adding or changing a record automatically.
6. Confirm **Scan another ISBN**, cancel, and Library navigation reset the workflow cleanly.

Resume this checklist only when the Product Owner is ready. Parking it neither accepts nor rejects Version 31.

## Completed release maintenance

- Unpublished `4763cb1026911d4829b2dcb426e342d6f66dfa79` makes pnpm canonical, removes the stale npm lockfile, and makes the package scripts portable.
- The configured Node 24 direct Vinext build passes. The standard Site wrapper still fails on this host because its launcher reaches the system Node 18 path; that host/tooling limitation is separate from application correctness.

## Completed foundation and Shopkeeper pass

1. Reconcile the durable documentation from the rejected Version 26 state through accepted public Version 30.
2. Preserve the scanner stability note: photo upload is more reliable, while live capture may require retries.
3. Add focused unit coverage for the known read-only ISBN metadata and stored-cover retrieval endpoints.
4. Record ISBN and reference-cover enrichment as parallel design/test lanes over shared provider boundaries.
5. Record tags as a possible consumer of provider categories while keeping canonical tag persistence and owner decisions separate.

The original endpoint foundation passed 7/7 in Version 31 lineage. Unpublished source `339c3bf74960171be2373f6c99d78c459bc12a2e` now carries bounded enrichment evidence through the shared scanner resolver, rejects unsafe candidate links, and passes 164/164 full checks, focused lint, and a production build. Version 31 remains public at exact source `d9d83bb4c964c2de9af8c0affdcb1a44ed5e6792`.

## Next implementation milestone — enrichment boundary

Continue nonvisual contract and test work while Version 31 owner review is parked. Any visible presentation, Site version, deployment, or publication remains a separate gate.

The safest next implementation milestone is a provider-neutral, read-only enrichment boundary. It should be divided into independently reviewable slices:

### Slice A — provider and evidence contract — complete in unpublished source

- Existing Open Library lookup now returns bounded title, author, publisher, publication-date, first-year, subject, language, identifier, record-link, and CoverID evidence with explicit provider attribution.
- Transport and malformed-response failures return the existing stable unavailable outcome; empty results remain valid and manual fallback remains intact.
- Reference covers use CoverID URLs with `default=false`, remain remote candidates only, and do not consume Site storage.
- No additional provider, key, schema, persistence, tag, or UI behavior was added.

### Slice B — ISBN enrichment consumer — proposed for review

- First decide which existing Open Library fields may populate the reviewed add form and how conflicts are shown.
- Consider another no-cost source only after measured Open Library gaps justify it; Google Books is not the default because public-data calls require an API key or OAuth identifier.
- Preserve exact/equivalent local matching before external lookup.
- Return reviewable title, author, edition/date, and source evidence when available.
- Never create, merge, overwrite, or relabel a Book without explicit owner confirmation.

### Slice C — reference-cover consumer — proposed for review

- Consume the Open Library CoverID candidate already returned by the shared endpoint; prefer record/CoverID attribution over ISBN cover routing.
- Preserve uploaded personal covers and always distinguish personal from reference images.
- Define attribution, caching/storage limits, broken-link fallback, and replacement rules before enabling persistence.

### Slice D — tag discovery only

- Identify which approved provider fields might suggest tags.
- Do not create a tag table, import provider categories, or alter Books until the tag vocabulary and assignment workflow are separately approved.

Slices B and C may be researched, specified, and tested in parallel. Application-source edits remain sequential under the one-writer rule, and each slice must remain independently promotable.

The combined smallest visible proposal is in the [Enrichment Review Contract](ENRICHMENT_REVIEW_CONTRACT.md). It keeps one Add dialog, shows a compact read-only evidence block, uses a personal-cover-first reference fallback, and holds provider subjects out of the UI. Product Owner visual/UX approval is required before implementation.

## Later ordered work

1. Resolve the information gap for asset lifecycle and complete cover backup.
2. Design and implement tags.
3. Design safe import/restore.
4. Design AI Review over stable interchange and review proposals.
5. Expand administration and analysis.

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
