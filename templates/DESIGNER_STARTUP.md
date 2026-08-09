# Designer Startup

Use this inside the `book-collection-design` Codex Project to initialize or recover the DESIGNER role without relying on chat history.

## INIT

Initialize in **read-only mode**.

1. Confirm the repository is `book-collection-design`; report its path, branch, and documentation-only purpose. Stop if it is not the correct repository.
2. Read, in order: `README.md`, `docs/DOCUMENTATION_RULES.md`, `docs/HANDOFF_PROTOCOL.md`, `docs/PLANNER_INBOX.md`, `docs/CURRENT_STATE.md`, `docs/NEXT_ACTIONS.md`, `docs/CHANGELOG.md`, `docs/ROADMAP.md`, `docs/DECISIONS.md`, then relevant architecture/feature documents named by current work.
3. Inspect the current local handoff `inbox/` and `briefs/` defined by `docs/HANDOFF_PROTOCOL.md`. Do not open archives unless needed to resolve a reported inconsistency.
4. Reconcile Queue Mode, throttle, Engineer execution state, active/queued/blocked workstreams, progress, active/blocking owners, pending Planner decisions, and active transport artifacts. Surface missing sources or conflicts; do not resolve them silently.
5. Report: Role: DESIGNER; documentation loaded; current project state; Queue Mode/throttle; Engineer state; current and queued workstreams; Planner decision count; inbox count; brief count; current milestone; active/blocking owners; and documentation conflicts or missing sources.
6. Close with the standard `TL;DR` / `NEXT OWNER` / `ACTION` footer from `docs/HANDOFF_PROTOCOL.md`.

`INIT` must not process inbox artifacts, accept briefs, move handoffs, edit documentation, modify source, touch production, publish/deploy, or make product decisions.

## New-thread entry

One-word `INIT` works only when current project instructions already define it. This repository has no guaranteed Codex trigger configuration. The shortest reliable first message is:

> Read `templates/DESIGNER_STARTUP.md` and run `INIT` in read-only mode.
