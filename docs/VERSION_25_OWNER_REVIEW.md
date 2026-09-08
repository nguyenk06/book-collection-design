# Version 25 Product Owner Review

Use this checklist on the published public Site at `https://cyoa-collection.znesfreak.chatgpt.site`. Record each item as `PASS` or `FAIL` and add a short note when the observed result differs from the expected behavior.

## Identity and navigation

- [ ] **PASS / FAIL — Library identity:** Library shows visible `v25` and exposes the accessible release identity `Release version 25`.
- [ ] **PASS / FAIL — Shopkeeper identity:** Shopkeeper shows visible `v25` and exposes the accessible release identity `Release version 25`.
- [ ] **PASS / FAIL — Aggregate home:** Opening the root route shows aggregate My Library and the header says `My Library`.
- [ ] **PASS / FAIL — Desktop/mobile parity:** At representative desktop and mobile widths, Library, Shopkeeper, and How it works remain reachable and the primary state and actions below remain understandable and usable.

## Aggregate My Library

- [ ] **PASS / FAIL — Complete grouping:** My Library includes all books grouped by collection in the current collection order.
- [ ] **PASS / FAIL — Unassigned placement:** Books with unknown collection keys appear under `Unassigned`, last.
- [ ] **PASS / FAIL — Within-group order:** Books sort by series/index with null indexes last, then author and title.
- [ ] **PASS / FAIL — Add-target selector:** Changing the collection selector changes only the add target; it does not filter the aggregate Library.

## Scanner flows

- [ ] **PASS / FAIL — Library known ISBN:** Scanning or manually submitting a known ISBN-10 or equivalent ISBN-13 shows an explicit duplicate result and does not mutate ownership or create/change a record.
- [ ] **PASS / FAIL — Shopkeeper known ISBN:** A known ISBN produces the compact Shopkeeper result and `Scan another` resets the flow.
- [ ] **PASS / FAIL — Unknown valid ISBN:** A valid ISBN with no Library match reaches metadata-backed review or manual review without silently creating a record.
- [ ] **PASS / FAIL — Library late-result safety:** While `Checking`, changing the Library destination prevents the late result from reopening or overwriting the replacement flow.
- [ ] **PASS / FAIL — Shopkeeper late-result safety:** While `Checking`, starting a Shopkeeper search prevents the late scanner result from reopening or overwriting the search flow.

## Deferred observations

Cover loading and Shelf missing-title presentation are deferred work. Their current behavior is not a Version 25 acceptance failure and should be captured only as a note for the later bounded phase.

## Report

- **Overall:** `PASS` / `FAIL`
- **Failed item(s):**
- **Notes:**

A `FAIL` should identify the checklist item and observed behavior. It does not authorize source, Site, production, schema, data, authentication, provider, hosting, or recovery changes.
