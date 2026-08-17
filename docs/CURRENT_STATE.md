# Current State

**Last reviewed:** 2026-08-16

For a concise visual summary, see the [Project Dashboard](PROJECT_DASHBOARD.md). This document remains authoritative for exact operational state, gates, ownership, blockers, usage, and validation evidence.

## Authoritative snapshot

- **Published Site:** Version 19, the owner-authenticated administration surface.
- **Latest saved Site:** Version 20, an unpublished and undeployed preservation-only save of the exact validated cumulative Shopping/M3–M6/Bookshelf candidate.
- **Other retained Site versions:** Version 18 migration bridge; unpublished Version 17 Shopping persistence/API foundation.
- **Production gate:** Gate 4 independently observed `Shopping schema complete` and zero foreign-key issues through the read-only Version 19 surface, agreeing with Gate 3's immediate response. Gate 4 automatically stopped incomplete because target-price, count, identity, and preservation evidence was unavailable through that path.
- **Closed operations:** Additional production export/evidence, corrective writes, Shopping publication, live validation, smoke testing, rollback, restore, and destructive recovery all require later authority. Gate 3 cannot be retried.
- **Local milestones:** M1, M3, M4, and M5 are complete. M2 Gates 0–3 are complete within their distinct evidence layers. M4's missing formal transport acceptance was closed as unverifiable and was not reconstructed.
- **Completed work:** Engineer — Sei validated the exact 24-path cumulative candidate (160/160 full serial tests), identity-matched its commit, remote branch, package, and saved source, then saved it exactly once as Version 20. No deployment, publication, preview, production access, or migration execution occurred.

## Queue and ownership

- **Current role identities:** Planner — Quatre; Designer — Relena; Engineer — Sei.

- **Queue Mode:** `ENABLED`.
- **Throttle:** `DRAIN`; P1 is accepted complete and P2 is parked by its usage gate.
- **Engineer state:** `PAUSED` at a clean post-preservation checkpoint.
- **Engineer continuation:** The approved private Gate 4 export brief remains preserved but ineligible until a fresh post-reset usage reading supports its full 3–5 point envelope and clean stopping cost.
- **Planner decisions:** None pending. Product Owner selected preservation-only save and bounded private export evidence (`1: A; 2: A`).
- **Active owner:** `EXTERNAL/WAIT` — wait for the August 21 usage reset and a fresh Product Owner reading; no new decision is required for the already-approved P2 scope.
- **Potential later owner:** Product Owner hands-on validation still requires a separately designed live-only sequence because Sites exposes no runnable unpublished checkpoint.

## Usage reserve

The fresh post-P1 Product Owner reading is approximately 36% remaining, with usage resetting August 21. P2 remains estimated at 3–5 points, including evidence and clean stopping cost; its high estimate would finish near 31%, below the preferred 35% cushion. P2 is therefore parked until the reset and a fresh reading. The protected floor remains 30% and is not a target.

## Current workstreams

| Workstream | State | Verified boundary | Next condition |
| --- | --- | --- | --- |
| Version 19 administration | Complete/published | Gate 2 status/export and Gate 3 invocation used the owner-authenticated same-origin surface | No further action currently authorized |
| Production schema activation | Gate 4 incomplete | Read-only Gate 4 independently confirmed schema-complete and zero-FK signals; preservation invariants remain unverified | Approved private-export evidence brief parked until the post-reset usage gate clears |
| Shopping UI | Complete locally; saved in unpublished Version 20 | Search/scan/status, Purchase history/capture, quality, and accessibility validation passed | Gate 4 and later separately gated release steps |
| M3 canonical identifiers | Complete locally | Focused/full tests, lint, and build passed | Future promotion remains separately gated |
| M4 bounded Bookshelf | Complete locally; saved in unpublished Version 20 | Focused/full tests, build, and scoped lint passed | Product Owner checkpoint before activation; transport acceptance remains unverifiable |
| M5 catalog export foundation | Complete locally; saved in unpublished Version 20 | Format v1, stable Book IDs, referential validation, deterministic output, no-write proof, and recovered editable source verified | Consumed by the completed local M6 UI |
| M6 downloadable export UI | Complete locally; saved in unpublished Version 20 | 8/8 focused and 160/160 full serial tests, task lint, build, owner gating, no-write checks, and collision separation passed | No runnable preview, checkpoint, deployment, publication, or activation authority |

## Data and export status

- Gate 2 retained a private, validated structured bridge export covering 215 Books, 4 Collections, 0 Businesses, 0 Purchases, and 17 cover references, with unique identifiers and no broken references. It is not a D1 snapshot and excludes R2 bytes.
- Gate 4 independently agrees with Gate 3 on schema-complete and zero-FK signals, but current target price, counts, identities, and preservation invariants remain unverified.
- M5 provides a validated catalog format-v1 export foundation with persisted immutable Book stable IDs. M6 adds the validated owner-only downloadable UI. Both are preserved in unpublished Version 20 but have not been deployed, published, run, or validated against production.
- No complete production backup exists. Direct D1 export and Time Travel controls remain unavailable unless Sites exposes a supported mechanism.
- Existing mutable import remains immediate and insufficiently safe; no restore or round-trip import workflow is authorized.

## Capability status

| Area | Current state |
| --- | --- |
| Database | Gate 4 independently confirms schema-complete and zero-FK signals but is incomplete for target-price/count/identity/preservation evidence |
| Shopping | Bounded UI complete and validated locally; preserved in unpublished Version 20 |
| Scanner | Existing scanning works; M3 canonical identifier foundation is complete locally |
| Bookshelf | Bounded first release complete locally; preserved in unpublished Version 20 and checkpoint-gated |
| Import/Export | Bridge export completed privately at Gate 2; catalog format-v1 foundation and owner-only downloadable UI complete locally; import remains unsafe/immediate |
| AI Review | Planned; safe interchange and proposal workflow incomplete |
| Assets | Personal cover upload/R2 serving exist; metadata, variants, cleanup, and complete byte backup do not |
| Tags | Planned; persistence absent |

## Park-and-resume rule

A task-level question preserves the exact safe resume point and enters `WAITING FOR ANSWER`; unrelated eligible work may continue. The whole run pauses only for cross-cutting safety, correctness, authority, collision, exhaustion, or reserve conditions, or when no independent task remains. Answers attach to the parked task, and affected assumptions, shared files, dependencies, and remaining validation must be rechecked before resumption.

## Next milestone

P1 preservation is complete. P2 private export remains approved but parked because 36% cannot support its 3–5 point envelope while preserving the 35% cushion. Reassess after the August 21 reset; do not issue or accept it before a fresh reading. No preview, deployment, publication, correction, migration retry, production write, restore, rollback, or hands-on validation is authorized. See [Next Batch Plan](NEXT_BATCH_PLAN.md), [Next Actions](NEXT_ACTIONS.md), and [Staged Milestones](STAGED_MILESTONES.md).
