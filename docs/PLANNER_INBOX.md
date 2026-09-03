# Planner Inbox

This file contains only unresolved decisions requiring Planner or product-owner input.

It is not a task backlog, technical issue tracker, Engineer progress log, changelog, roadmap, architecture document, or resolved-decision history. Designer owns this queue and removes each item after recording the accepted decision in the appropriate permanent source of truth.

## Current Decisions

### Decision 1 — Response to Version 21 public behavior mismatch

**Context:** The bounded read-only fingerprint matched visible mobile Shopping navigation but not the exact candidate's other four markers. The public Site retained legacy `Gallery`, `List`, and `Bookshelf` controls with Gallery primary; no Bookcase-primary or Shelf-alternate control was present, so candidate missing-position and selected-book cover/fallback behavior could not match. Exact deployment/source identity remains unknown. The prior publication attempt remains consumed and ambiguous; authoritative deployment metadata is unavailable without the missing ID.

- **A — Authorize Designer to prepare one controlled exact-Version-21 republish brief.** The future brief must reverify the exact saved Version 21 candidate `f15ea8144ec277a737f5e491e0276b60555cafb8`, 47-file archive, exact three-file Version 20 delta, Site/session identities, preservation, collision, package, validation, and usage gates before permitting one new publication attempt. It must automatically stop for drift or ambiguity and must keep correction, migration, production schema/data mutation, broad smoke, held validation, rollback, restore, and destructive recovery closed. Any post-attempt observation must be separately bounded to the five public markers.
- **B — Park.** Preserve exact Version 21 and the mismatch evidence unchanged; perform no retry until supported authoritative release metadata becomes available or Product Owner supplies a different release direction.

**Designer recommendation:** `A` if the Product Owner still wants the five confirmed corrections live; the public behavior does not match the preserved exact candidate. A fresh usage reading and a new estimate are required before brief preparation.

### Decision 2 — Visible release marker request

**Context:** Sei III reported a Product Owner request to embed a release version on the homepage/footer. It was correctly excluded from the fingerprint brief. A static source marker would change exact `f15ea81`, require a new candidate/save/publication lifecycle, and still would not authoritatively identify a deployment unless its provenance and update rules are defined.

- **A — Queue separate design and local implementation planning after the current release is resolved.** Define a non-authoritative, owner-visible build/version marker with explicit provenance; keep implementation, save, and publication separately gated.
- **B — Defer.** Resolve the exact Version 21 release first and retain the marker as a later workflow improvement.

**Designer recommendation:** `B`. Do not alter the exact preserved candidate while resolving whether its unchanged saved version can be published successfully.

When several decisions are pending, number them and keep each independently understandable. Planner may respond compactly, for example `1: B; 2: A; 3: DEFER`. Do not delay urgent or high-risk decisions for batching.
