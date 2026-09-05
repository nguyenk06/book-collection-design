# Engineer Estimation Brief

> Durable read-only estimation, feasibility, or source/collision goal transmitted internally by Planner — Quatre to direct Engineer subagent Kira. The Product Owner does not carry this file. It grants no authority to modify application source or Site state.

Engineer must read `docs/ENGINEER_EXECUTION_CONTRACT.md` before acceptance and execution. Read-only tool failures block only the exact action unless evidence proves the whole request unsafe; use only the fallback ladder explicitly authorized here.

## Chat identity

- Assigned role: ENGINEER
- Parent/orchestrator: PLANNER — QUATRE
- Assigned name: KIRA
- Delegation depth: 1 — Kira must not spawn
- Expected context: <!-- continuing | new | source recovery -->
- Required source state: <!-- Exact source/version and access required for inspection -->

Before acceptance, Kira reports context continuity, unpublished work, editable-source access, working-tree state, latest saved/published versions, and whether actual context matches this request. A mismatch parks the request without reconstruction. Kira returns directly to Quatre.

## Request identity and lifecycle

- Request ID:
- Milestone/program:
- Work type: `ESTIMATION/INSPECTION ONLY`
- Status: `NON-EXECUTABLE IMPLEMENTATION AUTHORITY`
- Priority/dependencies:
- Quatre transmission/activation condition:
- Queue/throttle condition:

## Usage and model profile

Usage may be supplied as `!<five-hour>:<longer-period>`; `!40:75` means 40% five-hour and 75% longer-period. It records usage only and never accepts or activates this request.

- Preferred model: <!-- Default Kira profile: GPT-5.6 Terra. -->
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
- Prioritized read-only fallback ladder: <!-- Predictable access/tool limitations in order; mark any fallback requiring new authority. -->

The Product Owner controls actual model selection through Quatre. This request cannot change it automatically. Kira may use Sol only when this accepted request recommends it or a later Planner/Product Owner decision approves it. Model, reasoning, tools, context, and task complexity can change observed usage.

Keep this durable record in the designated internal brief store until Quatre accepts Kira's corresponding sanitized report and routes any needed design review to Relena. The Product Owner does not transport it. Repository planning text or an embedded estimation gate is not execution authority.

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

- Allowed: read authoritative documents and inspect the named existing source context without mutation; return one sanitized report directly to Quatre.
- Not allowed: spawn subagents; invoke Sites tools or obtain Sites credentials; modify or generate application source/tests/dependencies; materialize or overwrite source; create a commit/package; save or preview a Site version; deploy or publish; access production data; change schema/data; migrate; restore; roll back; or treat the estimate as implementation authority.
- Do not expose secrets, private data, credentials, environment values, private URLs, or unsanitized artifacts.

## Stop conditions

Stop and report if context/source identity does not match, required evidence remains inaccessible after the authorized fallback ladder, inspection would mutate state, sensitive data would be exposed, scope becomes implementation, the third substantive read-only approach fails, or the usage/clean-stop boundary is unsafe. Do not stop merely because the first authorized read-only approach failed.

## Required footer

Address acceptance, blocker, and completion reports to `PLANNER — QUATRE`. If a durable footer is used, set `NEXT OWNER: PLANNER — QUATRE`; never instruct the Product Owner to contact another agent.
