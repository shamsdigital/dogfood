# Stellan Eoin Builders — Implementation Guide for Claude Code (Joomla via Chrome)

**Who this is for:** an AI agent (Claude Code with the Chrome browsing plugin) executing the build inside the Joomla administrator, plus the human who owns the login. This file tells the agent exactly what to do, in what order, using the other files as source material. Do not improvise page copy or facts; everything needed is in files 01–06 and the two root files.

## The file set (read these first, in this order)
1. `01_Master_Strategy_and_Architecture.md` — the plan, architecture, 301 map, keyword mapping, technical checklist. **Read fully before touching Joomla.**
2. `02_Core_Page_Copy.md` — copy for About, Team, Contact, RightStart, Service Areas hub, the 4 city pages, Projects hub, the GATED Renovations page, and the reusable SSR section pattern.
3. `04_Remaining_Page_Copy.md` — copy for the 6 commercial sub-vertical pages and the 6 project case studies.
4. `03_Schema_JSON-LD_Pack.md` — sitewide graph (Block A) + per-page schema for the core pages.
5. `05_Additional_Schema_JSON-LD.md` — per-page schema for the sub-vertical pages and case studies.
6. `06_Meta_Tags_Master.md` — the `<title>` and meta description for every page.
7. `robots.txt` and `llms.txt` — deploy at the web root.

## Hard rules the agent must never break
- **Facts are fixed.** Use only the facts in these files. Never invent dates, dollar figures, square footage, client names, review counts, ratings, financing terms, or awards. The only numbers allowed are the ones already written: BC 73150, MCN151894, (615) 212-9005, 1993, 2018, 34 building categories, ~$350/sqft (Custom Homes page only), 120-plus-foot patio (Bedford only), 20-plus jurisdictions.
- **No em dashes** in any published body copy. Plain sentences.
- **NAP is one string, everywhere:** `Stellan Eoin Builders, LLC · 11 Willow Street, Ste. 11, Nashville, TN 37210 · (615) 212-9005 · quotes@stellaneoin.com`. The "Office 109 inside Suite 11" wayfinding line appears only in visible Contact-page copy, never in schema, meta, or the footer NAP.
- **Do not rewrite the client's three pages** (Home, Custom Homes, Commercial). You may set their `<title>`, meta description, canonical, and inject their schema (Blocks A/B/C). You may not alter their body copy.
- **Three gated pages/decisions are blocked until the human confirms** (see the Gate below). Do not publish them on your own initiative.
- **Keep the Joomla auto-schema plugin paused.** All schema here is hand-built. If it is running, it will double-generate and conflict; leave it off.
- **When a required fact or credential is missing** (for example a real GBP link for `sameAs`, or business hours), leave the clearly-marked placeholder and add a line to the human handoff list rather than guessing.

## GATE — confirm with the human before publishing these
Do not publish, and instead surface a one-line question for each:
1. **Renovations pillar** (`/renovations`, copy in file 02). Publish only if John confirms he still offers remodel/renovation/addition work. If no, skip the page and 301 the old renovation URLs to `/custom-homes`.
2. **Financing.** Absent from all copy by design. Do not add it anywhere unless John confirms terms.
3. **Canonical address / GBP verification.** The plan uses one Nashville NAP in schema. Before finalizing, confirm which address the Google Business Profile is verified at. If it is verified in Clarksville, pause and flag it, because that changes which address is canonical (see file 01 §0.3 and the GBP guidance).

---

## Joomla one-time setup (do before building pages)
1. **System → Global Configuration → Site:** set Search Engine Friendly URLs = Yes, URL Rewriting = Yes, Adds Suffix to URL = No. Confirm `.htaccess` exists (rename `htaccess.txt` to `.htaccess` if needed).
2. **Force one host + protocol:** in `.htaccess`, 301 all traffic to a single canonical host (pick https + www **or** https + non-www) and strip `/index.php/`. Match every canonical URL in file 06 to that choice.
3. **Global metadata:** set a sensible default, but every page will override title + description per file 06. Turn off any setting that auto-appends the site name twice.
4. **Confirm the schema plugin is disabled** (Extensions → Plugins → search "schema" / "structured data").
5. **Caching:** enable Gzip and page cache (Global Config → System) and the System Cache plugin.
6. **Create a "JSON-LD" Custom HTML module** you can assign per-menu-item, OR confirm articles allow raw `<script>` (some editors strip it — if so, use a Custom HTML module assigned to the specific menu item, which is the reliable path in Joomla).

## Sitewide elements (build once, show on every page)
- **Inject Block A** (Organization + WebSite graph from file 03) into the template, before `</head>` or at end of `<body>`, so it renders site-wide. Fill the four `sameAs` URLs with the real GBP, Houzz, Facebook, and LinkedIn links (ask the human for any that are missing; leave the rest out rather than using the `REPLACE` placeholder live).
- **Footer** (template, site-wide): real-text NAP block exactly as the canonical string, both license numbers, and internal-link columns to the two pillars, all four city pages, RightStart, Projects, About, Team, Contact. Use the footer markup in the SSR pattern at the end of file 02. This gives every page a site-wide internal link, which is what gets the new pages indexed.
- **Primary nav** (template): Home · Custom Homes · Commercial · RightStart · Service Areas ▾ · Projects · About ▾ · a persistent `tel:+16152129005` call button. Under Commercial, add a dropdown to the six sub-vertical pages. Under Service Areas, the four cities + "All service areas". Under About, Team + Contact.

---

## Per-page build loop (repeat for every page)
For each page, in the order given by the build sequence below:

1. **Create the Joomla article** with the exact clean URL slug (file 06 column 2). Set the menu item / alias so the SEF URL matches the canonical exactly.
2. **Paste the body copy** from file 02 or 04. Convert the markdown to the SSR HTML pattern (file 02 end): one `<h1>`, `<section>` blocks with `<h2>`/`<h3>`, real breadcrumb `<nav>`, real FAQ Q/A text. Resolve the `[→ Page]` link markers into real `<a href>` internal links using the canonical URLs. Body text and FAQ text must be in the server-rendered HTML, not injected by JS.
3. **Set the title + meta description** from file 06 (Menu Item → Page Display → Browser Page Title; Metadata tab → Meta Description).
4. **Set the self-referencing canonical** to the page's clean URL.
5. **Inject the page schema** (file 03 for core pages, file 05 for sub-verticals/case studies) via the assigned Custom HTML module or article, matching the page's `@id`s to its real URL and host. The FAQ text in the schema must match the visible FAQ text character-for-character.
6. **Images:** use real project photos where the copy references them (the old site's images and alt text are the starting point — tighten alt to be descriptive and geo-aware). Serve WebP, set explicit width/height, `loading="lazy"` below the fold.
7. **Verify in the browser:** View Source (not Inspect) and confirm the H1, body copy, FAQ text, and JSON-LD are all present in the raw HTML. Then run the URL through Google's Rich Results Test.

## Build sequence (dependency order)
**Phase 1 — foundation**
1. Template: inject Block A, build footer NAP + nav.
2. Set title/description/canonical + schema (Blocks B/C) on the three client pillar pages. Do not touch their body.
3. Build About, Team (with 3 Person nodes, Block E), Contact (Block F). Purge "since 2004 / 20+ years / design-build / sustainability" anywhere it appears site-wide.
4. Deploy `robots.txt`, `llms.txt`, and a fresh `sitemap.xml` at the web root. Implement the 301 map (file 01 §3): all `/plans/*` → `/custom-homes`, `/services/*` → the matching pillar/RightStart, `/leadership*` → `/team`, `/gallery` → `/projects`. Delete the thin `/plans/*` articles.

**Phase 2 — differentiator + local**
5. Build `/rightstart` (Block G).
6. Build `/service-areas` hub + the four city pages Nashville/Clarksville/Murfreesboro/Franklin (Block D template per city).

**Phase 3 — commercial depth + proof**
7. Build the six commercial sub-vertical pages under `/commercial-construction/` (file 04 Part A; file 05 Template 1). Add them to the Commercial nav dropdown and link them from the Commercial pillar page body.
8. Build `/projects` hub + the six case studies (file 04 Part B; file 05 Template 2).

**Phase 4 — gated + QA**
9. Only after the human confirms: publish `/renovations` (Gate item 1).
10. Full QA pass (below).

---

## Internal-linking pass (after pages exist)
Wire these so every page strengthens a pillar (full map in file 01 §9). Minimum:
- Commercial pillar → links down to all six sub-vertical pages.
- Each sub-vertical → back up to Commercial pillar + its matching case study (Restaurants↔Moringa Tree/Rome Records; Retail↔5.11/Rome Records; Hospitality↔Bedford; Adaptive Reuse↔Moringa Tree/Bedford; Historic↔Bedford; Tenant Improvements↔5.11).
- Each case study → its matching service page + Contact.
- Each city page → both pillars, RightStart, 2–3 sibling cities, Contact.
- Projects hub → all six case studies.

## Final QA checklist (do not call the job done until all pass)
- [ ] Every page renders its copy + JSON-LD in **View Source** (server-side), not just in Inspect.
- [ ] One `<h1>` per page; heading order is clean (no skipped levels).
- [ ] Every page has a unique title + description matching file 06, and a self-referencing canonical.
- [ ] All JSON-LD validates in Rich Results Test with zero errors; FAQ schema text matches visible text.
- [ ] No em dashes in any published body copy; no "since 2004 / 20+ years" anywhere; NAP identical on every page and in schema.
- [ ] No fabricated `aggregateRating`/`review` live. (Add only from real GBP data later.)
- [ ] 301 map implemented; visiting an old `/plans/*` or `/services/*` URL lands on the right new page with a 301, not a 404.
- [ ] `robots.txt`, `llms.txt`, `sitemap.xml` reachable at the root; sitemap submitted in Search Console; noindex pages excluded.
- [ ] Nav + footer link every new page; every location and sub-vertical page has at least one site-wide internal link.
- [ ] Gated pages (Renovations) NOT published unless confirmed; financing absent; GBP address question surfaced.

## Handoff list to leave for the human (fill as you go)
- Real `sameAs` URLs still needed: GBP share link, Houzz, Facebook, LinkedIn.
- Business hours for `openingHoursSpecification` (not yet in schema).
- Confirmation on the three Gate items.
- Real Google rating + review count, once available, to wire `aggregateRating`.
- Any project city that needs correcting (e.g., confirm Rome Records / 5.11 locations before setting `locationCreated`).

*End of implementation guide.*
