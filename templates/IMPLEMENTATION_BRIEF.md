# Implementation Brief

> Temporary Design-to-Site handoff for one milestone. Keep concise, link to design authority, and remove all sensitive or machine-specific information before sharing.

## Engineer assignment and context

- Assigned role: ENGINEER
- Assigned name: SEI
- Expected chat: CYOA — Engineer Sei
- Expected context: <!-- continuing | new | source recovery -->
- Required source state: <!-- Describe the required editable, saved, published, clean/dirty, or unpublished source baseline. -->

Sei must output the expected title at startup so the Product Owner can apply it manually. Before `!brief` acceptance, inspect the actual Sites/message context and report prior unpublished implementation, editable-source access, dirty or unsaved state, latest known saved and published Site versions, context match, and whether source composition and collision boundaries can be verified. If context or source does not match, park only this task and report the mismatch. Do not reconstruct, overwrite, materialize, save, or publish without authority.

## Transfer metadata

- Milestone: <!-- Short milestone name. -->
- Prepared date: <!-- YYYY-MM-DD -->
- Recommended filename: <!-- YYYY-MM-DD-<milestone>-implementation-brief.md -->
- Engineer acceptance: PENDING <!-- Engineer reports acceptance separately; do not edit this brief in place. -->
- Planner decision: <!-- NONE, or a concise accepted direction with a permanent repository link. Do not copy decision history. -->
- Attempt sequence: <!-- NEW SEQUENCE | ATTEMPT 2 | ATTEMPT 3 | POST-REASSESSMENT -->
- Attempt/reset rationale: <!-- Identify the underlying problem and prior attempt evidence; for a reset, explain the material architecture/capability/requirement/premise change. -->
- Queue priority: <!-- P1 | P2 | P3 | NOT QUEUED -->
- Eligible when: <!-- Objective dependency/gate condition. -->
- Can run alongside active work: <!-- YES | NO -->
- Collision/shared-surface concerns: <!-- Concise hotspots or NONE. -->
- Required Planner decision: <!-- Decision reference or NONE. -->
- Five-hour slice / milestone association: <!-- Slice identifier and parent milestone, or NOT APPLICABLE. -->
- Active Engineer project: <!-- CYOA; do not share this five-hour window with another Engineer project. -->

## Usage and reset boundary

- Minimum starting percentage: <!-- high estimate + provisional 30% floor -->
- Expected usage range: <!-- LOW / LIKELY / HIGH percentage-point range; planning estimate, not token conversion -->
- Usage immediately before `!brief`: <!-- Record at acceptance. -->
- Usage immediately before `!run`: <!-- Record at activation. -->
- Named safe checkpoints: <!-- Independently recoverable unit boundaries. -->
- Automatic stop conditions: <!-- Include reserve/window, authority, source, collision, validation, and risk boundaries. -->
- Deferred to next reset: <!-- Explicit remaining work that this slice does not authorize. -->

Start only when current usage is at least the high estimate plus the provisional 30% floor. If capacity or the five-hour window ends, preserve the current safe checkpoint and report `WAITING FOR RESET`; do not classify capacity exhaustion as `BLOCKED`.

Keep this file in `briefs/` until the Engineer creates a sanitized `YYYY-MM-DD-<milestone>-brief-acceptance.md` report in `inbox/`. Acceptance must confirm the attempt-sequence classification and must reject a silent Attempt 4. After validating clean acceptance, the Designer may move the brief and satisfied acceptance report to `processed/` without overwriting existing artifacts. Brief acceptance authorizes work already within this brief; it is not implementation completion.

Queue metadata does not activate Queue Mode, make a brief executable, or replace `!brief` acceptance. A reset does not reactivate the slice automatically. When Queue Mode is disabled, Engineer must not consume this as follow-on work without separate authority.

## Workstreams

Use one block per bounded stream. Remove this section only when the brief contains one simple workstream whose fields are fully represented below.

### <!-- WS-ID — Descriptive name -->

- Objective:
- Scope:
- Dependencies:
- Expected files/surfaces:
- Allowed actions:
- Explicit exclusions:
- Attempt sequence: <!-- NEW SEQUENCE | ATTEMPT 2 | ATTEMPT 3 | POST-REASSESSMENT | NOT APPLICABLE -->
- Production authority: <!-- Normally NONE; local authority never implies production authority. -->
- May continue independently: <!-- YES | NO; identify dependency/collision when NO. -->
- Convergence gate:

Identify shared hotspots across workstreams and serialize or coordinate conflicting edits. Do not create competing implementations merely to preserve parallel execution.

## Objective

<!-- State the single implementation outcome. -->

## Why this is next

<!-- Link the roadmap priority or accepted decision. -->

## Verified current state

<!-- State only observed behavior relevant to this milestone. Identify the evidence baseline. -->

## Requirements

- <!-- Required behavior or constraint. -->

## Data / schema implications

- <!-- Required persistence, migration, integrity, or preservation behavior; use "None" when applicable. -->

## User workflow

1. <!-- Short user flow. -->

## Acceptance criteria

- [ ] <!-- Observable outcome or validation requirement. -->

## Out of scope

- <!-- Explicit exclusion. -->

## Risks / cautions

- <!-- Data, compatibility, migration, security, or product risk. -->

## Relevant design documents

- <!-- Link to the public design repository document; do not duplicate it. -->

## Documentation handoff requirements

- Identify `ENGINEER — SEI` in every acceptance, blocker, completion, and source-recovery report.
- Return a completed `DESIGN_HANDOFF.md` based on verified evidence.
- Separate implemented, deferred, and not-attempted work.
- Report tests, local migration validation, saved-version state, and publication state independently.
- Recommend document updates as `UPDATE`, `NO CHANGE`, or `REVIEW NEEDED`.
- Close brief acceptance, progress/blocker, completion, saved-version, and publication/deployment reports with the standard `TL;DR` / `NEXT OWNER` / `ACTION` footer defined in `docs/HANDOFF_PROTOCOL.md`.

## Product Owner validation checkpoint

- Required for this milestone: <!-- YES | NO; use YES only for a meaningful user-facing boundary. -->
- Safe validation environment: <!-- Exact preview/saved version/environment, or NOT YET VERIFIED. -->
- Scenario checklist authority: <!-- Feature document section or concise attached checklist. -->
- Production separation: <!-- Confirm checkpoint completion does not authorize save, migration, publication, production writes, smoke testing, rollback, or destructive action. -->

## Approval boundary

- **Local authority:** Implement and validate only the named workstreams and scope above.
- **Production authority:** <!-- NONE unless a separately approved production action is stated explicitly. -->
- Stop before publishing unless explicit approval is provided separately.
- Do not modify the design repository.

> Sanitization required: do not include credentials, API keys, temporary repository credentials, tokens, owner emails, environment secrets, private operational data, unsafe D1/R2 resource IDs, local paths, machine usernames, or unnecessary operational identifiers. See [`docs/DOCUMENTATION_RULES.md`](https://github.com/nguyenk06/book-collection-design/blob/main/docs/DOCUMENTATION_RULES.md).
