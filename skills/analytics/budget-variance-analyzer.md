---
name: budget-variance-analyzer
description: >
  Compare planned vs. actual marketing spend, identify variances, and explain over/under-spend
  by channel and campaign. Use this skill when the user says "budget variance report",
  "planned vs actual spend", "where did we overspend", "marketing budget analysis",
  "budget tracking report", "spend variance by channel", "are we on budget", "budget
  reconciliation", "quarterly spend review", "marketing financial review", or "why are
  we over budget". Also trigger when the user has a marketing budget spreadsheet and
  actuals data and needs to reconcile them.
---

# Budget Variance Analyzer

Compares planned marketing budget against actual spend to identify variances by channel, campaign, and time period. Produces a variance report with explanations, trends, and reallocation recommendations.

## Granularity Check

> Can this be completed in a single Claude session? **Yes — expect ~5 min data prep → ~10 min Claude session → ~30-60 min building in Google Sheets / Looker / GA4.** If implementing output in a platform, add 10-20 min for setup. Input is budget plan + actuals CSV. Output is an XLSX variance report. No financial system access needed.

## User Intent Mapping

This skill should trigger when the user says things like:

- "Compare our Q4 budget plan to actual spend" (direct request)
- "Why are we 20% over budget on paid social?" (investigation)
- "Generate a budget variance report for the CMO" (deliverable)
- "Are we on track with marketing spend this quarter?" (status check)
- "Which channels are under-spending their allocation?" (gap identification)
- "Help me explain budget overruns to finance" (stakeholder communication)
- "Reallocate budget from underperforming to overperforming channels" (optimization)
- "Monthly budget tracking report" (recurring deliverable)
- "Marketing spend by campaign vs. plan" (granular view)
- "Forecast end-of-quarter spend based on current pace" (projection)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Budget Data | CSV | Columns: channel, campaign (optional), planned_spend, actual_spend, period |

### If You Don't Have This Data

- **No analytics access?** Ask your web developer for a GA4 export, or use Google Sheets to manually track key metrics for 2 weeks.
- **No historical data?** Start with the current month. Even 2 weeks of data can reveal patterns.
- **No attribution setup?** Use UTM parameters on all campaign links going forward. This skill can help you design the taxonomy.
- **No BI tool?** Google Sheets with pivot tables covers 80% of dashboard needs for teams under 50 people.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Performance Metrics | CSV columns | Leads, conversions, revenue per channel (for ROI-adjusted analysis) |
| Time Periods | CSV column | Monthly or weekly breakdown |
| Notes | CSV column | Explanations for known variances |
| Annual Budget | Number | Total annual budget for full-year context |
| Prior Period | CSV | Previous quarter/year for trend comparison |

### Sample Input CSV

```csv
channel,campaign,planned_spend,actual_spend,period,leads,conversions
Google Ads,Brand,15000,18500,2025-Q4,450,23
Google Ads,Non-Brand,25000,22000,2025-Q4,380,18
Facebook Ads,Retargeting,10000,10200,2025-Q4,120,15
LinkedIn Ads,ABM Campaign,20000,12000,2025-Q4,45,3
Content,Blog Production,8000,9500,2025-Q4,200,8
Events,Trade Show,30000,35000,2025-Q4,150,12
Email,Nurture Sequences,3000,2800,2025-Q4,0,22
SEO,Agency Retainer,12000,12000,2025-Q4,500,35
```

## Process

### Step 1: Variance Calculation
For each line item, calculate:
- Dollar variance: actual - planned
- Percentage variance: (actual - planned) / planned × 100
- Classify: Over budget (>5%), On budget (±5%), Under budget (<-5%)
- Cumulative impact on total budget

### Step 2: Variance Categorization
Group variances by significance:
- **Material** (>15% or >$5K): Needs explanation and action
- **Notable** (5-15% or $1-5K): Monitor, may need adjustment
- **Immaterial** (<5% and <$1K): Expected fluctuation

### Step 3: Root Cause Analysis
For material variances, identify likely causes:
- **Overspend**: CPC inflation, expanded targeting, unplanned campaigns, scope creep
- **Underspend**: Campaign delays, vendor underdelivery, conservative pacing, poor performance paused
- **Timing**: Spend shifted between months but on track for quarter

### Step 4: ROI-Adjusted Analysis (if performance data available)
- Cost per lead by channel (planned vs. actual)
- Cost per conversion by channel
- Effective CPA variance (spending more but getting more?)
- Channels where overspend was justified by performance

### Step 5: Forecast & Recommendations
- Pace-based forecast: at current run rate, where will we end the period?
- Reallocation recommendations: shift budget from underperforming/underspending to overperforming
- Action items: what to do about each material variance

## Output Contract

### Deliverable: Markdown Tables + CSV-Ready Data (3 sections)

**Section 1: Variance Summary**
Markdown table: `channel | campaign | planned | actual | variance_$ | variance_% | status | classification | explanation`

Can be pasted into Google Sheets, Excel, or any spreadsheet tool.

**Section 2: Channel Deep Dive**
Markdown table: `channel | planned | actual | variance | cpl_planned | cpl_actual | cpc_planned | cpc_actual | roi_assessment`

**Section 3: Recommendations**
Markdown table: `priority | action | channel | amount | rationale | expected_impact`

## Related Skills

- **ad-performance-analyzer** (../ads/ad-performance-analyzer.md) — Analyze performance of the channels and campaigns with budget variances; understand if overspend/underspend was justified.
- **marketing-roi-calculator** (./marketing-roi-calculator.md) — Calculate ROI per channel to inform reallocation decisions; move budget from low-ROI to high-ROI channels.
- **campaign-performance-benchmarker** (./campaign-performance-benchmarker.md) — Compare channel performance against benchmarks; identify if variances signal optimization opportunities.
- **attribution-model-builder** (./attribution-model-builder.md) — Use attribution insights to reallocate budget across channels; understand true credit per channel for conversion.
