# Planner Inbox

This file contains only unresolved decisions requiring Planner or product-owner input.

It is not a task backlog, technical issue tracker, Engineer progress log, changelog, roadmap, architecture document, or resolved-decision history. Designer owns this queue and removes each item after recording the accepted decision in the appropriate permanent source of truth.

## Current Decisions

### Decision 1 — Evidence standard after unavailable deployment metadata

**Context:** The one-query release-identity brief could not be accepted. The supported deployment-status lookup requires the exact opaque deployment ID that the ambiguous 1/1 publication invocation did not return, while the ordinary Site metadata view exposes no current published version/source or deployment history. No query was invoked; count remains 0/1. Version 21 is latest saved, a live release exists, and Version 20 is the last confirmed pre-invocation baseline, but exact current release identity remains unknown.

- **A — Authorize bounded read-only public-content fingerprinting as behavior-level evidence.** Prepare a brief that reads only the live public UI and compares deterministic Version 21-only behaviors—visible mobile Shopping navigation, primary multi-row Bookcase, horizontal Shelf alternate, selectable informative missing positions, and selected-book cover/fallback presentation—against the exact candidate. Explicitly do not claim exact version/source/deployment identity. If all fingerprints match without mixed state, return for Designer acceptance of behavior availability and a separate decision on whether that evidence is sufficient to open the already authorized read-only Product Owner checklist. Stop for any mismatch, ambiguity, authentication requirement, or mutation risk. No retry/publication/health sweep or data mutation.
- **B — Park for authoritative metadata.** Keep exact release identity unknown and all release-dependent validation closed until Sites exposes deployment history/current-version metadata or the missing deployment ID is supplied through a supported path.

**Designer recommendation:** `A` if the Product Owner accepts behavior-level rather than deployment-identity evidence; otherwise `B`. A fingerprint assessment is estimated at 2/4/7 five-hour points and requires a fresh reading of at least 22%, including the 15% floor.

When several decisions are pending, number them and keep each independently understandable. Planner may respond compactly, for example `1: B; 2: A; 3: DEFER`. Do not delay urgent or high-risk decisions for batching.
