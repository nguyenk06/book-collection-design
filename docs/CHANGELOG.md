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

Next major transition: complete the read-only production migration and rollback investigation, then seek separate approval for any production operation. See [Current State](CURRENT_STATE.md), [Database](DATABASE.md), and [Next Actions](NEXT_ACTIONS.md).

### Changed

- Deferred portable immutable Purchase identifiers until cross-database Import/Export, reconciliation, or AI Review requires them.

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
