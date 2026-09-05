# Knowledge Ownership Index

This page defines where knowledge belongs. It intentionally does not reproduce Engineer-local records, sources, classifications, experiments, or licensing notes.

| Knowledge space | Owner and storage | Authoritative purpose |
| --- | --- | --- |
| [My Library Visual Experience](VISUAL_EXPERIENCE.md) | Designer/Product Owner in this GitHub repository | Canonical future visual, responsive, mode, theme, safety-presentation, and phased-estimation direction; not implementation authority |
| [Future Improvement Catalog](FUTURE_IMPROVEMENT_CATALOG.md) | Planner/Designer in this GitHub repository | Ranked product and UX candidates; not roadmap commitments |
| Engineer Research Sandbox | Engineer-local shared handoff workspace under `knowledge/` | Raw technical notes, experiments, feasibility observations, source reviews, revalidation notes, and speculative options |
| Kira goal/brief | Internal durable brief storage routed by Quatre | Explicit bounded Kira authority: completion-oriented implementation through `IMPLEMENTATION_BRIEF.md`, or read-only estimation/source inspection through `ESTIMATION_BRIEF.md` |
| Kira report/release packet | Returned directly to Quatre; optional internal local evidence storage | Sanitized conclusions, validation, collision boundaries, release identity, material conflicts, and next-parent action |
| Tester knowledge | Engineer/Tester-local knowledge with formal evidence returned as needed | Coverage strategy, regression knowledge, and evidence conventions |

## Coordination rules

- Before a goal, Kira reviews only knowledge mapped to that goal, relevant `Needs Revalidation` items, and newly added notes affecting that component.
- No-change findings allow the sprint to proceed.
- Non-blocking findings remain local and are summarized to Quatre without stopping implementation; Quatre routes design implications to Relena.
- Material findings involving safety, data integrity, acceptance criteria, architecture, cost, behavior, priority, or scope must be reported before affected work proceeds.
- Relena decides whether a finding changes authoritative design, roadmap scope, the Future Improvement Catalog, or a Kira goal/brief under Quatre orchestration.
- The Product Owner participates only through Quatre when a material conclusion affects product behavior, priority, cost, risk, or scope.
- Kira may read `book-collection-design` but must not create, modify, commit, push, or publish anything in the repository or its GitHub surfaces.
- Kira returns evidence to Quatre; raw supporting material remains in local `knowledge/` or another designated internal folder.
- Relena alone writes approved conclusions into authoritative GitHub documentation.
- Do not restart completed research merely because its storage location changed; reorganize the existing local work and continue from it.

## Current classifications

- ZXing remains excluded from the current system, plan, and active research.
- Spine recognition remains deferred and mapped only to its low-priority future sprint.
- The detailed 2026-08-12 Engineer classification is preserved locally; only Designer-approved conclusions may return to GitHub.
