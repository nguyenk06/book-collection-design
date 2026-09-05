# Design and Site Handoff Protocol

This protocol defines the file-based exchange between the Design workspace and the Site implementation workspace. Permanent product state belongs in GitHub design documents and Site version history. All briefs, reports, acceptance records, and handoff files are transport artifacts stored only in the external local handoff workspace; they must never be committed to `book-collection-design`, including for staging or archival.

## Active Pilot Precedence

The [CYOA One-Level Codex Subagent Pilot](ONE_LEVEL_SUBAGENT_PILOT.md) is the current workflow authority. Quatre is the persistent parent, Planner, usage governor, and Site-owning agent. Relena and Kira are direct Quatre children and must not spawn. The Product Owner communicates only with Quatre and no longer carries briefs, reports, `!inbox`, `!brief`, or role prompts between agents.

External `briefs/`, `inbox/`, and `processed/` remain optional durable evidence stores, but Quatre routes them internally. The old separate-chat workflow is retired. Its command/lifecycle sections below are retained for file-integrity, sanitization, and historical reference only; they cannot activate work or override the pilot topology, Product Owner interface, Kira Site prohibition, or Quatre Site ownership.

## Engineer Read Location

Primary source of design truth:

<https://github.com/nguyenk06/book-collection-design>

Priority documents:

1. `docs/ENGINEER_EXECUTION_CONTRACT.md`
2. `docs/PROJECT_VISION.md`
3. `docs/CURRENT_STATE.md`
4. `docs/NEXT_ACTIONS.md`
5. `docs/ROADMAP.md`
6. `docs/DATABASE.md`
7. `docs/DOCUMENTATION_RULES.md`
8. Relevant feature documents and ADRs

Kira treats the public design repository as read-only reference. Kira has no write role in `book-collection-design`. Quatre transmits the current completion-oriented goal and any durable [`IMPLEMENTATION_BRIEF.md`](../templates/IMPLEMENTATION_BRIEF.md) internally.

## Role Identity and Chat Continuity

Current identities are parent `PLANNER — QUATRE`, direct Designer child `DESIGNER — RELENA`, and direct Engineer child `ENGINEER — KIRA`. `ENGINEER — SEI` and Sei I–III are retired historical identities. Temporary test/review identities, when justified, are also direct Quatre children. No child may spawn.

Quatre's required title remains `CYOA — Planner Quatre`, applied manually by the Product Owner. Subagents identify their role, Quatre parent, one-level depth, continuity, and source/work state in their first report. Kira never inherits unpublished Sei state or authority by implication.

Default profiles are Quatre: **GPT-5.6 Sol / Medium / Standard**; Relena: **GPT-5.6 Sol / High / Standard**; Kira: **GPT-5.6 Terra / Medium / Standard**. The Product Owner controls actual model selection through Quatre. Fast mode remains off by default. Kira may use Sol only when the accepted goal recommends it or a later Planner/Product Owner decision approves it.

## Roles

### Designer

Relena is a direct Quatre child working in the `book-collection-design` repository and owns:

- Product design and accepted requirement documentation within Quatre/Product Owner direction
- Roadmap
- Architecture
- Accepted requirements
- Documentation
- ADRs
- Preparation of implementation briefs and explicitly non-executable estimation/source-inspection briefs
- Internal handoff evidence reconciliation and housekeeping
- Planner decision framing and `PLANNER_INBOX.md` housekeeping

Relena returns results to Quatre. Durable local transport may support the exchange, but the Product Owner never carries it.

The Designer must not:

- Claim implementation occurred without verified Site evidence.
- Modify production Site state.
- Spawn subagents or invoke Sites tools.

### Engineer — Kira

Kira is a direct Quatre child and owns authorized application-source work:

- Site implementation
- Database, API, and UI changes
- Tests, build, and lint
- Local migration validation
- Exact candidate packaging and validated release packets for Quatre

Kira must not:

- Modify the design repository directly.
- Create commits, branches, pull requests, issues, comments, releases, or any other GitHub artifact in `book-collection-design`.
- Spawn subagents or communicate directly with the Product Owner.
- Invoke Sites tools, obtain Sites credentials, save versions, preview, deploy, publish, or perform the final Site handoff.
- Return Engineer reports through GitHub; return them internally to Quatre.
- Invent product direction.
- Mark roadmap work complete without implementation evidence.
- Publish without explicit approval.
- Move briefs or reports between shared handoff folders.
- Archive, overwrite, delete, or reorganize shared handoff artifacts.
- Edit `PLANNER_INBOX.md` directly.

### Quatre-owned Sites operations

Quatre is the Site-owning agent. Kira prepares an exact validated release packet; Relena confirms the product/release boundary. Only then may Quatre perform a specifically Product-Owner-authorized Site operation after revalidating Site, session, candidate, credential, production, and usage gates.

Publication, schema/data mutation, migration, credential changes, destructive recovery, rollback, restore, and external sharing always remain explicit Product Owner gates. Kira cannot perform or inherit any Site operation.

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
- Kira work begins from a Quatre-transmitted completion-oriented goal and any required durable brief. Implementation goals contain approved implementation only; estimation/source-inspection goals are separately labeled read-only and non-executable. Repository planning text and estimation gates are context—not authority.
- Tester knowledge contains coverage strategy, regression knowledge, and evidence conventions; it does not authorize product or implementation changes.

Kira reviews only knowledge mapped to the goal, relevant `Needs Revalidation` records, and newly added notes affecting that component. No-change findings allow work to proceed. Preserve non-blocking improvements and report them to Quatre without stopping implementation. Quatre routes material product/release-boundary conflicts to Relena.

All Kira reports return directly to Quatre. Supporting material may remain in internal local storage; Kira must not place reports in GitHub. Quatre routes design/documentation conclusions to Relena. The Product Owner receives only Quatre's consolidated result and genuine decisions. Research classification never authorizes dependencies, schema changes, source changes, Site operations, or production actions.

Kira reads the public design repository at <https://github.com/nguyenk06/book-collection-design> and receives the applicable goal/brief from Quatre. Repository access does not replace required authority.

## Design to Engineer Goal

Relena prepares a completion-oriented goal or durable [`IMPLEMENTATION_BRIEF.md`](../templates/IMPLEMENTATION_BRIEF.md) when Quatre requests design/scope support. Quatre transmits it internally to Kira. A goal covers one coherent outcome and records constraints, verification, usage envelope, safe checkpoint, genuine stop conditions, and deferred work.

- Link to authoritative design documents instead of copying them.
- Distinguish verified current state from accepted requirements.
- State acceptance criteria, exclusions, risks, documentation evidence, and the approval boundary.
- Keep the file short enough to download, share, and review on mobile.

The goal authorizes only stated Kira implementation and validation work. It never authorizes Kira to use Sites. A later Quatre Site operation requires explicit Product Owner authority plus a Kira release packet and Relena boundary confirmation.

## Kira Return to Quatre

After implementation or a genuine stop, Kira prepares [`DESIGN_HANDOFF.md`](../templates/DESIGN_HANDOFF.md) or an equivalent validated packet directly for Quatre. The report must be sanitized and based on observed evidence.

- Select exactly one status: `COMPLETE IMPLEMENTATION`, `PARTIAL IMPLEMENTATION`, or `VALIDATION FAILED`.
- Separate implemented, deferred, and not-attempted scope.
- Distinguish local validation, saved Site version, and publication state.
- Do not imply production verification unless it actually occurred and is safe to document.
- Identify proposed design changes separately from implementation facts.
- Mark each suggested documentation target `UPDATE`, `NO CHANGE`, or `REVIEW NEEDED`.

Quatre routes the packet to Relena under [`DOCUMENTATION_RULES.md`](DOCUMENTATION_RULES.md) when documentation or product/release-boundary review is required.

## Legacy Separate-Chat Mobile Workflow (Inactive During Pilot)

The remainder of this section documents the retired Product-Owner-carried workflow. Do not use it during the one-level pilot; use [CYOA One-Level Codex Subagent Pilot](ONE_LEVEL_SUBAGENT_PILOT.md).

Use explicit `!` commands for defined lifecycle actions and ordinary sentences for requests that are not workflow commands. For example:

1. Planner: `!inbox` to read and report repository `docs/PLANNER_INBOX.md`.
2. Designer: `!inbox` to process Engineer evidence in the external local `inbox/`, or prepare an implementation/estimation brief as a normal request.
3. Site Engineer: `!brief` to accept the next eligible brief, then `!drain` when the current safe unit should finish without new intake. Engineer does not use `!inbox`.
4. Any role: `!status` for a read-only state report or `!init` for a read-only state refresh.
5. Any role: `!40:75` to record 40% five-hour and 75% longer-period usage without activating work.
6. Designer: `!prompt-engineer`, `!prompt-designer`, or `!prompt-planner` to produce a copy/paste-ready startup prompt.

Never omit `!` when explicit workflow behavior is intended. Plain words and abbreviations remain conversation.

## Legacy Separate-Chat Workflow Commands (Inactive During Pilot)

The command table below is historical compatibility reference only. The active Product Owner command set is defined in [CYOA One-Level Codex Subagent Pilot](ONE_LEVEL_SUBAGENT_PILOT.md) and `templates/PLANNER_STARTUP.md`.

The `!` prefix identifies explicit workflow intent. Commands are case-insensitive. An unprefixed word or abbreviation is normal conversation and must not trigger workflow behavior. Commands invoke only their documented lifecycle behavior; they do not create authority, replace evidence or required reports, or bypass approval, production, destructive-action, sanitization, lifecycle, or workspace-ownership rules.

| Command | Role | Behavior |
| --- | --- | --- |
| `!init` | All | Read-only role initialization or state refresh |
| `!status` | All | Read-only current-state report; do not process artifacts or change authority |
| `!<five-hour>:<longer-period>` | All | Record the two displayed usage percentages; `!40:75` means 40% five-hour and 75% longer-period |
| `!inbox` | Planner | Read and report `docs/PLANNER_INBOX.md`; do not process local Engineer transport |
| `!inbox` | Designer | Process the external local Engineer `inbox/` lifecycle |
| `!brief` | Site Engineer | Check and process the next eligible brief |
| `!prompt-engineer` | Designer | Output the complete Engineer startup prompt |
| `!prompt-designer` | Designer | Output the complete Designer startup prompt |
| `!prompt-planner` | Designer | Output the complete Planner startup prompt |
| `!run` | Authorized operator | Activate or continue approved work until its objective completes or a genuine stopping boundary is reached |
| `!drain` | Authorized operator | Finish the current safe unit and accept no further work |
| `!stop` | Authorized operator | Stop at the nearest safe checkpoint |

Optional compact aliases are `!pe`, `!pd`, `!pp`, `!ci`, and `!cb`. `!ci` is Designer-only and maps to Designer `!inbox`; `!cb` is Engineer-only and maps to `!brief`. Plain `PE`, `PD`, `PP`, `CI`, `CB`, `INIT`, `RUN`, `DRAIN`, or `STOP` tokens are not commands.

The numeric usage command accepts exactly two whole-number percentages from 0 through 100 separated by one colon immediately after `!`. The first is always the five-hour window and the second is the longer-period Codex allowance. It may accompany another explicit command; record the reading first and then perform only that command's documented behavior. A usage command never means `!brief` or `!run`, never activates work, and never broadens authority. If either value is missing, malformed, or out of range, do not guess.

Role identity dispatches `!inbox`: Quatre addresses repository `docs/PLANNER_INBOX.md`; Relena addresses external local Engineer `inbox/`; Sei has no `!inbox` command. The command never crosses those boundaries or gains the other role's authority.

### Legacy all-role `!init` and `!status`

`!init` initializes or reinitializes the current role from authoritative project state. It is always read-only.

- **DESIGNER:** execute [`DESIGNER_STARTUP.md`](../templates/DESIGNER_STARTUP.md) inside the Design Codex Project.
- **SITE ENGINEER:** after the bootstrap prompt is supplied to the Sites chat, execute [`ENGINEER_STARTUP.md`](../templates/ENGINEER_STARTUP.md).
- **PLANNER:** execute [`PLANNER_STARTUP.md`](../templates/PLANNER_STARTUP.md) from the public Design repository.

`!init` never accepts a brief, processes or moves existing inbox artifacts, updates documentation, modifies source, touches production, publishes/deploys, or makes a product decision automatically. It only reconstructs role state and reports readiness. A new or replacement Engineer `!init` must create one concise sanitized `INITIALIZATION / CONTEXT VERIFICATION` report in the shared local `inbox/`; writing that evidence is part of reporting, not project execution or brief acceptance.

`!status` reports the same current role, queue, gate, ownership, and blocker state without processing artifacts or changing authority. It is always read-only.

For a new Designer thread, use: **“Read `templates/DESIGNER_STARTUP.md` and run `!init`.”**

### Legacy Designer prompt commands

`!prompt-engineer` (alias `!pe`) outputs the current self-contained, copy/paste-ready contents of [`ENGINEER_STARTUP.md`](../templates/ENGINEER_STARTUP.md), including the instruction to run `!init` in the actual CYOA Collection Sites context.

`!prompt-designer` (alias `!pd`) outputs the complete [`DESIGNER_STARTUP.md`](../templates/DESIGNER_STARTUP.md) prompt for a replacement Designer.

`!prompt-planner` (alias `!pp`) outputs the complete [`PLANNER_STARTUP.md`](../templates/PLANNER_STARTUP.md) prompt for a replacement Planner.

Prompt commands are read-only. Every copy-and-paste handoff prompt must name its recipient in the first line, state that the entire block should be pasted into that recipient's chat, be self-contained, and require no pronoun or context rewriting by the Product Owner. Do not embed transient milestone state, process transport, expose sensitive/local details, depend on prior role memory, or alter project state.

### Legacy Designer `!inbox`

`!inbox` (alias `!ci`) means **Process Engineer Inbox**. It does not merely list `inbox/`.

When the Designer receives `!inbox`, execute the normal inbox lifecycle:

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

Before `!inbox` is complete, at least one legitimate continuation must be clear. Several may exist simultaneously:

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

### Legacy Site Engineer `!brief`

`!brief` (alias `!cb`) means **Check and Process Next Brief**. It does not merely list `briefs/`.

When the Site Engineer receives `!brief`, execute the normal brief-intake lifecycle:

1. Inspect the shared local `briefs/` and identify the next eligible Engineer brief, including its explicit work type and authority boundary.
2. Read the complete brief and validate feasibility against the actual implementation workspace.
3. Identify every named workstream, its dependencies, local authority, production exclusions, likely ordering/parallelism, and file/surface collision risks.
4. Identify each workstream's attempt sequence: new, Attempt 2, Attempt 3, post-reassessment, or not applicable. Do not accept a workstream that silently creates Attempt 4.
5. Accept the brief as the active specification when appropriate and create the required sanitized brief-acceptance report in `inbox/`, including accepted workstreams and their attempt classifications.
6. Do not move the brief; Designer owns housekeeping.
7. If the brief is accepted outside an active `!run`, wait for the separate `!run`. If it is an eligible continuation already inside an active `!run`, continue without requesting another go message.
8. If one workstream blocks, continue independent authorized workstreams that do not share the blocker or an unsafe file/surface collision.
9. Stop only the affected workstream at its gate. Stop the whole engineering cycle when every eligible stream is blocked, a cross-cutting conflict prevents safe continuation, shared-file conflicts require convergence, production sequencing requires waiting, or no authorized work remains.

When Queue Mode is enabled with `!run`, completion of the current milestone triggers a mandatory fresh queue check before the Engineer ends its turn or declares itself available:

1. Create the required sanitized completion/state handoff for the finished milestone.
2. Refresh the live `briefs/` directory after creating the handoff. A listing captured at startup or before completion is stale for this decision.
3. Reconfirm Queue Mode, throttle, dependencies, Planner decisions, attempt sequence, and collision boundaries.
4. If an eligible brief exists, run `!brief` immediately and continue after clean acceptance without waiting for another operator message.
5. Use `AVAILABLE` only when the fresh scan finds no eligible authorized brief. Report every waiting brief with its unmet eligibility condition.

`!drain`, `!stop`, an explicit gate, unsafe collision, missing authority, or no eligible work overrides automatic continuation. These checks do not auto-accept a brief or expand its scope.

Planner uses `!init`, `!status`, and role-specific `!inbox`. Quatre's `!inbox` reads and reports `docs/PLANNER_INBOX.md`; it does not process external local Engineer reports. Planner returns decisions as ordinary text such as `Decision 1:A`. Unprefixed conversational words such as “inbox,” “status,” and “next” remain normal conversation. Planner reads permanent documentation in this order:

1. [`PLANNER_INBOX.md`](PLANNER_INBOX.md)
2. [`CURRENT_STATE.md`](CURRENT_STATE.md)
3. [`NEXT_ACTIONS.md`](NEXT_ACTIONS.md)
4. [`CHANGELOG.md`](CHANGELOG.md)
5. [`ROADMAP.md`](ROADMAP.md)

## Thread Continuity and Necessary Replacement

During the pilot, Quatre is persistent. Relena and Kira are direct children and are reused while coherent. Kira is the current Engineer; Sei III is retired. A child replacement remains a direct Quatre child and never gains authority or unpublished state by implication.

Permanent documentation and actual implementation/source state remain authoritative, but continuity is preferred. Continue using the same parent or direct child while it remains coherent and retains the correct repository, source, and tool access. Do not replace it merely because the conversation is long, Codex compacts older context, a milestone finishes, one task blocks, a new goal appears, or substantial context has been used.

Replacement is justified only when required workspace, editable source, or tools are unavailable; initialization cannot reconcile identity and authoritative state; the agent repeatedly uses stale or contradictory state after refresh; the role changes materially; or Quatre/Product Owner explicitly requests replacement or an independent context.

Before replacing Kira, inspect and report unpublished working state to Quatre. A new child does not automatically inherit unsaved source. If replacement is necessary:

1. Create the private local-only `ENGINEER_CONTINUITY_HANDOFF.md` artifact and a separate sanitized `DESIGN_HANDOFF.md` report. The private artifact may contain only successor-critical machine state and must never contain credentials, tokens, owner identity, secrets, or private production data.
2. Preserve exact editable-source path, repository/remote, branch/HEAD, clean/dirty and modified/untracked/staged/stashed state, active brief/authority/exclusions, candidate baseline/manifest, consumed attempts, completed/remaining checks, last attributable commands, process state, available dependencies, safe resume point, usage/reset state, and exact successor initialization/resume sequence.
3. Quatre starts the replacement as a direct child with the correct role/workspace context. Do not reuse a retired identity.
4. Supply the successor startup prompt and require read-only initialization plus the [Engineer Execution Contract](ENGINEER_EXECUTION_CONTRACT.md) and private continuity artifact.
5. Independently verify actual source path, repository, remote, branch, HEAD, clean/dirty state, candidate identity, active authority, attempt count, process state, dependencies, and remaining validation. Documentation naming a commit is not proof that source transferred.
6. Return one sanitized `INITIALIZATION / CONTEXT VERIFICATION` report directly to Quatre. It identifies the successor, records each verification result and mismatch without exposing private paths, and states that no goal or run was accepted. Quatre routes design review to Relena when needed.
7. Only after Quatre accepts continuity evidence may the successor accept a new or explicitly superseding completion-oriented goal. Product Owner `!brief` is not used.
8. Never reset attempt counts merely because the chat changed.

Do not require a handoff solely because a context is long or compacted. Retain concise, evidence-focused records for durable goals, Kira completion/blocker/validation evidence, release packets, production-gate evidence, cross-role decisions/conflicts, and unpublished-source preservation before an actual replacement.

## Engineer execution contract

The concise [Engineer Execution Contract](ENGINEER_EXECUTION_CONTRACT.md) is mandatory for Kira during initialization, goal acceptance/activation, post-compaction recovery, and replacement initialization. It defines the active-run invariant, mandatory pre-final continuation test, exact terminal stopping conditions, progress/terminal distinction, tool-failure scope, and three-approach behavior.

`PROGRESS UPDATE — NONTERMINAL` is commentary returned to Quatre while work continues and expects no Product Owner response. A terminal Kira report ends only because the objective completed or a genuine stopping condition applies. A timeout, truncated output, lost controller result, access denial, failed lint/test/build, or missing PID blocks only that action unless evidence proves a cross-cutting hazard. Predictable tool limitations should have a prioritized goal-authorized fallback ladder.

## Standard Response Footer

During the pilot, this canonical footer is mandatory for Quatre's consolidated terminal responses. Subagent terminal reports return to Quatre and never instruct the Product Owner to contact another agent; durable Kira packets use `NEXT OWNER: PLANNER — QUATRE`.

All roles use this concise footer for meaningful workflow responses:

```text
TL;DR:
<brief current result or state, usually 1-4 short lines>

NEXT OWNER:
<DESIGNER | ENGINEER | PLANNER | EXTERNAL/WAIT | NONE — PROJECT COMPLETE>

ACTION:
<single clearest next action, command, approval, or resume condition>
```

When work can proceed in parallel, use this complete footer instead:

```text
TL;DR:
<brief current result or state, usually 1-4 short lines>

ACTIVE OWNERS:
- DESIGNER — <completed handoff intake, when applicable>
- ENGINEER — <eligible workstreams>
- PLANNER — <pending decisions>

BLOCKING OWNER:
<NONE | DESIGNER | ENGINEER | PLANNER | EXTERNAL/WAIT>

ACTION:
<concise actions that can proceed now>
```

`TL;DR` and `ACTION` are always present in either form. Use exactly one ownership form: single-owner `NEXT OWNER`, or parallel `ACTIVE OWNERS` plus `BLOCKING OWNER`. Do not mix or omit these labels in meaningful workflow responses.

Every Quatre terminal workflow response to a numeric usage command, `!init`, `!status`, `!run`, `!drain`, or `!stop` must use exactly one footer form. The requirement survives chat compaction or summarization and remains mandatory without a full reinitialization. It also applies to internal subagent terminal packets, implementation completion, Planner decisions, blocked states, and publication/deployment reports; a Kira packet names Quatre as its next owner. Ordinary `PROGRESS UPDATE — NONTERMINAL` commentary emitted while work continues does not require the full footer and must not imply another Product Owner prompt is needed.

- Keep `TL;DR` concise and mobile-readable.
- `NEXT OWNER` identifies responsibility for advancing the workflow, not merely status.
- Use `ACTIVE OWNERS` when two or more roles have independent actions, including Designer intake running alongside continued engineering. `BLOCKING OWNER: NONE` means at least one authorized stream can continue.
- Do not imply Engineer must stop merely because Planner has a pending decision on an unrelated stream.
- `ACTION` states what that owner should do next. Do not invent an action when legitimately waiting.
- Use `PLANNER` for approval gates, `ENGINEER` for an actionable or already-authorized brief, and `DESIGNER` for a completed Engineer handoff awaiting intake.
- Use `EXTERNAL/WAIT` with the resume condition when blocked outside the three roles.
- Use `NONE — PROJECT COMPLETE` when no action remains.
- Before sending a terminal response, validate that exactly one footer form exists; `TL;DR` and `ACTION` exist; ownership forms are not mixed; and the named owner can perform the action. Never use `NEXT OWNER: ENGINEER` to end an active `!run` when Engineer can continue immediately.
- For every terminal transport artifact, place the footer skeleton at the file bottom before drafting the report. After saving, reopen and inspect the tail. The last non-comment block must be exactly one canonical footer. A chat footer does not substitute for an artifact footer.
- Designer classifies a terminal artifact without its own valid footer as incomplete or superseded, not as the final handoff. Engineer corrects it only by creating a collision-safe, uniquely named formatting-only superseding report; preserve the original unchanged and never repeat implementation, validation, save, deployment, publication, or production work merely to repair formatting.
- The footer does not replace evidence, acceptance criteria, handoffs, Planner Inbox entries, or permanent documentation. The full protocol remains authoritative.

## Pilot Internal Goal and Evidence Routing

Quatre routes goals and results inside the parent task. Files remain useful as durable scope and evidence records, but the Product Owner does not carry them and no separate `!inbox` or `!brief` command is required.

| Direction | Durable record | Pilot handling |
| --- | --- | --- |
| Relena to Kira | `IMPLEMENTATION_BRIEF.md` or `ESTIMATION_BRIEF.md` | Relena returns it to Quatre; Quatre transmits the goal/record internally |
| Kira to Quatre | `DESIGN_HANDOFF.md` or equivalent validated packet | Kira returns it directly to Quatre; Quatre routes product/release review to Relena |
| Quatre to Product Owner | Consolidated terminal response | Quatre reports state, decisions, gates, and action without asking the Product Owner to move an artifact |
| Product Owner decision | `PLANNER_INBOX.md` | Quatre records only genuine Product Owner choices; technical reports and task queues do not belong there |

The external local `briefs/`, `inbox/`, `processed/`, and archive areas may remain as durable evidence storage. Relena may maintain them when Quatre assigns documentation/evidence reconciliation, but their filenames or presence never activate work. Never commit private continuity artifacts, credentials, local paths, owner identity, secrets, or production data to GitHub.

### Goal acceptance and reports

Kira accepts the complete Quatre-transmitted goal directly. Acceptance records identity, parent, exact source/branch/HEAD, working state, unpublished work, context match, source/collision boundary, scope/exclusions, verification, usage envelope, safe checkpoint, genuine stops, and feasibility. A read-only goal must restate that it grants no implementation or Site authority.

Kira reports material transitions and the terminal result directly to Quatre. Routine progress and action-by-action logs need no durable report. Completion, a genuine blocker, a direction-changing validation failure, source or collision ambiguity, a release packet, or a required gate does. Reports remain sanitized and name Quatre—not the Product Owner—as recipient.

Quatre routes product/release-boundary review to Relena. Relena updates permanent design documentation only from verified evidence and creates a `PLANNER_INBOX.md` item only for a genuine Product Owner choice. Durable conclusions belong in current state, decisions, roadmap, changelog, or Site-version history rather than copied transport chatter.

### Legacy external workspace lifecycle

The earlier Designer-managed `briefs/` → Engineer `inbox/` → `processed/` command lifecycle is inactive during the pilot. Preserve existing artifacts as evidence, but do not require the Product Owner to transport them or use their movement as a prerequisite for Quatre to route an approved goal internally.

### Authority and continuation

After Kira accepts a Quatre-transmitted goal and Quatre activates it under existing authority, Kira proceeds without another Product Owner command when all of the following are true:

- The completion-oriented goal and any durable brief are accepted as the active specification.
- The work is feasible.
- No material conflict exists.
- The next actions are already authorized by the brief.

Kira must stop and report to Quatre when:

- The brief contains an explicit approval gate for the next action.
- Scope changes materially.
- A new production-changing action is required.
- A destructive action becomes necessary.
- An unresolved design conflict appears.

Acceptance never expands the goal or brief's authorization boundary. Quatre consolidates any genuine Product Owner decision; Kira does not contact the Product Owner directly.

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

### Independent promotion boundary

Design parallel workstreams so each can be preserved, validated, saved, and published independently whenever the implementation platform permits. A shared working copy, dirty worktree, common file, or later completed milestone must not silently bundle unrelated scope into an earlier release candidate.

- Give each workstream an explicit source baseline, included/excluded change set, tests, migration set, and release authority.
- Prefer isolated branches, commits, patches, saved versions, or other supported source-selection mechanisms in the Site implementation workspace when they preserve exact provenance safely.
- Shared-file edits require deliberate integration, but integration for testing does not automatically create joint publication authority.
- Before saving or publishing, compare the candidate against its approved manifest and remove or reject unrelated work.
- If the platform cannot promote the pieces independently, report the coupling before release. Designer decides whether to re-isolate, deliberately converge scopes, or defer; Engineer must not publish the bundle by convenience.

This rule never permits Engineer writes to `book-collection-design`. Any implementation-source push allowed by the Sites source-preservation exception remains scoped to the exact independently approved Site candidate.

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

Product Owner feedback reaches Quatre, which routes it to Relena before production activation. Under a specifically documented live-validation exception, Quatre must route it to Relena immediately after controlled publication and before release acceptance or further progression. Kira may receive actionable implementation feedback internally, but Relena owns requirement reconciliation and permanent state. Do not expand Queue Mode merely to keep capacity occupied while this gate is unresolved.

When Product Owner explicitly selects post-publication live validation because no safe preview exists, document that exception in an accepted decision and preserve the same separation of layers. Require backup/export and preservation evidence, schema activation/verification, publication, hands-on validation, and smoke review as sequential gates. The direction does not authorize every gate automatically or make later evidence retroactive. A failed live checkpoint stops further release progression and triggers rollback/repair assessment under existing authority rules.

After an explicitly approved publication, perform a concise Product Owner smoke review of critical workflows in production. Read-only checks are preferred. Any write, cleanup, restore, rollback, or destructive action remains separately authorized; the smoke review does not inherit authority from pre-publication validation.

### Pilot queue and goal mode

The durable goal/brief set may serve as a lightweight queue visible to Quatre. A new window, reset, `!init`, or the mere presence of a file never activates work. Quatre activates only a completion-oriented goal covered by recorded authority and an applicable Product Owner `!run`.

When Queue Mode is disabled:

- Kira completes only already accepted work and does not consume another goal automatically.
- Relena may document or plan future work but must not create executable authority without Quatre routing the required approval.
- Queue throttle is `NOT APPLICABLE`; an earlier `!run` instruction cannot carry across a disabled period.

When enabled, record an Engineer execution state distinct from workstream states:

- `WORKING` — authorized executable work is actively progressing.
- `AVAILABLE` — current work is complete and Quatre may route an eligible approved goal.
- `BLOCKED` — no authorized executable work can currently continue.
- `DRAINING` — finish the current safe unit or convergence point, then do not accept another queued brief.
- `PAUSED` — a safe resumable state is preserved; do not consume queued work until resumed.
- `WAITING FOR RESET` — the five-hour capacity floor or window boundary was reached at a safe checkpoint; this is not an implementation blocker.
- `STOPPED AT GATE` — an explicit design, approval, or production gate prevents continuation.

The Product Owner controls Quatre's active queue with:

- `!run` — Quatre activates or continues only approved completion-oriented goals until the outcome completes or a genuine stopping boundary is reached. It does not expand authority or carry across a real stop/reset boundary automatically.
- `!drain` — Quatre has active children finish the current safe unit, validation, or convergence point; preserve/report a resumable state; do not start another goal.
- `!stop` — Quatre stops active work at the nearest safe checkpoint, preserves/reports resumable state, and starts no other goal. It is not an abrupt interruption during an integrity-sensitive write, migration, save, or similar operation unless Product Owner explicitly orders an emergency stop.

`!run`, `!drain`, and `!stop` never authorize production, override exclusions or decisions, bypass dependencies or attempt limits, or cross a design/production gate. After `!drain` or `!stop`, preserve workstream progress, accepted and queued goals/briefs, blockers, attempt counts, decisions, and next eligibility so a future `!init` plus explicit `!run` can resume safely.

### Five-hour execution slices and usage capacity

Treat the displayed percentage as available capacity, not as a token count or fixed task conversion. Do not claim that a percentage point equals a stable amount of work until observed evidence supports it.

- One active Engineer project is allowed per five-hour window by default. Do not spend the same window on CYOA and another Engineer project.
- A completion-oriented goal may span several windows but must define independently resumable safe checkpoints. A durable brief records scope and authority; it does not require a new micro-brief at every checkpoint.
- Record a displayed usage reading at new-slice intake. A second reading immediately before `!run` is required only when the intake reading is stale, a reset or other material usage occurred, the slice is large/high-risk, or the remaining high estimate may no longer fit above the floor. Do not request duplicate readings for a small or normal continuation in the same window with ample margin.
- Every goal or durable brief records the preferred model, reasoning effort, speed mode, current five-hour percentage, reset time, current longer-period Codex percentage, estimated five-hour consumption, minimum starting percentage, automatic stopping percentage, safe checkpoint, and work deferred to the next reset.
- Use a provisional **15% five-hour automatic stopping floor**. Check the longer-period allowance separately; it is not an alternative execution reserve and does not make an exhausted five-hour window runnable.
- Planning-class guides are: diagnostic/status only **35%**; small implementation **50%**; normal implementation **70%**; migration, release, or other high-risk work **85%**. These help size fresh work but are not universal vetoes. The operational minimum for an approved bounded slice is its remaining high estimate plus the 15% floor. Split work into independently resumable safe units when that calculation does not fit.
- Reaching the floor or the end of the five-hour window changes Engineer state to `WAITING FOR RESET`, not `BLOCKED`. Preserve the exact checkpoint, remaining scope, validation state, and next command.
- After reset, the Product Owner uses `!status`, then `!run` only when the recorded authority still covers resumption. Quatre transmits any new or revised goal internally. A reset does not broaden authority.
- During execution, request another reading only for a large/high-risk checkpoint, a reset/window transition, material scope or estimate growth, another project's intervening consumption, or credible approach to the floor. A practical floor-risk trigger is when the current reading may be within roughly ten points of the remaining high estimate plus the 15% floor. Capture an ending reading when readily available, but do not interrupt or block an otherwise complete small/normal run merely to obtain it. Model, reasoning, tools, context, and task complexity can change actual usage; Designer calibrates ranges from evidence rather than treating percentages as fixed work units.

Before activating `!run`, Quatre reviews both usage periods and uses Relena when product/release-boundary sizing is needed. The active goal identifies dependencies, genuine approval gates, production-risk boundaries, shared hotspots, likely blockers, and clean stopping cost. Keep useful approved work moving toward the 15% floor. Reduce or checkpoint work when the remaining high estimate cannot preserve that floor or no safe checkpoint fits.

After `!run`, Kira owns practical sequencing within the approved goal. Kira may investigate, implement, test, remediate ordinary defects, converge, validate, and prepare the required packet without repeated Product Owner approval. The run is completion-oriented: an ordinary in-scope lint error, test failure, build failure, or reversible local defect is evidence for the next authorized remediation attempt, not by itself a reason to stop or request a new brief. Continue through up to three distinct substantive approaches for the same problem when the accepted scope permits them, recording attempts internally and returning to Quatre only after completion or a genuine stopping boundary. A blocked stream is preserved and reported only when it needs direction or cannot advance; Kira may then move to another independently eligible, non-conflicting stream already authorized inside the same goal. Productively use available five-hour capacity by continuing the highest-value eligible CYOA work; never invent work or generate activity solely to burn usage. Enter `WAITING FOR RESET` at the 15% floor or when no safe authorized unit fits. Production publication, schema/data writes, destructive or difficult-to-reverse operations, rollback/restore, and other recorded gates always retain their separate explicit approvals.

#### Queue priority and eligibility

Filename order is not authoritative. Each queued goal or durable brief states:

- Queue priority: `P1` highest currently useful, `P2` normal upcoming, or `P3` useful fill-in.
- Eligibility and a precise `Eligible when` condition.
- Dependencies and current state.
- Blocker or minimum pending question, if any.
- Precise safe resume point.
- Authoritative answer reference, when answered.
- Whether it can run alongside active work and any shared-file/surface hotspot conflicts.
- Remaining validation requirements.
- Required Planner decisions.
- Local and production authority.
- Sprint/envelope association when applicable.

Under enabled `!run`, Quatre may route the highest-priority eligible goal only after the current work reaches a suitable transition/convergence point, dependencies and decisions are satisfied, authority already covers the work, and no unsafe collision exists. A queued goal is never automatically accepted. Normal feasibility, conflict, authority, attempt-sequence, and acceptance checks still apply; a silent Attempt 4 must be rejected or held.

At milestone completion, Quatre refreshes the queue. Refresh usage only when the next work is a new large/high-risk slice, the prior reading is stale, a reset/intervening workload occurred, or the next high estimate may approach the floor. Kira may accept follow-on work only when Quatre routes it, authority already covers it, it remains inside the same approved CYOA slice, and its high estimate plus floor still fits. Otherwise preserve it for the next reset.

A blocked stream does not stop queue consumption while independent authorized work remains eligible. Engineer becomes globally `BLOCKED` only when no authorized executable work remains.

Under `!run`, encountering a milestone blocker is a queue transition, not automatically a reason to end the engineering cycle. Kira preserves the affected milestone and reports the minimum blocker directly to Quatre. Quatre may route the next independently authorized goal when its dependencies, authority, collision checks, and acceptance criteria are satisfied. Never treat moving on as permission to bypass the blocked milestone's gate, weaken its acceptance criteria, or activate its user-facing/production outcome.

#### Park and resume

A question or decision affecting one task blocks only that task unless it also affects the safety or correctness of every other eligible task. When clarification is required, Engineer:

1. Preserves the task state and records a precise safe resume point.
2. Records only the minimum specific question and the assumptions deliberately not made.
3. Marks the task `WAITING FOR ANSWER` and reports it directly to Quatre.
4. Continues with the next independently eligible, non-conflicting task already authorized in the same five-hour project slice without ending the run or reinitializing solely for the parked task.
5. Attaches the authoritative Planner/Designer answer when received and resumes at the next safe work boundary, including after the alternate task completes or blocks.
6. Revalidates affected assumptions, dependencies, and shared files before resuming. If the answer materially changes completed work, Engineer reports the impact before substantial rework.

Quatre may route questions to Relena, change future priorities within authority, and surface genuine Product Owner gates while Kira works elsewhere. New instructions enter the queue without interrupting safe active work unless they explicitly invoke `!stop`, say `HOLD`, or invalidate the work in progress. A parked question may pause the entire run only when it affects every remaining eligible task; continued work could cross an unapproved production, destructive, security, or privacy boundary; the answer could invalidate shared architecture or create conflicting work; no independent task remains; or usage approaches the protected floor.

#### Parent routing and reporting

During enabled `!run`, Quatre may route verified evidence to Relena, maintain the live parent view, batch genuine Product Owner decisions, reprioritize unaccepted goals within authority, and prepare the next independently resumable slice while Kira continues. Stay no more than one meaningful executable slice ahead. Do not create speculative work merely to keep the queue non-empty or consume a reset window.

Quatre's consolidated status reports Kira state, active workstreams, queued work, blocked work, pending decisions, whether Kira can continue, whether replenishment is needed, and whether `!drain` or `!stop` is in effect. Do not ask the Product Owner to act merely because a decision is pending when Kira can safely continue elsewhere.

Meaningful Kira-to-Quatre reports include:

```text
ENGINEER STATE:
<WORKING | AVAILABLE | BLOCKED | DRAINING | PAUSED | WAITING FOR RESET | STOPPED AT GATE>

AWAITING QUATRE ROUTING:
<completed milestones, validated packets, or genuine questions; or NONE>

CURRENTLY PROCESSING:
<active workstreams and accepted goal, or NONE>

QUEUED AFTER CURRENT:
<eligible or waiting goals/workstreams and unmet conditions, or NONE>

BLOCKED:
<blocked streams and reason>

WAITING FOR ANSWER:
<task; minimum question; assumptions not made; safe resume point; answer reference or PENDING; conflicts; remaining validation; or NONE>

ENGINEER CAN CONTINUE:
<YES | NO>
```

Do not require this expanded block for trivial acknowledgements. Queue state survives child replacement through permanent `CURRENT_STATE.md`, accepted/queued goals or durable records, and Quatre's parent context.

This block is parent-facing live context. When a completed milestone awaits Relena review while Kira continues another authorized goal, Quatre shows both facts in its consolidated `ACTIVE OWNERS` footer, for example:

```text
TL;DR:
P2 is waiting for Relena review while Kira continues P3 under `!run`.

ACTIVE OWNERS:
- DESIGNER — RELENA — review the completed P2 packet
- ENGINEER — KIRA — continue P3 under `!run`

BLOCKING OWNER:
NONE

ACTION:
Quatre may keep Kira moving while Relena reviews P2.
```

Quatre is the persistent parent and may be active for orchestration without a Product Owner decision. List the Product Owner as blocking only when a genuine decision or explicit gate is required.

### Three-attempt reassessment rule

Within each workstream, a materially similar implementation, integration, deployment, migration, authentication, or production-operation problem may receive at most three substantive attempts before mandatory reassessment.

An attempt is a meaningful execution path intended to resolve the same underlying problem. It is not rerunning after a typo, correcting obvious syntax, fixing trivial local setup, or rerunning a flaky test without changing the approach. The rule protects usage, time, momentum, simplicity, and Product Owner attention without discouraging ordinary debugging.

After Attempt 1 or 2 fails, Engineer continues without returning for permission when the accepted brief still authorizes the work, new evidence materially informs the next attempt, no new approval gate is crossed, and no material design conflict appears. Do not issue an intermediate blocker merely because an ordinary authorized approach failed. Record concisely for the eventual completion or reassessment report:

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

### Design evidence lifecycle

1. Kira returns a sanitized validated packet directly to Quatre.
2. Quatre verifies the engineering boundary and routes product/release implications to Relena.
3. Relena incorporates only supported facts into permanent design documentation and updates [`CHANGELOG.md`](CHANGELOG.md) for a major transition under [`DOCUMENTATION_RULES.md`](DOCUMENTATION_RULES.md).
4. Quatre records a [`PLANNER_INBOX.md`](PLANNER_INBOX.md) item only when a genuine Product Owner choice remains.
5. Quatre consolidates the outcome for the Product Owner. The Product Owner does not carry the packet or a follow-up prompt between children.

Partial implementations and failed validations use the same evidence gate. Preserve unresolved durable artifacts without overwriting them; storage movement is housekeeping, not authority or acceptance.

### Naming and collision safety

Use descriptive milestone filenames rather than generic transport names. Recommended patterns are:

- `YYYY-MM-DD-<milestone>-implementation-brief.md`
- `YYYY-MM-DD-<milestone>-design-handoff.md`

Use lowercase kebab-case for `<milestone>`, for example `2026-08-08-shopping-persistence-design-handoff.md`. Add a revision suffix such as `-r2` when the same milestone produces another artifact.

Before creating, copying, or moving a file, check both the source and destination names. Never overwrite an unrelated or earlier handoff. If a destination filename already exists, compare its milestone and lifecycle context, then select a unique revision or timestamped filename. Do not delete or replace the existing artifact merely to resolve a collision.

If permissions prevent Relena from moving an artifact, leave it in place and report the housekeeping limitation to Quatre. Never weaken read-only protection or modify Kira's source packet to force a lifecycle transition.

Only Relena performs movement into `processed/` when Quatre assigns transport housekeeping. Kira may create collision-safe durable reports but may not move, archive, overwrite, delete, or reorganize shared artifacts.

### Processed artifact archive

During normal Designer housekeeping, keep approximately the most recent 30 days of completed artifacts in `processed/`. Move older eligible artifacts into `archive/YYYY-MM/` according to their completion or processing period.

- Preserve filenames when possible and use collision-safe descriptive naming when necessary.
- Never overwrite, routinely delete, ZIP, or compress normal Markdown artifacts.
- Never archive an active artifact, unresolved conflict, or item still awaiting approval.
- Archival means **completed and retained**, not discarded.
- Relena alone owns archival housekeeping when assigned by Quatre; Kira must not reorganize the archive.

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
