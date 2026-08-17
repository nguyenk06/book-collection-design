# Knowledge Ownership Index

This page defines where knowledge belongs. It intentionally does not reproduce Engineer-local records, sources, classifications, experiments, or licensing notes.

| Knowledge space | Owner and storage | Authoritative purpose |
| --- | --- | --- |
| [My Library Visual Experience](VISUAL_EXPERIENCE.md) | Designer/Product Owner in this GitHub repository | Canonical future visual, responsive, mode, theme, safety-presentation, and phased-estimation direction; not implementation authority |
| [Future Improvement Catalog](FUTURE_IMPROVEMENT_CATALOG.md) | Planner/Designer in this GitHub repository | Ranked product and UX candidates; not roadmap commitments |
| Engineer Research Sandbox | Engineer-local shared handoff workspace under `knowledge/` | Raw technical notes, experiments, feasibility observations, source reviews, revalidation notes, and speculative options |
| Engineer brief | External local `briefs/` transport only | Explicit bounded Engineer authority: implementation through `IMPLEMENTATION_BRIEF.md`, or read-only estimation/source inspection through `ESTIMATION_BRIEF.md`; the work type and exclusions must be explicit |
| Engineer report/handoff | Local shared `inbox/` only | Sanitized conclusions, material conflicts, verified facts, and requested decisions |
| Tester knowledge | Engineer/Tester-local knowledge with formal evidence returned as needed | Coverage strategy, regression knowledge, and evidence conventions |

## Coordination rules

- Before a sprint, Engineer reviews only local knowledge mapped to that sprint, relevant `Needs Revalidation` items, and newly added notes affecting that component.
- No-change findings allow the sprint to proceed.
- Non-blocking findings remain local and are summarized to Designer without stopping implementation.
- Material findings involving safety, data integrity, acceptance criteria, architecture, cost, behavior, priority, or scope must be reported before affected work proceeds.
- Designer decides whether a finding changes authoritative design, roadmap scope, the Future Improvement Catalog, or an Engineer brief.
- Planner/Product Owner participates only when a material conclusion affects product behavior, priority, cost, risk, or scope.
- Engineer may read `book-collection-design` but must not create, modify, commit, push, or publish anything in the repository or its GitHub surfaces.
- All Engineer communication to Designer goes through local `inbox/`; raw and supporting technical material remains in local `knowledge/` or another designated local folder.
- Designer alone decides what approved conclusion, if any, is written into authoritative GitHub documentation.
- Do not restart completed research merely because its storage location changed; reorganize the existing local work and continue from it.

## Current classifications

- ZXing remains excluded from the current system, plan, and active research.
- Spine recognition remains deferred and mapped only to its low-priority future sprint.
- The detailed 2026-08-12 Engineer classification is preserved locally; only Designer-approved conclusions may return to GitHub.
