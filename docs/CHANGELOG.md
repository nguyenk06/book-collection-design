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
| Published | No; Version 16 remains published and live |
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
