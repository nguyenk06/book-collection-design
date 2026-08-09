# Design Repository Handoff

> Temporary Site-to-Design report. Include only verified, sanitized evidence needed to update permanent design documentation.

## Transfer metadata

- Milestone: <!-- Short milestone name matching the accepted brief. -->
- Prepared date: <!-- YYYY-MM-DD -->
- Source brief: <!-- Descriptive brief filename or safe identifier. -->
- Related state reports: <!-- Descriptive filenames or "None". -->
- Recommended filename: <!-- YYYY-MM-DD-<milestone>-design-handoff.md -->
- Attempt sequence: <!-- NEW SEQUENCE | ATTEMPT 2 | ATTEMPT 3 | POST-REASSESSMENT | NOT APPLICABLE -->

The Designer keeps this source unchanged in `inbox/` until its verified evidence is incorporated into permanent documentation and accepted. It may then move to `processed/` without overwriting an existing artifact.

## Handoff status

<!-- Select exactly one: COMPLETE IMPLEMENTATION | PARTIAL IMPLEMENTATION | VALIDATION FAILED -->

## Baseline

<!-- Identify the design brief or safe implementation baseline reviewed. Do not include machine paths, private IDs, or unnecessary commit hashes. -->

## Implementation completed

### Workstream summary

| ID | State | Progress | Attempt | Blocker / next gate |
| --- | --- | ---: | --- | --- |
| <!-- WS-ID --> | <!-- controlled state --> | <!-- coarse % --> | <!-- number / N/A --> | <!-- concise --> |

Use `PLANNED`, `ACTIVE`, `BLOCKED`, `READY FOR REVIEW`, `COMPLETE`, or `DEFERRED`. Progress is informational; evidence and acceptance criteria remain authoritative.

### Implemented

- <!-- Verified implementation fact. -->

### Deferred

- <!-- In-scope work intentionally postponed. -->

### Not attempted

- <!-- In-scope work not started. -->

## Database changes

- <!-- Schema, migration, constraints, and persistence behavior; use "None" when applicable. -->

## API changes

- <!-- Routes or contracts at an architectural level; use "None" when applicable. -->

## User-visible behavior

- <!-- Observable behavior; distinguish local from published behavior. -->

## Data preservation

- <!-- Evidence that identifiers and records were preserved, or state what was not verified. -->

## Tests and validation

- Tests:
- Build:
- Lint:
- Local migration validation:
- Site saved-version state:
- Publication state:
- Production verification: <!-- Use "Not performed" unless actually verified. -->

## Architecture decisions made

- <!-- Decision forced by implementation. Mark proposals requiring Design approval. -->

## Known limitations

- <!-- Remaining limitation or uncertainty. -->

## Attempt / reassessment evidence

<!-- When repeated failures apply, summarize attempt numbers, hypotheses, results, new evidence, blocker classification, simpler alternatives, and continuation cost. Otherwise use "Not applicable." -->

## Roadmap impact

- <!-- Evidence-supported impact only; do not mark work released or complete without support. -->

## Suggested documentation updates

- `docs/CURRENT_STATE.md` — <!-- UPDATE | NO CHANGE | REVIEW NEEDED --> — <!-- reason -->
- `docs/DATABASE.md` — <!-- UPDATE | NO CHANGE | REVIEW NEEDED --> — <!-- reason -->
- `docs/NEXT_ACTIONS.md` — <!-- UPDATE | NO CHANGE | REVIEW NEEDED --> — <!-- reason -->
- Relevant feature document — <!-- UPDATE | NO CHANGE | REVIEW NEEDED --> — <!-- document and reason -->
- `docs/ROADMAP.md` — <!-- UPDATE | NO CHANGE | REVIEW NEEDED --> — <!-- reason -->
- `docs/CHANGELOG.md` — <!-- UPDATE | NO CHANGE | REVIEW NEEDED --> — <!-- reason -->
- `docs/PLANNER_INBOX.md` — <!-- UPDATE | NO CHANGE | REVIEW NEEDED --> — <!-- unresolved Planner decision only -->
- ADRs / `docs/DECISIONS.md` — <!-- UPDATE | NO CHANGE | REVIEW NEEDED --> — <!-- reason -->

## Sanitization confirmation

Complete each item to confirm that this handoff contains no:

- [ ] Credentials, API keys, temporary repository credentials, tokens, or secrets
- [ ] Owner emails, personal information, or private environment values
- [ ] Local filesystem paths or machine usernames
- [ ] Private operational data or unnecessary operational identifiers
- [ ] D1/R2 resource IDs unless explicitly necessary and confirmed safe

<!-- Check every box before sharing. -->

See [`docs/DOCUMENTATION_RULES.md`](https://github.com/nguyenk06/book-collection-design/blob/main/docs/DOCUMENTATION_RULES.md) for the governing sanitization policy.

## Workflow footer

TL;DR:
<!-- Usually 1-4 short lines summarizing the verified result/state. -->

NEXT OWNER:
<!-- DESIGNER | ENGINEER | PLANNER | EXTERNAL/WAIT | NONE — PROJECT COMPLETE -->

ACTION:
<!-- The single clearest next action, approval, command, or resume condition. -->

<!-- When roles have independent simultaneous actions, replace NEXT OWNER with:
ACTIVE OWNERS:
- ENGINEER — <eligible workstreams>
- PLANNER — <pending decisions>

BLOCKING OWNER:
<NONE | DESIGNER | ENGINEER | PLANNER | EXTERNAL/WAIT>
-->
