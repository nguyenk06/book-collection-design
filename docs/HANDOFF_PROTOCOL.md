# Design and Site Handoff Protocol

This protocol defines the file-based exchange between the Design workspace and the Site implementation workspace. Permanent product state belongs in the design documents and Site version history; handoff files are temporary transport artifacts unless explicitly archived.

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

The Site Engineer treats the public design repository as read-only reference. When starting significant implementation work, read or request the relevant current documents. If the Site workspace cannot read GitHub directly, use the latest exported [`IMPLEMENTATION_BRIEF.md`](../templates/IMPLEMENTATION_BRIEF.md) as the handoff package.

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
- Invent product direction.
- Mark roadmap work complete without implementation evidence.
- Publish without explicit approval.
- Move briefs or reports between shared handoff folders.
- Archive, overwrite, delete, or reorganize shared handoff artifacts.

### Sites source-preservation exception

The Site Engineer may create and push the minimum source commit required to preserve an already validated source state through the Sites saved-version workflow when that workflow requires pushed source provenance.

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
- Relevant feature documents

The Site Engineer reads the public design repository at <https://github.com/nguyenk06/book-collection-design> or receives the latest implementation brief when direct reading is unavailable.

## Design to Site Handoff

The Designer prepares [`IMPLEMENTATION_BRIEF.md`](../templates/IMPLEMENTATION_BRIEF.md) for one milestone. It is a concise, share-ready specification containing only what the Site Engineer needs.

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

## File Handling

The preferred workflow is file-based rather than large chat copy-and-paste blocks.

| Direction | File | Handling |
| --- | --- | --- |
| Design to Site | `IMPLEMENTATION_BRIEF.md` template | Create a milestone-specific file in `briefs/`; share it with the Site Engineer |
| Site to Design | `DESIGN_HANDOFF.md` template | Receive a milestone-specific file in `inbox/`; review it as read-only evidence |

Do not treat transport files as permanent project history unless the product owner explicitly asks to archive them. Durable facts must be incorporated into the relevant design documents or Site version history.

## Handoff Workspace Lifecycle

The handoff workspace is outside both repositories. The Designer owns its housekeeping and maintains three logical areas:

| Area | Purpose | Exit gate |
| --- | --- | --- |
| `inbox/` | Read-only Site Engineer handoffs awaiting Design review | Verified evidence is incorporated into permanent documentation and the resulting documentation state is accepted |
| `briefs/` | Designer-prepared implementation briefs awaiting Engineer acceptance | Site Engineer confirms receipt and accepts the brief as the active implementation specification |
| `processed/` | Transport artifacts that passed their applicable exit gate | Retain locally according to product-owner housekeeping needs; do not commit by default |

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

The Designer owns report housekeeping. Keep a report in `inbox/` while it represents an unresolved blocker, approval request, conflict, or unapplied implementation evidence. Move it to `processed/` only after its lifecycle purpose is satisfied, without altering or overwriting it.

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

### Design handoff lifecycle

1. A Site Engineer handoff enters `inbox/` and remains unchanged during intake review.
2. The Designer verifies sanitization, evidence boundaries, conflicts, and referenced design authorities.
3. The Designer incorporates only supported facts into permanent design documentation.
4. The Designer evaluates whether the evidence is a major milestone state transition and updates [`CHANGELOG.md`](CHANGELOG.md) when required by [`DOCUMENTATION_RULES.md`](DOCUMENTATION_RULES.md).
5. Resolve and record any required product-owner decisions.
6. Only after the verified evidence has been incorporated and the resulting documentation state is accepted may the Designer move the handoff to `processed/`.

Partial implementations and failed validations use the same gate: record their verified state before processing the artifact. If evidence is missing, conflicted, rejected, or still under review, leave the handoff in `inbox/`.

### Naming and collision safety

Use descriptive milestone filenames rather than generic transport names. Recommended patterns are:

- `YYYY-MM-DD-<milestone>-implementation-brief.md`
- `YYYY-MM-DD-<milestone>-design-handoff.md`

Use lowercase kebab-case for `<milestone>`, for example `2026-08-08-shopping-persistence-design-handoff.md`. Add a revision suffix such as `-r2` when the same milestone produces another artifact.

Before creating, copying, or moving a file, check both the source and destination names. Never overwrite an unrelated or earlier handoff. If a destination filename already exists, compare its milestone and lifecycle context, then select a unique revision or timestamped filename. Do not delete or replace the existing artifact merely to resolve a collision.

If permissions prevent the Designer from moving an artifact, leave it in place and report the housekeeping limitation. Never weaken read-only protection or modify the Site Engineer's source handoff to force a lifecycle transition.

Only the Designer performs movement into `processed/`. The Site Engineer may read briefs and create new collision-safe reports or handoffs in `inbox/`, but may not move, archive, overwrite, delete, or reorganize shared artifacts.

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
