---
name: ad-budget-optimizer
description: >
  Optimize ad budget allocation across channels and campaigns using performance data.
  Use this skill when the user says "optimize ad budget", "budget allocation across channels",
  "where should I spend my ad dollars", "ad spend optimization", "marketing budget reallocation",
  "reduce CPA across campaigns", "scale ad spend efficiently", "diminishing returns on ad spend",
  "channel mix optimization", "media budget planning", or "ad budget forecasting". Also trigger
  for ROAS optimization, spend pacing analysis, or budget shift recommendations.
---

# Ad Budget Optimizer

Analyzes cross-channel ad performance data to recommend optimal budget allocation, identify diminishing returns, and project impact of budget shifts on key metrics.

## Granularity Check

> **Time**: ~5 min data prep → ~10 min Claude session → ~30-60 min building in Google Ads / Meta Ads Manager. If implementing output in a platform, add 15-20 min for budget adjustments. Input is multi-channel performance CSV. Output is Markdown optimization report with budget reallocation plan.

## User Intent Mapping

- "Where should I shift my ad budget?" (reallocation)
- "We have $10K/month — how to split across channels?" (planning)
- "Our Google Ads CPA is rising — should we move budget to Meta?" (channel comparison)
- "Are we hitting diminishing returns on any channel?" (efficiency analysis)
- "Scale our best-performing campaigns" (scaling)
- "Ad budget forecast for next quarter" (forecasting)
- "Reduce overall CPA by 20%" (target-driven)
- "Which campaigns should I pause?" (cut analysis)
- "Budget pacing — are we on track this month?" (pacing)
- "Compare ROAS across all channels" (benchmarking)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Performance Data | CSV | Columns: channel, campaign, spend, impressions, clicks, conversions, revenue (if applicable) |
| Total Budget | Number | Monthly or quarterly total budget |

### If You Don't Have This Data

- **No cross-channel data?** Export from each platform separately (Google Ads, Meta, LinkedIn) and paste into one spreadsheet with consistent columns.
- **No revenue data?** Use conversions (leads, signups) as the optimization metric instead of ROAS.
- **No historical data?** Provide your current budget split and goals. Claude will use industry benchmarks to recommend a starting allocation.
- **No attribution model?** Use platform-reported conversions as a starting point. Note that this double-counts cross-channel journeys.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Historical Data | CSV | 3-6 months of performance for trend analysis |
| Business Goals | Text | Target CPA, ROAS, or conversion volume |
| Constraints | Text | Minimum spend per channel, contractual commitments |
| Seasonality | Text | Known seasonal patterns (Q4 spike, summer dip) |
| New Channels | Text | Channels you're considering adding |

## Process

### Step 1: Performance Summary
Calculate per-channel metrics:
- CPA (Cost Per Acquisition) = Spend ÷ Conversions
- ROAS (Return on Ad Spend) = Revenue ÷ Spend
- CTR (Click-Through Rate) = Clicks ÷ Impressions
- Conversion Rate = Conversions ÷ Clicks
- Cost efficiency score = weighted index of CPA + volume + trend

### Step 2: Marginal Returns Analysis
For each channel, assess:
- Is CPA increasing as spend increases? (diminishing returns signal)
- What's the spend level where efficiency drops?
- Are there underserved channels with low spend but strong efficiency?
- Which campaigns have headroom to scale?

### Step 3: Budget Reallocation Model
Apply rules:
- Move 10-20% of budget from lowest-efficiency channels to highest
- Never cut a channel below minimum viable spend (enough for learning)
- Increase budget on channels with CPA below target AND room to scale
- Maintain a 10-15% testing budget for new channels/campaigns

### Step 4: Scenario Modeling
Model 3 scenarios:
- **Conservative**: Shift 10% — expected CPA reduction, projected conversions
- **Moderate**: Shift 20% — expected impact
- **Aggressive**: Shift 30%+ — expected impact with risk assessment

### Step 5: Pacing & Forecasting
- Current month pacing (on track, underspending, overspending)
- Next 30/60/90-day spend projection
- Seasonal adjustment recommendations

### Confidence & Sample Size
> **Confidence Note**: Budget optimization requires minimum 30 days of data and 100+ conversions per channel for reliable CPA comparisons. Platform-reported conversions use different attribution windows (Google: 30-day click, Meta: 7-day click/1-day view) which inflates total conversions when summed. Use a consistent attribution model or apply a 15-25% deduplication factor.

### ⚠️ Human Checkpoint
> Review reallocation recommendations against business context — some channels serve brand/awareness goals that CPA alone doesn't capture. Verify no contractual minimum spends would be violated. Consider attribution model differences before making large shifts.

> **Benchmark Context**: See Statista 2024 Digital Advertising Report, and Forrester 2024 Marketing Attribution Study for current industry benchmarks relevant to this analysis.
## Output Contract

### Deliverable: Markdown Optimization Report

```markdown
# Ad Budget Optimization: [Brand] — [Period]

## Current Performance Summary
| Channel | Spend | Conversions | CPA | ROAS | Trend |
|---|---|---|---|---|---|

## Efficiency Ranking
1. [Channel]: CPA $X (best)
...

## Diminishing Returns Analysis
| Channel | Current Spend | Efficiency Zone | Max Efficient Spend |
|---|---|---|---|

## Reallocation Recommendations
| Channel | Current Budget | Recommended | Change | Rationale |
|---|---|---|---|---|

## Scenario Projections
| Scenario | Total Conversions | Blended CPA | Change vs. Current |
|---|---|---|---|

## Pacing Check
- Month-to-date spend: $X of $Y (X%)
- Projected end-of-month: $Z
- Status: [on track / underpacing / overpacing]

## Action Items
1. [Specific action with timeline]
```

## Platform Implementation Steps

### Google Ads
1. Adjust campaign budgets in Campaign → Settings → Budget
2. Use Shared Budgets for campaigns that should flex together
3. Monitor Search Impression Share — if <70%, budget may be limiting reach

### Meta Ads Manager
1. Adjust at Campaign Budget Optimization (CBO) level
2. Use Ad Set spend limits if certain audiences need floors/caps
3. Review Learning Phase status after budget changes

### Cross-Channel (Google Sheets)
1. Create a master budget tracker with columns per channel
2. Update weekly with actual spend from each platform
3. Compare to plan and flag variances >10%
4. Monthly rebalance meeting using this report as input

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| CPA increased after reallocation | Scaled too fast, triggered learning phase | Increase budgets gradually (20% max per change) |
| Cut channel that was assisting conversions | Didn't account for multi-touch attribution | Restore partial budget; analyze assisted conversions |
| Underspending on high-ROAS channel | Budget cap set too low | Remove or increase daily budget cap; check impression share |
| Over-indexing on one channel | All budget shifted to one performer | Maintain minimum viable diversification (no channel >60% of total) |

## How to Get Your Data

- **Google Ads**: Reports → Predefined → Campaign → Download CSV
- **Meta Ads**: Campaigns → Export → CSV (select all columns)
- **LinkedIn**: Campaign Manager → Export performance data
- **Multi-channel**: Combine exports in Google Sheets with consistent columns
- **No data**: Provide total budget and goals — Claude allocates using industry benchmarks

## Example

**Input**: CSV with 3 months of data across Google Ads ($4K/mo, $45 CPA), Meta ($3K/mo, $38 CPA), LinkedIn ($2K/mo, $120 CPA), TikTok ($1K/mo, $28 CPA). Total budget: $10K/month. Goal: maximize conversions at <$50 CPA.

**Output**: Efficiency ranking: TikTok ($28) > Meta ($38) > Google ($45) > LinkedIn ($120). LinkedIn CPA 2.4x above target — recommend reducing from $2K to $800 (awareness budget only). TikTok showing no diminishing returns at current spend — recommend scaling from $1K to $2.5K. Conservative scenario: shift $1.2K from LinkedIn to TikTok → projected blended CPA drops from $51 to $42 (+22 additional conversions/month). Moderate scenario: reduce LinkedIn to $800, increase TikTok to $2.5K, increase Meta to $3.7K → projected CPA $39 (+38 additional conversions). Action items: (1) Scale TikTok 25%/week over 4 weeks, (2) Reduce LinkedIn to brand awareness only, (3) Test new Meta audiences with the freed budget.

## Related Skills

- **[ad-performance-analyzer](./ad-performance-analyzer.md)** — Use before this skill to identify which channels and campaigns are underperforming.
- **[ppc-keyword-strategy](./ppc-keyword-strategy.md)** — Optimize after reallocation by refining keyword targeting to reduce CPA on allocated budget.
- **[audience-targeting-builder](./audience-targeting-builder.md)** — Use in parallel to segment budget across more targeted audience layers, maximizing efficiency.
- **[marketing-roi-calculator](../analytics/marketing-roi-calculator.md)** — Validate budget reallocation ROI projections with this analysis tool.
