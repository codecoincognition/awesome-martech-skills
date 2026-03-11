---
name: content-localization-planner
description: >
  Plan content localization and translation for international markets — language, cultural adaptation, and workflow.
  Use this skill when the user says "content localization", "content translation strategy",
  "international content plan", "multilingual content strategy", "content for global markets",
  "cultural adaptation of content", "translation workflow", "localization priority matrix",
  "which content to translate first", "localization budget planning", or "global content operations".
  Also trigger for transcreation strategy, locale-specific content, or translation management.
---

# Content Localization Planner

Plans content localization strategy for international markets — prioritizing which content to localize, cultural adaptation requirements, translation workflows, and quality assurance processes.

## Granularity Check

> **Time**: ~5 min data prep → ~10 min Claude session → ~30-60 min implementing in your CMS. If implementing, add variable time for translation/adaptation. Input is content inventory and target markets. Output is Markdown localization plan with prioritization matrix.

## User Intent Mapping

- "Which content should we translate first?" (prioritization)
- "Content localization strategy for EMEA" (regional)
- "Multilingual content workflow" (process)
- "Localization budget planning" (budget)
- "Cultural adaptation for our content" (cultural)
- "Translation vs. transcreation — what do we need?" (approach)
- "Global content operations" (operations)
- "Localization quality assurance" (QA)
- "Content for Japanese market" (market-specific)
- "How to scale content localization" (scaling)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Target Markets | Text | Countries or regions to localize for |
| Content Inventory | Text/CSV | Content to consider for localization |
| Business Priority | Text | Which markets matter most for revenue |

### If You Don't Have This Data

- **Not sure which markets?** Claude uses your website traffic by country (Google Analytics) to identify highest-opportunity markets.
- **No content inventory?** Claude starts with your top 20 pages by traffic and works from there.
- **No localization budget?** Claude provides a tiered approach from free (machine translation + human review) to full transcreation.
- **No translation team?** Claude recommends vendor options from budget freelancers to enterprise LSPs.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| International Traffic | CSV | Traffic by country/language from analytics |
| Revenue by Market | Text | Current or projected revenue per market |
| Existing Translations | Text | What's already been translated |
| Brand Guidelines | Text | Voice/tone guidelines per market |
| Competitor Localization | Text | How competitors approach localization |

## Process

### Step 1: Market Prioritization
| Factor | Weight | Assessment |
|---|---|---|
| Revenue potential | 30% | Current + projected revenue per market |
| Traffic volume | 25% | Existing organic traffic from that market |
| Competition | 20% | Competitor localization coverage |
| Effort | 15% | Language complexity, cultural distance |
| Strategic importance | 10% | Market expansion plans |

### Step 2: Localization Approach
| Approach | When to Use | Quality | Cost |
|---|---|---|---|
| Machine translation | Internal docs, low-priority pages | Low-medium | Very low |
| MT + human review | Support content, help docs | Medium | Low |
| Professional translation | Marketing content, product pages | High | Medium |
| Transcreation | Brand campaigns, taglines, CTAs | Very high | High |
| Local creation | Market-specific content, cultural pieces | Highest | Highest |

### Step 3: Content Prioritization Matrix
- **Tier 1 (translate first)**: Homepage, product pages, pricing, signup flow — direct revenue impact
- **Tier 2**: Top 10 blog posts by traffic, help documentation, email templates
- **Tier 3**: Secondary blog content, social templates, case studies
- **Tier 4**: All remaining content, niche blog posts, archived content

### Step 4: Cultural Adaptation Checklist
- Currency and pricing format
- Date and time format
- Imagery and color associations
- Humor, idioms, and cultural references
- Legal and regulatory differences
- Payment methods and trust signals
- Social proof relevant to that market
- Local competitor references

### Step 5: Workflow Design
1. Content selection and prioritization
2. Source content preparation (remove culturally specific elements)
3. Translation/transcreation by qualified linguists
4. In-country review by native speaker
5. QA (functional testing, layout check, link verification)
6. Publication and SEO optimization (hreflang, local keywords)
7. Performance monitoring and iteration

### Confidence & Sample Size

> **Confidence Note**: Localization ROI varies dramatically by market maturity and product fit. Machine translation quality has improved significantly but still produces errors in marketing copy — always have a human review customer-facing content. Keyword research must be done natively per language, not translated from English. Cultural missteps can damage brand trust — invest in in-market reviewers.

### ⚠️ Human Checkpoint
> Have in-market native speakers review all localized content before publication. Verify legal/regulatory compliance per market. Test all localized user flows end-to-end.

> **Benchmark Context**: Consult current industry reports for up-to-date benchmarks relevant to this analysis.

## Output Contract

### Deliverable: Markdown Localization Plan

```markdown
# Content Localization Plan: [Markets]

## Market Prioritization
| Market | Language | Revenue Potential | Traffic | Priority | Approach |
|---|---|---|---|---|---|

## Content Prioritization
### Tier 1: Immediate
| Content | Type | Approach | Est. Cost | Timeline |
|---|---|---|---|---|

### Tier 2: Next Quarter
| Content | Type | Approach | Est. Cost | Timeline |
|---|---|---|---|---|

## Cultural Adaptation Notes
### [Market]
- Key adaptations: [list]
- Avoid: [cultural pitfalls]
- Opportunities: [market-specific angles]

## Workflow
| Step | Owner | Tool | Timeline |
|---|---|---|---|

## Budget Summary
| Market | Content Volume | Approach | Total Cost |
|---|---|---|---|

## Measurement
| Market | Metric | Baseline | Target |
|---|---|---|---|
```

## Platform Implementation Steps

### CMS Setup
1. Enable multi-language support (WordPress WPML, Webflow Localization, etc.)
2. Configure hreflang tags for all language versions
3. Set up language switcher in navigation
4. Create locale-specific URL structure (subdirectory or subdomain)

### Translation Management
1. Set up TMS (Phrase, Lokalise, Smartling, or Crowdin)
2. Create translation memory and glossary per language
3. Integrate TMS with CMS for automated content sync
4. Establish review workflow with in-market reviewers

### SEO
1. Research keywords natively per target language (not translations)
2. Optimize meta titles and descriptions per locale
3. Submit localized sitemaps to search engines
4. Build local backlinks per market

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Poor translation quality | Machine translation without human review | Add native speaker review step; invest in professional translation for key pages |
| Cultural misstep | Direct translation without cultural adaptation | Engage in-market reviewers; create cultural adaptation guidelines per market |
| No SEO impact | Translated English keywords instead of native keyword research | Conduct native keyword research per market; optimize for local search intent |
| Budget overrun | Underestimated volume or revision cycles | Start with Tier 1 content only; establish clear revision limits per project |

## How to Get Your Data

- **International traffic**: Google Analytics → Audience → Geo → Language/Country
- **Revenue by market**: CRM or payment platform → filter by country
- **Content inventory**: CMS → export all published pages with traffic data
- **No data**: Share your target markets and top content — Claude creates a starter localization plan

## Example

**Input**: "Content localization plan. B2B SaaS with growing DACH and France markets. Currently English-only. 200 blog posts, 15 product pages, help docs. Google Analytics shows 18% traffic from Germany, 8% from France. No localization budget yet."

**Output**: Priority: DACH first (18% traffic, larger addressable market), then France. Approach: Tier 1 (now) — professional translation of 15 product pages + pricing + signup flow into German (est. $8-12K). Use machine translation + human review for top 20 help docs ($2-3K). Tier 2 (quarter 2) — translate top 10 blog posts by German organic traffic potential (native keyword research required). Tier 3 (quarter 3) — begin French localization of Tier 1 content. Cultural notes: DACH — formal tone (Sie, not du), data privacy emphasis (GDPR prominence), local payment methods, case studies from DACH companies. France — formal tone, metric units, French-specific compliance references. Quick win: add German language option with top 15 product pages — expected 25-40% conversion lift from German visitors. Budget: Phase 1 (DACH product pages + help docs) = $10-15K. Full year plan across DACH + France = $40-60K.

## Related Skills

- **[International SEO Strategy](../seo/international-seo-strategy.md)** — Use to plan language-specific SEO strategy and technical implementation for localized content.
- **[Content Governance Framework](./content-governance-framework.md)** — Use to establish standards and workflows for localizing content across multiple languages and regions.
- **[Editorial Calendar Builder](./editorial-calendar-builder.md)** — Use to plan content creation and localization timelines for each market.
- **[Local SEO Optimizer](../seo/local-seo-optimizer.md)** — Use for region-specific optimization of localized content and market targeting.
