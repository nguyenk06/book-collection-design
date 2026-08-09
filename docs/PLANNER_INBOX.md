# Planner Inbox

This file contains only unresolved decisions requiring Planner or product-owner input.

It is not a task backlog, technical issue tracker, Engineer progress log, changelog, roadmap, architecture document, or resolved-decision history. Designer owns this queue and removes each item after recording the accepted decision in the appropriate permanent source of truth.

## Current Decisions

### Provide an Authorized D1 Operator Path

**Status:** AWAITING PLANNER / PRODUCT OWNER

**Decision needed:** Select or provide a privately authenticated, authorized D1 access path that lets the Site Engineer verify the exact production target and execute Packet A backup operations. Suitable paths may include an authenticated operator session or supported D1 connector.

**Current evidence:** Packet A revision 2 was explicitly authorized but automatically aborted before D1 contact because no authenticated direct operator path, supported connector, or existing authenticated Cloudflare session was available. The no-write window ended; no production query or operation occurred.

**Impact:** Access resolution does not itself authorize production access. After the path is available, a new explicit Packet A authorization and no-write window are required. Migration, D1/R2 writes, restore/import, Site deployment/publication, and smoke testing remain unauthorized.

Do not record credentials, tokens, resource identifiers, account details, or other private access information here. Confirm only that the path has been established privately.
