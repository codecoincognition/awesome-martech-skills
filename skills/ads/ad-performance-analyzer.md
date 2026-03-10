---
name: ad-performance-analyzer
description: >
  Analyze ad campaign performance data to identify winners, losers, and optimization opportunities.
  Use this skill when the user says "analyze my ad performance", "ad campaign report", "which ads
  are working", "ad performance analysis", "campaign performance review", "ad metrics breakdown",
  "why are my ads underperforming", "ad campaign audit", "compare ad performance", "weekly ad
  report", or "monthly ad review". Also trigger for creative performance analysis, audience
  performance comparison, or ad spend efficiency review.
---

# Ad Performance Analyzer

Analyzes ad campaign performance data across platforms to identify top performers, diagnose underperformers, surface optimization opportunities, and generate actionable recommendations.

## Granularity Check

> **Session time**: ~5 min data prep + ~10 min Claude session. If implementing output in a platform, add 10-15 min for adjustments. Input is campaign performance CSV export. Output is Markdown analysis report with prioritized recommendations.

## User Intent Mapping

- "Analyze my Google Ads performance this month" (platform-specific review)
- "Which of my ads are performing best?" (winner identification)
- "Why is my CPA increasing?" (diagnostic)
- "Weekly ad performance report" (recurring report)
- "Compare performance across campaigns" (benchmarking)
- "Our ROAS dropped — what happened?" (root cause analysis)
- "Creative performance breakdown" (creative analysis)
- "Audience performance comparison" (targeting analysis)
- "Should I pause any campaigns?" (cut decisions)
- "Ad performance trends over the last 90 days" (trend analysis)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Performance Data | CSV | Columns: campaign, ad_set/ad_group, ad, spend, impressions, clicks, conversions, cost_per_conversion |

### If You Don't Have This Data

- **No CSV export?** Copy-paste the campaign summary table from your ad platform dashboard.
- **No conversion tracking?** Use clicks and CTR as proxy metrics. Set up conversion tracking as a priority.
- **No historical comparison?** Claude analyzes the current snapshot against industry benchmarks. Start saving monthly exports for trend analysis.
- **Multiple platforms?** Export from each platform separately. Include a "platform" column to distinguish data sources.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Revenue Data | Column in CSV | Revenue per conversion for ROAS calculation |
| Time Period | Text | Analysis window (e.g., "March 2026" or "last 90 days") |
| Previous Period | CSV | Comparison period for trend analysis |
| Goals | Text | Target CPA, ROAS, or conversion volume |
| Creative Details | Text | Ad type (image, video, carousel) for creative analysis |

## Process

### Step 1: Data Summary
- Total spend, impressions, clicks, conversions, revenue
- Blended CPA, ROAS, CTR, conversion rate
- Period-over-period comparison (if data provided)

### Step 2: Campaign Ranking
Rank all campaigns by efficiency:
- Top performers: Lowest CPA or highest ROAS with meaningful volume
- Steady performers: Near-target CPA with consistent volume
- Underperformers: Above-target CPA or declining metrics
- Emerging: New campaigns with promising early signals

### Step 3: Diagnostic Analysis
For underperformers, diagnose root cause:
- Low CTR → Creative or targeting issue
- High CTR, low conversion rate → Landing page or offer mismatch
- High CPA → Bid strategy, audience saturation, or competitive pressure
- Declining ROAS → Ad fatigue, seasonal shift, or market change

### Step 4: Creative Performance (if data available)
- Best-performing ad creative by CPA and CTR
- Format comparison: image vs. video vs. carousel
- Copy analysis: which headlines and CTAs drive conversions
- Creative fatigue detection: performance decay over time

### Step 5: Recommendations
Prioritized action list:
- Immediate (this week): Pause/scale decisions
- Short-term (2 weeks): Creative refreshes, audience adjustments
- Medium-term (30 days): Strategy shifts, new campaign tests

### Confidence & Sample Size
> **Confidence Note**: Results are only as reliable as your input data. Small datasets (<50 conversions per campaign or <14 days of data) produce directional insights, not statistically significant conclusions. CPA comparisons require similar time periods and audience sizes to be meaningful. Always note your sample size when sharing results with stakeholders.

### ⚠️ Human Checkpoint
> Review pause/scale recommendations against business context — some campaigns serve strategic goals (brand, new market entry) that CPA alone doesn't capture. Verify attribution model consistency across platforms before comparing cross-channel performance.

> **Benchmark Context**: Average Google Search ads CTR is 3-5%, Display is 0.5-1%. Average Meta ads CTR is 1-2%. Top 10% of ads outperform median by 3-5x. Creative refreshes typically needed every 2-4 weeks. A 20% CPA variance week-over-week is normal; investigate sustained 4+ week trends.

## Output Contract

### Deliverable: Markdown Analysis Report

```markdown
# Ad Performance Report: [Brand] — [Period]

## Executive Summary
- Total spend: $X | Conversions: X | Blended CPA: $X
- vs. Previous period: [trend]
- Key insight: [one sentence]

## Campaign Rankings
| Rank | Campaign | Spend | Conv. | CPA | ROAS | Status |
|---|---|---|---|---|---|---|

## Top Performers
1. [Campaign]: [why it's winning]

## Underperformers & Diagnostics
1. [Campaign]: [root cause] → [recommended action]

## Recommendations
### Immediate (This Week)
1. [Action]
### Short-Term (2 Weeks)
1. [Action]
### Medium-Term (30 Days)
1. [Action]

## Key Metrics Trends
| Metric | Current | Previous | Change |
|---|---|---|---|
```

## Platform Implementation Steps

### Google Ads
1. Download data: Reports → Predefined → Campaigns → Download CSV
2. Apply recommendations: Campaigns → select campaign → adjust budget/bid/status
3. Set up automated rules for pause/scale triggers

### Meta Ads Manager
1. Download data: Campaigns → Columns: Performance → Export
2. Review Delivery column for learning phase status
3. Use Breakdown by delivery to analyze placement/audience performance

### Google Sheets Dashboard
1. Import CSV data into a master tracking sheet
2. Create pivot tables: CPA by campaign, ROAS by channel
3. Add conditional formatting: green (<target CPA), red (>target CPA)
4. Set up weekly refresh cadence

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Misleading CPA comparison | Different attribution windows across platforms | Standardize to same-click window; note limitations |
| Premature optimization | Acting on <7 days of data | Wait for statistical significance; use 14-day minimum |
| Paused a winner | Short-term dip in long-term performer | Check 30-day trend before pausing; use 7-day pause instead |
| Missing conversions | Pixel or tracking issues | Verify conversion tracking with platform diagnostics |

## How to Get Your Data

- **Google Ads**: Reports → Predefined → Campaign → Download CSV
- **Meta Ads Manager**: Campaigns → Customize Columns → Export
- **LinkedIn Campaign Manager**: Campaign Performance → Export
- **TikTok Ads Manager**: Campaign → Export Data
- **Multi-platform**: Combine exports with consistent column naming

## Example

**Input**: CSV with 8 campaigns across Google Search, Google Display, and Meta over 30 days. Total spend: $12,000. Target CPA: $40.

**Output**: Executive summary: 342 conversions at $35 blended CPA (12% below target). Top performers: Google Brand Search ($12 CPA, 89 conversions — scaling opportunity) and Meta Prospecting Campaign A ($32 CPA, 78 conversions — increase budget 20%). Underperformers: Google Display Campaign ($85 CPA, 22 conversions — pause non-converting placements, test responsive display ads), Meta Prospecting Campaign C ($62 CPA, 18 conversions — creative fatigue detected, refresh needed). Recommendations: (1) Immediately increase Brand Search budget by 30% (impression share only 62%); (2) Pause Google Display placements with <0.3% CTR; (3) Refresh Meta Campaign C creative within 1 week; (4) Test new Meta lookalike audience (1% based on top 50 customers) within 2 weeks.
