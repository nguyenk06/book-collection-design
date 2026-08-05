# AI Review

## Purpose

Assist the collector in finding and resolving incomplete, inconsistent, or uncertain records without surrendering control of canonical data.

## Scope

- Identify records that may need attention.
- Propose normalized or enriched values with explanations.
- Compare suggestions with existing values and source evidence.
- Accept, reject, edit, or defer suggestions individually or in safe batches.
- Record review outcomes.

## User workflow

1. Open a queue filtered by issue type or confidence.
2. Compare current data, evidence, and the proposed change.
3. Accept, edit, reject, or defer the suggestion.
4. Review a concise audit result.

## Data requirements

- Existing value and proposed value kept separately.
- Source inputs, model/provider, prompt or rule version, timestamp, and confidence.
- Explanation suitable for a collector's decision.
- Reviewer action and resulting canonical change.
- Privacy and retention classification for submitted data.

## Out of scope

- Unreviewed destructive changes.
- Treating generated text as authoritative bibliographic evidence.
- Sending private collection data to providers without an explicit policy.
- Requiring AI for core collection access.

## Dependencies

- [Database](DATABASE.md)
- [Scanner and Matching](SCANNER_AND_MATCHING.md)
- Provenance and audit model
- Provider privacy, cost, and failure policies

## Future improvements

- Calibrated confidence by issue type.
- Batch review for low-risk, reversible suggestions.
- Provider-independent evaluation sets.
- Learning from explicit collector feedback without obscuring rules.
