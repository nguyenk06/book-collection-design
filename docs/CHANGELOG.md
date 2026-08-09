# Changelog

Material changes to the project's design, architecture, and documented milestones will be recorded here.

The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/) and uses calendar dates. This documentation project does not currently assign versions.

## Milestone State Model

Major milestone states are independent. Implementation does not imply validation; validation does not imply a saved Site version; saving does not imply production migration, verification, or publication. Record only verified transitions using these states when applicable:

- Planned
- Implemented locally
- Validated locally
- Saved as Site version
- Production migrated
- Production verified
- Published
- Superseded or rolled back

## Unreleased

### Shopping Persistence Foundation

| State | Verified status |
| --- | --- |
| Planned | Yes; Priority 0 foundation before Shopping UI |
| Implemented locally | Yes |
| Validated locally | Yes |
| Saved as Site version | Yes; unpublished Version 17 |
| Production migrated | No |
| Production verified | No |
| Published | No; Version 17 remains unpublished while Version 18 bridge is published |
| Superseded or rolled back | No |

Next major transition: prepare the gated Production Backup & Migration Execution Plan, then seek separate approval for each production operation. See [Current State](CURRENT_STATE.md), [Database](DATABASE.md), and [Next Actions](NEXT_ACTIONS.md).

### Production Migration & Rollback Investigation

| State | Verified status |
| --- | --- |
| Planned | Yes |
| Read-only investigation complete | Yes |
| Production data accessed | No |
| Production backup/export executed | No |
| Production migrated | No |
| Production verified | No |
| Version 17 published | No |

Planner selected preparation for an operator-controlled D1 migration because public Sites documentation does not establish packaged migration execution or traffic gating. Time Travel bookmark capture, SQL export, migration, verification, publication, smoke testing, and destructive restore remain separately gated. See [Database](DATABASE.md) and [Next Actions](NEXT_ACTIONS.md).

### Production Backup & Migration Execution Planning

| State | Verified status |
| --- | --- |
| Operator runbook complete | Yes |
| Packet A backup gate authorized | Yes for revision 2; authorization ended with automatic abort |
| Packet A execution attempt | Automatically aborted before D1 access; authorized target/access path unavailable |
| Production access performed | No |
| Time Travel bookmark retrieved | No |
| SQL export created | No |
| Production migrated | No |
| Version 17 published | No |

Planner authorized production target verification, read-only preflight, bookmark retrieval, protected export, and write freeze only. Migration, publication, smoke testing, and destructive recovery remain separately gated.

Planner subsequently right-sized Packet A readiness for the private, single-owner project. Explicit Product Owner authorization starts the backup window; the Product Owner/Site Engineer may operate without a second human verifier or separate communication plan. The Engineer validates results and Planner reviews sanitized evidence. Packet A remains unexecuted, and the six backup, migration, verification, publication, smoke-test, and destructive-restore gates remain independent.

Packet A revision 2 was explicitly authorized and attempted, then automatically aborted at the required target/access verification gate. No production D1 query, bookmark retrieval, export, backup verification, migration, publication, or other production operation occurred. At that transition, an authorized D1 operator path was considered the retry prerequisite; the later Sites-native decision below superseded that requirement.

Planner then accepted Sites-native operations as the project constraint and removed external D1 operator access as a requirement. Direct operator-controlled migration and backup controls are unavailable unless Sites exposes them. The next milestone is a read-only Sites-native Version 17 activation investigation; this decision did not migrate, verify, or publish Version 17.

### Sites-Native Version 17 Activation Investigation

| State | Verified status |
| --- | --- |
| Read-only investigation complete | Yes |
| Disposable repeat/partial-state validation | Passed |
| Migration bridge architecture | Approved for local implementation/validation and unpublished Site save only |
| Site/source version changed | No |
| Production data accessed | No |
| Production migrated or verified | No |
| Version 17 published | No; Version 18 bridge is now published |

The investigation found direct Version 17 publication unsafe on current evidence because packaged migration execution remains unknown and runtime `ensureSeeded()` does not create the Shopping schema expected by Version 17. A Version 16-compatible migration bridge is proposed; no architecture approval or implementation is implied by this entry.

Planner approved the migration-bridge architecture for local implementation/validation and an unpublished Site save only. Bridge publication, production export, production schema upgrade, final Shopping publication, smoke testing, and destructive recovery remain unauthorized.

### Sites-Native Migration Bridge

| State | Verified status |
| --- | --- |
| Implemented locally | Yes |
| Validated locally | Yes; 37/37 tests, build and bridge/task lint pass |
| Saved as Site version | Yes; unpublished Version 18 |
| Archive excludes packaged `0004` | Yes; migrations `0000`-`0003` present |
| Production deployed/published | Yes; Version 18 deployment succeeded and Version 16 was superseded |
| Production export or schema upgrade | No |
| Production verified or smoke tested | No |

Full-project lint still reports three pre-existing errors and one warning in the main page. Version 18 publication and all production API/database operations remain separate approval gates.

Planner approved Version 18 bridge publication as an isolated next gate. Approval is not publication evidence and does not authorize production API invocation, export, schema upgrade, final Shopping publication, smoke testing, or destructive recovery.

Sites subsequently reported Version 18 publication succeeded. No application/API request, export, D1/R2 operation, schema migration/verification, Shopping activation, smoke test, restore/import, rollback, or destructive action occurred. Publication status does not establish application health or database schema state.

Planner approved owner-only production schema status and versioned JSON export as the next isolated read-only gate. Approval is not execution evidence and does not authorize schema upgrade, D1/R2 writes, final Shopping publication, smoke testing, restore/import, or destructive recovery.

The first preflight/export attempt automatically aborted because no owner-authenticated Site browser context was available. Neither approved bridge endpoint returned an application response, no export or database operation occurred, and the no-write window ended. A single read-only Site root load occurred outside the strict endpoint scope during troubleshooting; no interaction or mutation followed.

A second attempt also aborted before an application response after Product Owner reported owner mode; the authenticated tab was not available to the Engineer browser context and direct navigation was blocked. No production read, export, write, or D1/R2 change occurred. The next milestone changed from retry to read-only comparison of proven in-Site persistence/authentication paths against the administrative bridge.

### Site Authentication and Persistence Path Investigation

| State | Verified status |
| --- | --- |
| Read-only investigation complete | Yes |
| Focused disposable validation | Passed; 34/34 |
| Source or Site version changed | No |
| Production request/data access | No |
| Production migration or verification | No |
| Publication/deployment changed | No; Version 18 remains published |

The investigation verified that normal owner mutations and bridge routes share the same server-side owner authorization helper, Site worker, and managed D1 binding. Normal UI requests use a same-origin browser path; both direct Engineer attempts failed before application route execution and therefore do not establish an application-authentication or D1 failure. A narrow permanent owner-only in-Site administration surface is recommended but awaits Planner approval; no implementation or production authority follows from the investigation.

Planner approved the administration-surface architecture for local implementation and validation. The surface must operate only within an owner-authenticated Site session, retain server-side authorization, and must not bypass authentication or provide owner credentials/session material to Engineer. Site saving, publication, production requests, export, migration, verification, and destructive actions remain unauthorized.

### Owner-Authenticated Administration Surface

| State | Verified status |
| --- | --- |
| Implemented locally | Yes |
| Validated locally | Yes; 44/44 tests, build, and task lint pass |
| Full source lint | Known three errors and one warning remain; no new task lint debt |
| Saved as Site version | Yes; unpublished Version 19 |
| Published/deployed | No change; Version 18 remains published |
| Production request/export/migration/verification | No |

The local surface uses the existing owner-authenticated same-origin path, withholds controls/data from non-owners, validates private exports before download, and adds server-enforced same-origin and deliberate-confirmation checks before the schema-upgrade service. It creates no authentication bypass or Engineer credential path. Preserving this exact source as an unpublished Site version is the next separately approved gate.

Planner approved that unpublished Site-version preservation gate. The approval is recorded for a future explicitly started development session; no save, publication, production request, export, migration, verification, or other Site/production change occurred from the decision.

The exact validated administration source was subsequently preserved as unpublished Site Version 19. Validation passed 44/44 tests, build, and task lint immediately before saving. Version 18 remains published; no application invocation, production request/data access, export, D1/R2 operation, migration, production verification, smoke test, or publication occurred.

### Shopping Mode Local UI

| State | Verified status |
| --- | --- |
| Search/scan/status flow | Implemented and locally validated |
| Purchase history and capture | Implemented and locally validated |
| Price contract | Required non-negative purchase price; optional sticker price; unknown is never zero |
| Tests/build/task lint | 50/50 serial tests, 6/6 focused Shopping tests, 14/14 isolated collection tests, build, and task lint pass |
| Saved as Site version | No; Version 19 remains latest |
| Published/production changed | No; Version 18 remains published |

The unsaved local Shopping flow supports existing search/scanner behavior, collection status, Purchase history and owner-only capture, repeat-shopping navigation, ownership-independence messaging, and accessible state handling. Successful Purchase creation refreshes history without changing Book ownership or copies. The first parallel full-suite run encountered resource timeouts in unchanged collection tests; the isolated collection suite and authoritative serial full suite passed, establishing local resource contention rather than a behavior regression. No unauthorized schema, API, Site, or production change occurred.

### Changed

- Deferred portable immutable Purchase identifiers until cross-database Import/Export, reconciliation, or AI Review requires them.
- Established platform portability as a proportional architecture constraint: keep APIs, migrations, JSON contracts, adapters, and business rules reasonably replaceable without adding new deployment targets to current scope.

## 2026-08-04

### Production Baseline Recorded

- Verified Site Version 16 as the published, live, stable application baseline. The original publication date was not established by this assessment.

### Database Architecture Assessment

- Verified v16 architecture, database, capability, risk, and status documentation.
- ADRs for additive identity-preserving migrations, Shopping persistence, and canonical book identifiers.
- Completed the read-only database-first architecture assessment.
- Completed the current database review and replaced the provisional schema description with verified findings.
- Validated the roadmap order, dependencies, effort, and blockers.
- Updated project status without changing application code, schema, production data, or deployment.
