# Proposed Next Execution Batch

**Status:** APPROVED FOR BRIEF PREPARATION; AWAITING EXPLICIT `!run`
**Prepared:** 2026-08-16  
**Current usage:** Approximately 50% remaining  
**Protected reserve:** 30% remaining  
**Preferred planning cushion:** Finish above 35% remaining

Planner/Product Owner approved both bounded read-only activities (`1: A; 2: A`). Two queued briefs implement this envelope, but throttle remains `DRAIN`: neither brief is executable until a separate explicit `!run`. The decisions create no Site save, preview, source change, publication, corrective write, migration retry, restore, rollback, or later production-gate authority.

## Current stopping state

- The completed M3–M6, Shopping, and Bookshelf source remains in one recovered cumulative editable working tree based on published Version 19.
- M6 is complete and validated locally. Saved and published Site versions remain Version 19.
- Engineer — Sei is paused at a clean stopping point; no eligible implementation brief remains.
- Queue Mode remains enabled with throttle `DRAIN`. Do not replace or reinitialize the continuing Sei chat merely because the cycle ended.
- Preserve the cumulative source unchanged until a separately authorized operation begins with fresh composition and collision checks.

## Proposed batch

| Priority | Activity | Dependency | Estimated usage | Result / stop boundary |
| --- | --- | --- | ---: | --- |
| P1 | M2 Gate 4 read-only production verification | Separate Product Owner approval; correct Site, Version 19 surface, and owner session available | 3–5 points | Sanitized verification report; stop before every correction or later production gate |
| P2 | Sites checkpoint/preview feasibility investigation | Separate approval for read-only investigation; cumulative source remains unchanged | 2–4 points | Supported capability and exact next gate identified, or a blocker report if none exists |
| P3 | Candidate composition and preservation assessment | P2 platform evidence; no save authority | 2–3 points | Exact cumulative manifest, collision assessment, preservation recommendation, and pre-save validation checklist |

The activities share intake, source/context reconciliation, evidence preparation, and clean stopping. Estimated total is **8–12 percentage points**, including ordinary remediation within the read-only scopes, full relevant validation, reports, handoff preparation, and stop cost. From approximately 50%, expected remaining usage is **38–42%**. If any activity trends above its high estimate, drain after its current safe unit and defer the next priority.

## P1 — M2 Gate 4 verification plan

Gate 4 is a separately approved read-only production verification of the one-time Gate 3 response. It must:

1. Reconfirm the authoritative CYOA Collection Site, the Product Owner-controlled owner session, published Version 19, and the owner-authenticated same-origin administration surface before any request.
2. Use only the existing read-only status/verification path. Do not invoke the Gate 3 action again.
3. Verify the reported Shopping schema objects and constraints, zero foreign-key issues, the CYOA target price, and the preservation invariants for Book IDs, collection keys/data, covers/references, ownership, copies, and existing values.
4. Compare observed counts and identities against the private Gate 2 baseline: 215 Books, 4 Collections, 0 Businesses, 0 Purchases, and 17 cover references, while accounting only for explicitly known intervening authorized changes. Compare schema findings with the immediate Gate 3 completion/zero-foreign-key response.
5. Automatically stop on an unexpected Site/version/session, partial or ambiguous schema, count/identity/preservation mismatch, nonzero foreign-key issue, unavailable evidence, or any prompt/path that could write.
6. Produce sanitized evidence separating observed production state from the prior immediate response.

Gate 4 excludes corrective writes, Gate 3 retry, migration, schema/data mutation, Shopping publication, Site save, deployment, live validation, smoke testing, restore, rollback, forward repair, and destructive action. Every later production gate stays closed regardless of the result.

## P2 — User-facing checkpoint feasibility

First perform a read-only capability investigation. Do not assume Sites provides a runnable unpublished preview. Determine whether the continuing source-bearing Sei context exposes a supported Product Owner-accessible checkpoint that can use the cumulative editable source without publishing it.

Keep these operations independent:

1. Read-only feasibility investigation.
2. Preservation of the current editable source.
3. Creation of an unpublished saved Site version.
4. Creation or use of a preview/checkpoint.
5. Publication.
6. Production activation or migration.
7. Product Owner hands-on validation.

The investigation may inspect Sites capabilities, source/version metadata, access requirements, binding isolation, and whether a checkpoint would be runnable and private. It must not create a preview, save a Site version, deploy, publish, access production data, or alter source. If no safe unpublished checkpoint exists, report that result; do not silently fall back to live publication. ADR-0012's controlled live Shopping sequence remains authoritative for Shopping.

If a supported environment is later separately authorized, the Product Owner checkpoint should cover only concise realistic scenarios for:

- Shopping search/scan/status and owner Purchase history/capture.
- Visible canonical-identifier matching behavior without merge or mutation claims.
- Bookshelf collection selection, ordering/gaps, book detail, return context, keyboard, and mobile behavior.
- Catalog format-v1 download, filename/scope messaging, image-byte limitation, success/error/retry, and accessibility behavior.

Hands-on validation returns `ACCEPT`, `ACCEPT WITH FOLLOW-UP`, or `REVISE BEFORE RELEASE`; it never grants publication or production authority.

## P3 — Candidate composition and preservation

### Recommendation

Preserve the recovered cumulative source as one candidate unless supported Sites tooling can select exact changes without reconstructing the dirty working tree. Do not split it merely to recreate earlier milestone boundaries.

The cumulative candidate would include:

- Shopping search/scan/status, Purchase history, and owner Purchase capture.
- M3 canonical identifier utilities/model and migration `0005`.
- M4 Bookshelf view, main-page integration, global styling, and collection behavior.
- M5 catalog format-v1 service, stable Book IDs, API/schema integration, and migration `0006`.
- M6 owner-only catalog download page/API/client/styles and tests.
- The existing Shopping persistence foundation and its migration boundary already present in the cumulative source.

Shared surfaces include `db/schema.ts`, Book API/creation paths, authentication/database runtime, the main collection page, global styles, and the ordered migration set. M6's five files are isolated, but M6 depends on M5 and shared owner/runtime behavior. Shopping, M3, and M5 share schema, Book, identifier, and migration assumptions. Reconstructing separate worktrees now would repeat work and risk omitting validated interactions.

This preservation recommendation does not authorize publishing the cumulative candidate. The exact Shopping release candidate under ADR-0012 still excludes later work unless a future explicit convergence decision changes that boundary.

Published Version 19 remains protected as the clean production base. If Sites later proves that an unpublished save preserves source without preview, deployment, publication, migration, or activation, that save still requires separate Product Owner authority and an exact manifest.

Immediately before any future save, reverify:

- Correct continuing Sei context, editable source, dirty/unsaved state, and Version 19 base.
- Exact included/excluded file and migration manifest, with no unexpected generated files, secrets, or dependencies.
- Cross-workstream collision boundaries and owner/authentication behavior.
- Focused Shopping, M3, M4, M5, and M6 tests plus the authoritative full serial suite.
- Task lint, production build, `git diff --check`, no-write export evidence, and clean stopping capacity above reserve.
- That the proposed operation is save-only and cannot publish, deploy, activate migrations, or access production bindings implicitly. Stop if this cannot be established.

## Fallback work

No fallback implementation should be queued. AI Review, assets/covers, tags, import, and analysis are not mature independent fill-in work for this envelope, and advancing them would create scope merely to consume capacity. Keep the remaining usage for Gate 4, feasibility, remediation, validation, evidence, and a clean stop.

## Required authority sequence

1. Gate 4 read-only verification is approved for the next batch but awaits explicit `!run` and brief acceptance.
2. The read-only checkpoint/source-preservation feasibility investigation is independently approved for the next batch but awaits P1 transition, explicit `!run`, and brief acceptance.
3. Based on feasibility evidence, a later separate decision may authorize an exact unpublished save or supported preview. No such operation is authorized now.
4. After an exact safe environment exists, a later separate decision schedules Product Owner hands-on validation. Its outcome does not authorize publication.
5. No fallback implementation decision is needed because none is proposed.

Remain at `DRAIN` with Engineer — Sei paused until the Product Owner explicitly issues `!run`. Final batch order is P1 Gate 4 verification, then P2 checkpoint/source-preservation feasibility and composition assessment. P2 may proceed after P1 produces a completion or automatic-stop report unless P1 exposes a cross-cutting safety or identity conflict.
