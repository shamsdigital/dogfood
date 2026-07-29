# Stellan Eoin Builders — JSON-LD Schema Pack

**How to deploy:** keep the Joomla auto-schema plugin **paused**. Inject **Block A (sitewide graph)** once via the template so it appears on every page. Add the **per-page block** in each article (Custom HTML module or custom field). Every value below matches the v3 consistency keys character-for-character. Change `https://www.stellaneoin.com` to the live host (and pick www vs non-www to match your canonical).

> **Do NOT add `aggregateRating` or `review` with invented numbers.** Wire those only from real, verifiable Google/GBP data once it exists. Fake rating counts are a manual-action risk. A commented placeholder is included at the end.

---

## BLOCK A — Sitewide graph (Organization + WebSite). Inject on every page.

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "GeneralContractor",
      "@id": "https://www.stellaneoin.com/#organization",
      "name": "Stellan Eoin Builders",
      "legalName": "Stellan Eoin Builders, LLC",
      "url": "https://www.stellaneoin.com/",
      "logo": {
        "@type": "ImageObject",
        "@id": "https://www.stellaneoin.com/#logo",
        "url": "https://www.stellaneoin.com/images/logo.png"
      },
      "image": { "@id": "https://www.stellaneoin.com/#logo" },
      "description": "Licensed Tennessee general contractor managing custom home and commercial construction across Nashville and Middle Tennessee. Building since 1993; firm established 2018.",
      "telephone": "+1-615-212-9005",
      "email": "quotes@stellaneoin.com",
      "foundingDate": "2018",
      "founder": { "@id": "https://www.stellaneoin.com/team#john-hochstetler" },
      "address": {
        "@type": "PostalAddress",
        "streetAddress": "11 Willow Street, Ste. 11",
        "addressLocality": "Nashville",
        "addressRegion": "TN",
        "postalCode": "37210",
        "addressCountry": "US"
      },
      "areaServed": [
        { "@type": "City", "name": "Nashville" },
        { "@type": "City", "name": "Clarksville" },
        { "@type": "City", "name": "Murfreesboro" },
        { "@type": "City", "name": "Franklin" },
        { "@type": "City", "name": "Brentwood" },
        { "@type": "AdministrativeArea", "name": "Davidson County" },
        { "@type": "AdministrativeArea", "name": "Williamson County" },
        { "@type": "AdministrativeArea", "name": "Montgomery County" },
        { "@type": "AdministrativeArea", "name": "Rutherford County" },
        { "@type": "AdministrativeArea", "name": "Middle Tennessee" }
      ],
      "hasCredential": [
        {
          "@type": "EducationalOccupationalCredential",
          "credentialCategory": "Tennessee Contractor License",
          "identifier": "BC 73150",
          "description": "Tennessee contractor license BC 73150, the state's broadest building classification, covering residential, commercial, and industrial construction across 34 building categories."
        },
        {
          "@type": "EducationalOccupationalCredential",
          "credentialCategory": "Metro Nashville / Davidson County Master Contractor",
          "identifier": "MCN151894"
        }
      ],
      "award": "2024 Kitchen of the Year, Nashville Design Collective",
      "knowsAbout": [
        "Custom home construction",
        "Commercial construction",
        "Adaptive reuse",
        "Historic preservation",
        "Restaurant and assembly-occupancy buildouts",
        "Tenant improvements",
        "Construction preconstruction and feasibility"
      ],
      "makesOffer": [
        {
          "@type": "Offer",
          "itemOffered": { "@id": "https://www.stellaneoin.com/custom-homes#service" }
        },
        {
          "@type": "Offer",
          "itemOffered": { "@id": "https://www.stellaneoin.com/commercial-construction#service" }
        }
      ],
      "sameAs": [
        "https://www.google.com/maps/REPLACE-with-GBP-share-link",
        "https://www.houzz.com/REPLACE",
        "https://www.facebook.com/REPLACE",
        "https://www.linkedin.com/company/REPLACE"
      ]
    },
    {
      "@type": "WebSite",
      "@id": "https://www.stellaneoin.com/#website",
      "url": "https://www.stellaneoin.com/",
      "name": "Stellan Eoin Builders",
      "publisher": { "@id": "https://www.stellaneoin.com/#organization" },
      "inLanguage": "en-US"
    }
  ]
}
</script>
```

*Notes:* fill the four `sameAs` URLs with real profiles (this is a key GEO signal). If you keep the Clarksville HQ as narrative-only (recommended), do **not** add a second `PostalAddress`. Add an `openingHoursSpecification` block once hours are confirmed.

---

## BLOCK B — Home page (add to Block A page). WebPage + FAQPage (7 Q&A).

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "WebPage",
      "@id": "https://www.stellaneoin.com/#webpage",
      "url": "https://www.stellaneoin.com/",
      "name": "Nashville Custom Home & Commercial General Contractor | Stellan Eoin",
      "isPartOf": { "@id": "https://www.stellaneoin.com/#website" },
      "about": { "@id": "https://www.stellaneoin.com/#organization" },
      "inLanguage": "en-US"
    },
    {
      "@type": "FAQPage",
      "@id": "https://www.stellaneoin.com/#faq",
      "mainEntity": [
        {
          "@type": "Question",
          "name": "Do you have hands-on construction experience, or do you just manage subcontractors?",
          "acceptedAnswer": { "@type": "Answer", "text": "Both, and in that order. I started building as a kid and spent years doing the work myself: framing, roofing, finish carpentry. I run a general contracting firm now and we do not self-perform, but everything I know about managing trade partners comes from having been the one doing the work." }
        },
        {
          "@type": "Question",
          "name": "What is the RightStart program?",
          "acceptedAnswer": { "@type": "Answer", "text": "RightStart is our preconstruction process. It covers site evaluation, feasibility, scope definition, budget development, and schedule, all worked out in writing before construction starts." }
        },
        {
          "@type": "Question",
          "name": "What is the most important thing I can do to make my construction project go well?",
          "acceptedAnswer": { "@type": "Answer", "text": "Spend more time planning before you build. Most of what goes wrong on a project traces back to a decision that was not made early enough. Decisions are inexpensive on paper and costly in the field." }
        },
        {
          "@type": "Question",
          "name": "Do you handle both design and construction?",
          "acceptedAnswer": { "@type": "Answer", "text": "We are a general contractor rather than a design-build firm. We work with established design partners for drawings and selections. What stays under one roof is accountability: one point of contact, one party responsible for the outcome." }
        },
        {
          "@type": "Question",
          "name": "Can you help me find land to build on?",
          "acceptedAnswer": { "@type": "Answer", "text": "Yes. We are not realtors and we do not sell lots, but we are glad to connect you with a reputable realtor. More importantly, we will evaluate any lot you are considering before you buy it, because site conditions drive a large share of what a home costs to build." }
        },
        {
          "@type": "Question",
          "name": "Are you licensed and insured?",
          "acceptedAnswer": { "@type": "Answer", "text": "Yes. Our Tennessee license is BC 73150, the state's broadest classification, covering residential, commercial, and industrial construction across 34 building categories. We also hold Metro Nashville Master Contractor license MCN151894. We carry general liability and workers' compensation coverage and will provide certificates on request." }
        },
        {
          "@type": "Question",
          "name": "Do you self-perform any of the work?",
          "acceptedAnswer": { "@type": "Answer", "text": "No. We are a general contractor. Every trade on your project is a licensed partner we selected, contracted, and manage, and we are accountable for all of it." }
        }
      ]
    }
  ]
}
</script>
```

---

## BLOCK C — Service pillar page (Custom Homes shown). WebPage + BreadcrumbList + Service + FAQPage.

Swap the marked values for the Commercial page (`@id .../commercial-construction#...`, serviceType "Commercial Construction", its 10 FAQs).

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "WebPage",
      "@id": "https://www.stellaneoin.com/custom-homes#webpage",
      "url": "https://www.stellaneoin.com/custom-homes",
      "name": "Custom Home Builder in Nashville, TN | Stellan Eoin Builders",
      "isPartOf": { "@id": "https://www.stellaneoin.com/#website" },
      "about": { "@id": "https://www.stellaneoin.com/custom-homes#service" },
      "breadcrumb": { "@id": "https://www.stellaneoin.com/custom-homes#breadcrumb" },
      "inLanguage": "en-US"
    },
    {
      "@type": "BreadcrumbList",
      "@id": "https://www.stellaneoin.com/custom-homes#breadcrumb",
      "itemListElement": [
        { "@type": "ListItem", "position": 1, "name": "Home", "item": "https://www.stellaneoin.com/" },
        { "@type": "ListItem", "position": 2, "name": "Custom Homes", "item": "https://www.stellaneoin.com/custom-homes" }
      ]
    },
    {
      "@type": "Service",
      "@id": "https://www.stellaneoin.com/custom-homes#service",
      "serviceType": "Custom Home Construction",
      "name": "Custom Home Construction",
      "provider": { "@id": "https://www.stellaneoin.com/#organization" },
      "areaServed": [
        { "@type": "City", "name": "Nashville" },
        { "@type": "City", "name": "Franklin" },
        { "@type": "City", "name": "Brentwood" },
        { "@type": "AdministrativeArea", "name": "Middle Tennessee" }
      ],
      "description": "Custom home construction managed by a licensed Tennessee general contractor (BC 73150). Site evaluation before you buy land, RightStart preconstruction, design-partner coordination, construction, and a tiered warranty."
    },
    {
      "@type": "FAQPage",
      "@id": "https://www.stellaneoin.com/custom-homes#faq",
      "mainEntity": [
        {
          "@type": "Question",
          "name": "How much does it cost to build a custom home in Nashville?",
          "acceptedAnswer": { "@type": "Answer", "text": "Every home we build is different, so no two land at the same cost per square foot. That said, it is common right now for a custom home in this market to land somewhere around $350 per square foot. Yours could come in lower or considerably higher, depending almost entirely on decisions you make about finishes, land, and site conditions." }
        },
        {
          "@type": "Question",
          "name": "Can you build on land I already own?",
          "acceptedAnswer": { "@type": "Answer", "text": "Yes. We evaluate your site during preconstruction, including grading, utilities, and permitting, so those costs are in the budget from the beginning rather than surfacing later as change orders." }
        },
        {
          "@type": "Question",
          "name": "I haven't bought land yet. Can you still help?",
          "acceptedAnswer": { "@type": "Answer", "text": "Yes, and this is the best time to talk to us. We will connect you with a reputable realtor, and we will evaluate any lot you are serious about before you close, so you know what it costs to build there while you still have the option not to." }
        }
      ]
    }
  ]
}
</script>
```

*(Add the remaining Custom Homes FAQs from the v3 copy to `mainEntity` in the same shape. Keep answers character-for-character with the visible page.)*

---

## BLOCK D — Location page (Clarksville shown). WebPage + BreadcrumbList + Service(areaServed=City) + FAQPage.

Duplicate for Nashville / Murfreesboro / Franklin, swapping city name, county, URLs, and the local FAQs.

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "WebPage",
      "@id": "https://www.stellaneoin.com/service-areas/clarksville#webpage",
      "url": "https://www.stellaneoin.com/service-areas/clarksville",
      "name": "General Contractor & Home Builder in Clarksville, TN | Stellan Eoin",
      "isPartOf": { "@id": "https://www.stellaneoin.com/#website" },
      "about": { "@id": "https://www.stellaneoin.com/#organization" },
      "breadcrumb": { "@id": "https://www.stellaneoin.com/service-areas/clarksville#breadcrumb" },
      "inLanguage": "en-US"
    },
    {
      "@type": "BreadcrumbList",
      "@id": "https://www.stellaneoin.com/service-areas/clarksville#breadcrumb",
      "itemListElement": [
        { "@type": "ListItem", "position": 1, "name": "Home", "item": "https://www.stellaneoin.com/" },
        { "@type": "ListItem", "position": 2, "name": "Service Areas", "item": "https://www.stellaneoin.com/service-areas" },
        { "@type": "ListItem", "position": 3, "name": "Clarksville", "item": "https://www.stellaneoin.com/service-areas/clarksville" }
      ]
    },
    {
      "@type": "Service",
      "@id": "https://www.stellaneoin.com/service-areas/clarksville#service",
      "serviceType": "General Contracting, Custom Home and Commercial Construction",
      "provider": { "@id": "https://www.stellaneoin.com/#organization" },
      "areaServed": [
        { "@type": "City", "name": "Clarksville" },
        { "@type": "AdministrativeArea", "name": "Montgomery County" }
      ]
    },
    {
      "@type": "FAQPage",
      "@id": "https://www.stellaneoin.com/service-areas/clarksville#faq",
      "mainEntity": [
        {
          "@type": "Question",
          "name": "Do you build in Clarksville and Montgomery County?",
          "acceptedAnswer": { "@type": "Answer", "text": "Yes. Clarksville is our headquarters market, and we build both custom homes and commercial projects here." }
        },
        {
          "@type": "Question",
          "name": "Can you evaluate a Clarksville lot before I buy it?",
          "acceptedAnswer": { "@type": "Answer", "text": "Yes. We assess topography, drainage, utilities, setbacks, and what the jurisdiction will allow, before you close, while you still have the option to walk away." }
        },
        {
          "@type": "Question",
          "name": "Are you licensed for commercial work in Clarksville?",
          "acceptedAnswer": { "@type": "Answer", "text": "Yes. Our BC 73150 classification covers commercial, residential, and industrial construction across 34 building categories." }
        }
      ]
    }
  ]
}
</script>
```

---

## BLOCK E — Team page. Person x3 (John is the founder node referenced by Organization).

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "AboutPage",
      "@id": "https://www.stellaneoin.com/team#webpage",
      "url": "https://www.stellaneoin.com/team",
      "name": "Our Team | Stellan Eoin Builders Leadership | Nashville",
      "isPartOf": { "@id": "https://www.stellaneoin.com/#website" },
      "about": { "@id": "https://www.stellaneoin.com/#organization" },
      "inLanguage": "en-US"
    },
    {
      "@type": "Person",
      "@id": "https://www.stellaneoin.com/team#john-hochstetler",
      "name": "John Hochstetler",
      "jobTitle": "Founder and CEO",
      "worksFor": { "@id": "https://www.stellaneoin.com/#organization" },
      "description": "Founder and CEO of Stellan Eoin Builders. Building since 1993; learned the trades hands-on before managing projects."
    },
    {
      "@type": "Person",
      "@id": "https://www.stellaneoin.com/team#josh-hendrick",
      "name": "Josh Hendrick",
      "jobTitle": "Chief Operations Officer",
      "worksFor": { "@id": "https://www.stellaneoin.com/#organization" }
    },
    {
      "@type": "Person",
      "@id": "https://www.stellaneoin.com/team#aric-catlett",
      "name": "Aric Catlett",
      "jobTitle": "Project Technical Director",
      "worksFor": { "@id": "https://www.stellaneoin.com/#organization" }
    }
  ]
}
</script>
```

---

## BLOCK F — Contact page. ContactPage + BreadcrumbList (NAP already in Block A Organization).

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "ContactPage",
      "@id": "https://www.stellaneoin.com/contact#webpage",
      "url": "https://www.stellaneoin.com/contact",
      "name": "Contact Stellan Eoin Builders | Request a Construction Quote in Nashville",
      "isPartOf": { "@id": "https://www.stellaneoin.com/#website" },
      "about": { "@id": "https://www.stellaneoin.com/#organization" },
      "breadcrumb": { "@id": "https://www.stellaneoin.com/contact#breadcrumb" },
      "inLanguage": "en-US"
    },
    {
      "@type": "BreadcrumbList",
      "@id": "https://www.stellaneoin.com/contact#breadcrumb",
      "itemListElement": [
        { "@type": "ListItem", "position": 1, "name": "Home", "item": "https://www.stellaneoin.com/" },
        { "@type": "ListItem", "position": 2, "name": "Contact", "item": "https://www.stellaneoin.com/contact" }
      ]
    }
  ]
}
</script>
```

---

## BLOCK G — RightStart page. WebPage + BreadcrumbList + Service + FAQPage.

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "WebPage",
      "@id": "https://www.stellaneoin.com/rightstart#webpage",
      "url": "https://www.stellaneoin.com/rightstart",
      "name": "RightStart Preconstruction | Plan Before You Build | Stellan Eoin",
      "isPartOf": { "@id": "https://www.stellaneoin.com/#website" },
      "about": { "@id": "https://www.stellaneoin.com/rightstart#service" },
      "breadcrumb": { "@id": "https://www.stellaneoin.com/rightstart#breadcrumb" },
      "inLanguage": "en-US"
    },
    {
      "@type": "BreadcrumbList",
      "@id": "https://www.stellaneoin.com/rightstart#breadcrumb",
      "itemListElement": [
        { "@type": "ListItem", "position": 1, "name": "Home", "item": "https://www.stellaneoin.com/" },
        { "@type": "ListItem", "position": 2, "name": "RightStart", "item": "https://www.stellaneoin.com/rightstart" }
      ]
    },
    {
      "@type": "Service",
      "@id": "https://www.stellaneoin.com/rightstart#service",
      "serviceType": "Construction Preconstruction and Feasibility",
      "name": "RightStart Preconstruction",
      "provider": { "@id": "https://www.stellaneoin.com/#organization" },
      "areaServed": { "@type": "AdministrativeArea", "name": "Middle Tennessee" },
      "description": "RightStart is Stellan Eoin's preconstruction process: site evaluation, feasibility, scope, budget, and schedule settled in writing before construction begins."
    },
    {
      "@type": "FAQPage",
      "@id": "https://www.stellaneoin.com/rightstart#faq",
      "mainEntity": [
        {
          "@type": "Question",
          "name": "What is RightStart?",
          "acceptedAnswer": { "@type": "Answer", "text": "Our preconstruction process: site evaluation, feasibility, scope, budget, and schedule, settled in writing before construction begins." }
        },
        {
          "@type": "Question",
          "name": "Does RightStart apply to commercial projects?",
          "acceptedAnswer": { "@type": "Answer", "text": "Yes, and it matters more there, because a lease clock or opening date is usually involved. We assess buildability and code path before you sign a lease or purchase agreement." }
        }
      ]
    }
  ]
}
</script>
```

---

## BLOCK H — Project case study (The Bedford shown). CreativeWork/WebPage + BreadcrumbList.

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "WebPage",
      "@id": "https://www.stellaneoin.com/projects/commercial/the-bedford-nashville-event-venue#webpage",
      "url": "https://www.stellaneoin.com/projects/commercial/the-bedford-nashville-event-venue",
      "name": "The Bedford Nashville Event Venue | Stellan Eoin Builders",
      "isPartOf": { "@id": "https://www.stellaneoin.com/#website" },
      "about": { "@id": "https://www.stellaneoin.com/#organization" },
      "breadcrumb": { "@id": "https://www.stellaneoin.com/projects/commercial/the-bedford-nashville-event-venue#breadcrumb" },
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
    }
  ]
}
</script>
```

---

## PLACEHOLDER — aggregateRating (DO NOT deploy until real)

Once you have a verifiable public rating (e.g., from Google), you may add this **inside the Organization node**, using real counts only:

```jsonc
// "aggregateRating": {
//   "@type": "AggregateRating",
//   "ratingValue": "REAL_VALUE",
//   "reviewCount": "REAL_COUNT",
//   "bestRating": "5"
// }
```

Never hardcode numbers that a user cannot verify on the source platform.

*End of schema pack.*
