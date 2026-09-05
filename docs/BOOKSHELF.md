# Bookshelf

## Purpose

Provide an understandable, useful view of the collector's books for browsing, finding, and maintaining the collection.

The canonical future standing-bookcase, collection-switching, responsive, theme, and motion direction is [My Library Visual Experience](VISUAL_EXPERIENCE.md). This document retains the accepted bounded M4 behavior and evidence.

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

## Accepted bounded first release

Planner accepted a bounded collection shelf using existing collection and series-position data:

- Order within the selected collection by the existing series position.
- Represent gaps as clearly labeled missing-position indicators, not synthetic Book records.
- Open the existing Book detail/edit behavior for real Book records.
- Preserve the active collection, browsing position, and applicable view context when returning.
- Do not add physical locations, saved views, tags, bulk actions, or a new identity model in this phase.

This accepted bounded contract was implemented and validated locally; user-facing activation remains checkpoint-gated. The later standing-bookcase redesign is separate planning work and has no implementation authority.

## Verified local implementation

The bounded Bookshelf is complete locally and published in exact cumulative Version 20. It adds a persisted Bookshelf collection view, deterministic series-position ordering, explicit noninteractive missing-position gaps, keyboard-operable real Book spines, an accessible detail dialog with metadata fallbacks, and return behavior that preserves collection/view/scroll context. Focused collection tests pass 16/16; the then-authoritative full suite passed 81/81, and the later cumulative publication suite passed 160/160; build and scoped lint pass apart from one pre-existing scanner hook warning. Publication health did not exercise Bookshelf scenarios. Product Owner hands-on validation remains required.

Historical checkpoint `80e4c61` remains retired as an executable candidate. Replacement remediation from exact Version 20 is complete at clean checkpoint `f15ea81`, saved, and definitively published as Version 21. Controlled Attempt 2 returned deployment identity and `succeeded` status. After propagation, anonymous checks matched Bookcase primary, Shelf alternate, selectable informative missing positions, and selected-book cover fallback. Product Owner hands-on validation is parked by Decision 1:B. See the [remediation plan](VERSION20_CONFIRMED_FAILURE_REMEDIATION_PLAN.md).

## Future improvements

- One continuing vertical bookcase per collection, explicit switching, mobile bottom-sheet details, and restrained transitions as defined in [Visual Experience](VISUAL_EXPERIENCE.md).
- Saved views and configurable shelf groupings.
- Physical location and lending views if later approved.
- Bulk maintenance actions with clear previews.
- Accessibility and performance tuning for large collections.
