# AI Review — manual portability workflow

## Purpose

Use the existing export and safe-import boundaries to let the Product Owner obtain external review proposals without embedding an AI provider or surrendering control of canonical data.

## Scope

- Export the collection or an explicitly chosen subset in the supported portable format.
- Let the Product Owner choose which exported records and fields to supply manually to an external agent or chat.
- Receive proposed filled-in data as a portable, reviewable file rather than an in-app automated action.
- Compare proposals through the safe-import dry run, then accept, reject, edit, or defer them under the import contract.
- Record the external review source and the Product Owner's final import decisions when available.

## User workflow

1. Export the current collection in catalog-v1 JSON.
2. Explicitly choose the records and fields to share, then manually provide that material to an external agent or chat.
3. Receive proposed filled-in catalog data without any application-side write.
4. Load the proposal through the catalog-v1 safe-import dry run and inspect every proposed change, conflict, exclusion, and failure.
5. Confirm only accepted changes through the separately authorized import workflow and retain the result report.

## Data requirements

- Source export identity and catalog-format version.
- Explicitly shared record and field scope.
- Existing values and proposed values kept separately.
- External agent/chat, prompt or instructions, timestamp, source evidence, explanation, and confidence recorded by the Product Owner when available.
- Safe-import dry-run outcome, reviewer action, and resulting canonical change kept distinguishable.

## Out of scope

- Unreviewed destructive changes.
- Treating generated text as authoritative bibliographic evidence.
- Any application-side provider integration, credential, prompt execution, or automatic transmission of collection data.
- Background agents, recurring review, silent whole-Library submission, or autonomous canonical mutation.
- Requiring AI for core collection access.

## Dependencies

- [Import and Export](IMPORT_EXPORT.md)
- Catalog-v1 portability and safe-import validation
- Provenance and audit model
- Product Owner control of external-agent privacy, cost, and retention

## Accepted manual-review boundary

- The application exports; it does not contact the external agent or chat. The Product Owner manually chooses and supplies the export or selected records and fields.
- Sharing scope never silently expands to other Books, Collections, Purchases, covers, or notes. A whole-collection export may be shared only as an explicit Product Owner choice.
- The external response is untrusted proposed data. It must conform to the accepted catalog-v1 safe-import boundary and pass a non-mutating dry run before any change can be confirmed.
- Proposed values never become canonical automatically. The Product Owner reviews the diff and confirms accepted import changes through the safe-import workflow.
- No embedded AI solution, background or recurring agent, in-app provider integration, provider credential, autonomous mutation, or application-managed external retention is part of this milestone.

This workflow direction does not authorize implementation, an external data transfer, safe-import execution, production access, or release.

## Future improvements

- Reusable external-review instruction templates.
- A stricter proposal schema layered on catalog-v1 when real review evidence justifies it.
- Clearer local diff and evidence reports for large owner-reviewed proposals.
- Provider-independent evaluation fixtures built from sanitized records.
