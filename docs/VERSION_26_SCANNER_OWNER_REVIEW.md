# Version 26 Scanner Product Owner Review

Use this checklist on the published public Site at `https://cyoa-collection.znesfreak.chatgpt.site`. This review is scanner-only; broader visual-design acceptance remains held.

## Library

- [ ] **PASS / FAIL — Release identity:** Library shows visible `v26` and exposes accessible `Release version 26`.
- [ ] **PASS / FAIL — Authoritative readiness:** Scanner controls remain unavailable until the Library data is ready, with a visible loading or failure state rather than checking fallback data.
- [ ] **PASS / FAIL — Duplicate/equivalence:** A known ISBN-10 and its equivalent ISBN-13 show the tracked Library record without creating or changing data.
- [ ] **PASS / FAIL — Conflict:** An ISBN claimed by multiple records shows an explicit conflict and does not choose, merge, or mutate a record.
- [ ] **PASS / FAIL — Unknown ISBN:** An unknown valid ISBN reaches metadata-prefilled review, or manual review when metadata is empty, unavailable, or stalls.
- [ ] **PASS / FAIL — Anchored recovery:** The checking/result message remains visible in the Library workspace, receives focus when complete, and `Scan another ISBN` starts a fresh scan.

## Shopkeeper and continuation

- [ ] **PASS / FAIL — Release identity:** Shopkeeper shows visible `v26` and exposes accessible `Release version 26`.
- [ ] **PASS / FAIL — Shared outcome:** Known, conflict, metadata, manual-review, and unavailable outcomes match Library resolution while retaining the compact Shopkeeper presentation.
- [ ] **PASS / FAIL — Retry:** `Scan another ISBN` resets the Shopkeeper flow.
- [ ] **PASS / FAIL — Sign-in continuation:** An unauthenticated Library handoff visibly preserves ISBN and available metadata through sign-in; an authenticated handoff opens explicit prefilled review.

## Report

- **Overall:** `PASS` / `FAIL`
- **Failed item(s):**
- **Notes:**

A `FAIL` identifies the item and observed behavior only. It does not authorize implementation, another Site operation, production data/schema access or mutation, authentication/provider changes, or broader visual-design work.
