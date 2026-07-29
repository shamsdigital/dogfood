# Stellan Eoin Builders — Local SEO / GEO / AEO Master Strategy & Architecture

**Prepared for:** the Stellan Eoin restructure (Joomla, section-based SSR build)
**Source of truth for all facts:** *Site Copy v3* (John's 07-26 feedback letter). Nothing in this plan invents history, awards, services, or numbers. Where the old site or old research conflicts with v3, **v3 wins.**
**Keyword signal:** *Keyword Stats 2026-07-13* (Google Keyword Planner export, 1,566 keywords).

> **How to read this pack**
> 1. `01_Master_Strategy_and_Architecture.md` — this file (the plan: what to build and why).
> 2. `02_Core_Page_Copy.md` — ready-to-paste copy for the pages the client did **not** already write.
> 3. `03_Schema_JSON-LD_Pack.md` — copy-paste JSON-LD for every page, with a consistent entity graph.
> 4. `robots.txt` — deploy at site root.
> 5. `llms.txt` — deploy at site root (the GEO/AEO file).

---

## 0. Three decisions to lock before publishing (flagged, not assumed)

These are the only places where old-site material and v3 disagree. I have **not** guessed — each is written so you can confirm with John in one message.

1. **Renovations / remodeling as a service line.** The old site sold renovations, additions, decks, ADA/age-in-place, fire rebuilds, barns, and cabins. v3 narrowed the public offering to **two pillars: Custom Homes and Commercial.** But the keyword data shows real, high-intent remodeling demand (`home remodeling nashville`, `nashville home renovations`, `home addition contractors` all at ~500/mo), and the review corpus is full of renovation, addition, and fire-rebuild jobs. **Decision needed:** does John still take renovation/remodel work? If yes, we add one `/renovations` pillar (draft copy is included in file 02, marked GATED). If no, we drop it cleanly and 301 the old service URLs into Custom Homes. **Do not publish the renovations page until this is confirmed.**
2. **Financing.** The old homepage advertised project financing up to $250,000. v3 does not mention it. **Decision needed:** keep, drop, or reword. Until confirmed, it appears nowhere in the new copy or schema.
3. **Clarksville as "headquarters."** v3 states the official HQ is in Clarksville, but the structured NAP on every page and in all citations is the **Nashville** address (`11 Willow Street, Ste. 11, Nashville, TN 37210`). That is correct for citation consistency and is how this plan treats it: **one LocalBusiness entity, one address (Nashville), Clarksville referenced only as narrative HQ, never as a second schema address.** If John wants a verified Clarksville GBP location later, that is a separate multi-location project with its own NAP — not part of this launch.

---

## 1. Business Analysis

**Entity:** Stellan Eoin Builders, LLC — a licensed Tennessee **general contractor** (not a design-build firm, does not self-perform).

**Verifiable facts (the assets AI and Google can cite):**
- Tennessee contractor license **BC 73150** — the state's broadest building classification: residential, commercial, and industrial across 34 building categories.
- Metro Nashville / Davidson County Master Contractor **MCN151894**.
- **Building since 1993** (founder's hands-on experience); firm **established 2018**.
- Award: **2024 Kitchen of the Year, Nashville Design Collective**.
- Founder **John Hochstetler** — grew up Amish, learned the trades hands-on (framing, roofing, finish carpentry) before ever managing a project. This is the core, un-fakeable differentiator.
- Insurance: general liability and workers' compensation, certificates on request (no carriers or limits published).
- **RightStart** — proprietary preconstruction process (site evaluation, feasibility, scope, budget, schedule, in writing before ground breaks).
- Tiered warranty by system and component (no durations published).
- Custom-home market reference: **~$350/sqft** — allowed on the Custom Homes page **only**.

**NAP (must match character-for-character everywhere — schema, GBP, citations, llms.txt):**
`Stellan Eoin Builders, LLC · 11 Willow Street, Ste. 11, Nashville, TN 37210 · (615) 212-9005 · quotes@stellaneoin.com`
(The "Office 109 inside Suite 11" wayfinding line lives on the Contact page in visible copy only — never in schema, GBP, or citations.)

**Two service pillars:**
- **Custom Homes** — land/site evaluation before purchase, RightStart, design-partner coordination, construction, walkthrough + tiered warranty.
- **Commercial** — hospitality, restaurants, retail, assembly & event spaces, adaptive reuse, historic preservation, tenant improvements.

**Real portfolio (usable proof — all from the existing site):**
- *The Bedford* (Nashville) — historic restaurant reimagined as an event venue; preserved arched brickwork and exposed structure; 120+ ft covered patio; integrated lighting/sound. (Adaptive reuse + historic + assembly.)
- *Rome Records & Café* — café + vinyl retail + live-music hybrid; acoustic solutions, custom casework, flexible layout. (Hospitality/retail/assembly.)
- *The Moringa Tree* — residential structure converted to a health-focused café with retail. (Adaptive reuse + restaurant.)
- *5.11 Tactical* — fast-track retail franchise buildout with national builder Action RCS; code compliance and inspections under tight deadlines. (Retail/tenant improvement.)
- *Dickson, TN custom home* — transitional forever-home; open-concept, vaulted ceilings, stone fireplace.
- *Multi-family renovation (Gallatin)* — full interior/exterior overhaul (client Kim Robertson).
- *Accessible / age-in-place* residential work.

**Leadership (entities for E-E-A-T + Person schema):** John Hochstetler (Founder/CEO), Josh Hendrick (COO), Aric Catlett (Project Technical Director).

**Conversion goals (in priority order):** phone call → quote request form → email. Primary CTA everywhere: **call (615) 212-9005** / **request a quote**.

**Existing strengths:** strong review sentiment (integrity, communication, craftsmanship, "RightStart"); genuine hands-on founder story; real, photogenic commercial case studies; the broadest TN license class.

**Existing weaknesses (what this restructure fixes):** thin doorway pages (`/plans/*` are empty); duplicated boilerplate ("The Expensive Lesson" repeated verbatim on 6+ pages); generic, keyword-thin service copy; no dedicated location pages despite clear local demand; outdated facts ("since 2004," "20+ years," design/sustainability claims); no structured entity graph; auto-schema paused with nothing replacing it.

---

## 2. Competitor Insights (what to do about them)

The old research named a long list of luxury builders (Castle Homes, Brentwood Builders, Grove Park, Carbine, etc.). Two corrections from the actual data:

- **The keyword export has essentially zero volume for Brentwood, Green Hills, Belle Meade, Hendersonville, Mount Juliet, Nolensville, Spring Hill, Gallatin, Lebanon, Smyrna.** Building location pages for those markets now would be building doorway pages for demand that this dataset does not show. Hold them.
- **The volume that exists is in Nashville, Clarksville, Murfreesboro, and Franklin** — plus low-competition generic head terms (`general contractors`, `construction companies` at 5,000/mo, Low competition).

**How to out-position, without copying anyone:**
- **Own the "general contractor + city" head terms** the luxury builders ignore (they chase "luxury custom home builder"; you can take `general contractors nashville`, `general contractors clarksville tn`, `general contractors murfreesboro tn` — 500/mo, and the 5,000/mo national-generic terms are Low competition).
- **Differentiate on RightStart + site-evaluation-before-purchase.** No competitor has a branded preconstruction entity. Make it a real page and a schema-described process.
- **Differentiate on the trades-first founder story.** "A GC who did the work before managing it" is verifiable and unique; "built with integrity / award-winning / trusted" is what everyone claims.
- **Differentiate on permitting fluency (20+ jurisdictions).** This maps directly to the multi-city location strategy and to commercial code-path questions AI users ask.
- **Win commercial niches with near-zero competition:** restaurant/assembly buildouts, adaptive reuse, historic preservation. The case studies already prove it.

---

## 3. Website Architecture (topical clusters)

Flat, shallow, cluster-based. Every page supports a pillar and links back to it.

```
HOME (hub)
│
├── SERVICES (pillars)
│   ├── /custom-homes ......................... [copy exists — v3]
│   ├── /commercial-construction .............. [copy exists — v3]
│   └── /renovations .......................... [GATED — Decision #1]
│
├── RIGHTSTART (differentiator pillar)
│   └── /rightstart
│
├── SERVICE AREAS (local SEO engine)
│   ├── /service-areas (hub)
│   ├── /service-areas/nashville
│   ├── /service-areas/clarksville
│   ├── /service-areas/murfreesboro
│   └── /service-areas/franklin
│
├── PROJECTS (proof cluster)
│   ├── /projects (hub)
│   ├── /projects/commercial/the-bedford-nashville-event-venue
│   ├── /projects/commercial/rome-records-cafe
│   ├── /projects/commercial/the-moringa-tree-restaurant-cafe
│   ├── /projects/commercial/5-11-tactical
│   ├── /projects/residential/dickson-tn-custom-home
│   └── /projects/residential/multifamily-gallatin
│
├── COMPANY (trust / E-E-A-T cluster)
│   ├── /about
│   ├── /team  (John Hochstetler, Josh Hendrick, Aric Catlett)
│   └── /contact
│
├── SUPPORTING / AEO (keep best existing — out of scope to rewrite)
│   ├── /guides/how-much-does-it-cost-to-build-a-home-in-nashville
│   ├── /guides/... (keep the strongest; prune the rest)
│   └── /blog (Builder's Notes)
│
└── UTILITY
    ├── /privacy-policy · /terms-of-use · /sitemap (HTML)
    └── /login · /forgot-password  (noindex)
```

**Deprecate + 301 redirect (kills thin content and consolidates authority):**

| Old URL | Action | New target |
|---|---|---|
| `/services/residential` | 301 | `/custom-homes` |
| `/services/commercial` | 301 | `/commercial-construction` |
| `/services/renovations` | 301 | `/renovations` (if Decision #1 = keep) else `/custom-homes` |
| `/services/project-management` | 301 | `/rightstart` |
| `/services/consulting` | 301 | `/rightstart` |
| `/services/ada-age-in-place` | 301 | `/renovations` (if kept) else `/custom-homes` |
| `/plans/barndominiums`, `/plans/contemporary`, `/plans/cottage`, `/plans/country`, `/plans/craftsman`, `/plans/mid-century-modern`, `/plans/modern-farmhouse`, `/plans/multi-family`, `/plans/new-american`, `/plans/pool-houses-dadus-garages`, `/plans/scandinavian`, `/plans/transitional`, `/plans` | 301 | `/custom-homes` |
| `/leadership`, `/leadership/john-hochstetler`, etc. | 301 | `/team` (+ anchor) |
| `/gallery` | 301 | `/projects` |

Keep `/services` **only** as a lean overview hub that links the pillars (optional — you can also 301 it to the homepage services section). Recommendation: keep it, it captures `construction services nashville` and gives AI a clean services list.

---

## 4. Sitemap (final, launch scope)

Priority reflects crawl importance, not a literal `<priority>` value.

| # | URL | Type | Primary target | Priority |
|---|---|---|---|---|
| 1 | `/` | Home hub | general contractor nashville / brand | ★★★★★ |
| 2 | `/custom-homes` | Service pillar | custom home builders nashville | ★★★★★ |
| 3 | `/commercial-construction` | Service pillar | commercial general contractor nashville | ★★★★★ |
| 4 | `/rightstart` | Differentiator pillar | preconstruction / rightstart | ★★★★ |
| 5 | `/service-areas` | Location hub | middle tennessee general contractor | ★★★★ |
| 6 | `/service-areas/nashville` | Location | general contractors nashville tn | ★★★★ |
| 7 | `/service-areas/clarksville` | Location | general contractors clarksville tn | ★★★★ |
| 8 | `/service-areas/murfreesboro` | Location | general contractors murfreesboro tn | ★★★★ |
| 9 | `/service-areas/franklin` | Location | custom home builders franklin tn | ★★★ |
| 10 | `/projects` | Proof hub | — | ★★★ |
| 11–16 | `/projects/...` (6 case studies) | Proof | niche/adaptive-reuse terms | ★★–★★★ |
| 17 | `/about` | Trust | brand / entity | ★★★ |
| 18 | `/team` | Trust (Person) | John Hochstetler builder | ★★ |
| 19 | `/contact` | Convert | contact / quote nashville | ★★★ |
| 20 | `/services` (optional) | Overview | construction services nashville | ★★ |
| — | `/renovations` | Pillar (GATED) | home remodeling nashville | ★★★★ *(if kept)* |

Utility, legal, guides, and blog stay in the XML sitemap except `noindex` pages.

---

## 5. URL Structure (rules)

- Lowercase, hyphenated, no trailing slash inconsistency (pick one; Joomla default is no trailing slash — keep it).
- Descriptive and short; keyword-bearing where natural. `/service-areas/clarksville`, not `/sa?id=7`.
- Location pages nested under `/service-areas/` for clean breadcrumbs and a topical hub.
- **Joomla-specific:** enable **Search Engine Friendly URLs** + **URL Rewriting** (System → Global Configuration → SEO). Turn **"Adds Suffix to URL"** off. Kill the `Itemid`/`?view=` duplicates with self-referencing canonicals (see §12). Ensure one, and only one, URL resolves per page (no `/index.php/...` duplicate — force removal via `.htaccess`).

---

## 6. Navigation

**Primary nav (server-rendered `<nav>`, plain semantic HTML — no JS-dependent rendering):**

`Home · Custom Homes · Commercial · RightStart · Service Areas ▾ · Projects · About ▾ · [ Call (615) 212-9005 ]`

- **Service Areas ▾** → Nashville, Clarksville, Murfreesboro, Franklin, "All service areas".
- **About ▾** → Our Team, Contact.
- Persistent phone CTA button (tel: link) — highest-converting element for a service business.
- **Footer** (sitewide internal-linking + NAP block): full NAP, both license numbers, the two service pillars, all four location pages, RightStart, Projects, About/Team/Contact, hours, and a Google Maps link. The footer NAP is a ranking and citation signal — render it as real text, not an image.
- **Breadcrumbs** on every non-home page, server-rendered, matched by `BreadcrumbList` schema (§ file 03).

---

## 7. Page Blueprints (the pages you're building)

Full ready-to-paste copy for each of these is in **`02_Core_Page_Copy.md`**. This section is the spec each page must hit. The three client-written pages (Home, Custom Homes, Commercial) are shown as targets only — do not rewrite them.

### 7.1 `/rightstart` — RightStart Preconstruction (NEW pillar)
- **Business goal:** convert planning-stage leads; own a branded, un-copyable differentiator.
- **Search / user intent:** informational → commercial ("what is preconstruction," "site evaluation before buying land," "rightstart").
- **Primary keyword:** preconstruction (branded: RightStart). **Supporting:** site evaluation before buying land, feasibility study construction, construction budget planning Nashville, design build vs general contractor.
- **Entities:** preconstruction, feasibility, site evaluation, scope/budget/schedule, authority having jurisdiction, code path.
- **H1:** RightStart: Preconstruction That Decides Whether a Project Goes Well
- **Sections:** what RightStart is → the five things it settles (site, feasibility, scope, budget, schedule) → why planning wins → residential vs commercial application → what you walk away with (written scope/budget/schedule) → FAQ → CTA.
- **Schema:** WebPage + BreadcrumbList + Service (serviceType "Construction Preconstruction Services", provider #organization) + FAQPage.
- **Internal links in:** Home, Custom Homes, Commercial, all location pages. **Out:** Custom Homes, Commercial, Contact.
- **CTA:** "Start with RightStart" → Contact.

### 7.2 `/service-areas` — Service Areas hub (NEW)
- **Goal:** consolidate geographic authority; distribute link equity to city pages.
- **Primary keyword:** middle tennessee general contractor. **Supporting:** general contractor middle tennessee, counties served.
- **H1:** Where Stellan Eoin Builds Across Middle Tennessee
- **Sections:** territory overview (Davidson + Williamson core; 20+ jurisdictions) → county/city grid linking each location page → "licensed across 20+ jurisdictions, and why that matters" (permitting fluency) → FAQ → CTA.
- **Schema:** WebPage + BreadcrumbList + FAQPage; areaServed enumerated on #organization.

### 7.3 `/service-areas/nashville` — Nashville (NEW)
- **Primary keyword:** general contractors nashville tn. **Supporting:** construction companies nashville, contractors nashville tn, nashville home construction. (Custom-home + commercial city terms are handled by the pillars — this page owns the GC head-term + geo and routes to the pillars.)
- **H1:** General Contractor in Nashville, TN
- **Must include:** Davidson County / Metro Nashville framing, Master Contractor MCN151894 (Nashville-specific credential), a real Nashville project (The Bedford), local permitting note, links to both pillars, local FAQ, NAP + map.

### 7.4 `/service-areas/clarksville` — Clarksville (NEW, high value)
- **Primary keyword:** general contractors clarksville tn. **Supporting:** home builders clarksville tn, contractors clarksville tn, construction companies clarksville tn, custom home builders clarksville tn.
- **H1:** General Contractor and Home Builder in Clarksville, TN
- **Angle:** Montgomery County; note the firm's HQ roots in Clarksville (narrative only, Nashville NAP stays in schema). Both pillars served. Local FAQ.

### 7.5 `/service-areas/murfreesboro` — Murfreesboro (NEW, high value)
- **Primary keyword:** general contractors murfreesboro tn. **Supporting:** home builders murfreesboro tn, contractors murfreesboro tn, custom home builders murfreesboro tn, construction companies murfreesboro tn.
- **H1:** General Contractor and Home Builder in Murfreesboro, TN
- **Angle:** Rutherford County growth market; custom homes + commercial; permitting fluency.

### 7.6 `/service-areas/franklin` — Franklin (NEW)
- **Primary keyword:** custom home builders franklin tn. **Supporting:** home builders franklin tn, general contractor franklin tn, custom homes franklin tn, contractors franklin tn.
- **H1:** Custom Home Builder and General Contractor in Franklin, TN
- **Angle:** Williamson County core territory; custom homes + historic/commercial (Franklin's historic district ties to preservation strength).

### 7.7 `/about` — About (REWRITE to v3)
- **Primary keyword:** stellan eoin builders / about (brand + entity). **Supporting:** licensed general contractor nashville, general contractor since 1993.
- **H1:** About Stellan Eoin Builders
- **Purge:** "since 2004," "20+ years," "leading … remodeling company," sustainability/innovation boilerplate.
- **Must include:** the hands-on / Amish-upbringing origin (John, first person), GC model (no self-perform, accountability under one roof), license BC 73150 + MCN151894, award, RightStart in one line, service territory, honest-budget ethos.
- **Schema:** AboutPage + BreadcrumbList; reinforces #organization.

### 7.8 `/team` — Leadership (REWRITE to v3)
- **Primary keyword:** stellan eoin team / John Hochstetler builder. 
- **H1:** The People Behind the Build
- **Bios:** John Hochstetler (Founder/CEO — trades-first story, no "two decades"/"sustainability" invention), Josh Hendrick (COO — operations, keep role), Aric Catlett (Project Technical Director — keep role/tools). Each gets `Person` schema with `worksFor` #organization.

### 7.9 `/contact` — Contact (REWRITE to v3)
- **Primary keyword:** contact stellan eoin / construction quote nashville.
- **H1:** Contact Stellan Eoin Builders
- **Must include:** phone, email, NAP, hours, quote form, the "Office 109 inside Suite 11" wayfinding line (visible copy only), embedded Google Map, service-area line.
- **Schema:** ContactPage + BreadcrumbList + LocalBusiness (the canonical NAP block).

### 7.10 `/projects` + case studies (REWRITE hub, keep case studies)
- **Hub primary keyword:** construction projects nashville / portfolio. **Case studies target niches:** restaurant buildout nashville, adaptive reuse nashville, event venue construction, historic restaurant renovation, retail buildout.
- Each case study: WebPage/CreativeWork + BreadcrumbList; 60–120 words of specific, factual narrative + gallery + one CTA. These are strong AEO citation surfaces — keep them factual and specific (materials, code path, what was preserved).

### 7.11 `/renovations` — Renovations & Additions (GATED — Decision #1)
- **Primary keyword:** home remodeling nashville. **Supporting:** nashville home renovations, home addition contractors, whole house remodel nashville, home renovation contractors near me.
- Copy drafted in file 02 but **do not publish until John confirms he offers this**.

---

## 8. Keyword Mapping (one keyword → one page; no cannibalization)

Volumes are the Keyword Planner tiers (5000 / 500 / 50). Each page has **one** primary; supporting terms are secondary H2/FAQ targets on that page only.

| Page | Primary keyword | Vol | Supporting keywords (same page only) |
|---|---|---|---|
| `/` Home | general contractor nashville / general contractors | 5000 | construction companies, general construction contractor, construction co, building contractors near me |
| `/custom-homes` | custom home builders nashville | 500 | custom home builders (500), custom home builders near me (500), custom home builders nashville tn (500), builder for custom homes (500), custom house builders (500), custom homebuilder near me (500), new home building cost per square foot (50), custom home construction (50) |
| `/commercial-construction` | commercial general contractor nashville | 50 | commercial contractors (50), commercial construction firms (50), general contractor for commercial construction (50), commercial remodeling (50), office building construction companies (50), commercial and residential general contractor (50) |
| `/rightstart` | construction preconstruction | 50 | design build company (50)*, feasibility, site evaluation, construction budget planning *(target the concept, but keep the page's own framing as GC-led, not "design-build"; see note)* |
| `/service-areas` | middle tennessee general contractor | 50 | general contractor middle tennessee, tennessee home builders (500), house builders in tennessee (500), builders in tennessee (50) |
| `/service-areas/nashville` | general contractors nashville tn | 500 | construction companies nashville (500), construction companies in nashville tn (500), contractors nashville tn (500), general contractors in nashville tn (500), nashville home construction (500), house builders nashville (500) |
| `/service-areas/clarksville` | general contractors clarksville tn | 500 | contractors clarksville tn (500), home builders clarksville tn (500), construction companies clarksville tn (500), clarksville contractors (500), home builders clarksville (500), custom home builders clarksville tn (50), remodeling contractors clarksville tn (50), builders in clarksville tn (50) |
| `/service-areas/murfreesboro` | general contractors murfreesboro tn | 500 | contractors murfreesboro tn (500), home builders murfreesboro tn (500), murfreesboro contractors (500), murfreesboro home builders (500), custom home builders murfreesboro tn (50), construction companies murfreesboro tn (50), builders in murfreesboro tn (50) |
| `/service-areas/franklin` | custom home builders franklin tn | 50 | home builders franklin tn (50), general contractor franklin tn (50), franklin general contractor (50), custom homes franklin tn (50), contractors franklin tn (50), franklin tn contractors (50), construction companies in franklin tn (50) |
| `/about` | stellan eoin builders | brand | licensed general contractor nashville, general contractor since 1993 |
| `/team` | John Hochstetler builder | brand | stellan eoin team, nashville custom home builder team |
| `/contact` | construction quote nashville | brand | contact stellan eoin, request construction quote nashville |
| `/services` (opt) | construction services nashville | 50 | general contractors nashville services |
| `/renovations` (GATED) | home remodeling nashville | 500 | nashville home renovations (500), home remodeling contractors (500), home addition contractors (500), house remodeling contractors (500), whole house remodel, home renovation contractors near me (500) |

\* **RightStart note:** the export shows "design build" demand (`design build company`, `design builders near me`, all 50/mo). v3 is explicit that Stellan Eoin is **not** design-build. Do **not** claim to be design-build to chase these. Instead, address the query honestly on the RightStart/Custom Homes FAQ ("Do you handle both design and construction?" — the v3 answer already does this). Answer the intent; don't misrepresent the model.

**Cannibalization guardrails:**
- "custom home builder(s) nashville" lives **only** on `/custom-homes`. The Nashville location page uses the *GC* head-term and links to `/custom-homes` for the custom-home intent.
- Each city page owns its own `[service] [city] tn` cluster; no two city pages compete for the same term.
- The 5,000/mo national-generic terms (`general contractors`, `construction companies`) are Low competition — anchor them on Home, but understand they're non-geo and will convert worse than the geo terms. The geo 500-terms are the real revenue.

---

## 9. Internal Linking Strategy

Principle: every page strengthens a pillar; pillars strengthen Home; location pages triangulate the pillars + Home.

- **Home →** both pillars, RightStart, Service Areas hub, Projects, Contact. (Home passes the most equity — link the money pages.)
- **Pillars (Custom Homes / Commercial) →** RightStart (contextual: "planning starts with RightStart"), 2–3 relevant Projects, the relevant location pages (Custom Homes → Franklin/Clarksville/Murfreesboro; Commercial → Nashville + relevant case studies), Contact.
- **RightStart →** both pillars, Contact.
- **Service Areas hub →** all four city pages (and receives links from footer sitewide).
- **Each city page →** both pillars (or the relevant one), RightStart, one local Project if available, sibling city pages (2–3, contextual: "also serving…"), Contact.
- **Projects hub →** each case study; **each case study →** the matching pillar + Contact.
- **About / Team / Contact →** pillars + Home.
- **Footer (sitewide) →** pillars, all city pages, RightStart, Projects, About/Team/Contact, NAP. This alone gives every location page a sitewide internal link, which matters for indexation.

**Anchor text:** descriptive and varied, not exact-match-spammy. "our custom home process," "commercial construction in Nashville," "how RightStart works," "building in Clarksville." Avoid repeating the exact primary keyword as anchor on every link.

**Breadcrumbs** double as internal links and must match `BreadcrumbList` schema.

---

## 10. Local SEO Strategy

**NAP consistency.** One canonical string (see §1) everywhere: site footer, Contact page, schema, GBP, every citation/directory. No variants (no "Suite 11" vs "Ste. 11" drift; no Office 109 in structured data). Audit existing citations and correct any that still say "since 2004," an old phone, or the Office 109 address.

**Google Business Profile.**
- **Primary category:** General Contractor. **Secondary:** Custom Home Builder, Commercial Contractor. (Add Kitchen Remodeler / Home Builder only if Decision #1 keeps renovations.)
- Services: mirror the two pillars + RightStart + the commercial niches (restaurant, retail, adaptive reuse, historic preservation, tenant improvement).
- Service areas: Nashville, Clarksville, Murfreesboro, Franklin, + county names (Davidson, Williamson, Montgomery, Rutherford).
- Verify **(615) 212-9005 rings the business** before it goes on GBP (this is on John's own follow-up list).
- Seed GBP Q&A with the homepage/location FAQs (owner-answered).
- Post monthly (projects, "kitchen of the year," RightStart explainer). Photos: real project photos with geo-relevant filenames + alt.

**Reviews.** Ask at the final walkthrough (highest-satisfaction moment). Prioritize Google, then Houzz. Respond to every review, mentioning the service + city naturally ("Thanks for trusting us with your Franklin renovation"). Don't gate or incentivize.

**Local links / citations.** Manufacturer/brand partner pages the old site already lists (Marvin, James Hardie, Daltile, Trex, Cambria, Kohler, Benjamin Moore, etc.) — pursue "find a builder/dealer" listings. The Nashville Design Collective award page. Local chamber (Nashville, Clarksville-Montgomery County, Rutherford, Williamson), BNI, and supplier co-marketing. Real project press (The Bedford, Rome Records) for editorial links.

**Geo signals on-page.** Embedded Google Map on Contact and each location page; county names, neighborhoods, and nearby landmarks written naturally into location copy; driving-context lines where relevant; local FAQ per city.

---

## 11. GEO Strategy (Generative Engine Optimization — ChatGPT, Gemini, Perplexity, Claude)

The goal: make the entity unambiguous and consistently described so generative engines resolve "Stellan Eoin Builders" to one clear, citable profile and recommend it for Middle-TN construction queries.

- **One entity, described identically everywhere.** The v3 "consistency keys" (BC 73150 · MCN151894 · (615) 212-9005 · quotes@stellaneoin.com · 11 Willow Street, Ste. 11, Nashville, TN 37210 · 2024 Kitchen of the Year · building since 1993 · established 2018) must match **character-for-character** across visible copy, JSON-LD, and `llms.txt`. Inconsistency is what makes an LLM hedge or omit you.
- **Ship `llms.txt`** (provided) at the root — a clean, factual, link-rich summary of who you are, what you do, where, and your credentials. This is the single most GEO-relevant new asset.
- **Semantic entity coverage, not keyword repetition.** Name the real things: license classifications, "authority having jurisdiction," "Type I hood," "grease interceptor," "adaptive reuse," "occupancy change," counties. Specific nouns are what LLMs quote.
- **Citable specifics.** "34 building categories," "20+ Tennessee jurisdictions," "~$350/sqft," license numbers, the award. Numbers and named credentials get quoted; adjectives don't.
- **`sameAs` graph.** Link GBP, Houzz, LinkedIn, Facebook, and the award listing from Organization schema so engines can corroborate the entity.
- **Author/entity attribution** on guides/notes (Person → John Hochstetler, `worksFor` #organization) so expertise is attributable.

---

## 12. AEO Strategy (Answer Engine Optimization)

Every important page should directly answer Who/What/Why/Where/When/How/Cost so the answer can be lifted verbatim by Google's AI Overviews and assistants.

- **FAQPage schema** on Home (7 Q&A), Custom Homes (10), Commercial (10), RightStart, and each location page (3–5 local Q&A). The v3 copy is already written as clean question→answer pairs — mirror it in `FAQPage` JSON-LD character-for-character.
- **Answer shape:** lead with a direct 40–60 word answer, then elaborate. Phrase headings the way people search ("How much does it cost to build a custom home in Nashville," not "Understanding cost drivers") — the v3 letter already did this correction.
- **Definitional answers** for RightStart, adaptive reuse, occupancy change, feasibility — these are exactly what assistants pull for "what is…" queries.
- **One clear numeric answer per costable question**, placed only where allowed (the ~$350/sqft answer lives solely on Custom Homes).
- **Objection-handling Q&A** ("Do you self-perform?", "Are you licensed and insured?", "What size commercial projects?") — these convert and get cited.
- Keep each FAQ answer self-contained (no "as mentioned above") so it stands alone when extracted.

---

## 13. Schema Recommendations (summary — full JSON-LD in file 03)

**Sitewide entity graph** (inject once, in the template, on every page):
- `GeneralContractor` (a `LocalBusiness`/`HomeAndConstructionBusiness` subtype) `@id …/#organization` — the master node: NAP, telephone, email, `founder` (John), `foundingDate` 2018, `areaServed` (4 cities + 4 counties), `hasCredential` (BC 73150, MCN151894), `award`, `makesOffer` (Custom Homes, Commercial), `sameAs`, `knowsAbout`.
- `WebSite` `@id …/#website`, `publisher` → #organization.

**Per page (in the page body):**
- `WebPage`/`AboutPage`/`ContactPage`/`CollectionPage` `@id {url}#webpage`, `isPartOf` #website, `about` #organization, `breadcrumb`.
- `BreadcrumbList`.
- `Service` on the two pillars, RightStart, and (optionally) each location page (`areaServed` = the city).
- `FAQPage` where FAQs exist.
- `Person` (×3) on `/team`.
- `CreativeWork`/`WebPage` on each project case study.

**Rules:** one consistent `@id` scheme; reference, don't duplicate, the Organization node; en-US; **no fabricated `aggregateRating`** — wire it from real GBP counts only once they exist (a placeholder with fake numbers is a manual-action risk). Keep the paused auto-schema plugin **off**; this hand-built graph replaces it.

---

## 14. Technical SEO Checklist (Joomla + SSR)

**Rendering (the SSR question you asked):**
- Joomla renders HTML server-side in PHP by default, so a section-based build **is** SSR-friendly **as long as the content and the JSON-LD are in the server HTML response**, not injected by client-side JavaScript. Rule of thumb: if you "View Source" (not "Inspect") and the copy + schema are there, crawlers and LLM fetchers see them. Keep hero text, body copy, FAQs, and JSON-LD in the rendered markup; reserve JS for enhancement (menus, galleries), never for primary content.
- **Section pattern (per page):** semantic HTML5 — one `<h1>`, then `<section>` blocks with `<h2>`/`<h3>`, real `<nav>` breadcrumbs, real footer NAP text. See the reusable pattern at the end of file 02.

**Head / indexation:**
- Self-referencing `<link rel="canonical">` on every page, pointing to the clean SEF URL (this neutralizes Joomla's `?Itemid`/`/index.php/` duplicates).
- Unique `<title>` + meta description per page (provided in file 02).
- `noindex,follow` on `/login`, `/forgot-password`, search results, and any `component/tags` pages; block them in robots.txt too.
- Force one host + protocol (https, www **or** non-www — pick one, 301 the other) in `.htaccess`.
- One XML sitemap (or a small sitemap index); submit in Search Console; reference it in robots.txt.

**Performance / CWV (Joomla specifics):**
- Enable Gzip + page cache (System → Global Config) and a caching plugin; minimize extensions.
- Serve images as WebP, correctly sized, `loading="lazy"` below the fold, explicit `width`/`height` to protect CLS.
- Defer non-critical JS; inline critical CSS if practical (no design system means you control the CSS — keep it lean).
- Descriptive, keyword-aware `alt` on every project image (the old site's alt text is a decent starting point — tighten it).

**Files at root:** `robots.txt`, `llms.txt`, `sitemap.xml`, `favicon`. Add a visible **"Last updated"** date on the three pillar pages (John's quarterly-refresh follow-up) — a freshness and trust signal for both Google and LLMs.

**Structured-data QA:** validate every template's JSON-LD in Google's Rich Results Test + Schema.org validator after Adam publishes, before announcing.

---

## 15. Content Priority Roadmap

**Phase 1 — Foundation (week 1–2): fix facts, stop the bleeding, ship the graph.**
1. Publish the three v3 pillar pages (Home, Custom Homes, Commercial) with new titles/descriptions.
2. Inject the sitewide Organization + WebSite JSON-LD graph (file 03) via the template.
3. Rewrite + publish About, Team, Contact to v3 facts. Purge "since 2004 / 20+ years / design-build / sustainability" sitewide.
4. Deploy `robots.txt`, `llms.txt`, canonicals, and the 301 map (§3). Kill the thin `/plans/*` pages.
5. Lock NAP; verify the phone; correct citations.

**Phase 2 — Local + differentiator (week 3–4): the revenue layer.**
6. Publish `/rightstart`.
7. Publish `/service-areas` hub + the four city pages (Nashville, Clarksville, Murfreesboro, Franklin) with local FAQs + per-page schema.
8. Wire footer sitewide internal links + NAP block.
9. GBP optimization pass (categories, services, areas, Q&A seeding, first posts).

**Phase 3 — Proof + polish (week 5–6).**
10. Rebuild `/projects` hub + the six case studies (factual, specific, schema'd).
11. Add FAQPage schema across pillars + locations; validate all structured data.
12. (If Decision #1 = keep) publish `/renovations`.
13. Begin review-velocity routine + first local link/citation outreach.

**Phase 4 — Ongoing.**
14. Quarterly refresh of the three pillars (visible "last updated").
15. Monthly GBP posts + review responses.
16. Supporting content: keep/refresh the strongest guide ("cost to build a home in Nashville") as an AEO asset; prune weak ones. New Builder's Notes only where they answer a real search question (out of this scope).

---

## 16. Action Plan (do-this-next checklist)

- [ ] Confirm the **three gated decisions** (§0) with John: renovations, financing, Clarksville HQ handling.
- [ ] Turn on Joomla SEF URLs + URL rewriting; force single host/protocol; remove `/index.php/` duplicates.
- [ ] Keep the schema plugin **paused**; paste the hand-built graph from file 03 into the template `<head>`/end-of-body.
- [ ] Publish Home / Custom Homes / Commercial (client v3 copy) with the file-02 titles + descriptions.
- [ ] Rewrite About / Team / Contact from file 02; purge outdated facts sitewide.
- [ ] Add self-referencing canonicals + unique titles/descriptions to every page.
- [ ] Deploy `robots.txt` + `llms.txt` + `sitemap.xml` at root.
- [ ] Implement the §3 301 redirect map; delete thin `/plans/*`.
- [ ] Build `/rightstart`, `/service-areas`, and the four city pages from file 02; add per-page schema + FAQPage.
- [ ] Wire the sitewide footer NAP + internal-link block.
- [ ] Optimize GBP; verify the phone; fix citations to the canonical NAP.
- [ ] Rebuild `/projects` + case studies.
- [ ] Validate all JSON-LD (Rich Results Test) post-publish; submit sitemap in Search Console; QA on live pages.
- [ ] Stand up review-velocity + local-link routine; set the quarterly pillar-refresh reminder.

*End of master strategy. Page copy → `02_Core_Page_Copy.md`. Schema → `03_Schema_JSON-LD_Pack.md`.*
