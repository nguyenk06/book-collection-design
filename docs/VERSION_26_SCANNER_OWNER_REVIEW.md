# Version 26 Scanner Product Owner Review

## Current result

- **Overall:** `REJECTED`
- **Athrun severity:** `S2 MAJOR / RELEASE-BLOCKING`
- **Observed symptoms:** On published Version 26, desktop-class in-app-browser automation found accepted main-page capture could close without an explicit result, two supplied cover photos failed to decode, and metadata from two valid manual ISBNs did not reconcile probable ISBN-less owned records before Add item opened. Separately, the Product Owner's mobile scanner attempt did not react; the exact trigger/result is not attributable.
- **Scope:** Main-page scanner only. The Product Owner did not test desktop; the photo/manual fixture evidence below is desktop-class automation. Shopkeeper was not reviewed, and broader visual-design acceptance remains held.
- **Partial corrective evidence:** Exact local unpublished `115b1a57ad92e96a0ff41b9c2660f6a757e037e1` addresses the earlier explicit-result symptom and retains 124/124 tests, production build `PASS`, lint with zero errors/one unchanged image advisory, and Relena's earlier bounded `PASS`. It is not public and does not address the expanded ISBN-less reconciliation and real-image boundary.
- **QA evidence:** Athrun validated exact clean `115b1a57` under Node `24.19.0`: resolver 6/6, selected main-page scanner 26 tests passed, bounded collection/identifier 33/33, full serial 11/11 files and 124/124 tests in 148.37 seconds, lint zero errors/one existing image advisory, production build `PASS`, and clean diff.
- **Evidence limit:** Public camera, live metadata, and operator behavior remain unproven until an authorized release is reviewed. Automated/local evidence does not replace this checklist.
- **Next gate:** No implementation brief is active. A future bounded correction requires explicit implementation authority; publication/version change remains a separate Product Owner gate. If later published, rerun the checklist below against the new exact public version.

## Sanitized public evidence — 2026-09-11

- **Evidence class:** The photo/manual runs below used public Version 26 through desktop-class in-app-browser automation; they are not Product Owner desktop testing.
- **Bellmaker Photo 1:** Decoded retail UPC `072742006992` and correctly requested the printed ISBN. Manual `044100315X` retrieved *Bellmaker* / Brian Jacques but did not reconcile the existing ISBN-less Redwall #7; Add item opened with CYOA selected and was canceled.
- **Subtle Art Photo 4:** Photo decode failed. Manual `9781250425409` correctly reported an existing My Books record with one owned.
- **Hurricane Photo 5:** Photo decode failed. Manual `0553273566` retrieved *Hurricane!* / Richard Brightfield but did not reconcile the existing ISBN-less owned CYOA #82; Add item opened with My Books selected and was canceled.
- No Add item action was confirmed and no mutation was observed.
- **Separate mobile operator failure:** The Product Owner reported that scanner testing on mobile failed to react. Exact trigger, browser/device, last visible state, and result were not captured, so this evidence does not identify camera-callback, upload, lookup, or result-rendering failure.

## Planned acceptance boundary — not active authority

- After metadata returns, conservatively compare against ISBN-less records. A unique sufficiently supported candidate is reported as probable existing for review; ambiguous candidates are an explicit conflict. Do not silently attach an ISBN or mutate a record.
- Exercise representative real cover-image fixtures and only bounded preprocessing needed for reliable decoding. Preserve distinct outcomes for a decoded non-book UPC, no barcode decoded, and a valid ISBN.
- Present an explicit result before any Add item transition. Preserve cancel/no-mutation behavior.
- Update visible and accessible release identity, run full attributable validation, and then—only after separately authorized publication—repeat public photo, manual, and live-camera checks. Instrument the mobile retest and capture exact action, browser/version, device/OS, permission state, last visible state, and safely attributable callback/upload/lookup/rendering evidence.
- Shopkeeper and broader visual design remain excluded.

Use this checklist on the published public Site at `https://cyoa-collection.znesfreak.chatgpt.site` only after a corrected release is separately authorized. This review is main-page-scanner-only; Shopkeeper and broader visual design remain excluded.

## Library

- [ ] **PASS / FAIL — Review record:** Record the exact public version, browser and version, desktop/mobile device/OS or viewport, local date/time with time zone, sign-in and camera-permission state, exact trigger action, last visible UI state, and only sanitized fixture identifiers.
- [ ] **PASS / FAIL — Release identity:** Library's visible and accessible version labels agree with the exact separately authorized release.
- [ ] **PASS / FAIL — Authoritative readiness:** Scanner controls remain unavailable until the Library data is ready, with a visible loading or failure state rather than checking fallback data.
- [ ] **PASS / FAIL — Duplicate/equivalence:** A known ISBN-10 and its equivalent ISBN-13 open an explicit result modal with title, collection, status, and `View Library record`, without creating or changing data.
- [ ] **PASS / FAIL — Probable ISBN-less existing:** Metadata for a manual or photo-derived ISBN conservatively finds a unique sufficiently supported ISBN-less owned record and presents a probable-existing review result instead of opening Add item; ambiguous matches present conflict.
- [ ] **PASS / FAIL — Conflict:** An ISBN claimed by multiple records opens an explicit conflict result and does not choose, merge, or mutate a record.
- [ ] **PASS / FAIL — Metadata review/cancel:** An unknown valid ISBN with metadata opens an explicit result showing title/author and `Review and add`; canceling review creates or changes nothing.
- [ ] **PASS / FAIL — Offline/manual fallback:** After Library data has loaded, empty, unavailable, stalled, or offline metadata produces an explicit `Enter details and add` fallback without silently creating or changing data.
- [ ] **PASS / FAIL — Retry:** `Scan another ISBN` closes the result and opens a fresh scanner.
- [ ] **PASS / FAIL — Real-image decoding:** Representative Bellmaker, Subtle Art, and Hurricane cover-photo fixtures exercise bounded preprocessing and clearly distinguish a decoded retail UPC that requests a printed ISBN from a photo where no barcode is decoded.
- [ ] **PASS / FAIL — Instrumented mobile reaction:** On a real mobile browser, manual, photo/upload, and live-camera triggers each produce a visible next state. If any fails to react, record safely attributable callback/upload/lookup/render evidence rather than inferring the failed layer.
- [ ] **PASS / FAIL — Pending lookup (optional timing case):** If the lookup can be held pending reproducibly, changing collection or search does not silently discard its accepted result; replacing or explicitly canceling the scanner still prevents a stale result from reopening or overwriting the flow.
- [ ] **PASS / FAIL — Explicit add boundary:** Scanning and lookup do not mutate data; creation can occur only after explicit review and add.

## Report

- **Overall:** `PASS` / `FAIL`
- **Public version / browser / device/OS / time / permission state:**
- **Exact trigger and last visible state:**
- **Failed item(s):**
- **Notes:**
- **Failure evidence:** Sanitized screenshot or recording, exact step, expected result, observed result, ISBN fixture class (duplicate/equivalent/conflict/unmatched; not private production content), console/network symptom if safely available, and whether retry recovered.

A `FAIL` identifies the item and observed behavior only. It does not authorize implementation, another Site operation, production data/schema access or mutation, authentication/provider changes, Shopkeeper work, or broader visual-design work.
