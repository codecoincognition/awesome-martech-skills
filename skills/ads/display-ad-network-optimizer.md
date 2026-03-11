---
name: display-ad-network-optimizer
description: >
  Optimize display and programmatic ad campaigns across networks — placements, viewability, and fraud prevention.
  Use this skill when the user says "display ad optimization", "programmatic ads strategy",
  "Google Display Network optimization", "display ad placements", "ad viewability audit",
  "banner ad performance", "display campaign audit", "programmatic buying strategy", "ad fraud
  prevention", "display ad creative specs", or "GDN placement analysis". Also trigger for
  responsive display ads, placement exclusions, or display ad frequency management.
---

# Display Ad Network Optimizer

Optimizes display and programmatic ad campaigns with placement analysis, viewability improvements, fraud prevention, creative recommendations, and frequency management.

## Granularity Check

> **Time**: ~5 min data prep → ~10 min Claude session → ~30-60 min building in Google Ads / Meta Ads Manager. If implementing output in a platform, add 15-20 min for placement adjustments. Input is display campaign performance CSV. Output is Markdown optimization report.

## User Intent Mapping

- "Our display ads have low CTR" (optimization)
- "Which placements should we exclude?" (placement hygiene)
- "Display campaign audit for our brand" (audit)
- "How to improve display ad viewability" (viewability)
- "Are we getting click fraud?" (fraud detection)
- "Google Display Network best practices" (best practices)
- "Responsive display ads vs. uploaded images" (format guidance)
- "Display ad frequency is too high" (frequency management)
- "Programmatic buying strategy" (strategic)
- "Banner ad specs and sizes" (creative specs)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Campaign Data | CSV | Columns: campaign, placement/site, impressions, clicks, conversions, cost, viewable_impressions (if available) |
| Campaign Goal | Text | Awareness, retargeting, conversions |

### If You Don't Have This Data

- **No placement report?** Google Ads → Campaigns → Placements → Where Ads Showed. Export this CSV.
- **No viewability data?** Enable Active View metrics in Google Ads. Check after 7 days of data collection.
- **No conversion tracking?** Use view-through conversions and assisted conversions as proxy metrics for display.
- **No historical data?** Claude analyzes your campaign setup and provides best-practice recommendations without performance data.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Placement Exclusion List | CSV | Sites/apps already excluded |
| Creative Assets | Text | Ad sizes and formats currently running |
| Brand Safety Requirements | Text | Content categories to avoid |
| Monthly Budget | Number | For pacing recommendations |
| Industry | Text | For benchmark comparisons |

## Process

### Step 1: Placement Analysis
- Identify top 20 placements by spend and conversions
- Flag placements with high spend but 0 conversions
- Detect suspicious placements (very high CTR, very low viewability)
- Categorize: premium sites, mid-tier, low-quality, apps, YouTube

### Step 2: Viewability Audit
- Overall viewability rate vs. benchmark (70%+ is good, 50% is industry average)
- Viewability by placement (exclude <30% viewable sites)
- Viewability by ad size (300x250 and 728x90 typically most viewable)
- Above-the-fold vs. below-the-fold placement analysis

### Step 3: Fraud & Invalid Traffic Detection
Red flags to investigate:
- CTR > 3% on display (unusually high, possible bot clicks)
- Bounce rate > 95% from specific placements
- 0-second sessions from specific sources
- Placements with names containing random strings or mobile app IDs you don't recognize
- Geographic anomalies (clicks from unexpected countries)

### Step 4: Creative Optimization
- Responsive display ads: test 5+ headlines, 5+ descriptions, 3+ images
- Top-performing ad sizes: 300x250, 336x280, 728x90, 160x600, 300x600
- Animated vs. static performance comparison
- CTA button best practices (contrasting color, action verb)

### Step 5: Frequency & Reach Management
- Frequency cap recommendations (3-5/day for awareness, 1-2/day for retargeting)
- Reach vs. frequency trade-off analysis
- Audience fatigue detection (declining CTR over time at same frequency)

### Confidence & Sample Size
> **Confidence Note**: Display ad metrics are noisier than search. CTR benchmarks (0.1-0.5%) mean you need 10,000+ impressions per placement for reliable performance data. View-through conversions are modeled and should be weighted lower than click-through conversions. Invalid traffic detection is directional — use Google's IVT reports and third-party verification for definitive fraud analysis.

### ⚠️ Human Checkpoint
> Review placement exclusion list before applying — some legitimate sites may appear as poor performers due to attribution gaps. Verify brand safety categories align with your policies. Check that creative meets platform specs before uploading.

> **Benchmark Context**: See WordStream 2024 Industry Benchmarks for current industry benchmarks relevant to this analysis.
## Output Contract

### Deliverable: Markdown Optimization Report

```markdown
# Display Campaign Optimization: [Brand] — [Period]

## Performance Summary
| Metric | Current | Benchmark | Status |
|---|---|---|---|

## Placement Analysis
### Top Performers
| Placement | Impressions | Clicks | Conv. | CPA |
|---|---|---|---|---|

### Recommended Exclusions
| Placement | Reason | Spend Saved |
|---|---|---|

## Viewability Report
- Overall viewability: X%
- Improvement recommendations: [list]

## Fraud Indicators
| Flag | Placements Affected | Action |
|---|---|---|

## Creative Recommendations
| Current | Issue | Recommendation |
|---|---|---|

## Frequency Analysis
- Current avg. frequency: X
- Recommended cap: X
- Estimated impact: [metric change]
```

## Platform Implementation Steps

### Google Ads (GDN)
1. Placements → Where Ads Showed → download performance
2. Add exclusions: Placements → Exclusions → paste site list
3. Set frequency caps: Campaign settings → Additional settings → Frequency capping
4. Create responsive display ads: Ads → New Ad → Responsive Display Ad
5. Enable Active View metrics in Columns → Customize

### DV360 / Programmatic
1. Review Inventory Quality reports for viewability and fraud
2. Apply pre-bid viewability targeting (target 70%+ viewable)
3. Enable IAS or DoubleVerify for third-party verification
4. Set up PMPs (Private Marketplace deals) for premium inventory

### Brand Safety (Any Platform)
1. Exclude sensitive content categories in campaign settings
2. Upload site exclusion list from the optimization report
3. Consider third-party brand safety tools (IAS, DoubleVerify, Zefr)
4. Review quarterly and update exclusion lists

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Excluded too many placements | Over-aggressive exclusions killed reach | Restore placements with 500+ impressions; re-evaluate after 14 days |
| Low viewability persists | Wrong ad sizes or poor placement quality | Switch to high-viewability sizes (300x250, 300x600); target above-the-fold |
| Click fraud continues | Sophisticated bot traffic | Enable click fraud protection; report to Google; consider IVT vendor |
| Creative fatigue | Same ads for 30+ days | Refresh creative monthly; test 3-5 variants |

## How to Get Your Data

- **Google Ads**: Campaigns → Placements → Where Ads Showed → Export CSV
- **DV360**: Insights → Create Report → include placement and viewability metrics
- **No data**: Describe your campaign setup — Claude provides best-practice recommendations

## Example

**Input**: CSV with 30-day GDN placement report. 500 placements, $8,000 spend, 45 conversions, $178 CPA (target: $100).

**Output**: Top 10 placements drive 70% of conversions at $85 CPA. Bottom 200 placements spent $2,400 with 0 conversions — exclude immediately (saves 30% of budget). 15 placements flagged for fraud indicators: CTR >5% with 0 conversions and 100% bounce rate. Viewability: 48% overall (below 50% benchmark) — exclude 30 sites with <20% viewability. Creative: only running 2 static 300x250 ads — recommend switching to Responsive Display Ads and adding 728x90 and 300x600 sizes. Frequency: averaging 8.2 impressions/user/day (too high) — set cap at 3/day. Projected impact: CPA reduction from $178 to $95-110 by cutting waste placements and capping frequency.

## Related Skills

- **[ad-performance-analyzer](./ad-performance-analyzer.md)** — Analyze overall display campaign performance to identify underperforming placements.
- **[audience-targeting-builder](./audience-targeting-builder.md)** — Build targeted display audiences to reduce wasted impressions on irrelevant placements.
- **[ad-creative-testing-framework](./ad-creative-testing-framework.md)** — Test different display creative sizes and formats to improve viewability and performance.
- **[ad-compliance-checker](./ad-compliance-checker.md)** — Ensure display ads meet platform brand safety and policy requirements before placement.
