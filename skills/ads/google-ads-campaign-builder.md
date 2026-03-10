---
name: google-ads-campaign-builder
description: >
  Structure a complete Google Ads campaign with ad groups, keywords, match types, negatives, bid
  strategy, and ad copy. Use this skill whenever the user mentions Google Ads campaign, Google Ads
  setup, PPC campaign structure, search ads campaign, ad group structure, keyword match types,
  Google Ads account structure, "set up Google Ads", "build a search campaign", "structure my
  Google Ads", RSA copy, responsive search ads, "plan my PPC", Google Ads keyword strategy,
  campaign hierarchy, ad group organization, or any request to plan or build a Google Ads search
  campaign from scratch. Also trigger on "help me set up paid search" or "create a Google Ads plan".
---

# Google Ads Campaign Builder

Structure a complete Google Ads search campaign from scratch: campaign settings, ad group hierarchy, keyword lists with match types, negative keywords, responsive search ad copy, bid strategy, and budget recommendations.

## Granularity Check

> Can this be completed in a single Claude session? **Yes — expect ~5 min data prep → ~10 min Claude session → ~30-60 min building in Google Ads / Meta Ads Manager.** If implementing output in a platform, add 10-20 min for setup. Input is business context + target keywords. Output is a complete campaign structure in XLSX ready for Google Ads Editor import.

## User Intent Mapping

Trigger when the user says:

- "Build a Google Ads campaign for my product" (direct request)
- "Structure my PPC campaign" (campaign architecture)
- "Set up search ads for [keyword]" (keyword-specific)
- "Create ad groups for my Google Ads" (structural)
- "What match types should I use?" (strategy question)
- "Write RSA headlines and descriptions" (ad copy)
- "Plan my Google Ads account structure" (account planning)
- "I'm launching Google Ads for the first time" (new advertiser)
- "Organize my keywords into ad groups" (grouping)
- "Build a campaign with negative keywords" (comprehensive)

## Input Contract

### Required Input

| Field | Type | Description |
|---|---|---|
| `product_or_service` | string | What you're advertising |
| `target_keywords` | list or CSV | Keywords to target (or seed keywords to expand) |
| `landing_page_url` | string | Where ads will send traffic |

### If You Don't Have This Data

- **No product description?** Write 2-3 sentences about what you sell, who buys it, and why they choose you over alternatives.
- **No target audience?** Start with your last 10 customers — what do they have in common? Use that as your audience.
- **No performance data?** That's fine — this skill generates fresh copy from scratch. Performance data only helps with optimization iterations.
- **No competitor info?** Search your primary keyword on Google — the ads that appear are your competitors. Note their headlines.

### Optional Input

| Field | Type | Default | Description |
|---|---|---|---|
| `monthly_budget` | float | Not set | Budget in USD |
| `target_location` | string | United States | Geographic targeting |
| `campaign_goal` | string | Conversions | Conversions / Leads / Traffic / Brand awareness |
| `competitors` | list | null | Competitor names (for conquest campaigns) |
| `existing_keywords` | CSV | null | Current keyword data with performance |
| `industry` | string | Inferred | Industry vertical for benchmarks |
| `bid_strategy` | string | Maximize conversions | Preferred bidding approach |
| `brand_terms` | list | null | Brand keywords (separate campaign recommended) |

### Sample Input

```
Product: Project management SaaS ($29-99/month plans)
Target keywords: project management software, PM tools, task management app, team collaboration software
Landing page: https://example.com/free-trial
Monthly budget: $5,000
Target location: US + Canada
Goal: Free trial sign-ups
```

### Input Validation Rules

1. At least 5 seed keywords recommended (warn if fewer)
2. Landing page URL required — campaign performance depends on page quality
3. If budget provided, calculate estimated click volume and keyword feasibility
4. Flag any keywords that are too broad for the budget (e.g., single-word terms with $50+ CPCs)

## Process

1. **Expand keywords** — From seed keywords, generate 30-80 related keywords organized by theme. Group by:
   - Intent (commercial, informational, navigational)
   - Funnel stage (awareness, consideration, decision)
   - Specificity (head terms, mid-tail, long-tail)

2. **Structure ad groups** — Create 5-10 ad groups, each containing 5-15 tightly themed keywords:
   - SKAG alternative: Themed Ad Groups (TAGs) with 5-15 related keywords
   - Each ad group shares a common intent and can be served by the same ad copy
   - Name convention: `[Campaign]_[Theme]_[Intent]`

3. **Assign match types** — For each keyword:
   - **Exact match** `[keyword]` — High-intent, high-volume keywords
   - **Phrase match** `"keyword"` — Mid-volume, capturing variations
   - **Broad match** `keyword` — Only with smart bidding and sufficient conversion data
   - Recommend starting with exact + phrase, adding broad after 30+ conversions

4. **Build negative keyword list** — Generate 20-50 negatives:
   - Universal negatives (free, cheap, jobs, salary, how to, DIY, reddit, review)
   - Industry-specific negatives
   - Cross-ad-group negatives (prevent internal competition)

5. **Write RSA ad copy** — Per ad group:
   - 15 headlines (30 char limit each): mix keyword-containing, benefit-driven, CTA, social proof
   - 4 descriptions (90 char limit each): value prop, features, CTA, trust signal
   - Pin headline 1 (keyword) and headline 2 (benefit) for message consistency
   - Ensure at least 3 unique headlines contain the target keyword

6. **Set campaign parameters:**
   - Bid strategy recommendation based on goal and budget
   - Budget allocation across ad groups (proportional to opportunity)
   - Ad schedule (if data suggests optimal times)
   - Device targeting recommendations
   - Ad extensions: sitelinks (4), callouts (4), structured snippets, call extension

7. **Human checkpoint** — Present campaign structure overview. Ask: "Does this ad group structure make sense? Any keywords to add/remove?"

8. **Generate structured output** — Data tables in Markdown with step-by-step instructions to paste into Google Sheets or Excel for formatting.


> **Benchmark Context**: Average Google Ads CTR across industries is 3.17% (search) and 0.46% (display) (WordStream 2024 Industry Benchmarks). B2B averages 2.41% search CTR (LinkedIn 2024 B2B Marketing Benchmark). Top-performing responsive search ads have 8+ unique headlines. Meta Ads average CTR is 0.90% across industries, with 1.5%+ considered strong (Meta 2024 Advertising Benchmarks). (Google Ads 2024 Performance Benchmarks)


### Confidence & Sample Size.
> **Confidence Note**: Results are only as reliable as your input data. Small datasets (<50 records or <30 days of data) produce directional insights, not statistically significant conclusions. Always note your sample size when sharing results with stakeholders. Recommendations should be validated with A/B testing or additional data before making major strategic changes.

## Output Contract

### Output Format

| Output | Format | Contents |
|---|---|---|
| Campaign structure | Markdown tables + CSV-ready data | Four data sections: ad groups, keywords, ads, negatives — paste into Google Sheets or Excel for formatting |
| Campaign summary | Markdown | Overview + recommendations |

### Sheet 1: Ad Group Structure

| Column | Type | Description |
|---|---|---|
| `campaign_name` | string | Campaign identifier |
| `ad_group` | string | Ad group name |
| `theme` | string | Thematic focus |
| `intent` | string | Commercial / Informational / Transactional |
| `keyword_count` | integer | Keywords in group |
| `est_monthly_searches` | integer | Combined volume |
| `est_cpc` | float | Estimated cost per click |
| `budget_allocation_pct` | float | % of budget recommended |

### Sheet 2: Keywords

| Column | Type | Description |
|---|---|---|
| `ad_group` | string | Parent ad group |
| `keyword` | string | The keyword text |
| `match_type` | string | Exact / Phrase / Broad |
| `est_search_volume` | integer | Monthly volume |
| `est_cpc` | float | Expected CPC |
| `competition` | string | High / Medium / Low |

### Sheet 3: Ad Copy (RSA)

| Column | Type | Description |
|---|---|---|
| `ad_group` | string | Parent ad group |
| `headline_1` | string | Pinned headline (keyword) |
| `headline_2` | string | Pinned headline (benefit) |
| `headline_3` through `headline_15` | string | Additional headlines |
| `description_1` | string | Primary description |
| `description_2` | string | Secondary description |
| `description_3` | string | Tertiary description |
| `description_4` | string | Quaternary description |
| `final_url` | string | Landing page URL |
| `path_1` | string | Display URL path 1 |
| `path_2` | string | Display URL path 2 |

### Sheet 4: Negative Keywords

| Column | Type | Description |
|---|---|---|
| `level` | string | Campaign / Ad Group |
| `ad_group` | string | Specific ad group (if ad group level) |
| `keyword` | string | Negative keyword |
| `match_type` | string | Exact / Phrase / Broad |
| `reason` | string | Why it's negative |

## Platform Implementation Steps

### Google Ads
1. Navigate to Google Ads → Campaigns → select your campaign → Ads & Assets
2. Click "+" to add new responsive search ad
3. Paste headlines into the 15 headline slots (one per slot)
4. Paste descriptions into the 4 description slots
5. Use "Ad Strength" indicator to verify — aim for "Good" or "Excellent"

### Meta Ads Manager
1. Open Meta Business Suite → Ads Manager → select campaign
2. At Ad level, click "Edit" on your ad
3. Paste Primary Text, Headline, and Description into respective fields
4. Preview across placements (Feed, Stories, Reels) before publishing

### LinkedIn Campaign Manager
1. Open Campaign Manager → select campaign → Ads tab
2. Click "Create new ad" → Single Image Ad or other format
3. Paste Introductory Text, Headline, and Description
4. Preview on both desktop and mobile before saving

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Keywords too broad | Single-word terms | Suggest long-tail variations; set as phrase/exact only |
| Budget too low for keywords | High-CPC industry | Focus on long-tail, lower-competition keywords |
| Too few keywords (<5) | Limited input | Expand from seed keywords using related terms |
| Competing with own organic rankings | Brand terms bidding | Recommend separate brand vs non-brand campaigns |
| No conversion tracking | New account | Strongly recommend setting up conversion tracking before spending |
| Very niche industry | Few keywords exist | Focus on broader awareness campaigns; suggest Display/YouTube |

## How to Get Your Data

### From Google Keyword Planner

1. Google Ads → Tools → Keyword Planner → "Discover new keywords"
2. Enter seed keywords or competitor URL
3. Download keyword ideas as CSV
4. Upload to Claude

### From SEMrush/Ahrefs PPC Data

1. Export competitor's paid keywords (Advertising Research)
2. CSV with keyword, CPC, competition data
3. Upload to Claude for campaign structuring

### From Scratch

1. Tell Claude your product, target audience, and budget
2. Provide 5-10 seed keywords
3. Claude expands and structures the full campaign

## Example

**User prompt:** "Build a Google Ads campaign for my project management SaaS. Budget: $5,000/month. Target: US businesses. Goal: free trial sign-ups."

**Claude responds:**

> Here's your campaign structure:
>
> **Campaign:** PM_Software_Search_US
> **Budget:** $5,000/month (~$167/day)
> **Bid strategy:** Maximize conversions (switch to Target CPA after 30 conversions)
>
> | Ad Group | Keywords | Est. CPC | Budget % |
> |---|---|---|---|
> | PM_Software_General | 12 keywords (project management software, PM tools...) | $4.20 | 30% |
> | PM_SmallTeams | 10 keywords (PM for small teams, startup PM tool...) | $3.10 | 20% |
> | PM_Comparison | 8 keywords (best PM software, PM tool comparison...) | $5.50 | 20% |
> | TaskMgmt | 10 keywords (task management app, task tracker...) | $2.80 | 15% |
> | PM_Features | 8 keywords (gantt chart software, kanban board app...) | $3.40 | 15% |
>
> **Total keywords:** 48 (exact + phrase match)
> **Negative keywords:** 35 (including: free, open source, jobs, salary, certification)
> **RSA ads:** 5 (one per ad group), each with 15 headlines + 4 descriptions
>
> Estimated monthly performance: 1,100-1,400 clicks, $3.60-4.50 avg CPC
>
> Want me to generate the full XLSX with all keywords, ad copy, and negatives?

## Related Skills

- **[ppc-keyword-strategy](./ppc-keyword-strategy.md)** — Refine your keyword strategy with match types and negative keywords after building the campaign structure.
- **[ad-copy-generator](./ad-copy-generator.md)** — Generate additional RSA headline and description variants to improve ad strength.
- **[landing-page-ad-matcher](./landing-page-ad-matcher.md)** — Ensure your landing pages align with your ad group themes for quality score optimization.
- **[ad-performance-analyzer](./ad-performance-analyzer.md)** — Analyze campaign performance after launch to optimize ad groups and keywords.
