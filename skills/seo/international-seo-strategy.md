---
name: international-seo-strategy
description: >
  Build an international SEO strategy — hreflang implementation, multi-language content, and geo-targeting.
  Use this skill when the user says "international SEO strategy", "hreflang implementation",
  "multi-language SEO", "geo-targeting SEO", "multi-region SEO", "global SEO strategy",
  "localization SEO", "ccTLD vs subdomain vs subfolder", "international keyword research",
  "multilingual content strategy", or "country-specific SEO". Also trigger for hreflang
  audit, international site structure, or cross-border search optimization.
---

# International SEO Strategy

Creates international SEO strategies with site structure decisions, hreflang implementation, multi-language keyword research, and geo-targeting configuration for global search visibility.

## Granularity Check

> **Time**: ~5 min data prep → ~10 min Claude session → ~30-60 min implementation in Google Search Console / CMS. If implementing, add 5-20 hours for hreflang and content localization. Input is target markets and current site structure. Output is Markdown international SEO plan with technical specifications.

## User Intent Mapping

- "We're expanding to new markets — how do we handle SEO?" (expansion)
- "Implement hreflang tags for our multi-language site" (technical)
- "Should we use subdomains or subfolders for country sites?" (structure)
- "International keyword research for [country]" (keywords)
- "Our content is in 3 languages but we're not ranking locally" (diagnosis)
- "Hreflang audit — we have errors in GSC" (audit)
- "Localization vs. translation for SEO" (content strategy)
- "Geo-targeting strategy for our SaaS" (targeting)
- "ccTLD strategy for European markets" (domain strategy)
- "Multi-region content strategy" (content)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Current Site | Text | Domain, structure, languages currently supported |
| Target Markets | Text list | Countries/regions and languages to target |
| Business Model | Text | SaaS, e-commerce, content, services — affects structure |

### If You Don't Have This Data

- **No international presence yet?** Describe your target markets. Claude designs the site structure and implementation plan from scratch.
- **No local keyword data?** Claude identifies the right keyword research approach for each market. Start with translating top 20 English keywords and checking local volume.
- **No hreflang experience?** Claude provides exact hreflang tag code ready for implementation. Use the hreflang tag generator tool for validation.
- **No localization budget?** Claude prioritizes markets and recommends phased rollout starting with highest-opportunity markets.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Current Traffic by Country | CSV | GSC or GA4 geographic data |
| Existing Translations | Text | What content exists in other languages |
| Competitor International Presence | Text | How competitors handle international SEO |
| Budget Constraints | Text | Resources for localization and content |
| Local Teams | Text | In-country teams or partners available |

## Process

### Step 1: Market Prioritization
- Search demand analysis per target market
- Competitive landscape per country (different competitors in different markets)
- Business readiness assessment (payment, fulfillment, support)
- Language vs. country targeting decision
- Phased rollout recommendation

### Step 2: Site Structure Decision
| Structure | Pros | Cons | Best For |
|---|---|---|---|
| ccTLDs (.de, .fr) | Strongest geo signal | Separate domains, split authority | Large companies with local entities |
| Subdomains (de.site.com) | Easy to set up | Weaker geo signal, may split authority | Medium-sized international expansions |
| Subfolders (site.com/de/) | Consolidated authority | Requires strong hosting | Most SaaS and content sites |
| Parameters (site.com?lang=de) | Easy to implement | Weakest signal, hard to target | Not recommended for SEO |

### Step 3: Hreflang Implementation
- Correct hreflang tag format: `<link rel="alternate" hreflang="xx-YY" href="URL" />`
- Self-referencing hreflang tags (every page references itself)
- x-default tag for unmatched languages
- Bidirectional hreflang (if page A references page B, page B must reference page A)
- Implementation method: HTML head, HTTP header, or XML sitemap

### Step 4: Content Localization Strategy
- Translation vs. localization vs. transcreation
- Keyword-first localization (research local keywords before translating)
- Cultural adaptation (images, examples, currency, units)
- Local content creation (market-specific topics and trends)
- User-generated content in local language

### Step 5: Technical Implementation
- Geotargeting in GSC (for subfolders/subdomains)
- Language-specific XML sitemaps
- CDN and hosting for local page speed
- Local structured data (currency, language, country)
- Canonical tag strategy across language versions

### Step 6: Local Link Building & Citations
- Country-specific directory submissions
- Local media and PR outreach
- Local business partnerships and sponsorships
- Country-specific social platforms

### Confidence & Sample Size
> **Confidence Note**: International SEO takes 6-12 months to show results in new markets. Hreflang implementation is the most error-prone technical SEO element — validate thoroughly. Direct translation without local keyword research often targets wrong terms. Each market should be evaluated independently — what works in Germany may not work in Japan.

### ⚠️ Human Checkpoint
> Have native speakers review all localized content and keyword targeting. Verify hreflang tags with a validation tool before deployment. Confirm business readiness (payment, legal, support) before launching in new markets.

> **Benchmark Context**: See Semrush 2024 State of Search for current industry benchmarks relevant to this analysis.
## Output Contract

### Deliverable: Markdown International SEO Plan

```markdown
# International SEO Strategy: [Brand]

## Market Prioritization
| Market | Language | Search Demand | Competition | Priority |
|---|---|---|---|---|

## Site Structure
- Recommended: [structure]
- URL pattern: [pattern]
- Rationale: [why]

## Hreflang Implementation
| Page | Hreflang Tags |
|---|---|

## Content Localization Plan
| Market | Content Type | Approach | Timeline |
|---|---|---|---|

## Technical Checklist
- [ ] [Implementation item]

## Local SEO by Market
| Market | Directories | Link Targets | Local Content |
|---|---|---|---|

## Rollout Timeline
| Phase | Markets | Actions | Duration |
|---|---|---|---|
```

## Platform Implementation Steps

### CMS Configuration
1. Set up language/region versions (subfolder or subdomain based on recommendation)
2. Implement hreflang tags in page templates (or via SEO plugin)
3. Create language-specific XML sitemaps
4. Configure language switcher (user-facing, not for SEO)
5. Set up geotargeting in Google Search Console per property

### Translation & Localization
1. Export content for translation (CMS export or content inventory)
2. Keyword research per market BEFORE translating
3. Localize, don't just translate — adapt examples, currency, cultural references
4. Native speaker QA on all localized content
5. Implement localized structured data (local currency, language markup)

### Monitoring
1. Set up GSC properties per country/language version
2. Track rankings per market with local rank tracking (Ahrefs, Semrush)
3. Monitor hreflang errors in GSC → International Targeting
4. Compare traffic and conversion rates per market monthly

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Hreflang errors in GSC | Missing bidirectional tags or wrong language codes | Audit with hreflang validator; fix tag pairs |
| Wrong language version ranking | Missing or incorrect hreflang implementation | Verify self-referencing tags; check canonical tags |
| Translated content doesn't rank | Keywords translated literally, not researched locally | Redo keyword research with native speaker; localize content |
| Duplicate content across languages | Missing hreflang or canonical confusion | Implement complete hreflang set; verify canonical tags |

## How to Get Your Data

- **Traffic by country**: GA4 → Reports → Demographics → Country; GSC → Performance → Countries
- **Local keyword volumes**: Ahrefs/Semrush → set country filter → check local volumes
- **Hreflang validation**: Use hreflang.org or Screaming Frog hreflang audit
- **No data**: Describe target markets — Claude designs the strategy from best practices

## Example

**Input**: "International SEO strategy for a SaaS product. Currently English-only (US). Want to expand to Germany, France, Japan, and Brazil. 200-page site including 80 blog posts. Subfolder structure preferred."

**Output**: Market priority: Germany (highest SaaS adoption in EU), France, Brazil, Japan (highest localization effort). Structure: subfolders — site.com/de/, site.com/fr/, site.com/ja/, site.com/pt-br/. Phase 1 (months 1-3): Germany — localize top 20 product pages + 10 highest-traffic blog posts; implement full hreflang. Phase 2 (months 3-6): France — same approach. Phase 3 (months 6-9): Brazil and Japan simultaneously. Content approach: keyword-first localization — research German SaaS keywords before translating (e.g., "Projektmanagement-Software" not "project management software"). Hreflang implementation: HTML head tags on all pages, 5 versions per page (en, de, fr, ja, pt-BR + x-default → en). Technical: deploy CDN with edge nodes in Frankfurt, Paris, Tokyo, São Paulo for local page speed. Quick win: add hreflang for existing English pages immediately (establishes x-default before other languages launch).

## Related Skills

- **[Content Localization Planner](../content/content-localization-planner.md)** — Use to plan content translation and cultural adaptation for the international markets in your SEO strategy.
- **[Technical SEO Auditor](./technical-seo-auditor.md)** — Use to implement hreflang tags, language targeting, and ensure proper multi-language site structure.
- **[SEO Content Strategy](./seo-content-strategy.md)** — Use to build region-specific content strategies and keyword targeting for different markets.
- **[Local SEO Optimizer](./local-seo-optimizer.md)** — Use for country-specific local optimization (Google Business Profiles, local citations, geo-targeting).
