# Implementation Brief

> Temporary Design-to-Site handoff for one milestone. Keep concise, link to design authority, and remove all sensitive or machine-specific information before sharing.

## Transfer metadata

- Milestone: <!-- Short milestone name. -->
- Prepared date: <!-- YYYY-MM-DD -->
- Recommended filename: <!-- YYYY-MM-DD-<milestone>-implementation-brief.md -->
- Engineer acceptance: PENDING <!-- Engineer reports acceptance separately; do not edit this brief in place. -->
- Planner decision: <!-- NONE, or a concise accepted direction with a permanent repository link. Do not copy decision history. -->

Keep this file in `briefs/` until the Engineer creates a sanitized `YYYY-MM-DD-<milestone>-brief-acceptance.md` report in `inbox/`. After validating clean acceptance, the Designer may move the brief and satisfied acceptance report to `processed/` without overwriting existing artifacts. Brief acceptance authorizes work already within this brief; it is not implementation completion.

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

- Return a completed `DESIGN_HANDOFF.md` based on verified evidence.
- Separate implemented, deferred, and not-attempted work.
- Report tests, local migration validation, saved-version state, and publication state independently.
- Recommend document updates as `UPDATE`, `NO CHANGE`, or `REVIEW NEEDED`.
- Close brief acceptance, progress/blocker, completion, saved-version, and publication/deployment reports with the standard `TL;DR` / `NEXT OWNER` / `ACTION` footer defined in `docs/HANDOFF_PROTOCOL.md`.

## Approval boundary

- Implement and validate only the scope above.
- Stop before publishing unless explicit approval is provided separately.
- Do not modify the design repository.

> Sanitization required: do not include credentials, API keys, temporary repository credentials, tokens, owner emails, environment secrets, private operational data, unsafe D1/R2 resource IDs, local paths, machine usernames, or unnecessary operational identifiers. See [`docs/DOCUMENTATION_RULES.md`](https://github.com/nguyenk06/book-collection-design/blob/main/docs/DOCUMENTATION_RULES.md).
