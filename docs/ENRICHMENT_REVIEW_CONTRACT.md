# Enrichment Review Contract

**State:** Product Owner approved `1:A; 2:A; 3:A; 4:A`; implemented and pushed in unpublished source `893faa8a6b6e0282c788cdc6e1c7dc6fd8fe7bff`.

## Product Owner decision

- Use the existing **Add item** dialog for retrieved evidence.
- Show a reference cover only when no personal cover exists.
- Limit the compact evidence set to publisher, date/year, language, source link, and one thumbnail.
- Keep provider subjects hidden until the separate Tags milestone.

This approval authorized the bounded presentation implementation. It did not authorize a Site save, version, deployment, publication, production mutation, or tag model.

## Goal

Use the already-returned Open Library evidence to make scanned books easier to verify and books without personal cover photos easier to recognize, without creating another scanner workflow, silently changing records, or consuming Site storage for remote images.

## Recommended first visible slice

### 1. Keep one review path

- Preserve the current scanner result and its **Review and add** / **Enter details and add** action.
- Open the existing **Add item** dialog; do not introduce a third popup or a separate enrichment page.
- Keep title, author, ISBN, collection, series/issue number, and copies editable exactly where they are.
- Continue prefilling title and author from the first usable provider candidate, as the current scanner already does.

### 2. Add a clearly secondary evidence block

Place a compact **Retrieved information** block below the editable identity fields and above the final actions. It may show:

- publisher;
- publication date or first publication year;
- language;
- a labeled **Open Library record** source link; and
- one remote thumbnail labeled **Reference cover** when available.

The block is evidence, not saved Book data. It must say **Not saved until you add this book** and must not imply that every displayed field will be persisted.

### 3. Preserve cover ownership and fallback order

For an existing Book detail:

1. Show the uploaded personal cover when one exists.
2. Otherwise, if the Book has a valid ISBN and Open Library returns a CoverID candidate, show it as **Reference cover · Open Library** with a source link.
3. Otherwise, keep the current no-cover fallback.

A reference cover is never uploaded, copied into R2, or promoted to the personal-cover slot by this slice. A broken or unavailable remote image falls back without blocking the Book detail.

### 4. Hold tag presentation

Provider subjects may be retained as evidence but should not appear in the first visible slice. They are often numerous and inconsistent, and displaying them as tags would suggest a persistence model that does not yet exist.

## Responsive behavior

- Desktop: keep the existing dialog width and actions; place the small reference thumbnail beside the read-only metadata only when space permits.
- Mobile: stack the thumbnail above the read-only metadata, keep editable fields before evidence, and keep Cancel/Add actions reachable without horizontal scrolling.
- Do not make the remote cover a required loading dependency for opening, editing, or saving the form.
- Preserve keyboard focus, dialog labeling, source-link accessibility, 200% text enlargement, and the existing scanner-return behavior.

## Explicit state language

| Condition | Required message or label |
| --- | --- |
| Provider metadata present | `Retrieved information` |
| Remote image present | `Reference cover · Open Library` |
| Remote image fails | Use the current no-cover fallback; do not show a broken image |
| Provider unavailable | Preserve `Book information was not returned` and manual entry |
| Before add | `Not saved until you add this book` |
| Existing personal cover | Show it first; do not request or substitute a reference cover |

## Acceptance boundary

The first visible slice passes only when:

- duplicate, probable-existing, conflict, new-book, and unavailable-metadata scanner outcomes remain unchanged;
- scanning and lookup still perform no mutation;
- title and author remain editable before Add;
- the source and reference-cover labels are explicit;
- personal covers always win;
- reference-cover failure is non-blocking;
- no provider subject becomes a stored or implied canonical tag;
- mobile and desktop use the same workflow; and
- focused tests, the full suite, production build, and Product Owner review pass before publication.

## Not included

- Additional metadata providers or credentials.
- Provider-result caching or persistence.
- Saving publisher, publication date, language, subjects, or a remote cover to the Book record.
- Multiple-candidate comparison UI.
- Tag creation or assignment.
- Cover-byte backup, lifecycle cleanup, or recovery claims.
- Phase F bookcase/shelf visual changes.

## Product Owner review questions

1. Is the single existing Add dialog the correct place for retrieved information?
2. Is the reference-cover fallback acceptable only when no personal cover exists?
3. Should publisher, date/year, language, source link, and one cover thumbnail be the entire first visible evidence set?
4. Should provider subjects remain hidden until the separate Tags milestone?

All four questions were accepted as option A on 2026-09-13. The resulting source passed 71/71 focused checks, 167/167 full checks, lint with zero errors and three expected dynamic-image advisories, a production build, and `git diff --check` before commit and source-only push. Publication and hands-on visual acceptance remain separate gates.
