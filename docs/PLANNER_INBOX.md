# Planner Inbox

This file contains only unresolved decisions requiring Planner or product-owner input.

It is not a task backlog, technical issue tracker, Engineer progress log, changelog, roadmap, architecture document, or resolved-decision history. Designer owns this queue and removes each item after recording the accepted decision in the appropriate permanent source of truth.

## Current Decisions

### M5 first-export entity scope

- **Status:** `AWAITING PLANNER`
- **Raised by:** Designer during M4 completion intake
- **Decision question:** Should the first portable export include Purchase history, or export the collection catalog first and defer Purchases?
- **Why Planner authority is required:** Including Purchases expands user-visible scope and requires an immutable Purchase identifier plus additional schema/compatibility work; excluding them makes the first export incomplete as a transaction-history backup.
- **Option A — Catalog-first:** Export Collections, Books, canonical identifiers, collection state, and image references; explicitly exclude Businesses/Purchases from format version 1 and add them only through a later compatible format revision.
- **Option B — Include Purchases:** Add immutable external IDs for Purchases and Businesses and include their relationships in version 1 before M5 implementation.
- **Designer recommendation:** A. It keeps M5 read-only and bounded while preserving an explicit, versioned path for transaction history.
- **Impact:** Resolves the M5 external-ID and field/scope contract. This decision authorizes documentation/brief revision only, not implementation, schema migration, export of production data, or publication.
- **Response:** `Decision: A` or `Decision: B`

When several decisions are pending, number them and keep each independently understandable. Planner may respond compactly, for example `1: B; 2: A; 3: DEFER`. Do not delay urgent or high-risk decisions for batching.
