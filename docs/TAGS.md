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
- Uniqueness and normalization rules.
- Created and updated timestamps.
- Safe merge and deletion semantics.

## Out of scope

- Replacing structured fields such as ownership status or identifiers.
- Global taxonomy governance.
- Automatic AI tagging without visible suggestions and confirmation.
- Complex tag hierarchies in the initial design.

## Dependencies

- [Database](DATABASE.md)
- [Bookshelf](BOOKSHELF.md)
- Import/export mapping rules
- Bulk-action safeguards

## Future improvements

- Tag colors, descriptions, and saved combinations.
- Merge suggestions for near-duplicates.
- Optional rules-based or AI-assisted tag suggestions.
- Hierarchies only if collector workflows justify the added complexity.
