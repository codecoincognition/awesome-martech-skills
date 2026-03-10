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

> Can this be completed in a single Claude session? **Yes — expect ~5 min data prep + ~10 min Claude session.** If implementing output in a platform, add 10-20 min for setup. Input is budget plan + actuals CSV. Output is an XLSX variance report. No financial system access needed.

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


### Confidence & Sample Size
> **Confidence Note**: Results are only as reliable as your input data. Small datasets (<50 records or <30 days of data) produce directional insights, not statistically significant conclusions. Always note your sample size when sharing results with stakeholders. Recommendations should be validated with A/B testing or additional data before making major strategic changes.

### ⚠️ Human Checkpoint
> Review variance explanations with channel owners before sharing with finance. Some variances have legitimate strategic reasons that need context.


> **Benchmark Context**: Marketing teams typically allocate 5-15% of budget to analytics tools. A well-built dashboard should answer 80% of weekly reporting questions without manual queries. GA4 reports average 24-48 hour data lag for standard processing.

## Output Contract

### Deliverable: XLSX Report (3 sheets)

**Sheet 1: Variance Summary**
Columns: `channel | campaign | planned | actual | variance_$ | variance_% | status | classification | explanation`

**Sheet 2: Channel Deep Dive**
Columns: `channel | planned | actual | variance | cpl_planned | cpl_actual | cpc_planned | cpc_actual | roi_assessment`

**Sheet 3: Recommendations**
Columns: `priority | action | channel | amount | rationale | expected_impact`

Plus a summary section:
| Metric | Value |
|---|---|
| Total Planned | $X |
| Total Actual | $X |
| Total Variance | $X (Y%) |
| Material Variances | count |
| Channels Over Budget | count |
| Channels Under Budget | count |

## Platform Implementation Steps

### Google Analytics 4
1. Navigate to GA4 → Admin → Data Streams → your stream
2. Under Events, use "Create Event" for custom events
3. For dimensions/metrics: Admin → Custom Definitions → Create
4. Import any CSV data via Data Import: Admin → Data Import → Create

### Looker Studio / Google Data Studio
1. Open Looker Studio → Create → Report
2. Add data source (GA4, Google Sheets, BigQuery, etc.)
3. Paste calculated metric formulas into custom fields
4. Use the "Blend Data" feature for multi-source reports

### Spreadsheet (Fallback)
If no BI tool available, create analysis in Google Sheets or Excel:
1. Import CSV data using File → Import
2. Use PIVOT tables for aggregation
3. Create charts using Insert → Chart

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| No planned budget | User only has actuals | Analyze spend distribution and trends, can't do variance analysis |
| Mismatched categories | Plan uses different channel names than actuals | Ask user to map categories, normalize names |
| Missing time periods | Annual plan but monthly actuals (or vice versa) | Prorate annual to monthly, or aggregate monthly to match |
| No performance data | Spend only, no leads/conversions | Do spend variance only, note ROI analysis unavailable |

## How to Get Your Data

- **Budget plan**: Usually a Google Sheet or Excel file from finance/marketing ops
- **Google Ads**: Billing → Cost data by campaign
- **Meta Ads**: Ads Manager → Export spend data
- **LinkedIn Ads**: Campaign Manager → Export
- **Marketing automation**: HubSpot/Marketo → Campaign spend reports
- **Finance**: Accounting system → Marketing cost center export

## Example

**Input**: Q4 2025 marketing budget, 8 channels, $123K planned vs. $122K actual.

**Output**: Total variance -$1K (-0.8%) — on budget overall. But 3 material variances: Google Ads Brand +$3.5K (+23%) due to CPC inflation — justified, CPL actually improved. LinkedIn ABM -$8K (-40%) — campaign launched 3 weeks late, budget unspent. Events +$5K (+17%) — venue cost increase, should have been flagged earlier. Recommendations: (1) Reallocate $5K from LinkedIn underspend to Google Ads Brand (proven ROI). (2) Negotiate venue costs earlier for next event. (3) Increase LinkedIn pacing to spend remaining Q1 allocation on time.
