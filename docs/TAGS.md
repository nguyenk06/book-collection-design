# Tags

## Purpose

Let collectors organize books with flexible, personal labels that do not distort canonical bibliographic data.

Tags remain future persistence work. The My Library shell may reserve visual space for tag-driven organization, but must not present tags as implemented; see [Visual Experience](VISUAL_EXPERIENCE.md).

## Scope

- Create, rename, assign, unassign, and delete tags.
- Filter and group bookshelf views by tags.
- Normalize display safely while preserving intentional names.
- Support bulk assignment with a clear preview.

## User workflow

1. Create or select a tag.
2. Assign it from book detail, bookshelf selection, or supported import.
3. Browse or filter the collection using the tag.
4. Rename, merge, or remove it with an impact preview.

## Data requirements

- Stable tag identity separate from display name.
- Collector ownership and assignment relationships.
- An assignment design that keeps Books as the only initial target without coupling tag identity to Book-only assumptions that would block a later Collection target.
- Uniqueness and normalization rules.
- Created and updated timestamps.
- Safe merge and deletion semantics.

## Out of scope

- Replacing structured fields such as ownership status or identifiers.
- Global taxonomy governance.
- Automatic AI tagging without visible suggestions and confirmation.
- Collection-level tag attachment in the first release.
- Complex tag hierarchies in the initial design.

## Dependencies

- [Database](DATABASE.md)
- [Bookshelf](BOOKSHELF.md)
- Import/export mapping rules
- Bulk-action safeguards

## Accepted initial boundary

- Canonical tags remain collector-controlled. Provider subjects or categories may seed default suggestions, but each suggestion remains uncommitted, visibly attributed, editable or rejectable, and requires explicit confirmation before a tag is created or assigned.
- Provider wording never silently becomes the canonical vocabulary, and repeated provider values must not create duplicate canonical tags or assignments.
- The first attachment target is Books only. Initial filtering, assignment, import/export, and review behavior must not imply that Collections can already be tagged.
- The durable tag and assignment design must preserve a clear extension path for possible later Collection-level tags without promising or implementing them now.

This accepted direction does not authorize persistence, schema, provider, UI, import/export, or release work.

## Future improvements

- Tag colors, descriptions, and saved combinations.
- Merge suggestions for near-duplicates.
- Optional rules-based or AI-assisted tag suggestions.
- Hierarchies only if collector workflows justify the added complexity.
