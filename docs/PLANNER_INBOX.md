# Planner Inbox

This file contains only unresolved decisions requiring Planner or product-owner input.

It is not a task backlog, technical issue tracker, Engineer progress log, changelog, roadmap, architecture document, or resolved-decision history. Designer owns this queue and removes each item after recording the accepted decision in the appropriate permanent source of truth.

## Current Decisions

### Decision 1 — Safe recovery from unavailable process visibility

**Context:** Sei II preserved clean local candidate `7b3842379f01f9fc2cb29e1a7f9aa8dbc5745489`. The isolated responsive-link test passes. A focused run returned 11 passes and two explicit 10-second timeouts but no attributable PID or final summary. The next brief required a read-only full-command-line/ancestry query before another runner launch; that supported query returned `Access denied`, and no equivalent process-visibility mechanism is available in the Engineer environment. Starting or terminating another runner without quiescence evidence remains unsafe.

**Question:** Which bounded recovery path may Designer prepare?

- **A — One elevated read-only process inspection (recommended):** permit exactly one supported elevated query limited to full command lines and ancestry for processes referencing the exact candidate path or installed Vitest runner. It grants no termination or other system mutation. If the query proves quiescence, Designer may prepare a continuation using the retained candidate, synchronous PID capture, polling, and bounded 30-second command-line test/hook timeouts. If it finds an unowned candidate-scoped process or remains ambiguous, stop and return evidence.
- **B — Exact-commit isolated validation workspace:** permit Designer to prepare a separately gated disposable validation workspace materialized only from exact clean commit `7b38423`. It may not alter the retained candidate, use network dependency installation, change dependencies/configuration, or perform remote/Site/production work. Exact source identity, dependency viability, and collision isolation must pass before testing. Retain the workspace until Designer processes the result; deletion is not authorized by this decision.
- **DEFER:** retain `7b38423` unchanged and perform no further validation work.

Both A and B retain the 15% floor and require a fresh `!brief` followed by separate `!run`. Neither authorizes source correction, push, Site save/version, preview, deployment, publication, production access/mutation, schema/data work, held validation, rollback, restore, or destructive recovery.

When several decisions are pending, number them and keep each independently understandable. Planner may respond compactly, for example `1: B; 2: A; 3: DEFER`. Do not delay urgent or high-risk decisions for batching.
