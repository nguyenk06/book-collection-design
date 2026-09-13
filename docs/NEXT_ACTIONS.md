# Next Actions

This document contains the current execution horizon. Long-term ordering is in the [Roadmap](ROADMAP.md); exact operational truth is in [Current State](CURRENT_STATE.md).

## Immediate Product Owner review — public Version 31

1. Open Shopkeeper on mobile first, then desktop, and confirm the compact scan/search surface is visually usable.
2. Scan a known Library ISBN and confirm the duplicate/ownership result is explicit.
3. Present a retail UPC, confirm printed-ISBN recognition starts, and use **Retry text scan** when needed.
4. Upload a barcode photo and confirm either a recognized ISBN for confirmation or a clear manual fallback.
5. Check one new ISBN and one metadata-unavailable ISBN; confirm both hand off to Library without adding or changing a record automatically.
6. Confirm **Scan another ISBN**, cancel, and Library navigation reset the workflow cleanly.

Record only failures, unclear wording, or visual problems that require correction. Acceptance closes the Shopkeeper parity release.

## Release-maintenance follow-up

- Choose the repository's canonical package manager and remove the redundant tracked lockfile in a dedicated cleanup change.
- Re-run the standard Site build wrapper after cleanup. Until then, the direct Vinext production build is the verified release path.

## Completed foundation and Shopkeeper pass

1. Reconcile the durable documentation from the rejected Version 26 state through accepted public Version 30.
2. Preserve the scanner stability note: photo upload is more reliable, while live capture may require retries.
3. Add focused unit coverage for the known read-only ISBN metadata and stored-cover retrieval endpoints.
4. Record ISBN and reference-cover enrichment as parallel design/test lanes over shared provider boundaries.
5. Record tags as a possible consumer of provider categories while keeping canonical tag persistence and owner decisions separate.

The endpoint-focused suite passed 7/7. The Shopkeeper parity candidate passed 15/15 focused checks and the full application suite passed 161/161; the Version 31 identity passed 37/37 focused checks and a production build. Version 31 is public at exact source `d9d83bb4c964c2de9af8c0affdcb1a44ed5e6792`.

## Next implementation milestone — enrichment boundary

Begin only after Version 31 owner review is accepted or its bounded corrections are closed.

The safest next implementation milestone is a provider-neutral, read-only enrichment boundary. It should be divided into independently reviewable slices:

### Slice A — provider and evidence contract

- Inventory current ISBN and cover endpoints and their unit-test coverage.
- Define normalized response fields, source attribution, timeouts, partial failure, no-result behavior, and manual fallback.
- Prefer no-cost services that fit the hosted runtime and limited Site storage.
- Keep captured ISBN, local Library evidence, provider metadata, and provider image candidates distinguishable.

### Slice B — ISBN enrichment

- Try additional approved no-cost metadata evidence only after a valid ISBN lacks sufficient current results.
- Preserve exact/equivalent local matching before external lookup.
- Return reviewable title, author, edition/date, and source evidence when available.
- Never create, merge, overwrite, or relabel a Book without explicit owner confirmation.

### Slice C — reference-cover enrichment

- Find reference-cover candidates from approved sources using canonical ISBN evidence.
- Preserve uploaded personal covers and always distinguish personal from reference images.
- Define attribution, caching/storage limits, broken-link fallback, and replacement rules before enabling persistence.

### Slice D — tag discovery only

- Identify which approved provider fields might suggest tags.
- Do not create a tag table, import provider categories, or alter Books until the tag vocabulary and assignment workflow are separately approved.

Slices B and C may be researched, specified, and tested in parallel. Application-source edits remain sequential under the one-writer rule, and each slice must remain independently promotable.

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

- Resolve which package manager is canonical. Both `package-lock.json` and `pnpm-lock.yaml` are currently tracked, so the standard Site build wrapper refuses to choose one even though the direct production build succeeds.
- Treat removal of either lockfile as a deliberate, tested cleanup rather than incidental deletion during feature work.
