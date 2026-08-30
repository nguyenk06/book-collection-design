# Engineer Estimation Brief

> Designer-to-Engineer transport for bounded read-only estimation, feasibility, or source/collision inspection. This is not an implementation brief and grants no authority to modify application source or Site state.

## Chat identity

- Assigned role: ENGINEER
- Assigned name: SEI
- Expected chat: CYOA — Engineer Sei
- Expected context: <!-- continuing | new | source recovery -->
- Required source state: <!-- Exact source/version and access required for inspection -->

Before acceptance, Sei reports context continuity, unpublished work, editable-source access, working-tree state, latest saved/published versions, and whether actual context matches this request. A mismatch parks the request without reconstruction.

## Request identity and lifecycle

- Request ID:
- Milestone/program:
- Work type: `ESTIMATION/INSPECTION ONLY`
- Status: `NON-EXECUTABLE IMPLEMENTATION AUTHORITY`
- Priority/dependencies:
- Eligibility command or condition:
- Queue/throttle condition:

## Usage and model profile

Usage may be supplied as `!<five-hour>:<longer-period>`; `!40:75` means 40% five-hour and 75% longer-period. It records usage only and never accepts or activates this request.

- Preferred model: <!-- Default Sei profile: GPT-5.6 Terra. -->
- Reasoning effort: <!-- Default: Medium. -->
- Speed mode: <!-- Default: Standard; Fast remains off. -->
- Current five-hour percentage:
- Five-hour reset time:
- Current longer-period Codex percentage:
- Estimated five-hour consumption: <!-- LOW / LIKELY / HIGH -->
- Planning-class guide: <!-- Diagnostic/status default: 35%. -->
- Operational minimum starting percentage: <!-- Remaining HIGH estimate + 15% floor. -->
- Automatic stopping percentage: **15%**
- Safe checkpoint:
- Work deferred until the next reset:

The Product Owner selects the actual model. This request cannot change it automatically. Sei may escalate from Terra to Sol only when this accepted request recommends it or a later Planner/Product Owner decision approves it. Model, reasoning, tools, context, and task complexity can change observed usage.

Keep this file in `briefs/` until Designer accepts the corresponding sanitized report. The request must exist in transport before Engineer begins; repository planning text, a copy-ready prompt, or an embedded estimation gate is not a brief and does not authorize work retroactively.

## Authoritative inputs

- Repository commit:
- Documents/ADRs:
- Source/Site baseline:
- Product Owner decisions:

## Questions to answer

1. <!-- Exact bounded estimation/inspection question -->

## Required report

For each requested unit, return as applicable:

- exact files, components, routes, runtime surfaces, and collision boundaries;
- verified present/absent/unknown capabilities;
- dependencies and unresolved decisions;
- data/schema, authentication, authorization, security, privacy, and operational implications;
- mobile, desktop, accessibility, performance, regression, and evidence requirements;
- low/likely/high effort including intake, checks, ordinary remediation allowance, validation, handoff, and clean stop;
- independent-development feasibility, recommended order/splits, safe stopping points, and parking conditions.

## Authority and exclusions

- Allowed: read authoritative documents and inspect the named existing message/Sites/source context without mutation; prepare one sanitized report in `inbox/`.
- Not allowed: modify or generate application source/tests/dependencies; materialize or overwrite source; create a commit/package; save or preview a Site version; deploy or publish; access production data; change schema/data; migrate; restore; roll back; or treat the estimate as implementation authority.
- Do not expose secrets, private data, credentials, environment values, private URLs, or unsanitized artifacts.

## Stop conditions

Stop and report if context/source identity does not match, required evidence is inaccessible, inspection would mutate state, sensitive data would be exposed, scope becomes implementation, or the usage/clean-stop boundary is unsafe.

## Required footer

Close acceptance, blocker, and completion reports using the canonical `TL;DR` / `NEXT OWNER` / `ACTION` footer in `docs/HANDOFF_PROTOCOL.md`.
