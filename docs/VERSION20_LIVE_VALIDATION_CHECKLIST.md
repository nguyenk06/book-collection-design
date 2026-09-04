# Version 20 Product Owner Live Validation Checklist

**Status:** Historical Version 20 checkpoint; confirmed UI failures were remediated and published in Version 21. A refreshed Version 21 checklist requires the separate decision in [Planner Inbox](PLANNER_INBOX.md).
**Candidate:** Published Version 20, commit `6a2191b1b506d171d576cbb6a6b160964595c051`  
**Live Site:** <https://cyoa-collection.znesfreak.chatgpt.site>  
**Boundary:** Initial validation is read-only. Checkpoint `608553f` is excluded.

Use a current desktop browser and a mobile phone or narrow mobile viewport. Do not enter private book data into evidence; capture a screenshot or short note only when useful for a failure or follow-up.

## Read-only checklist

### 1. Desktop navigation

- **Device/viewport:** Desktop, approximately 1280px or wider
- **Start:** `/`
- **Action:** Open the collection workspace, then navigate to Shopping and back to the collection.
- **Expected:** Navigation succeeds without an error or lost collection context; the published interface still identifies itself as CYOA Collection.
- **Result:** `PASS / FOLLOW-UP / FAIL`
- **Evidence if useful:** Screenshot only for wrong destination, broken navigation, or lost context.

### 2. Desktop Shopping search

- **Device/viewport:** Desktop
- **Start:** `/shopping`
- **Action:** Search for one known library book by title or author; open the result without recording a purchase.
- **Expected:** Matching result appears with understandable owned/wanted/copy status, collection target price when present, and Purchase history kept distinct from ownership.
- **Result:** `PASS / FOLLOW-UP / FAIL`
- **Evidence if useful:** Query type and sanitized screenshot of incorrect or unclear status.

### 3. Visible M3 identifier behavior

- **Device/viewport:** Desktop
- **Start:** `/shopping`
- **Action:** Search for one known valid ISBN. If both ISBN-10 and equivalent ISBN-13 are available, repeat with the equivalent form.
- **Expected:** Valid equivalent identifiers resolve consistently to the same canonical Book; malformed input fails clearly; no duplicate or mutation is created.
- **Result:** `PASS / FOLLOW-UP / FAIL`
- **Evidence if useful:** Sanitized identifier forms and differing result titles only when behavior is inconsistent.

### 4. Desktop Bookshelf

- **Device/viewport:** Desktop
- **Start:** `/`
- **Action:** Select CYOA, switch to Bookshelf, scan several numbered positions including a visible missing gap, open one real Book spine, then close the detail view.
- **Expected:** Books follow stable series order; missing positions remain noninteractive gaps; the real spine opens accessible details; closing returns to the same collection/view context.
- **Result:** `PASS / FOLLOW-UP / FAIL`
- **Evidence if useful:** Position number and screenshot for ordering, gap, detail, or return-context problems.

### 5. Owner-only catalog download

- **Device/viewport:** Desktop, authenticated owner session
- **Start:** `/catalog-download`
- **Action:** Review scope/limitations, choose the existing download action once, and inspect only the downloaded filename and top-level format metadata.
- **Expected:** Owner page loads; messaging states included/excluded entities and that image bytes are excluded; one safe filename downloads a format-v1 catalog without changing library data.
- **Result:** `PASS / FOLLOW-UP / FAIL`
- **Evidence if useful:** Filename, format/version, and sanitized error text. Do not attach the catalog or raw records.

### 6. Mobile navigation and Shopping

- **Device/viewport:** Mobile phone or approximately 390×844 viewport
- **Start:** `/`
- **Action:** Navigate to Shopping, perform one title/author search, open a result, and return without recording a purchase.
- **Expected:** Controls remain readable and reachable without horizontal overflow; search/result/status remain usable; back navigation preserves a coherent route and collection context.
- **Result:** `PASS / FOLLOW-UP / FAIL`
- **Evidence if useful:** Screenshot for overflow, obscured controls, focus, or navigation loss.

### 7. Mobile Bookshelf

- **Device/viewport:** Mobile phone or approximately 390×844 viewport
- **Start:** `/`
- **Action:** Select CYOA and Bookshelf, scroll vertically, open one real spine, close details, and continue scrolling.
- **Expected:** The collection remains a vertically usable continuing bookcase; missing gaps and real spines are distinguishable; detail and return behavior do not lose the user's place.
- **Result:** `PASS / FOLLOW-UP / FAIL`
- **Evidence if useful:** Screenshot and approximate series position for layout or return-position problems.

### 8. Mobile owner catalog and cross-surface return

- **Device/viewport:** Mobile phone or approximately 390×844 viewport, authenticated owner session
- **Start:** `/catalog-download`
- **Action:** Review the page without downloading again, then return to the collection and Shopping using normal navigation.
- **Expected:** Owner-only catalog scope/limitations remain readable; no download occurs without the explicit action; navigation reaches collection and Shopping without an error.
- **Result:** `PASS / FOLLOW-UP / FAIL`
- **Evidence if useful:** Screenshot only for unreadable content, accidental download, or broken navigation.

## Mutation scenarios — not authorized

Do not run any of these during this checkpoint:

- Record a Purchase or create a Business.
- Add, edit, delete, import, or reassign a Book or Collection.
- Change ownership, wanted state, copies, notes, prices, covers, identifiers, or collection membership.
- Upload/replace a cover or invoke any other write endpoint.
- Run a migration, schema/data operation, correction, retry/republish, rollback, restore, or destructive recovery.

Any desired mutation scenario requires another explicit Product Owner decision naming the exact action and preservation boundary.

## Required checkpoint conclusion

Select exactly one after completing or stopping the checklist:

- [ ] **ACCEPT** — all material items pass; no release-blocking follow-up.
- [ ] **ACCEPT WITH FOLLOW-UP** — the release remains acceptable; list bounded non-blocking follow-ups.
- [ ] **REVISE BEFORE RELEASE** — a material issue requires separately authorized correction; stop without changing the Site.

For every `FOLLOW-UP` or `FAIL`, record the item number, device/viewport, short observed result, and useful sanitized evidence. Do not implement a fix from this checklist.

## Interim Product Owner results

- **1 — PASS:** Basic desktop navigation works; aesthetics are a non-blocking follow-up.
- **2 — PASS WITH FOLLOW-UP:** Scan returns an ISBN and Shopping functions as a checker at the tested boundary. Recommendation accuracy and non-ISBN matching remain follow-up work because many missing/base-set books lack ISBNs; this follow-up is not a publication blocker.
- **3 — FOLLOW-UP / HOLD:** Equivalent-identifier hands-on testing deferred until August 25 when suitable books/ISBNs are available.
- **4 — FAIL:** Desktop Bookshelf needs a primary multi-row layout; horizontal shelf may remain an alternate. Missing slots lack useful/selectable detail, and selected-book cover presentation is absent or unverified.
- **5 — FOLLOW-UP / HOLD:** Owner catalog page is accessible; actual download, filename, and format-metadata validation deferred.
- **6 — FAIL:** Mobile root/header exposes no discoverable Shopping navigation control.
- **7 — FAIL:** Mobile Bookshelf needs a primary multi-row vertical option; horizontal may remain alternate. Missing-slot information/selection and selected-book cover presentation also fail.
- **8 — FOLLOW-UP / HOLD:** Mobile owner catalog page is accessible; download-related validation remains deferred.

No final `ACCEPT`, `ACCEPT WITH FOLLOW-UP`, or `REVISE BEFORE RELEASE` conclusion has been selected.
