# Bookshelf

## Purpose

Provide an understandable, useful view of the collector's books for browsing, finding, and maintaining the collection.

## Scope

- Search, filter, and sort collection records.
- Cover and compact list presentations.
- Owned, wanted, incomplete, and review-needed views.
- Navigation to book detail and maintenance actions.
- Stable behavior when covers or metadata are missing.

## User workflow

1. Open the bookshelf.
2. Select a saved view or apply search, filters, and sorting.
3. Scan the visible collection using cover and text cues.
4. Open a book for detail or maintenance.
5. Return without losing browsing context.

## Data requirements

- Canonical book identity and collection status.
- Display title, creator, and preferred cover with fallbacks.
- Filterable fields and collector-defined tags.
- Incomplete and review-needed indicators.
- Stable pagination or cursor semantics at scale.

## Out of scope

- Public social profiles or feeds.
- Physical shelf-location automation.
- Blocking display when enrichment is absent.
- Full administrative analysis.

## Dependencies

- [Database](DATABASE.md)
- [Asset Management](ASSET_MANAGEMENT.md)
- [Tags](TAGS.md)
- Consistent search and collection-state rules

## Future improvements

- Saved views and configurable shelf groupings.
- Physical location and lending views if later approved.
- Bulk maintenance actions with clear previews.
- Accessibility and performance tuning for large collections.
