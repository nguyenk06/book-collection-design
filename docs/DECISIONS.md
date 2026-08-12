# Architecture Decision Log

Architecture Decision Records capture durable choices and their consequences. Accepted ADRs are immutable; superseding decisions should link to earlier records.

| ADR | Decision | Status |
| --- | --- | --- |
| [ADR-0001](decisions/ADR-0001-purpose-of-repository.md) | Purpose of this repository | Accepted |
| [ADR-0002](decisions/ADR-0002-book-first-scope.md) | Book-first scope | Accepted |
| [ADR-0003](decisions/ADR-0003-shopping-mode-priority.md) | Shopping Mode is the highest user priority | Accepted |
| [ADR-0004](decisions/ADR-0004-reference-covers-as-enrichment.md) | Reference covers are enrichment, not core functionality | Accepted |
| [ADR-0005](decisions/ADR-0005-completion-over-edition-perfection.md) | Collection completion over edition perfection | Accepted |
| [ADR-0006](decisions/ADR-0006-preserve-identities-and-migrate-additively.md) | Preserve existing identities and migrate additively | Accepted |
| [ADR-0007](decisions/ADR-0007-shopping-persistence-foundation.md) | Separate Shopping persistence before UI work | Accepted |
| [ADR-0008](decisions/ADR-0008-canonical-books-and-identifiers.md) | Use canonical books with related identifiers, not AltBooks | Accepted |
| [ADR-0009](decisions/ADR-0009-sites-native-migration-bridge.md) | Use a Sites-native migration bridge before Shopping schema activation | Accepted |
| [ADR-0010](decisions/ADR-0010-owner-authenticated-administration-surface.md) | Operate the migration bridge through an owner-authenticated in-Site administration surface | Accepted |
| [ADR-0011](decisions/ADR-0011-catalog-first-export-identities.md) | Use catalog-first format v1 with persisted immutable Book IDs | Accepted |

The accepted database direction and migration sequence are summarized in [Database](DATABASE.md). Current implementation status is maintained in [Current State](CURRENT_STATE.md).

Unresolved questions requiring product-owner authority belong in the [Planner Inbox](PLANNER_INBOX.md). Only accepted, durable architectural decisions belong in this log and its ADRs.

## Adding a decision

1. Copy the structure of an existing ADR.
2. Use the next sequential number and a short descriptive filename.
3. Describe context, the decision, and both positive and negative consequences.
4. Add the ADR to this table.
5. Link superseded and superseding records without rewriting accepted history.
