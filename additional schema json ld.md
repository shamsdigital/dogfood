# Stellan Eoin Builders — Additional JSON-LD (sub-vertical pages + case studies)

**Deploy exactly like file 03:** Block A (the sitewide Organization + WebSite graph from `03_Schema_JSON-LD_Pack.md`) still injects on every page via the template. The blocks below are the **per-page** graphs for the pages created in `04_Remaining_Page_Copy.md`. Every `@id` references the one Organization node (`#organization`) so the entity graph stays consistent. Change the host to match your canonical (www vs non-www). All values match the v3 facts.

---

## TEMPLATE 1 — Commercial sub-vertical page

Shown for **Restaurants**. For the other five, change only: the URL slug, `name`, `serviceType`, breadcrumb leaf name, and the FAQ `mainEntity` (copy the three Q/A from that page in file 04, character-for-character). Slugs: `/commercial-construction/retail`, `/hospitality`, `/adaptive-reuse`, `/historic-preservation`, `/tenant-improvements`.

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "WebPage",
      "@id": "https://www.stellaneoin.com/commercial-construction/restaurants#webpage",
      "url": "https://www.stellaneoin.com/commercial-construction/restaurants",
      "name": "Restaurant & Bar Construction in Nashville, TN | Stellan Eoin Builders",
      "isPartOf": { "@id": "https://www.stellaneoin.com/#website" },
      "about": { "@id": "https://www.stellaneoin.com/commercial-construction/restaurants#service" },
      "breadcrumb": { "@id": "https://www.stellaneoin.com/commercial-construction/restaurants#breadcrumb" },
      "inLanguage": "en-US"
    },
    {
      "@type": "BreadcrumbList",
      "@id": "https://www.stellaneoin.com/commercial-construction/restaurants#breadcrumb",
      "itemListElement": [
        { "@type": "ListItem", "position": 1, "name": "Home", "item": "https://www.stellaneoin.com/" },
        { "@type": "ListItem", "position": 2, "name": "Commercial Construction", "item": "https://www.stellaneoin.com/commercial-construction" },
        { "@type": "ListItem", "position": 3, "name": "Restaurant & Bar Construction", "item": "https://www.stellaneoin.com/commercial-construction/restaurants" }
      ]
    },
    {
      "@type": "Service",
      "@id": "https://www.stellaneoin.com/commercial-construction/restaurants#service",
      "serviceType": "Restaurant and Bar Construction",
      "name": "Restaurant and Bar Construction",
      "provider": { "@id": "https://www.stellaneoin.com/#organization" },
      "isRelatedTo": { "@id": "https://www.stellaneoin.com/commercial-construction#service" },
      "areaServed": [
        { "@type": "City", "name": "Nashville" },
        { "@type": "City", "name": "Murfreesboro" },
        { "@type": "AdministrativeArea", "name": "Middle Tennessee" }
      ],
      "description": "Restaurant, bar, and cafe construction and buildouts managed by a licensed Tennessee general contractor (BC 73150), including commercial kitchen, exhaust, and the health-department and mechanical code path."
    },
    {
      "@type": "FAQPage",
      "@id": "https://www.stellaneoin.com/commercial-construction/restaurants#faq",
      "mainEntity": [
        {
          "@type": "Question",
          "name": "Do you handle the commercial kitchen and hood?",
          "acceptedAnswer": { "@type": "Answer", "text": "Yes. The kitchen, exhaust and make-up air, and grease handling are core to a restaurant buildout, and we coordinate them with the health-department and mechanical code path from the start." }
        },
        {
          "@type": "Question",
          "name": "Can you convert an existing building into a restaurant?",
          "acceptedAnswer": { "@type": "Answer", "text": "Yes. Adaptive reuse into food service is work we have done, including a full residential-to-cafe conversion." }
        },
        {
          "@type": "Question",
          "name": "Will you look at a space before I sign the lease?",
          "acceptedAnswer": { "@type": "Answer", "text": "Yes. We assess buildability and code path first, so a promising space does not turn into an expensive surprise after the lease is signed." }
        }
      ]
    }
  ]
}
</script>
```

**Reference values for the other five sub-vertical Service nodes** (drop into the same template):
- Retail — `serviceType`: "Retail Construction and Store Buildouts"; breadcrumb leaf "Retail Construction".
- Hospitality — `serviceType`: "Hospitality and Event Venue Construction"; breadcrumb leaf "Hospitality & Event Venues".
- Adaptive Reuse — `serviceType`: "Adaptive Reuse Construction"; breadcrumb leaf "Adaptive Reuse".
- Historic Preservation — `serviceType`: "Historic Preservation and Restoration"; breadcrumb leaf "Historic Preservation".
- Tenant Improvements — `serviceType`: "Commercial Tenant Improvements"; breadcrumb leaf "Tenant Improvements".

---

## TEMPLATE 2 — Project case study

Shown for **The Bedford**. For the other five, change: URL, `name`, `headline`, breadcrumb (leaf name + whether it sits under `/projects/commercial` or `/projects/residential`), `about.keywords`, and `dateCreated` only if a real date is known (otherwise omit it — do not invent one). `CreativeWork` is used because these are documented works; `author`/`creator` points to the Organization.

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "WebPage",
      "@id": "https://www.stellaneoin.com/projects/commercial/the-bedford-nashville-event-venue#webpage",
      "url": "https://www.stellaneoin.com/projects/commercial/the-bedford-nashville-event-venue",
      "name": "The Bedford: Historic Restaurant to Nashville Event Venue | Stellan Eoin",
      "isPartOf": { "@id": "https://www.stellaneoin.com/#website" },
      "about": { "@id": "https://www.stellaneoin.com/#organization" },
      "breadcrumb": { "@id": "https://www.stellaneoin.com/projects/commercial/the-bedford-nashville-event-venue#breadcrumb" },
      "primaryImageOfPage": { "@id": "https://www.stellaneoin.com/projects/commercial/the-bedford-nashville-event-venue#image" },
      "inLanguage": "en-US"
    },
    {
      "@type": "BreadcrumbList",
      "@id": "https://www.stellaneoin.com/projects/commercial/the-bedford-nashville-event-venue#breadcrumb",
      "itemListElement": [
        { "@type": "ListItem", "position": 1, "name": "Home", "item": "https://www.stellaneoin.com/" },
        { "@type": "ListItem", "position": 2, "name": "Projects", "item": "https://www.stellaneoin.com/projects" },
        { "@type": "ListItem", "position": 3, "name": "The Bedford", "item": "https://www.stellaneoin.com/projects/commercial/the-bedford-nashville-event-venue" }
      ]
    },
    {
      "@type": "CreativeWork",
      "@id": "https://www.stellaneoin.com/projects/commercial/the-bedford-nashville-event-venue#project",
      "name": "The Bedford Nashville Event Venue",
      "headline": "A historic Nashville restaurant reimagined as an event venue",
      "creator": { "@id": "https://www.stellaneoin.com/#organization" },
      "about": {
        "@type": "Thing",
        "name": "Adaptive reuse and historic preservation of a restaurant into an assembly-occupancy event venue",
        "keywords": "adaptive reuse, historic preservation, event venue construction, assembly occupancy, Nashville"
      },
      "locationCreated": { "@type": "Place", "name": "Nashville, TN" },
      "description": "A historic restaurant space reimagined as a Nashville event venue. Arched brickwork and exposed structure were preserved, custom-milled woodwork and aged finishes were applied on site, and a covered patio of more than 120 feet was added with integrated lighting and sound."
    },
    {
      "@type": "ImageObject",
      "@id": "https://www.stellaneoin.com/projects/commercial/the-bedford-nashville-event-venue#image",
      "url": "https://www.stellaneoin.com/images/projects/the-bedford-1.webp",
      "caption": "Interior of The Bedford event venue with preserved arched brickwork"
    }
  ]
}
</script>
```

**Reference values for the other five case-study `CreativeWork` nodes:**
- Rome Records & Café — path `/projects/commercial/rome-records-cafe`; keywords "retail construction, cafe buildout, live music venue, custom casework, acoustics"; location "Nashville, TN" (confirm city before publishing if different).
- The Moringa Tree — path `/projects/commercial/the-moringa-tree-restaurant-cafe`; keywords "adaptive reuse, restaurant construction, health cafe, occupancy change".
- 5.11 Tactical — path `/projects/commercial/5-11-tactical`; keywords "retail franchise buildout, tenant improvement, fast-track construction"; note the collaboration with Action RCS in `description` only (already in copy).
- Dickson Custom Home — path `/projects/residential/dickson-tn-custom-home`; breadcrumb under Projects; keywords "custom home, transitional design, vaulted ceilings, stone fireplace"; location "Dickson, TN".
- Multi-Family Gallatin — path `/projects/residential/multifamily-gallatin`; keywords "multifamily renovation, interior and exterior overhaul, code compliance"; location "Gallatin, TN".

---

## Validation note
All blocks in this file were checked as valid JSON before delivery. After the agent publishes each page, re-validate the rendered page in Google's Rich Results Test and the Schema.org validator, because a single stray comma introduced during paste will silently disable the block.

*End of additional schema.*
