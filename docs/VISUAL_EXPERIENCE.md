# My Library Visual Experience

## Status and authority

This document is the canonical future visual and interaction direction for **My Library**. It defines product-level experience requirements for later estimation and phased implementation. It does not describe current implementation state, authorize Engineer work, or open any Site, source, data, save, preview, deployment, publication, or production gate. [Current State](CURRENT_STATE.md), accepted briefs, tests, and gate evidence remain authoritative for delivery status.

The cumulative Shopping/M3–M6/Bookshelf source is published as exact Version 20. Later local Phase A/D work remains only at checkpoint `608553f` and was excluded from publication. Future work must begin with composition and collision checks across those distinct states. User-facing **Shopkeeper** is the successor name for the historically documented **Shopping Mode**; existing code, ADRs, migrations, and evidence may retain the historical name where renaming would obscure chronology.

## Experience principles

- Lead with the collector's library, not a marketing hero or CYOA-specific application shell.
- Adapt navigation, density, and primary actions to intent and device class; mobile is not compressed desktop.
- Keep view access, visual-test access, authentication, and write authority visibly separate.
- Use collection identity, covers, shelves, progress, and concise numbers to make the working application as intentional as the editorial surface.
- Preserve accessible alternatives, reduced motion, readable states, and server authority beneath every visual treatment.
- Treat percentages and KPIs as presentation summaries, never validation evidence.

## Product identity and information architecture

The product identity is **My Library**. The primary hierarchy is:

1. **Library** — default home and full personal catalog.
2. **Collections** — collection discovery and collection-specific Gallery, List, and Bookshelf views.
3. **Shopkeeper** — focused acquisition companion.
4. **Owner area** — administration, exports, settings, test controls, and additional tools.

CYOA and Redwall are collections, not separate libraries or permanent primary-navigation destinations. A collection can be pinned or favorited for prominence without changing its membership.

The domain and interface must not conflate:

| Concept | Meaning | Current/future boundary |
| --- | --- | --- |
| Library membership | A Book belongs to the owner's overall catalog | Existing core concept |
| Collection membership | A Book participates in a collector-defined or published collection | Existing bounded collection behavior; future many-to-many needs verification/design |
| Published series/order | Canonical or collection-specific sequence and numbering | Existing series-position behavior; alternates need explicit treatment |
| Genre | Bibliographic/category classification | Future relationship design |
| Personal tags | Owner-defined flexible labels | Future persistence; see [Tags](TAGS.md) |
| Pinned/favorite collection | Presentation prominence | Future preference; must not mutate membership |
| Shopkeeper session scope | Temporary matching and recommendation focus | Future session state; independent of membership |

Books may eventually belong to multiple collections, genres, and tags. No visual treatment may imply those relationships are implemented before their data contracts exist.

## Responsive shell, header, and footer

### Desktop

Use a stable header:

- Left: a small identity mark and **My Library**.
- Primary navigation: **Library**, **Collections**, **Shopkeeper**.
- Right: global search, light/dark theme control, and owner/profile menu.
- Owner menu: administration, test controls, exports, settings, and other privileged tools.

Help and About leave permanent primary navigation. A contextual row below the header communicates location, mode, scope, and safety state, for example:

- `Shopkeeper · Shopping for CYOA · Read-only`
- `Collections / CYOA / Bookshelf`
- `Read-only testing · New admin view`

### Mobile

Use a compact header showing the current page or collection plus one or two contextual actions. Use persistent bottom navigation for **Library**, **Collections**, **Shopkeeper**, and **More**. Shopkeeper may receive stronger visual emphasis as the mobile field tool. Important navigation must never depend on the footer.

### Footer

Remove language describing “three separate libraries.” Use a minimal My Library identity, Help/About, appropriate privacy/data information, and an owner-visible version/build reference. The footer is supporting information, not the mobile navigation system.

## Modes, access, and safety state

Keep three independent axes visible and enforceable:

1. **View mode:** Public, Tester, or Administrator presentation.
2. **Global write state:** Locked or Unlocked.
3. **Temporary test access:** permission to view one unreleased visual variant.

An admin-looking view does not grant mutation authority. Public views never allow adding, editing, or deleting Library data; those controls belong to the authenticated owner. Public and administrative layouts may be evaluated while writes remain locked. Show a compact persistent state such as `Read-only testing · New admin view`, with expanded explanation available without dominating content.

### Global write lock

The future write lock is server-enforced. Client-side disabling and read-only labels provide clarity but are never authoritative. When locked, reading, browsing, searching, filtering, exporting already-authorized read-only views, and visual testing may continue. Every mutation must be rejected at the server boundary.

The mutation inventory to verify includes at minimum:

- Book add, edit, delete, ownership, copy-count, and status changes.
- Collection create/edit/delete, membership, order, pin/favorite, and target-price changes.
- Purchase and Business creation/edit/delete and purchase recording.
- Import, restore, bulk action, merge, reconciliation, and staged-change application.
- Cover upload, replacement, deletion, metadata changes, and other R2/object mutations.
- Tag/genre assignment and future relationship mutations.
- Theme or personalization writes where stored server-side.
- Test-code creation/revocation and variant administration.
- Schema activation, migrations, repair, maintenance, and other administrative writes.
- Any API, route action, background job, alternate method, or legacy endpoint capable of the same mutations.

The global lock is a conditional visual-testing safeguard, especially for administration or other owner-mode flows; it is not a routine reason to shut down normal production writes. Sei must establish and verify the lock before publishing an authorized testing build. That build remains locked across restarts with no timeout or automatic unlock. Removing the lock requires the next separately controlled publication after testing; access to one build must not silently change another. Only the authenticated owner can authorize an unlocked build. Validation must enumerate all mutation endpoints/actions, prove locked rejection for owner and non-owner paths, prove reads remain available, check direct HTTP and alternate-method bypasses, verify lock visibility across responsive modes, and confirm restart/concurrency behavior appropriate to the storage design. The lock cannot be a client flag, hidden control, process-local assumption, or route-specific exception list with unknown coverage. Sei may determine which owner controls are clearer as visible-disabled versus hidden, subject to accessible state communication and no server bypass.

### Temporary visual-testing access

Owner-generated temporary codes may expose one unreleased presentation variant, such as a new public Library view, administration view, mobile navigation experiment, or Shopkeeper experiment. They do not replace permanent owner authentication and grant no write authority by default.

Required properties:

- Server-side validation and hashed code storage.
- A 24-hour expiration window, immediate revocation, rate-limited attempts without a hard total-attempt lockout, and variant-specific scope.
- Owner-visible active-code inventory without recoverable plaintext codes after creation.
- No secrets embedded in client bundles, URLs, logs, or documentation.
- Explicit association with view mode and locked/unlocked state.
- Documented disablement, data-retention, and removal path after testing.
- Tests for expired, revoked, wrong-variant, replay/rate-limit, malformed, and privilege-escalation attempts.

The current testers are agents, not invited external people. Before an authorized testing round, Sei hands the generated code to the Product Owner through the approved private channel; the Product Owner controls distribution to the testing agent. Creating or handing off a code does not authorize publication or writes. External-user privacy/onboarding policy is deferred until external testing is actually proposed.

## Application modes

Library, Collection/Bookshelf, Shopkeeper, and Administration share semantic tokens and recognizable identity while adapting information density, controls, and navigation to their jobs.

### Library home

Lead with the personal library. Reduce space before useful content and replace generic promotion with concise collector language. Preferred content includes pinned collections, overall progress, recently added books, missing priorities, purchase activity when useful, covers, shelf cues, and concise KPIs. Empty and partial states must remain useful without fabricated completeness.

### Collections and the standing bookcase

Treat each selected collection as one complete standing bookcase. For CYOA:

- Fill rows left to right and continue vertically down the page.
- Keep missing numbered titles visible as gaps or placeholder spines without creating synthetic Books.
- Preserve stable, meaningful collection order.
- Prevent alternate numbering from silently displacing canonical positions.
- Let vertical page scrolling traverse the continuing bookcase, including on mobile.
- Keep collection identity and relevant controls available.
- Open spine details in an accessible dialog or mobile bottom sheet.
- Provide explicit collection controls; gestures may supplement but never replace them.

Changing collections replaces the whole bookcase. A restrained slide or rotation can reinforce the transition. Gallery and List remain efficient alternatives. Horizontal shelf carousels are reserved for small subsets such as recently added, next missing, wishlist, upgrade candidates, or compact collection previews—not a 184-book CYOA row.

### Shopkeeper

Shopkeeper is a fast acquisition companion, primarily mobile. The core mobile sequence is:

1. Enter Shopkeeper.
2. Scan an ISBN/barcode, use a photo, or search manually.
3. Receive an immediate **Buy**, **Skip**, or **Upgrade** recommendation.
4. Record the purchase when authorized, or continue to the next Book.

The decision view prioritizes owned/missing/duplicate state, collection and series position, asking price versus collection target, existing copies, edition relevance, condition, personal cover, and one prominent next action. Use large capture controls, a minimal header, thumb-accessible controls, sticky bottom action area, concise summaries, and fast “next item” movement. Deterministic evidence and uncertainty remain visible; the visual label must not overstate match or edition confidence.

Desktop may use a broader workspace with scan/search, current decision/detail, recent scans or comparison queue, purchase and Business context, and keyboard-friendly entry.

A session may focus on CYOA, Redwall, the whole Library, or a future multi-collection trip. Launching from CYOA scopes matching, owned/missing state, issue order, alternate numbering, edition relevance, and target price to CYOA. Global launch searches the Library, suggests known collection relationships, and permits general intake where no relationship is known. Library membership, collection assignment, and session focus remain independent.

Recommendation rules have global defaults, with collection-specific rules taking priority. Missing-book recommendations consider the applicable ideal/target cost and the collection's trended average spend per Book. A duplicate scan compares available cover, edition/condition evidence, and notes to determine whether a meaningful upgrade is indicated. `Buy`, `Skip`, and `Upgrade` remain deterministic summaries of the underlying evidence; uncertain or missing evidence must be shown and must not be overstated. Sei must reconcile the exact existing rules and supported inputs before estimating or proposing thresholds.

## Themes and personalization

Initial themes are the existing warm light direction and a purpose-designed dark theme that feels like the same library under different lighting. Support system preference and saved user choice. For the current single-user product, use the simplest supported editable JSON-backed or equivalent preference store that can change without republishing. A database preference table is a later option if multi-user support justifies it. Define semantic tokens for navigation, shelves, books, cards, inputs, charts, status indicators, dialogs, administration, and Shopkeeper, including focus, disabled, locked, warning, success, and destructive states.

Custom palettes are later work. Advanced personalization inspired by early personal websites may eventually expose controlled color, typography, backgrounds, imagery, and possibly sanitized custom CSS. Arbitrary raw HTML or JavaScript is excluded.

## Copy and visual summaries

Review hero copy, headings, collection summaries, helper text, empty states, missing-cover states, repetitive Book cards, and KPI presentation. Prefer short text, clear hierarchy, useful counts, covers, shelf cues, status icons, and distinct Shopkeeper decisions. Accessibility names must retain meaning where visible copy is intentionally terse.

KPI percentages are coarse presentation summaries only. Operational briefs, tests, production gates, and [Current State](CURRENT_STATE.md) remain authoritative.

## Motion and ambient effects

Motion establishes atmosphere, confirms actions, or directs attention; it must not keep the whole screen moving. Candidate effects include sparse dust/snow/stars, subtle spine depth, a restrained pulse on a searched gap, Books settling after view changes, Shopkeeper card transitions, collection-bookcase transitions, and future terminal cursor/flicker.

All motion must respect reduced-motion preference, provide an **Ambient Effects** preference, automatically reduce decorative load on mobile, avoid animating every spine in a large collection, and preserve performance, input responsiveness, readability, and focus stability.

## Future-only personality layers

### Catalog Terminal Easter egg

A future optional owner presentation may evoke DOS terminals and early web-computer interfaces without copying protected characters, names, art, sounds, or assets. Read-only commands might include `STATUS`, `COLLECTIONS`, `MISSING CYOA`, `RECENT`, and `HELP`; supported controlled operations might expose `LOCK`, `EXPORT`, `TESTCODES`, or `THEME DARK`.

It is only a presentation over supported application operations. Normal accessible administration remains available; there is no arbitrary OS, SQL, or database execution; existing authorization, confirmation, write lock, and owner authentication remain authoritative; mobile offers usable command suggestions. Harmless personality responses are allowed. This is not current priority or implementation scope.

### Shopkeeper Buddy

A low-priority optional, dismissible, primarily mobile personality layer may react to existing deterministic outcomes such as missing, duplicate, below-target, upgrade, uncertain match, or read-only state. It requires no separate AI service, never replaces the recommendation, and always supplies accessible text. It begins only after matching and purchase workflows are stable.

## Current release versus later enhancement

| Layer | Direction |
| --- | --- |
| Current release planning | Phases A–G below may be estimated; each requires later scope and authority. Preserve Version 20 and all existing gates meanwhile. |
| Optional polish after stable foundations | Phase H ambient animation, controlled by performance/accessibility requirements. |
| Future only | Catalog Terminal, advanced personalization/custom palettes, and Shopkeeper Buddy. |
| Separate persistence/product work | Many-to-many collections, genres, tags, saved preferences where not already supported, multi-collection trips, and relationship editing. |

## Dependencies and collision boundaries

- **Version 20 cumulative candidate:** shared application page, global styles, schema, API, authentication/runtime, Shopping, Bookshelf, and ordered migration surfaces require exact pre-estimate and pre-implementation composition checks.
- **Collection relationships:** Product Owner expects the current collection model to be sufficient for the initial direction, but Sei must verify that assumption. Current collection/series behavior is not blanket authority for new many-to-many membership, genres, pins, or session-scope persistence if inspection shows missing capability.
- **Tags:** remain future schema and interaction work; visual filters may not imply persistence.
- **Authentication:** Public/Tester/Administrator presentation, owner authorization, temporary codes, and write state need separate server models.
- **Write enforcement:** requires complete server mutation inventory and likely shared enforcement below individual UI actions.
- **Responsive behavior:** shell, bottom navigation, dialogs/bottom sheets, scan/photo capture, sticky actions, large bookcases, keyboard, touch, and viewport changes require explicit coverage.
- **Themes/preferences:** semantic tokens can precede persistence. Prefer a simple editable JSON-backed/equivalent single-user store without republishing; defer a database table until multi-user needs justify it.
- **Migration/release gates:** visual design authority does not authorize schema work, saving, previewing, deploying, publishing, or production validation.

## Estimable implementation phases

The ranges below are Sei's accepted source-informed **low / likely / high Engineer effort points** from the Version 20 source at commit `6a2191b1b506d171d576cbb6a6b160964595c051`. They are not session-usage forecasts, commitments, implementation briefs, or execution authority. Each later phase still requires a fresh brief, usage reading, collision check, and clean-stop plan.

| Order | Phase | Scope and safe stop | Dependencies / collisions | Data and security | Responsive validation | Independence | Engineer range |
| ---: | --- | --- | --- | --- | --- | --- | ---: |
| 1 | **A — IA and responsive shell** | My Library naming, Library-first routing, desktop/mobile header, bottom navigation, contextual row, footer. Stop with routes and shell usable behind current data/actions. | Existing root page, global styles, navigation, Bookshelf/Shopping entry points, Version 20 composition. | Prefer no schema; preserve auth boundaries and do not expose owner tools. | Desktop widths, small/large mobile, keyboard, focus/order, orientation, safe areas. | Foundation for E–G; can precede B–D if current actions remain unchanged. | 6 / 8 / 11 |
| 2 | **B — Global write lock** | Server lock model, shared enforcement, state treatment, exhaustive mutation tests. Stop with an authorized testing build locked across restarts and verified reads/no bypass. | Complete mutation inventory, auth helper, APIs/actions, migrations/admin, background paths. | Conditional test-build safeguard; highest security risk; no client-only design. Removal occurs only through a later controlled publication. | Visible/understandable in every mode; Sei selects visible-disabled versus hidden controls; direct-request tests required. | Technically separable but required before meaningful admin visual testing. | 9 / 13 / 18 |
| 3 | **C — Temporary visual-test access** | Variant-scoped 24-hour codes, hashed storage, revocation, rate limiting without hard attempt cap, inventory/removal, private handoff to Product Owner. Stop with one harmless agent-only read-only variant end to end. | B lock semantics, auth/session/routing, deployment/platform capability. | Secret-like records likely require supported storage; threat model and log hygiene required. No external testers now. | Code entry, errors, expiry, revocation, variant state on mobile/desktop. | Feasibility must precede implementation; park if Sites lacks a private runnable variant or durable state. | 11 / 16 / 22 |
| 4 | **D — Theme foundation** | Semantic warm-light/dark tokens, system preference, user choice, all current components. Stop when both themes pass contrast and regression review without redesigning every page. | Global CSS/current colors, charts, dialogs, admin and Shopkeeper states. | Use simplest supported editable single-user JSON/equivalent preference storage; database table deferred for multi-user. Avoid security state encoded only by color. | System changes, persistence, flash prevention, contrast, forced colors, mobile OLED/readability. | Split static tokens/themes from saved preference if storage remains unsupported. | 6 / 9 / 13 |
| 5 | **E — Library home and copy** | Personal-library home, pinned/favorite presentation, concise summaries, recent/missing/purchase modules, empty/copy/card cleanup. Stop with existing-data modules only. | A shell, current queries, covers, collection progress definitions; pinned collections are absent. | Existing-data modules are read-only; persisted pins require a later contract and B enforcement. | Loading/empty/error, narrow cards, touch targets, screen-reader summary order. | Can use existing data independently; omit unsupported pins/relationships. | 6 / 9 / 13 |
| 6 | **F — Standing collection bookcase** | Complete vertical CYOA bookcase, stable gaps/order, explicit collection controls, bottom-sheet detail, Gallery/List alternatives; retain generic architecture for later collections. Stop with CYOA and regression-safe alternate views. | Existing M4 page/styles/tests, canonical/alternate numbering, large-list performance, A/D. | Verified current singular model is sufficient only for CYOA; no synthetic Books or unapproved relationship schema. | 184-item mobile scroll, keyboard/focus, virtualization if needed, resize/return context, reduced motion. | Builds on M4; split extraction/performance baseline from presentation. | 8 / 12 / 17 |
| 7 | **G — Responsive Shopkeeper** | Rename/presentation transition, deterministic mobile Buy/Skip/Upgrade decision, capture/search, sticky action, next-item flow, desktop workspace, collection session scope. Stop with verified CYOA/global defaults and current mutation semantics. | Existing Shopping/M3/scanner/APIs/styles, target and trended-average cost, duplicate cover/edition/condition/notes evidence, A/B/D. | Recommendation engine, rule overrides, confidence explanation, and session scope are absent; all writes honor B. | Camera/photo/manual fallbacks, thumb reach, keyboard desktop, rapid repeat, errors, locked/uncertain states. | Split read-only engine/evidence contract, responsive UI, then purchase integration. | 12 / 18 / 25 |
| 8 | **H — Ambient effects** | Tokenized sparse effects and purposeful transitions with preference and reduced-motion fallback. Stop with effects globally disableable and performance budget passing. | Stable A/D/E–G surfaces; avoid collision with bookcase rendering. | Preference only; no tracking or external assets. | Reduced motion, mobile auto-reduction, battery/performance, focus/readability. | Optional polish and first phase to park. | 4 / 6 / 9 |

The simple sum is **62 / 91 / 128** points. Sei estimates approximately **56 / 82 / 115** after ordered shared-foundation reuse; this is not a commitment. Recommended order is A → B → D → E → F → G → H, with C after B but independently parked until storage, routing, and private test-access feasibility are proven. G should be split into read-only recommendation/evidence, responsive decision UI, and purchase integration. Each phase requires its own recorded authority; the checkpoint below records the later bounded A/D authorization and result.

### Local implementation checkpoint — 2026-08-20

- **A — complete locally:** My Library identity and responsive shell are implemented and preserved in application checkpoint `608553f`. Targeted suites and the complete current-source serial suite pass; Site save, preview, publication, and live validation remain absent.
- **Static D foundation — complete locally:** semantic conversion, warm/dark/system presentation, session-only manual control, focus treatment, route-family styling, desktop/mobile viewport checks, overflow checks, and sampled contrast are complete at `608553f`.
- **Confirmed validation remediation — saved / release identity ambiguous:** checkpoint `80e4c61` remains retired as historical evidence. Replacement checkpoint `f15ea81` implements the five bounded corrections and is saved as Version 21 with all release gates passed. The sole publication invocation returned no deployment identity. Public fingerprinting matched mobile Shopping navigation but retained the legacy bookshelf UI, so four candidate markers mismatched. Exact identity, republish, and hands-on validation remain gated. See the [Version 20 remediation plan](VERSION20_CONFIRMED_FAILURE_REMEDIATION_PLAN.md).
- **D limits:** Admin/catalog visual navigation was blocked by unavailable local sign-in; forced-colors and reduced-motion emulation were unavailable; saved preference persistence remains a later separately gated slice.
- This checkpoint does not activate B/C/E/F/G/H or authorize preference persistence, Site operations, or production work.

### Accepted source findings

- Many-to-many collection membership, pinned collections, saved theme preferences, durable global operational state, secure variant routing, and rate-limited hashed temporary-code infrastructure are all absent in Version 20.
- The current singular collection model is sufficient for the initial CYOA bookcase, not future many-to-many membership.
- B spans 11 current mutation handlers and requires centralized durable enforcement.
- C is a new security/runtime subsystem; prior platform evidence found no runnable unpublished preview, so feasibility comes before code.
- G is larger than the Designer range because the requested deterministic recommendation engine and session/rule model do not exist.
- Theme tokens can proceed without persistence; current browser `localStorage` is not the requested editable cross-device preference store.

## Resolved Product Owner direction

- Public views are read-only; only the authenticated owner receives Library mutation controls.
- The server lock is conditional for testing administration/owner-mode visuals. It persists across restarts until a later controlled publication removes it; there is no timeout or routine production lock.
- Agent-only visual-test codes expire after 24 hours, are rate-limited without a hard attempt cap, and are handed privately by Sei to the Product Owner before the testing round.
- Single-user preferences use the simplest supported editable JSON-backed/equivalent store that avoids republishing; a database table is reserved for future multi-user needs.
- Shopkeeper uses global deterministic rules with collection overrides. Target/ideal and trended average collection spend inform missing-book recommendations; duplicate upgrade evaluation uses cover, edition/condition evidence, and notes.
- Phase F focuses on CYOA while retaining a generic later-collection architecture.
- The current collection model is presumed sufficient but must be verified by Sei; missing capability does not authorize schema reconstruction.
- Sei selects visible-disabled versus hidden locked owner controls while retaining accessible state and server enforcement.
- Testers are agents only. External tester privacy/onboarding is not current scope.

No Product Owner decision from this design-question set remains open. Source inspection may still produce new technical questions before an implementation phase can be scoped.

## Estimation completion and transport correction

Sei completed the read-only source-informed estimate on 2026-08-17 without modifying source, tests, dependencies, schema, Site state, production, or data. Designer accepted the sanitized evidence and incorporated it above.

The request had been embedded here rather than delivered through `briefs/`. That was a transport error: repository planning text describes authority but does not assign Engineer work. Acceptance of this safe read-only report does not create retroactive authority or precedent. Every future Engineer estimate, feasibility check, or source inspection requires a prior explicit [`ESTIMATION_BRIEF.md`](../templates/ESTIMATION_BRIEF.md) artifact in transport; implementation phases require separate implementation briefs and later authorization.
