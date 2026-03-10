---
name: technical-seo-auditor
description: >
  Audit technical SEO issues — crawlability, indexing, site speed, structured data, and Core Web Vitals.
  Use this skill when the user says "technical SEO audit", "site crawl issues", "indexing problems",
  "Core Web Vitals optimization", "site speed SEO", "structured data audit", "XML sitemap review",
  "robots.txt analysis", "canonical tag audit", "crawl budget optimization", or "technical SEO checklist".
  Also trigger for redirect chain analysis, hreflang audit, or JavaScript SEO issues.
---

# Technical SEO Auditor

Performs a comprehensive technical SEO audit covering crawlability, indexing, site architecture, page speed, structured data, and Core Web Vitals with prioritized fix recommendations.

## Granularity Check

> **Session time**: ~5 min data prep + ~10 min Claude session. If implementing fixes, add 2-20 hours depending on issue severity. Input is crawl data exports or site URL. Output is Markdown audit report with prioritized action items.

## User Intent Mapping

- "Run a technical SEO audit on our site" (full audit)
- "Why aren't our pages getting indexed?" (indexing diagnosis)
- "Our Core Web Vitals are failing" (performance)
- "Fix our crawl errors" (crawlability)
- "Structured data review" (schema markup)
- "Our site is slow — how does it affect SEO?" (speed)
- "XML sitemap issues" (sitemap)
- "Redirect chain cleanup" (redirects)
- "JavaScript rendering SEO problems" (JS SEO)
- "International SEO / hreflang issues" (i18n)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Site URL | Text | Domain to audit |
| Crawl Data | CSV/Text | Screaming Frog, Sitebulb, or GSC export (or describe issues) |
| Priority | Text | What matters most: indexing, speed, rankings, migration |

### If You Don't Have This Data

- **No crawl tool?** Use free Screaming Frog (500 URLs free) or Google Search Console Coverage report. Claude can audit from GSC data alone.
- **No Core Web Vitals data?** Run PageSpeed Insights on 5 key pages and paste the scores. Claude prioritizes fixes by impact.
- **No structured data?** Paste your page source or describe your page types. Claude recommends the right schema markup.
- **No server access?** Claude identifies issues and provides recommendations your developer can implement. Focus on what's controllable (meta tags, content, internal linking).

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| GSC Coverage Report | CSV | Index coverage status and issues |
| PageSpeed Insights | Text | CWV scores for key pages |
| Robots.txt | Text | Current robots.txt contents |
| Sitemap URL | Text | XML sitemap location |
| CMS/Platform | Text | WordPress, Shopify, Next.js, etc. |

## Process

### Step 1: Crawlability Audit
- Robots.txt analysis (blocked resources, crawl directives)
- XML sitemap validation (completeness, freshness, errors)
- Crawl depth analysis (pages >3 clicks from homepage)
- Internal linking structure and orphan pages
- Crawl budget optimization for large sites (10K+ pages)

### Step 2: Indexing Analysis
- Index coverage status (valid, excluded, error)
- Noindex/nofollow tag audit
- Canonical tag consistency
- Duplicate content identification
- Thin content pages flagging

### Step 3: Site Architecture Review
- URL structure and hierarchy
- Navigation depth and breadcrumbs
- Pagination handling (rel=next/prev, load more, infinite scroll)
- Faceted navigation and parameter handling
- Internal link equity distribution

### Step 4: Page Speed & Core Web Vitals
- LCP (Largest Contentful Paint) — target < 2.5s
- INP (Interaction to Next Paint) — target < 200ms
- CLS (Cumulative Layout Shift) — target < 0.1
- TTFB (Time to First Byte) optimization
- Image optimization, lazy loading, compression
- Render-blocking resources

### Step 5: Structured Data Audit
- Existing schema markup validation
- Missing schema opportunities (FAQ, HowTo, Product, Article, Organization)
- Rich result eligibility assessment
- JSON-LD implementation recommendations

### Step 6: Security & Mobile
- HTTPS implementation and mixed content
- Mobile-friendliness assessment
- Viewport and responsive design
- AMP status (if applicable)

### Confidence & Sample Size
> **Confidence Note**: Technical SEO audits from crawl exports provide high-confidence findings. However, JavaScript-rendered content may not appear in standard crawls — verify with "View Rendered Page" in GSC. Core Web Vitals field data (CrUX) is more reliable than lab data for ranking impact. Large sites (100K+ pages) should prioritize issues by page template, not individual URLs.

### ⚠️ Human Checkpoint
> Have a developer review all recommended changes before implementation. Robots.txt and canonical tag changes can accidentally deindex pages. Always test in staging before deploying site-wide changes.

> **Benchmark Context**: 60% of websites have technical SEO issues affecting rankings. Pages passing all Core Web Vitals are 24% less likely to be abandoned. Proper structured data increases CTR by 20-30% via rich results. Sites with XML sitemaps get indexed 3x faster. Pages beyond 3 clicks from homepage receive 76% less organic traffic.

## Output Contract

### Deliverable: Markdown Technical SEO Audit

```markdown
# Technical SEO Audit: [Domain]

## Executive Summary
- Critical issues: [count]
- Warnings: [count]
- Opportunities: [count]
- Estimated traffic impact: [assessment]

## Crawlability
| Issue | Severity | Pages Affected | Fix |
|---|---|---|---|

## Indexing
| Issue | Severity | Pages Affected | Fix |
|---|---|---|---|

## Core Web Vitals
| Metric | Current | Target | Fix Priority |
|---|---|---|---|

## Structured Data
| Page Type | Current Schema | Recommended | Rich Result Eligible |
|---|---|---|---|

## Site Architecture
- [Issues and recommendations]

## Prioritized Action Plan
| Priority | Issue | Impact | Effort | Owner |
|---|---|---|---|---|

## Quick Wins (< 1 hour each)
1. [Fix] — Expected impact: [metric]
```

## Platform Implementation Steps

### Google Search Console
1. Review Coverage report → Export errors and excluded pages
2. Check Core Web Vitals report for field data
3. Submit updated sitemap after fixes
4. Use URL Inspection tool to verify individual page fixes
5. Monitor index coverage trends weekly after changes

### Screaming Frog / Sitebulb
1. Run full site crawl with JavaScript rendering enabled
2. Export: response codes, canonical tags, meta robots, page titles, H1s
3. Filter for issues: 4xx/5xx errors, duplicate titles, missing H1s, orphan pages
4. Re-crawl after fixes to verify resolution

### CMS-Specific (WordPress)
1. Install Yoast SEO or Rank Math for meta tag management
2. Use WP Rocket or LiteSpeed Cache for Core Web Vitals
3. Generate XML sitemap via SEO plugin
4. Configure robots.txt via SEO plugin settings

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Accidental deindexing | Wrong noindex or robots.txt change | Revert immediately; request reindexing in GSC |
| CWV regression after fix | New code introduced layout shift or blocking resources | Roll back; test CWV in staging before deploying |
| Crawl budget wasted | Too many low-value pages in sitemap | Remove thin/duplicate pages from sitemap; use noindex strategically |
| Structured data errors | Invalid markup implementation | Validate with Google Rich Results Test before deploying |

## How to Get Your Data

- **Google Search Console**: Search Console → Coverage → Export; Performance → Export
- **Screaming Frog**: Crawl your site → Export all data as CSV
- **PageSpeed Insights**: Run at web.dev/measure → paste scores
- **No tools**: Describe your site (CMS, page count, main issues) — Claude audits against best practices

## Example

**Input**: "Technical SEO audit for an e-commerce site (Shopify, 5,000 product pages). Issues: many products not indexed, slow page speed on collection pages, no structured data. GSC shows 2,100 indexed out of 5,000."

**Output**: Critical: 2,900 pages not indexed — causes: (1) thin product descriptions (<100 words) on 1,800 pages, (2) faceted navigation creating duplicate URLs blocked by robots.txt but still linked, (3) collection pages have canonical pointing to wrong URLs. Core Web Vitals: LCP 4.2s on collection pages (target <2.5s) — fix: lazy-load below-fold product images, preload hero image, defer non-critical JS. Structured data: add Product schema to all product pages (price, availability, reviews), BreadcrumbList to all pages, Organization to homepage. Quick wins: (1) fix canonical tags on collection pages (30 min), (2) add Product schema via Shopify JSON-LD snippet (1 hour), (3) compress hero images (20 min). Priority plan: Week 1 — canonicals and schema; Week 2 — image optimization; Week 3-4 — expand thin product descriptions.
