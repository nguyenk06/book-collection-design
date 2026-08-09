# Changelog

Material changes to the project's design, architecture, and documented milestones will be recorded here.

The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/) and uses calendar dates. This documentation project does not currently assign versions.

## Unreleased

### Added

- Documented the locally implemented and validated Shopping persistence/API foundation: Businesses, Purchases, collection target price, Added Date, controlled conditions, and owner-authorized APIs.

### Changed

- Deferred portable immutable Purchase identifiers until cross-database Import/Export, reconciliation, or AI Review requires them.
- Recorded that the foundation is not saved as a Site version, migrated to production, or published.

## 2026-08-04

### Added

- Verified v16 architecture, database, capability, risk, and status documentation.
- ADRs for additive identity-preserving migrations, Shopping persistence, and canonical book identifiers.

### Changed

- Completed the read-only database-first architecture assessment.
- Completed the current database review and replaced the provisional schema description with verified findings.
- Validated the roadmap order, dependencies, effort, and blockers.
- Updated project status without changing application code, schema, production data, or deployment.

### Deprecated

### Removed

### Fixed

### Security
