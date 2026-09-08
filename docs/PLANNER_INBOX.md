# Planner Inbox

This file contains only unresolved decisions requiring Planner or product-owner input.

It is not a task backlog, technical issue tracker, Engineer progress log, changelog, roadmap, architecture document, or resolved-decision history. Designer owns this queue and removes each item after recording the accepted decision in the appropriate permanent source of truth.

## Current Decisions

### Version 25 corrective candidate publication

- **Decision:** Approve a separately bounded publication-preparation/release gate for exact local candidate `44a853f7430f92da37bf1c9cdef37bdfe2a6c7b2`, or hold it unpublished.
- **Context:** Scanner commit `41ca4fc` plus aggregate/corrections HEAD `44a853f` is locally release-ready with Relena `PASS`; public Version 24 remains unchanged. This decision does not itself authorize app push, Site save/deployment/publication, or public validation.
