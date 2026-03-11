---
name: ppc-keyword-strategy
description: >
  Build PPC keyword strategies with match types, negative keywords, and bid recommendations.
  Use this skill when the user says "PPC keyword strategy", "Google Ads keyword plan", "search
  ad keywords", "keyword match type strategy", "negative keyword list", "PPC keyword research",
  "search campaign keywords", "keyword bidding strategy", "broad match vs exact match",
  "keyword grouping for ads", or "search term analysis". Also trigger for keyword expansion,
  search query mining, or PPC keyword audit.
---

# PPC Keyword Strategy

Builds comprehensive PPC keyword strategies with keyword grouping, match type recommendations, negative keyword lists, bid strategy, and search query mining workflows.

## Granularity Check

> **Time**: ~5 min data prep → ~10 min Claude session → ~30-60 min building in Google Ads / Meta Ads Manager. If implementing output in Google Ads, add 20-30 min for campaign setup. Input is product/service info and optional search term data. Output is Markdown keyword strategy with grouped keyword lists.

## User Intent Mapping

- "Build a keyword strategy for our Google Ads" (full strategy)
- "Which match types should I use?" (match type guidance)
- "Create a negative keyword list" (negatives)
- "Analyze our search terms report" (optimization)
- "Expand our keyword coverage" (expansion)
- "Our CPC is too high — keyword strategy help" (cost optimization)
- "Keyword grouping for ad relevance" (structure)
- "Brand vs. non-brand keyword strategy" (segmentation)
- "Long-tail keyword opportunities" (discovery)
- "Competitor keyword targeting" (competitive)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Product/Service | Text | What you're advertising |
| Target Audience | Text | Who you're trying to reach |
| Business Goal | Text | Leads, sales, sign-ups, calls |

### If You Don't Have This Data

- **No existing keyword data?** Describe your product in 3-5 sentences. Claude generates seed keywords from the description.
- **No search terms report?** This is available in Google Ads after running campaigns for 7+ days. Start with Claude's keyword strategy and mine search terms after launch.
- **No competitor keywords?** Use Google search: type your product category and note the ads that appear. Check their landing pages for keyword clues.
- **No budget info?** Claude builds the strategy budget-agnostic. Prioritize keywords by estimated search volume and competition level.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Search Terms Report | CSV | From Google Ads: search term, impressions, clicks, conversions, cost |
| Current Keywords | CSV | Existing keyword list with performance data |
| Competitor URLs | Text | Landing pages of competing advertisers |
| Monthly Budget | Number | For bid strategy recommendations |
| Geographic Target | Text | Location targeting for local relevance |

## Process

### Step 1: Keyword Research
Generate keywords across intent tiers:

| Intent Tier | Description | Example | Expected CPA |
|---|---|---|---|
| Brand | Your brand name | "[brand] pricing" | Lowest |
| High Intent | Ready to buy/act | "buy [product]", "[product] demo" | Low |
| Comparison | Evaluating options | "[product] vs [competitor]", "best [category]" | Medium |
| Solution | Problem-aware | "how to [solve problem]", "[problem] solution" | Medium-High |
| Informational | Research phase | "what is [category]", "[topic] guide" | Highest |

### Step 2: Keyword Grouping
Group keywords into tight ad groups (5-15 keywords per group):
- Each ad group = one theme = one set of ads
- Tighter grouping = higher Quality Score = lower CPC
- Naming convention: [Campaign]_[AdGroup]_[Theme]

### Step 3: Match Type Strategy
| Match Type | When to Use | Risk |
|---|---|---|
| Exact [keyword] | High-value, proven keywords | Limited reach |
| Phrase "keyword" | Core terms with modifiers | Moderate waste |
| Broad keyword | Discovery and expansion (with smart bidding) | Requires strong negatives |

Recommended approach:
- Start with exact + phrase match for proven keywords
- Add broad match only with automated bidding and robust negative lists
- Never run broad match with manual CPC bidding

### Step 4: Negative Keyword Lists
Build 4 negative keyword lists:
1. **Universal negatives**: free, cheap, DIY, jobs, salary, how to (if not relevant)
2. **Industry negatives**: Terms specific to your space that indicate wrong intent
3. **Competitor brand negatives**: (if not targeting competitors)
4. **Campaign-specific negatives**: Cross-negative between campaigns to control routing

### Step 5: Bid Strategy Recommendations
| Scenario | Bid Strategy | Why |
|---|---|---|
| New account, <50 conv/month | Maximize Clicks → transition to tCPA | Build conversion data first |
| 50+ conv/month | Target CPA or Target ROAS | Algorithm has enough data |
| High-value leads | Maximize Conversion Value | Optimize for quality, not volume |
| Brand campaigns | Manual CPC or Max Clicks with cap | Predictable, low CPC |

### Confidence & Sample Size
> **Confidence Note**: Keyword performance requires minimum 100 clicks before judging CPA reliability. New keywords need 2-4 weeks to establish Quality Score. Broad match keywords need 200+ clicks and strong negative lists before performance stabilizes. Always compare keyword CPA to customer LTV, not in isolation.

### ⚠️ Human Checkpoint
> Review keyword lists for brand safety (avoid bidding on sensitive terms), trademark compliance (competitor brand bidding rules), and negative keyword over-blocking (don't accidentally exclude good traffic).

> **Benchmark Context**: Consult current industry reports for up-to-date benchmarks relevant to this analysis.

## Output Contract

### Deliverable: Markdown Keyword Strategy

```markdown
# PPC Keyword Strategy: [Business]

## Keyword Architecture
| Campaign | Ad Group | Theme | Keywords | Match Type |
|---|---|---|---|---|

## Full Keyword List
### High Intent
| Keyword | Match Type | Est. Volume | Competition | Priority |
|---|---|---|---|---|

### Comparison
...

### Solution-Aware
...

## Negative Keyword Lists
### Universal Negatives
[keyword list]

### Industry Negatives
[keyword list]

## Bid Strategy
| Campaign | Strategy | Target CPA/ROAS |
|---|---|---|

## Search Query Mining SOP
1. [Step-by-step for weekly review]
```

## Platform Implementation Steps

### Google Ads
1. Create campaigns matching the architecture in the blueprint
2. Create ad groups with keyword themes
3. Add keywords with specified match types
4. Apply negative keyword lists at campaign and account level
5. Set bidding strategy per campaign
6. Write 3 responsive search ads per ad group (15 headlines, 4 descriptions)
7. Schedule weekly search terms review

### Google Ads Editor (Bulk Upload)
1. Download Google Ads Editor
2. Import keyword list from CSV or spreadsheet
3. Review and bulk-edit match types
4. Post changes to account
5. Use for large keyword builds (100+ keywords)

### Search Terms Mining Workflow
1. Google Ads → Keywords → Search Terms (weekly)
2. Sort by impressions or cost
3. Add converting terms as keywords
4. Add non-converting terms as negatives
5. Document changes in a log

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| High CPC on all keywords | Competitive industry or low Quality Score | Focus on long-tail; improve ad relevance and landing page |
| Impressions but no clicks | Poor ad copy or low ad rank | Rewrite ads to match search intent; increase bids |
| Clicks but no conversions | Wrong keyword intent or landing page mismatch | Audit search terms for intent; align landing page |
| Budget exhausted by noon | No ad scheduling or bid caps | Set ad schedule for business hours; add bid caps |

## How to Get Your Data

- **Google Ads**: Keywords → Search Terms → Download CSV
- **Google Keyword Planner**: Tools → Keyword Planner → Get search volume
- **No data**: Describe your product — Claude generates the full keyword strategy from scratch
- **Competitor research**: Google search your product category; note ad copy and landing pages

## Example

**Input**: "PPC keyword strategy for an online accounting software targeting small businesses. Goal: free trial signups. Budget: $5,000/month. Currently running broad match only with high CPA."

**Output**: 4-campaign structure: (1) Brand (exact match brand terms, manual CPC $0.50 cap); (2) High Intent (exact + phrase: "accounting software free trial", "small business accounting tool", "online bookkeeping software" — 25 keywords); (3) Comparison (exact: "quickbooks alternative", "xero vs [brand]" — 15 keywords); (4) Solution (phrase: "small business tax tracking", "invoice management software" — 20 keywords). Negative keyword lists: Universal (47 terms including free download, open source, jobs, internship), Industry (32 terms including enterprise, corporate, SAP, Oracle), Cross-campaign negatives (brand terms excluded from non-brand campaigns). Bid strategy: switch from broad match to exact + phrase, use target CPA bidding at $35. Projected impact: CPA reduction from $65 to $35-40 by eliminating irrelevant broad match traffic. Weekly search terms mining SOP included.

## Related Skills

- **[google-ads-campaign-builder](./google-ads-campaign-builder.md)** — Use this skill to structure your complete Google Ads campaign after defining keyword strategy.
- **[ad-performance-analyzer](./ad-performance-analyzer.md)** — Analyze keyword performance over time to identify top performers and optimization opportunities.
- **[ad-budget-optimizer](./ad-budget-optimizer.md)** — Allocate budget across keywords based on performance and CPA.
- **[landing-page-ad-matcher](./landing-page-ad-matcher.md)** — Ensure landing pages match keyword intent to improve Quality Score.
