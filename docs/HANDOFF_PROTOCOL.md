# Design and Site Handoff Protocol

This protocol defines the file-based exchange between the Design workspace and the Site implementation workspace. Permanent product state belongs in GitHub design documents and Site version history. All briefs, reports, acceptance records, and handoff files are transport artifacts stored only in the external local handoff workspace; they must never be committed to `book-collection-design`, including for staging or archival.

## Site Engineer Read Location

Primary source of design truth:

<https://github.com/nguyenk06/book-collection-design>

Priority documents:

1. `docs/PROJECT_VISION.md`
2. `docs/CURRENT_STATE.md`
3. `docs/NEXT_ACTIONS.md`
4. `docs/ROADMAP.md`
5. `docs/DATABASE.md`
6. `docs/DOCUMENTATION_RULES.md`
7. Relevant feature documents and ADRs

The Site Engineer treats the public design repository as read-only reference. Engineer has no write role in `book-collection-design`: do not create, edit, move, delete, commit, push, branch, open a pull request, publish a release, or use GitHub issues/comments as an Engineer communication channel. When starting significant implementation work, read or request the relevant current documents. If the Site workspace cannot read GitHub directly, use the latest exported [`IMPLEMENTATION_BRIEF.md`](../templates/IMPLEMENTATION_BRIEF.md) as the handoff package.

## Roles

### Designer

The Designer works in the `book-collection-design` repository and owns:

- Product direction
- Roadmap
- Architecture
- Accepted requirements
- Documentation
- ADRs
- Preparation of implementation briefs
- Handoff workspace housekeeping
- Planner decision framing and `PLANNER_INBOX.md` housekeeping

GitHub communication is limited to Planner-facing decision items in `PLANNER_INBOX.md`. Designer-to-Engineer and Engineer-to-Designer communication uses only the external local `briefs/` and `inbox/` folders.

The Designer must not:

- Claim implementation occurred without verified Site evidence.
- Modify production Site state.

### Site Engineer

The Site Engineer works in the CYOA Collection ChatGPT Site workspace and owns:

- Site implementation
- Database, API, and UI changes
- Tests, build, and lint
- Local migration validation
- Site saved-version workflow
- Verified implementation handoffs

The Site Engineer must not:

- Modify the design repository directly.
- Create commits, branches, pull requests, issues, comments, releases, or any other GitHub artifact in `book-collection-design`.
- Return Engineer reports through GitHub; use only the local shared `inbox/` and other role-appropriate local folders.
- Invent product direction.
- Mark roadmap work complete without implementation evidence.
- Publish without explicit approval.
- Move briefs or reports between shared handoff folders.
- Archive, overwrite, delete, or reorganize shared handoff artifacts.
- Edit `PLANNER_INBOX.md` directly.

### Sites source-preservation exception

The Site Engineer may create and push the minimum source commit required to preserve an already validated source state through the Sites saved-version workflow when that workflow requires pushed source provenance.

This exception applies only to implementation source managed by the Sites workflow. It never permits any write to `book-collection-design`, which remains Designer-write-only.

- Limit the commit and push to the exact reviewed milestone source.
- Revalidate scope and sanitization before preserving the version.
- Treat the operation as Sites workflow plumbing, not a general user-managed Git release process.
- Saving a Site version does not authorize a production migration, preview deployment, or publication.
- Production migration and publication retain separate explicit approval gates.

This is an operational workflow rule, not a product or database architecture decision, so it does not require an ADR unless its scope later expands materially.

## Shared Information Locations

The Designer reads the following authorities in `book-collection-design`:

- `docs/PROJECT_VISION.md`
- `docs/ROADMAP.md`
- `docs/CURRENT_STATE.md`
- `docs/DATABASE.md`
- `docs/NEXT_ACTIONS.md`
- `docs/DOCUMENTATION_RULES.md`
- `docs/DECISIONS.md`
- `docs/KNOWLEDGE_INDEX.md` when research or future-improvement classification is in scope
- Relevant feature documents

## Research and knowledge handoff boundary

- Future Improvement Catalog records product/UX opportunities; it does not authorize roadmap scope.
- Engineer Research Sandbox is stored locally under the shared handoff workspace's `knowledge/` area and records technical feasibility, patterns, risks, experiments, and options; entries do not authorize implementation.
- Engineer briefs contain approved implementation only.
- Tester knowledge contains coverage strategy, regression knowledge, and evidence conventions; it does not authorize product or implementation changes.

Engineer reviews only local knowledge mapped to the new sprint, relevant `Needs Revalidation` records, and newly added notes affecting that component. No-change findings allow work to proceed. Preserve non-blocking improvements locally and report them to Designer without stopping implementation. Escalate material conflicts involving safety, data integrity, acceptance criteria, architecture, cost, behavior, priority, or scope before affected work proceeds.

All Engineer-to-Designer communication is written to the local shared `inbox/`; supporting Engineer material remains in the appropriate local folder. Engineer must not place raw or sanitized reports in GitHub. Designer alone decides whether a reported conclusion becomes authoritative GitHub design, roadmap scope, a Future Improvement Catalog disposition, or a brief. Planner/Product Owner participates only when a material escalation affects product behavior, priority, cost, risk, or scope. Research classification must never copy external code or authorize dependencies, schema changes, source changes, Site operations, or production actions.

The Site Engineer reads the public design repository at <https://github.com/nguyenk06/book-collection-design> or receives the latest implementation brief when direct reading is unavailable.

## Design to Site Handoff

The Designer prepares [`IMPLEMENTATION_BRIEF.md`](../templates/IMPLEMENTATION_BRIEF.md) for one coherent milestone. A brief may contain one or several bounded workstreams and remains a concise, share-ready specification containing only what the Site Engineer needs.

- Link to authoritative design documents instead of copying them.
- Distinguish verified current state from accepted requirements.
- State acceptance criteria, exclusions, risks, documentation evidence, and the approval boundary.
- Keep the file short enough to download, share, and review on mobile.

The brief authorizes only the stated implementation and validation work. It does not authorize publishing unless its approval boundary explicitly records separate product-owner approval.

## Site to Design Handoff

After implementation or a stopped attempt, the Site Engineer prepares [`DESIGN_HANDOFF.md`](../templates/DESIGN_HANDOFF.md). The report must be sanitized and based on observed implementation and validation evidence.

- Select exactly one status: `COMPLETE IMPLEMENTATION`, `PARTIAL IMPLEMENTATION`, or `VALIDATION FAILED`.
- Separate implemented, deferred, and not-attempted scope.
- Distinguish local validation, saved Site version, and publication state.
- Do not imply production verification unless it actually occurred and is safe to document.
- Identify proposed design changes separately from implementation facts.
- Mark each suggested documentation target `UPDATE`, `NO CHANGE`, or `REVIEW NEEDED`.

The Designer reviews the handoff under [`DOCUMENTATION_RULES.md`](DOCUMENTATION_RULES.md) before updating permanent project documents.

## Mobile-Friendly Workflow

The templates make these four commands sufficient for normal work:

1. Designer: **“Prepare implementation brief.”**
2. Site Engineer: **“Implement attached brief. Stop before publish.”**
3. Site Engineer: **“Prepare design handoff.”**
4. Designer: **“Apply attached handoff according to DOCUMENTATION_RULES.md.”**

## Workflow Shortcuts

Shortcuts are convenience aliases for existing lifecycle behavior. They reduce mobile typing but do not create authority, replace evidence or required reports, or bypass approval, production, destructive-action, sanitization, lifecycle, or workspace-ownership rules. The full written protocol is authoritative; if a shortcut conflicts with it, the full protocol wins.

Keep the shortcut set deliberately small. Add another shortcut only after repeated workflow use demonstrates a clear need.

### All roles: `INIT`

`INIT` initializes or reinitializes the current role from authoritative project state. It is always read-only.

- **DESIGNER:** execute [`DESIGNER_STARTUP.md`](../templates/DESIGNER_STARTUP.md) inside the Design Codex Project.
- **SITE ENGINEER:** after the bootstrap prompt is supplied to the Sites chat, execute [`ENGINEER_STARTUP.md`](../templates/ENGINEER_STARTUP.md).
- **PLANNER:** execute [`PLANNER_STARTUP.md`](../templates/PLANNER_STARTUP.md) from the public Design repository.

`INIT` never accepts a brief, processes inbox artifacts, moves handoffs, updates documentation, modifies source, touches production, publishes/deploys, or makes a product decision automatically. It only reconstructs role state and reports readiness.

This repository has no guaranteed project-level Codex trigger file. For a new Designer thread, use: **“Read `templates/DESIGNER_STARTUP.md` and run `INIT` in read-only mode.”** After the template is loaded, `INIT` is sufficient for reinitialization.

### Designer: `PE`

`PE` means **Prompt Engineer**. Output the current self-contained, copy/paste-ready contents of [`ENGINEER_STARTUP.md`](../templates/ENGINEER_STARTUP.md), including the instruction to run `INIT` in the actual CYOA Collection Sites context. Do not embed milestone state that belongs in permanent documents, expose sensitive/local details, or alter project state.

### Designer: `PP`

`PP` means **Prompt Planner**. Output the current self-contained, copy/paste-ready contents of [`PLANNER_STARTUP.md`](../templates/PLANNER_STARTUP.md), including its public repository link, reading order, and `INIT` instruction. Do not depend on prior Planner memory or alter project state.

### Designer: `CI`

`CI` means **Check Inbox / Process Inbox**. It does not merely list `inbox/`.

When the Designer receives `CI`, execute the normal inbox lifecycle:

1. Inspect the shared local `inbox/` and identify new Engineer reports or handoffs.
2. Validate evidence and referenced briefs or artifacts.
3. Classify each artifact as accepted, incomplete, blocked, conflicted, superseded, or awaiting a genuine Planner/product-owner decision.
4. Associate evidence with the affected workstream or workstreams; update permanent state and coarse progress only from verified evidence.
5. Identify completed, blocked, ready-for-review, and still-authorized workstreams.
6. Evaluate whether [`CHANGELOG.md`](CHANGELOG.md) needs a major milestone or state-transition update.
7. Add genuine Planner decisions to [`PLANNER_INBOX.md`](PLANNER_INBOX.md), batching independent non-urgent decisions when useful.
8. Perform Designer-owned housekeeping, moving eligible artifacts to `processed/` without overwriting or deleting unrelated artifacts and leaving unresolved artifacts active.
9. Prepare a new or revised brief only when remaining authority is insufficient; do not replace an implementation envelope that already authorizes eligible work.
10. Run the continuation check, including whether Engineer still has executable work, and identify active owners plus any owner blocking all progress.
11. Report the resulting state concisely.

Before `CI` is complete, at least one legitimate continuation must be clear. Several may exist simultaneously:

- **ENGINEER:** an eligible implementation brief exists in `briefs/`; identify the brief.
- **PLANNER:** a genuine actionable choice, approval, rejection, or requested provision exists in [`PLANNER_INBOX.md`](PLANNER_INBOX.md); identify the decision.
- **EXTERNAL/WAIT:** permanent state is explicitly `PAUSED` or `BLOCKED-EXTERNAL`; identify the condition required to resume.
- **NONE - PROJECT COMPLETE:** permanent state explicitly records completion.

Treat an empty `inbox/`, empty `briefs/`, empty Planner Inbox, actionable work in [`NEXT_ACTIONS.md`](NEXT_ACTIONS.md), and no explicit waiting/completion state as a workflow-continuity error. Do not merely report that there is nothing to process; determine the legitimate active owner or owners.

After processing an Engineer completion handoff, the Designer:

- Prepares the next adequately defined implementation brief when no Planner decision is needed.
- Creates or updates a Planner Inbox item when product direction, approval, scope choice, or risk acceptance is genuinely required.
- Records `PAUSED`, `COMPLETE`, or `BLOCKED-EXTERNAL` in permanent state when nobody can currently advance; a blocked-external state must name its resume condition.

Do not invent work or prepare a brief with inadequate requirements merely to keep the Engineer busy. The invariant ensures continuity of ownership, not continuous activity.

### Site Engineer: `CB`

`CB` means **Check Briefs / Process Next Brief**. It does not merely list `briefs/`.

When the Site Engineer receives `CB`, execute the normal brief-intake lifecycle:

1. Inspect the shared local `briefs/` and identify the next eligible implementation brief.
2. Read the complete brief and validate feasibility against the actual implementation workspace.
3. Identify every named workstream, its dependencies, local authority, production exclusions, likely ordering/parallelism, and file/surface collision risks.
4. Identify each workstream's attempt sequence: new, Attempt 2, Attempt 3, post-reassessment, or not applicable. Do not accept a workstream that silently creates Attempt 4.
5. Accept the brief as the active specification when appropriate and create the required sanitized brief-acceptance report in `inbox/`, including accepted workstreams and their attempt classifications.
6. Do not move the brief; Designer owns housekeeping.
7. If the brief is accepted, work is feasible, no material conflict exists, and actions are already authorized, advance eligible workstreams without a new go message.
8. If one workstream blocks, continue independent authorized workstreams that do not share the blocker or an unsafe file/surface collision.
9. Stop only the affected workstream at its gate. Stop the whole engineering cycle when every eligible stream is blocked, a cross-cutting conflict prevents safe continuation, shared-file conflicts require convergence, production sequencing requires waiting, or no authorized work remains.

When Queue Mode is enabled with `RUN`, completion of the current milestone triggers a mandatory fresh queue check before the Engineer ends its turn or declares itself available:

1. Create the required sanitized completion/state handoff for the finished milestone.
2. Refresh the live `briefs/` directory after creating the handoff. A listing captured at startup or before completion is stale for this decision.
3. Reconfirm Queue Mode, throttle, dependencies, Planner decisions, attempt sequence, and collision boundaries.
4. If an eligible brief exists, run `CB` immediately and continue after clean acceptance without waiting for another operator message.
5. Use `AVAILABLE` only when the fresh scan finds no eligible authorized brief. Report every waiting brief with its unmet eligibility condition.

`DRAIN`, `STOP`, an explicit gate, unsafe collision, missing authority, or no eligible work overrides automatic continuation. These checks do not auto-accept a brief or expand its scope.

No formal Planner shortcut system is defined. Planner may continue using conversational commands such as `inbox`, `status`, and `next`. Planner reads permanent documentation in this order:

1. [`PLANNER_INBOX.md`](PLANNER_INBOX.md)
2. [`CURRENT_STATE.md`](CURRENT_STATE.md)
3. [`NEXT_ACTIONS.md`](NEXT_ACTIONS.md)
4. [`CHANGELOG.md`](CHANGELOG.md)
5. [`ROADMAP.md`](ROADMAP.md)

## Thread Replacement and Recovery

Chat history is not the project source of truth. When a role thread becomes too large, stale, or unreliable:

1. Start a new thread in the correct role context.
2. Supply the appropriate startup template when the context does not already know `INIT`.
3. Run the read-only `INIT` bootstrap.
4. Validate role, permanent state, active workstreams, and active/blocking owners.
5. Continue from permanent documentation, actual Site/source state, and active handoff artifacts.

Do not create large conversational handoff summaries when authoritative sources are sufficient. Site Engineer must re-check actual Site/source state and accepted brief evidence after bootstrap; Site state outranks stale claims about what is deployed.

## Standard Response Footer

All roles use this concise footer for meaningful workflow responses:

```text
TL;DR:
<brief current result or state, usually 1-4 short lines>

NEXT OWNER:
<DESIGNER | ENGINEER | PLANNER | EXTERNAL/WAIT | NONE — PROJECT COMPLETE>

ACTION:
<single clearest next action, command, approval, or resume condition>
```

When work can proceed in parallel, replace `NEXT OWNER` with:

```text
ACTIVE OWNERS:
- DESIGNER — <completed handoff intake, when applicable>
- ENGINEER — <eligible workstreams>
- PLANNER — <pending decisions>

BLOCKING OWNER:
<NONE | DESIGNER | ENGINEER | PLANNER | EXTERNAL/WAIT>

ACTION:
<concise actions that can proceed now>
```

Use it for `CI`, `CB`, and `INIT` reports; brief acceptance; implementation completion; Designer handoff processing; Planner decisions; blocked states; and publication/deployment reports. Short or trivial acknowledgements do not require it.

- Keep `TL;DR` concise and mobile-readable.
- `NEXT OWNER` identifies responsibility for advancing the workflow, not merely status.
- Use `ACTIVE OWNERS` when two or more roles have independent actions, including Designer intake running alongside continued engineering. `BLOCKING OWNER: NONE` means at least one authorized stream can continue.
- Do not imply Engineer must stop merely because Planner has a pending decision on an unrelated stream.
- `ACTION` states what that owner should do next. Do not invent an action when legitimately waiting.
- Use `PLANNER` for approval gates, `ENGINEER` for an actionable or already-authorized brief, and `DESIGNER` for a completed Engineer handoff awaiting intake.
- Use `EXTERNAL/WAIT` with the resume condition when blocked outside the three roles.
- Use `NONE — PROJECT COMPLETE` when no action remains.
- The footer does not replace evidence, acceptance criteria, handoffs, Planner Inbox entries, or permanent documentation. The full protocol remains authoritative.

## File Handling

The preferred workflow is file-based rather than large chat copy-and-paste blocks.

| Direction | File | Handling |
| --- | --- | --- |
| Design to Site | `IMPLEMENTATION_BRIEF.md` template | Create a milestone-specific file in `briefs/`; share it with the Site Engineer |
| Site to Design | `DESIGN_HANDOFF.md` template | Receive a milestone-specific file in `inbox/`; review it as read-only evidence |

Never treat transport files as GitHub project history. If local retention is needed, use the external local `processed/` or `archive/` areas. Durable conclusions belong in the relevant high-level design documents, milestone state, decisions, changelog, or Site version history—not as copied briefs or handoffs.

## Handoff Workspace Lifecycle

The handoff workspace is outside both repositories. The Designer owns its housekeeping and maintains four logical areas:

| Area | Purpose | Exit gate |
| --- | --- | --- |
| `inbox/` | Read-only Site Engineer handoffs awaiting Design review | Verified evidence is incorporated into permanent documentation and the resulting documentation state is accepted |
| `briefs/` | Designer-prepared implementation briefs awaiting Engineer acceptance | Site Engineer confirms receipt and accepts the brief as the active implementation specification |
| `processed/` | Recently completed transport artifacts useful for immediate reference | Retain for approximately 30 days after completion/processing, then archive when eligible |
| `archive/YYYY-MM/` | Older completed artifacts retained as readable implementation evidence and history | Local/private retention; do not commit by default or routinely delete |

### Implementation brief lifecycle

1. The Designer prepares one milestone-specific brief in `briefs/` from the Implementation Brief template.
2. The Designer shares that exact file with the Site Engineer.
3. The brief remains in `briefs/` while receipt or scope acceptance is pending.
4. The Site Engineer reviews the brief and writes a sanitized acceptance report to `inbox/`; the Engineer does not edit or move the brief.
5. Only after the Site Engineer confirms receipt and accepts it as the active implementation specification may the Designer move the brief to `processed/`.
6. If the Engineer rejects or requests revision, retain the relevant artifacts without overwriting them and create a newly named revision after the conflict or approval request is resolved.

Moving a brief records transport acceptance only. It does not prove implementation, validation, Site versioning, migration, or publication.

### Brief acceptance report

Brief acceptance is an observable Engineer state transition. Use a short milestone-specific report named:

`YYYY-MM-DD-<milestone>-brief-acceptance.md`

The report must contain:

- Accepted brief filename
- Status: `ACCEPTED AS ACTIVE SPECIFICATION`
- Accepted workstream IDs and names
- Dependencies, planned ordering/parallelism, and likely shared-file/surface collisions
- Local authority and explicit production exclusions
- Attempt-sequence classification and underlying-problem reference
- Feasibility
- Material conflicts, or `NONE`
- Authorized scope
- Explicitly unauthorized actions
- Material risks or unknowns
- Next Engineer action
- Sanitization confirmation

The Designer then:

1. Verifies that the report references an existing brief in `briefs/`.
2. Confirms that the Engineer accepted that exact brief as the active implementation specification.
3. Checks for conflicts, scope changes, approval requests, or authorization mismatches.
4. If clean, moves the accepted brief from `briefs/` to `processed/` using a collision-safe name.
5. Leaves the Engineer report unchanged and read-only during review.
6. Moves the acceptance report to `processed/` when brief acceptance and movement are recorded and no acceptance issue remains active.
7. Does not treat acceptance as implementation completion or update product implementation status because of acceptance alone.

If the report identifies a conflict, scope change, or required approval, keep the brief and report active until the issue is resolved.

### Engineer state reports

Meaningful cross-workspace state transitions produce small, sanitized reports in `inbox/`. At minimum, report:

- `BRIEF ACCEPTED`
- `BLOCKED`
- `PARTIAL IMPLEMENTATION`
- `COMPLETE IMPLEMENTATION`
- `VALIDATION FAILED`
- `SAVED SITE VERSION`
- `PUBLICATION / DEPLOYMENT STATUS CHANGE`

Reports should identify the milestone, transition, related brief or prior report, verified facts, scope or approval impact, next action, and sanitization confirmation. Use the full Design Handoff template for implementation evidence that should update permanent documentation; a small state report may announce a transition but does not replace the final evidence handoff.

Routine progress, work-started notices, and action-by-action logs do not require inbox reports. The purpose is durable cross-workspace state, not implementation chatter.

Report workstream transitions at `BLOCKED`, `READY FOR REVIEW`, `COMPLETE`, mandatory reassessment, direction-changing validation failure, coherent milestone convergence, saved Site version, production gate, or publication/deployment change. Do not report every file edit, test run, minor progress increment, or ordinary authorized start.

The Designer owns report housekeeping. Keep a report in `inbox/` while it represents an unresolved blocker, approval request, conflict, or unapplied implementation evidence. Move it to `processed/` only after its lifecycle purpose is satisfied, without altering or overwriting it.

When a report contains an unresolved conflict, explicit approval requirement, material product choice, or meaningful risk acceptance, Designer evaluates whether a [`PLANNER_INBOX.md`](PLANNER_INBOX.md) item is required. When it is, Designer creates or updates the item automatically during intake without waiting for a separate instruction. Do not create an item merely because Engineer reports an unknown; first determine whether further authorized investigation can resolve it without Planner input.

### Authority and continuation

After accepting a brief, the Site Engineer proceeds without another Planner or product-owner “go” message when all of the following are true:

- The brief is accepted as the active specification.
- The work is feasible.
- No material conflict exists.
- The next actions are already authorized by the brief.

The Site Engineer must stop and request approval when:

- The brief contains an explicit approval gate for the next action.
- Scope changes materially.
- A new production-changing action is required.
- A destructive action becomes necessary.
- An unresolved design conflict appears.

Acceptance never expands the brief's authorization boundary.

### Parallel workstreams

A workstream is a bounded unit of engineering work with a stable short ID, descriptive name, objective, scope, dependencies, relevant file/surface ownership, state, coarse progress, attempt number when applicable, blocker, next gate, authority level, and whether it can continue independently.

Use only these states:

- `PLANNED` — authorized or design-defined, but not started.
- `ACTIVE` — Engineer may work on it now.
- `BLOCKED` — it cannot continue until a named dependency, decision, or gate resolves.
- `READY FOR REVIEW` — its planned engineering work reached its convergence/review point.
- `COMPLETE` — its accepted objective is complete for the current milestone.
- `DEFERRED` — intentionally outside the current execution envelope without permanent cancellation.

Record the concise current view in [`CURRENT_STATE.md`](CURRENT_STATE.md). Use a 10-segment bar and coarse 10% increments, for example `[████████░░] 80% — ACTIVE`. Progress estimates completion toward the current workstream objective; they are informational, retain their last value while blocked, and never replace acceptance criteria or validation evidence. `PLANNED` is normally 0%; `COMPLETE` is 100%.

A blocked workstream does not block Engineer when another authorized, independent stream can safely continue. Report the whole engineering cycle blocked only when every eligible stream is blocked, remaining work requires approval, a cross-cutting conflict or shared hotspot prevents safe continuation, production sequencing requires waiting, or no authorized work remains.

Briefs may authorize several named workstreams under one local implementation envelope. Each workstream states dependencies, expected files/surfaces, allowed actions, exclusions, attempt sequence, production authority, and convergence gate. Local authority never implies production authority.

Identify likely ownership boundaries and shared hotspots. Common hotspots include the main page, authentication/database helpers, shared API routes, migrations, global styles, and configuration. When streams need the same hotspot, serialize or coordinate that portion, or converge one stream before the other edits it. Do not create competing implementations to preserve parallelism.

### Convergence gate

Individually complete workstreams do not make a combined milestone ready. Before saving or presenting a combined Site version:

- Resolve shared-file conflicts and integrate the workstreams.
- Run integrated relevant tests, lint, and build.
- Verify cross-workstream interactions and schema/migration assumptions.
- Verify existing behavior remains intact and no unauthorized production behavior exists.
- Produce one coherent review handoff that identifies each workstream's outcome.

Production remains sequential. Saved-version creation, publication, production status/export, schema upgrade, verification, Shopping-capable publication, smoke testing, and destructive recovery retain explicit independent gates in dependency order. Never infer production authorization from a local multi-workstream brief.

### Product Owner hands-on validation checkpoint

Use this lightweight checkpoint at major user-facing boundaries: a new primary workflow, substantial navigation or interaction change, meaningful data-entry behavior, or a release candidate whose usability cannot be established by automated checks alone. Do not require it after background-only changes, refactors, documentation work, or narrow technical fixes with no meaningful user-facing effect.

The checkpoint preserves four independent layers:

1. **Automated engineering validation** — tests, lint, build, migration checks, and implementation evidence establish technical behavior.
2. **Designer convergence review** — Designer confirms the milestone coheres with accepted requirements and that evidence, state, and exclusions are documented.
3. **Product Owner hands-on validation** — Product Owner performs a short realistic scenario checklist in a safe user-accessible environment and returns one outcome: `ACCEPT`, `ACCEPT WITH FOLLOW-UP`, or `REVISE BEFORE RELEASE`.
4. **Production approval** — a separate explicit decision authorizes publication, migration, production writes, smoke testing, or other production action. No checkpoint outcome grants this authority automatically.

Before hands-on validation, record:

- The exact preview, unpublished saved version, or other safe validation environment the Product Owner can open.
- Whether it uses disposable/isolated data and whether any production D1/R2 binding or operation is possible.
- A short scenario checklist, normally three to seven realistic tasks and only the relevant desktop/mobile coverage.
- Known limitations, excluded production actions, and how feedback returns to Designer/Engineer.

Outcome meanings:

- `ACCEPT` — the milestone satisfies the hands-on scenarios; Designer may record checkpoint completion and prepare the next separately authorized gate.
- `ACCEPT WITH FOLLOW-UP` — the milestone is usable for the current boundary; Designer records bounded follow-up work that does not silently expand release authority.
- `REVISE BEFORE RELEASE` — user-facing issues must return to Designer/Engineer and converge again before release consideration.

Product Owner feedback must reach Designer before production activation. Engineer may receive actionable implementation feedback in parallel, but Designer owns requirement reconciliation and permanent state. Do not expand Queue Mode merely to keep capacity occupied while this gate is unresolved.

After an explicitly approved publication, perform a concise Product Owner smoke review of critical workflows in production. Read-only checks are preferred. Any write, cleanup, restore, rollback, or destructive action remains separately authorized; the smoke review does not inherit authority from pre-publication validation.

### Future engineering queue mode

The existing shared `briefs/` directory may serve as a lightweight future work queue. This capability is dormant unless Planner or Product Owner explicitly records `QUEUE MODE: ENABLED` for a bounded development session or sprint. A new week, `INIT`, `CI`, `CB`, or the mere presence of briefs never activates it.

When Queue Mode is disabled:

- Engineer completes only already accepted work and does not consume another brief automatically.
- Designer may document or plan future work but must not populate executable follow-on briefs for the current session unless separately authorized.
- Queue throttle is `NOT APPLICABLE`; an earlier `RUN` instruction cannot carry across a disabled period.

When enabled, record an Engineer execution state distinct from workstream states:

- `WORKING` — authorized executable work is actively progressing.
- `AVAILABLE` — current work is complete and Engineer may use `CB` to accept eligible queued work.
- `BLOCKED` — no authorized executable work can currently continue.
- `DRAINING` — finish the current safe unit or convergence point, then do not accept another queued brief.
- `PAUSED` — a safe resumable state is preserved; do not consume queued work until resumed.
- `STOPPED AT GATE` — an explicit design, approval, or production gate prevents continuation.

Planner/Product Owner controls future automatic queue consumption with:

- `RUN` — continue current authorized work and, at a suitable transition point, use `CB` to consider the highest-priority eligible queued brief within the approved sprint/envelope. It does not accept a brief or expand authority.
- `DRAIN` — finish the current safe unit, validation, or convergence point; preserve/report a resumable state; do not start another queued brief.
- `STOP` — stop at the nearest safe checkpoint, preserve/report resumable state, and do not start another queued brief. It is not an abrupt interruption during an integrity-sensitive write, migration, save, or similar operation unless Product Owner explicitly orders an emergency stop.

`RUN`, `DRAIN`, and `STOP` never authorize production, override exclusions or decisions, bypass dependencies or attempt limits, or cross a design/production gate. After `DRAIN` or `STOP`, preserve workstream progress, accepted and queued briefs, blockers, attempt counts, decisions, and next eligibility so a future `INIT` plus explicit `RUN` can resume safely.

#### Queue priority and eligibility

Filename order is not authoritative. Each queued brief states:

- Queue priority: `P1` highest currently useful, `P2` normal upcoming, or `P3` useful fill-in.
- Dependencies and a precise `Eligible when` condition.
- Whether it can run alongside active work.
- Shared-file/surface collisions.
- Required Planner decisions.
- Local and production authority.
- Sprint/envelope association when applicable.

Under enabled `RUN`, Engineer may use `CB` to consider the highest-priority eligible brief only after the current work reaches a suitable transition/convergence point, dependencies and decisions are satisfied, authority already covers the work, and no unsafe collision exists. A queued brief is never automatically accepted. Normal feasibility, conflict, authority, attempt-sequence, and acceptance checks still apply; a silent Attempt 4 must be rejected or held.

At milestone completion, “may use `CB`” becomes a required queue-refresh and intake check before stopping under `RUN`. The Engineer must not conclude that the operator is done, infer that no follow-on work exists from silence, or rely on a queue listing taken before the completion handoff was written.

A blocked stream does not stop queue consumption while independent authorized work remains eligible. Engineer becomes globally `BLOCKED` only when no authorized executable work remains.

Under `RUN`, encountering a milestone blocker is a queue transition, not a reason to end the engineering cycle. Engineer must preserve the affected milestone, write the required sanitized blocker/state report to local `inbox/`, refresh local `briefs/`, and run `CB` against the next priority. Continue with the next independently authorized brief when its own dependencies, authority, collision checks, and acceptance criteria are satisfied. Never treat moving on as permission to bypass the blocked milestone's gate, weaken its acceptance criteria, or activate its user-facing/production outcome.

#### Designer work-ahead and reporting

During enabled `RUN`, Designer may process CI evidence, maintain permanent state, batch decisions, reprioritize unaccepted briefs within Planner direction, and prepare eligible future work while Engineer continues. Stay only one or two meaningful executable briefs ahead. Do not create speculative work merely to keep the queue non-empty.

When Queue Mode is enabled, CI reports Engineer state, active workstreams, queued work, blocked work, pending decisions, whether Engineer can continue, whether replenishment is needed, and whether `DRAIN` or `STOP` is in effect. Do not ask Planner to act merely because a decision is pending when Engineer can safely continue elsewhere.

Meaningful future Engineer reports include:

```text
ENGINEER STATE:
<WORKING | AVAILABLE | BLOCKED | DRAINING | PAUSED | STOPPED AT GATE>

AWAITING DESIGNER INTAKE:
<completed milestones and handoff filenames, or NONE>

CURRENTLY PROCESSING:
<active workstreams and accepted brief, or NONE>

QUEUED AFTER CURRENT:
<eligible or waiting briefs/workstreams and unmet conditions, or NONE>

BLOCKED:
<blocked streams and reason>

ENGINEER CAN CONTINUE:
<YES | NO>
```

Do not require this expanded block for trivial acknowledgements. Queue state survives thread replacement through permanent `CURRENT_STATE.md`, accepted/queued transport artifacts, and the normal `INIT` bootstrap.

This block is operator-facing live context, not merely handoff metadata. When a completed milestone is waiting in `inbox/` while the next brief is being accepted or executed, show both facts simultaneously. Use the footer's `ACTIVE OWNERS` form so the operator can enable Designer intake or Planner work without interrupting Engineer continuation, for example:

```text
ACTIVE OWNERS:
- DESIGNER — process the completed P2 handoff
- ENGINEER — accept or execute P3 under RUN

BLOCKING OWNER:
NONE
```

Do not list Planner as active unless a genuine independent decision is present in `PLANNER_INBOX.md` or the current evidence requires one.

### Three-attempt reassessment rule

Within each workstream, a materially similar implementation, integration, deployment, migration, authentication, or production-operation problem may receive at most three substantive attempts before mandatory reassessment.

An attempt is a meaningful execution path intended to resolve the same underlying problem. It is not rerunning after a typo, correcting obvious syntax, fixing trivial local setup, or rerunning a flaky test without changing the approach. The rule protects usage, time, momentum, simplicity, and Product Owner attention without discouraging ordinary debugging.

After Attempt 1 or 2 fails, Engineer may continue only when the accepted brief still authorizes the work, new evidence materially informs the next attempt, no new approval gate is crossed, and no material design conflict appears. Record concisely:

- Attempt number
- Hypothesis tested
- Result
- New evidence justifying another attempt

After Attempt 3 fails, stop that workstream. Do not make Attempt 4 automatically. Other independent authorized workstreams may continue. Create a sanitized `BLOCKED / REASSESSMENT REQUIRED` report in `inbox/` that answers:

1. Original objective
2. Attempts 1, 2, and 3
3. What each established
4. Blocker classification: implementation defect, architecture mismatch, platform limitation, authorization/access limitation, unclear requirement, unsupported assumption, or unknown
5. Whether the original request remains worth pursuing
6. Simpler alternatives
7. Scope, cost, and usage risk of another attempt
8. Engineer recommendation: revised approach, redesign, defer, drop, or request Planner/product-owner decision

When Designer receives a third-attempt reassessment, do not simply create another retry brief. Review the original product need, all attempt evidence, architecture, platform constraints, roadmap priority, user value, and continuation cost. Then choose one outcome:

- Brief a clearly different implementation/design approach.
- Revise requirements.
- Defer the feature/operation.
- Drop the requirement.
- Frame a genuine Planner/product-owner decision.

Planner escalation asks whether solving the problem remains worth the added complexity/cost, not merely whether Engineer may try again. Include original value, failed assumptions/evidence, proposed alternative, expected effort/risk, and consequences of deferring or dropping.

Do not reset the attempt count because another workstream exists, a report was archived, or a new filename/brief exists. Reset only when Designer records that the underlying problem materially changed through a different architecture, different supported platform capability, materially revised requirement, or new authoritative information that changes the premise. State the reset rationale in the new brief.

### Design handoff lifecycle

1. A Site Engineer handoff enters `inbox/` and remains unchanged during intake review.
2. The Designer verifies sanitization, evidence boundaries, conflicts, and referenced design authorities.
3. The Designer incorporates only supported facts into permanent design documentation.
4. The Designer evaluates whether the evidence is a major milestone state transition and updates [`CHANGELOG.md`](CHANGELOG.md) when required by [`DOCUMENTATION_RULES.md`](DOCUMENTATION_RULES.md).
5. The Designer evaluates unresolved conflicts, approval requirements, product choices, and risk acceptance for a [`PLANNER_INBOX.md`](PLANNER_INBOX.md) item.
6. Resolve and record any required product-owner decisions.
7. Only after the verified evidence has been incorporated and the resulting documentation state is accepted may the Designer move the handoff to `processed/`.

Partial implementations and failed validations use the same gate: record their verified state before processing the artifact. If evidence is missing, conflicted, rejected, or still under review, leave the handoff in `inbox/`.

### Naming and collision safety

Use descriptive milestone filenames rather than generic transport names. Recommended patterns are:

- `YYYY-MM-DD-<milestone>-implementation-brief.md`
- `YYYY-MM-DD-<milestone>-design-handoff.md`

Use lowercase kebab-case for `<milestone>`, for example `2026-08-08-shopping-persistence-design-handoff.md`. Add a revision suffix such as `-r2` when the same milestone produces another artifact.

Before creating, copying, or moving a file, check both the source and destination names. Never overwrite an unrelated or earlier handoff. If a destination filename already exists, compare its milestone and lifecycle context, then select a unique revision or timestamped filename. Do not delete or replace the existing artifact merely to resolve a collision.

If permissions prevent the Designer from moving an artifact, leave it in place and report the housekeeping limitation. Never weaken read-only protection or modify the Site Engineer's source handoff to force a lifecycle transition.

Only the Designer performs movement into `processed/`. The Site Engineer may read briefs and create new collision-safe reports or handoffs in `inbox/`, but may not move, archive, overwrite, delete, or reorganize shared artifacts.

### Processed artifact archive

During normal Designer housekeeping, keep approximately the most recent 30 days of completed artifacts in `processed/`. Move older eligible artifacts into `archive/YYYY-MM/` according to their completion or processing period.

- Preserve filenames when possible and use collision-safe descriptive naming when necessary.
- Never overwrite, routinely delete, ZIP, or compress normal Markdown artifacts.
- Never archive an active artifact, unresolved conflict, or item still awaiting approval.
- Archival means **completed and retained**, not discarded.
- The Designer alone owns archival housekeeping; the Site Engineer must not reorganize the archive.

Sanitization overrides retention. If an artifact contains credentials, tokens, secrets, private resource identifiers, sensitive personal information, or inappropriate environment details, do not preserve it merely because it otherwise qualifies for archival. Do not silently rewrite historical evidence. Report the issue and follow [`DOCUMENTATION_RULES.md`](DOCUMENTATION_RULES.md) and the applicable safe-handling procedure.

Archived handoffs are supporting evidence, not primary project truth. Permanent truth remains in:

- [`PLANNER_INBOX.md`](PLANNER_INBOX.md) for unresolved owner decisions
- [`CURRENT_STATE.md`](CURRENT_STATE.md) for what is true now
- [`NEXT_ACTIONS.md`](NEXT_ACTIONS.md) for what should happen next
- [`CHANGELOG.md`](CHANGELOG.md) for major milestone and state history
- [`ROADMAP.md`](ROADMAP.md) for future direction
- [`DECISIONS.md`](DECISIONS.md) and ADRs for durable accepted decisions

The archive supports troubleshooting and reconstruction; Planner should not normally need to read it.

## Conflict Rules

If a handoff conflicts with existing design documentation:

- Do not resolve the conflict silently.
- Surface the conflict explicitly.
- Separate implementation fact from proposed design.
- Ask for a product-owner decision when the conflict affects product direction or accepted architecture.

Implementation evidence is authoritative for what currently exists. Design documentation is authoritative for intended future direction.

## Sanitization Rules

Both handoffs inherit the sanitization requirements in [`DOCUMENTATION_RULES.md`](DOCUMENTATION_RULES.md). They must not include:

- Credentials, API keys, temporary repository credentials, tokens, or secrets
- Owner emails or personal information
- Environment secrets or private operational data
- D1 or R2 resource IDs unless explicitly necessary and safe
- Local filesystem paths or machine usernames
- Unnecessary operational identifiers

Generalize evidence while preserving enough detail to support documentation decisions.
