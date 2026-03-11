---
name: meta-ads-campaign-builder
description: >
  Structure Meta (Facebook + Instagram) ad campaigns end-to-end — campaign structure, audience targeting, and budget allocation.
  Use this skill when the user says "Meta ads campaign", "Facebook ads setup", "Instagram ads campaign",
  "Meta campaign structure", "Facebook ad targeting", "Meta ads budget", "Advantage+ campaign",
  "Facebook lookalike audience", "Meta conversion campaign", "Instagram ad campaign builder",
  or "Facebook ads account structure". Also trigger for Meta ad audit, campaign restructuring,
  or Advantage+ Shopping setup.
---

# Meta Ads Campaign Builder

Structures complete Meta (Facebook + Instagram) ad campaigns with campaign/ad set/ad hierarchy, audience targeting, budget allocation, bidding strategy, and creative recommendations.

## Granularity Check

> **Time**: ~5 min data prep → ~10 min Claude session → ~30-60 min building in Google Ads / Meta Ads Manager. If implementing output in Meta Ads Manager, add 30-45 min for setup. Input is business goals and targeting info. Output is Markdown campaign blueprint.

## User Intent Mapping

- "Build a Meta ads campaign for our product launch" (full build)
- "How should I structure my Facebook ad account?" (account structure)
- "Set up Advantage+ Shopping campaigns" (specific format)
- "Our Meta ads aren't converting — audit our structure" (optimization)
- "Facebook lookalike audience strategy" (targeting)
- "Budget allocation across Meta campaigns" (budget)
- "Instagram ads for lead generation" (platform + objective)
- "Retargeting campaign setup on Facebook" (funnel stage)
- "Meta ads for e-commerce" (vertical-specific)
- "How to scale our Meta ad spend" (scaling)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Business/Product | Text | What you're advertising |
| Objective | Text | Sales, leads, traffic, awareness, app installs |
| Monthly Budget | Number | Total monthly Meta ad spend |

### If You Don't Have This Data

- **No Meta Pixel?** Install it first — go to Events Manager → Connect Data Sources → Web. Claude can guide post-setup.
- **No audience data?** Start with interest-based targeting. After 500 conversions, build lookalikes.
- **No creative assets?** Use Canva templates or UGC. The campaign structure works regardless of creative quality.
- **No conversion history?** Start with traffic or engagement campaigns to build data, then switch to conversions after 50+ events/week.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Target Audience | Text | Demographics, interests, behaviors |
| Current Performance | CSV | Campaign, spend, impressions, clicks, conversions, CPA |
| Website URL | Text | For Pixel verification and landing page alignment |
| Creative Assets | Text | What ads you have (video, image, carousel) |
| Competitor Info | Text | Key competitors for exclusion and research |

## Process

### Step 1: Campaign Structure
Design campaign hierarchy following Meta best practices:

| Level | Purpose | Recommendation |
|---|---|---|
| Campaign | Objective + budget | 3-5 campaigns max (1 per objective) |
| Ad Set | Audience + placement | 3-5 ad sets per campaign (consolidated) |
| Ad | Creative + copy | 3-6 ads per ad set (for testing) |

### Step 2: Audience Strategy
Build audience layers:
- **Prospecting**: Broad targeting, interest-based, lookalikes (1-5%)
- **Retargeting**: Website visitors (7/14/30/60/90 day), engaged users, video viewers
- **Retention**: Customer list, past purchasers, high-LTV segments
- **Exclusions**: Current customers (from prospecting), converted users, competitors' employees

### Step 3: Budget Allocation
- Prospecting: 60-70% of budget
- Retargeting: 20-30% of budget
- Testing: 10-15% of budget
- Use Campaign Budget Optimization (CBO) for automated allocation
- Minimum $20/day per ad set for learning phase

### Step 4: Bidding & Optimization
- Conversions < 50/week → Optimize for landing page views
- Conversions 50+/week → Optimize for purchases/leads
- Use lowest cost bidding to start, switch to cost cap after establishing CPA baseline
- Learning phase: 50 optimization events in 7 days to exit

### Step 5: Placement Strategy
- Start with Advantage+ Placements (automated)
- Review placement breakdown after 7 days
- Manually adjust if one placement dominates spend with poor performance
- Key placements: Feed, Stories, Reels, Audience Network (test)

### Confidence & Sample Size
> **Confidence Note**: Meta's algorithm needs 50+ conversion events per week per ad set to optimize effectively. Below this threshold, results are noisy. Don't make changes during the learning phase (first 50 events or 7 days). Account structure recommendations follow Meta's own 2024-2025 best practices but should be adapted to your specific business.

### ⚠️ Human Checkpoint
> Verify Pixel/Conversions API setup, confirm audience exclusions include existing customers (to avoid wasting spend), and review all ad copy for compliance with Meta Advertising Standards before launching.

> **Benchmark Context**: See Meta 2024 Advertising Benchmarks for current industry benchmarks relevant to this analysis.
## Output Contract

### Deliverable: Markdown Campaign Blueprint

```markdown
# Meta Ads Campaign Blueprint: [Business]

## Account Structure
| Campaign | Objective | Budget | Ad Sets |
|---|---|---|---|

## Audience Strategy
### Prospecting
- Audience 1: [targeting]
- Audience 2: [targeting]
### Retargeting
- [windows and segments]

## Budget Allocation
| Campaign | Daily Budget | Monthly Budget | % of Total |
|---|---|---|---|

## Ad Creative Recommendations
| Ad Set | Format | Quantity | Notes |
|---|---|---|---|

## Launch Checklist
- [ ] Pixel verified
- [ ] Audiences created
- [ ] Creative uploaded
- [ ] UTM parameters set
- [ ] Exclusions configured

## Week 1-4 Optimization Plan
| Week | Action | Metric to Watch |
|---|---|---|
```

## Platform Implementation Steps

### Meta Ads Manager
1. Go to adsmanager.facebook.com → Create Campaign
2. Select campaign objective matching the blueprint
3. Enable Campaign Budget Optimization (CBO)
4. Create ad sets with audiences from the blueprint
5. Upload creative and set copy per ad specifications
6. Set up UTM parameters: utm_source=meta&utm_medium=paid&utm_campaign=[name]
7. Review and publish

### Meta Events Manager (Pixel Setup)
1. Go to Events Manager → Connect Data Sources → Web
2. Install Pixel code or use partner integration (Shopify, WordPress, etc.)
3. Set up standard events: PageView, ViewContent, AddToCart, Purchase
4. Verify events are firing using the Test Events tool
5. Set up Conversions API for server-side tracking (recommended)

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Stuck in learning phase | Too many ad sets splitting budget | Consolidate ad sets; increase budget per ad set |
| High CPC, low conversions | Wrong objective or poor landing page | Switch optimization event; audit landing page |
| Ad account restricted | Policy violation | Review Meta Advertising Standards; appeal in Account Quality |
| Audience overlap | Too many similar ad sets | Use Audience Overlap tool; consolidate or exclude |

## How to Get Your Data

- **Meta Ads Manager**: Campaigns → Customize Columns → Export
- **Meta Events Manager**: Overview → event activity logs
- **No historical data**: Describe your business and budget — Claude builds from best practices

## Example

**Input**: "Meta ads campaign for a DTC supplement brand. Objective: online sales. Budget: $5,000/month. Audience: health-conscious adults 25-55. Have 3 product videos and customer UGC. Pixel installed, 200 purchases/month."

**Output**: 3-campaign structure: (1) Advantage+ Shopping ($3,000/mo) — broad targeting, all creative, automated optimization; (2) Retargeting ($1,500/mo) — 3 ad sets: 7-day website visitors, 14-day add-to-cart abandoners, 30-day video viewers 75%+; (3) Testing ($500/mo) — new creative and audience tests. Audience exclusions: purchasers last 30 days from prospecting. Creative recs: Lead with UGC video (2-3x ROAS vs. polished brand video), add carousel of top 3 products, test testimonial image ads. Bidding: lowest cost on Advantage+ (200 purchases/mo is well above learning phase threshold). Week 1-4 plan with specific optimization actions.

## Related Skills

- **[ad-copy-generator](./ad-copy-generator.md)** — Generate Meta-specific ad copy variations optimized for Facebook and Instagram formats.
- **[audience-targeting-builder](./audience-targeting-builder.md)** — Build detailed Meta audience segments with interest and demographic layering.
- **[ad-creative-testing-framework](./ad-creative-testing-framework.md)** — Test different creative formats across Meta placements to maximize ROAS.
- **[ad-performance-analyzer](./ad-performance-analyzer.md)** — Analyze Meta campaign performance to optimize budget allocation and placement strategy.
