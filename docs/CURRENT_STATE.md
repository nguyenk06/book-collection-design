# Current State

**Last reviewed:** 2026-08-16

## Authoritative snapshot

- **Published Site:** Version 19, the owner-authenticated administration surface.
- **Retained Site versions:** Version 18 migration bridge; unpublished Version 17 Shopping persistence/API foundation.
- **Production gate:** M2 Gate 3 was invoked exactly once through Version 19. Its immediate response reported Shopping schema completion and zero foreign-key issues. This is not Gate 4 verification or preservation proof.
- **Closed operations:** Gate 4 verification, corrective writes, Shopping publication, live validation, smoke testing, rollback, restore, and destructive recovery all require later authority. Gate 3 cannot be retried.
- **Local milestones:** M1, M3, M4, and M5 are complete. M2 Gates 0–3 are complete within their distinct evidence layers. M4's missing formal transport acceptance was closed as unverifiable and was not reconstructed.
- **Completed work:** Engineer — Sei completed and validated M6 locally in the recovered cumulative source. The downloadable catalog export UI remains unsaved and unpublished.

## Queue and ownership

- **Current role identities:** Planner — Quatre; Designer — Relena; Engineer — Sei.

- **Queue Mode:** `ENABLED`.
- **Throttle:** `DRAIN`; the approved batch is complete, no eligible brief remains, and new work requires a reviewed batch plus explicit authorization.
- **Engineer state:** `PAUSED`; the approved local batch is complete and no independently eligible brief remains.
- **Engineer continuation:** Preserve the cumulative M3–M6/Shopping/Bookshelf working source unchanged. Two read-only briefs are queued in P1/P2 order but remain ineligible until explicit `!run`.
- **Planner decisions:** None pending. Planner/Product Owner approved Gate 4 read-only verification and the independent read-only checkpoint/source-preservation feasibility investigation.
- **Active owner:** `EXTERNAL/WAIT` — Product Owner may issue `!run` when ready to activate the approved 8–12 point batch.
- **Potential later owner:** Product Owner must separately authorize any unpublished save/preview and hands-on validation after feasibility evidence identifies an exact safe environment.

## Usage reserve

The current Product Owner reading is approximately 50% remaining. The proposed next batch is estimated at 8–12 percentage points, leaving approximately 38–42%. The 30% remaining reserve is a mandatory floor, not a target; drain earlier for estimate overrun, missing authority, ambiguity, or insufficient validation/evidence/stop capacity.

## Current workstreams

| Workstream | State | Verified boundary | Next condition |
| --- | --- | --- | --- |
| Version 19 administration | Complete/published | Gate 2 status/export and Gate 3 invocation used the owner-authenticated same-origin surface | No further action currently authorized |
| Production schema activation | Stopped before Gate 4 | One Gate 3 invocation; immediate response reported completion and zero foreign-key issues | Separate Product Owner approval for Gate 4 verification |
| Shopping UI | Complete locally; unsaved/unpublished | Search/scan/status, Purchase history/capture, quality, and accessibility validation passed | Gate 4 and later separately gated release steps |
| M3 canonical identifiers | Complete locally | Focused/full tests, lint, and build passed | Future promotion remains separately gated |
| M4 bounded Bookshelf | Complete locally; unsaved/unpublished | Focused/full tests, build, and scoped lint passed | Product Owner checkpoint before activation; transport acceptance remains unverifiable |
| M5 catalog export foundation | Complete locally; unsaved/unpublished | Format v1, stable Book IDs, referential validation, deterministic output, no-write proof, and recovered editable source verified | Consumed by the completed local M6 UI |
| M6 downloadable export UI | Complete locally; unsaved/unpublished | 8/8 focused and 160/160 full serial tests, task lint, build, owner gating, no-write checks, and collision separation passed | Separate Product Owner checkpoint authority before any Site save or activation |

## Data and export status

- Gate 2 retained a private, validated structured bridge export covering 215 Books, 4 Collections, 0 Businesses, 0 Purchases, and 17 cover references, with unique identifiers and no broken references. It is not a D1 snapshot and excludes R2 bytes.
- Gate 3's immediate response reported activation success, but current production schema and preservation invariants remain unverified until Gate 4.
- M5 provides a validated local catalog format-v1 export foundation with persisted immutable Book stable IDs. M6 adds the validated owner-only downloadable UI locally; neither milestone has been saved, published, or run against production.
- No complete production backup exists. Direct D1 export and Time Travel controls remain unavailable unless Sites exposes a supported mechanism.
- Existing mutable import remains immediate and insufficiently safe; no restore or round-trip import workflow is authorized.

## Capability status

| Area | Current state |
| --- | --- |
| Database | Gate 3 immediate response reports Shopping schema completion; Gate 4 verification is unperformed |
| Shopping | Bounded UI complete and validated locally; unsaved/unpublished |
| Scanner | Existing scanning works; M3 canonical identifier foundation is complete locally |
| Bookshelf | Bounded first release complete locally; unsaved/unpublished and checkpoint-gated |
| Import/Export | Bridge export completed privately at Gate 2; catalog format-v1 foundation and owner-only downloadable UI complete locally; import remains unsafe/immediate |
| AI Review | Planned; safe interchange and proposal workflow incomplete |
| Assets | Personal cover upload/R2 serving exist; metadata, variants, cleanup, and complete byte backup do not |
| Tags | Planned; persistence absent |

## Park-and-resume rule

A task-level question preserves the exact safe resume point and enters `WAITING FOR ANSWER`; unrelated eligible work may continue. The whole run pauses only for cross-cutting safety, correctness, authority, collision, exhaustion, or reserve conditions, or when no independent task remains. Answers attach to the parked task, and affected assumptions, shared files, dependencies, and remaining validation must be rechecked before resumption.

## Next milestone

M6 is complete and validated locally, and the current cycle remains drained. The approved next batch contains separately gated Gate 4 read-only verification followed by read-only checkpoint feasibility and candidate-preservation assessment. Both briefs are prepared but require explicit `!run` and individual acceptance. No preview, Site save, source change, publication, production export, activation, or fallback development is authorized. See [Next Batch Plan](NEXT_BATCH_PLAN.md), [Next Actions](NEXT_ACTIONS.md), [Staged Milestones](STAGED_MILESTONES.md), and [ADR-0012](decisions/ADR-0012-live-shopping-validation-sequence.md).
