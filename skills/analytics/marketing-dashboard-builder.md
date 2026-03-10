---
name: marketing-dashboard-builder
description: >
  Build an interactive marketing KPI dashboard from raw data with charts, filters, and period
  comparisons. Use this skill whenever the user mentions marketing dashboard, KPI dashboard,
  marketing report dashboard, performance dashboard, interactive report, "build me a dashboard",
  "visualize my marketing data", traffic dashboard, lead dashboard, pipeline dashboard, marketing
  metrics visualization, campaign dashboard, "show my marketing KPIs", channel performance
  dashboard, executive marketing report, or any request to create a visual, interactive view of
  marketing metrics. Also trigger on "I have marketing data and want to see it visually" or
  "create a report I can share with my CMO".
---

# Marketing Dashboard Builder

Build a self-contained interactive HTML dashboard from raw marketing data. Includes charts for traffic, leads, pipeline, revenue, and channel performance with dropdown filters and period-over-period comparisons.

## Granularity Check

> Can this be completed in a single Claude session? **Yes — expect ~5 min data prep + ~10 min Claude session.** If implementing output in a platform, add 10-20 min for setup. Input is CSV data. Output is a single HTML file with embedded Chart.js visualizations. No server or database needed.

## User Intent Mapping

Trigger when the user says:

- "Build a marketing dashboard from this data" (direct request)
- "Visualize my marketing KPIs" (visualization)
- "Create an executive marketing report" (stakeholder reporting)
- "I need a dashboard showing traffic, leads, and revenue" (specific metrics)
- "Show me channel performance over time" (trend analysis)
- "Build a report I can share with leadership" (shareable output)
- "Create an interactive view of my campaign data" (interactivity)
- "I have GA4 + CRM data, build a unified view" (data merging)
- "Dashboard with month-over-month comparisons" (period comparison)
- "Visualize my marketing funnel metrics" (funnel view)

## Input Contract

### Required Input

| Column | Type | Description | Example |
|---|---|---|---|
| `date` or `period` | date/string | Time dimension | `2026-01-15` or `Jan 2026` |
| At least 1 metric | numeric | Any marketing metric | `sessions`, `leads`, `revenue` |

### Common Input Columns (use what you have)

| Column | Type | Description |
|---|---|---|
| `channel` or `source` | string | Traffic/campaign source |
| `sessions` or `traffic` | integer | Website visits |
| `leads` or `mqls` | integer | Lead count |
| `sqls` | integer | Sales-qualified leads |
| `opportunities` | integer | Pipeline opportunities |
| `revenue` or `closed_won` | float | Revenue generated |
| `spend` or `cost` | float | Marketing spend |
| `conversions` | integer | Goal completions |
| `impressions` | integer | Ad impressions |
| `clicks` | integer | Ad/email clicks |

### Sample Input

```csv
date,channel,sessions,leads,mqls,opportunities,revenue,spend
2026-01-01,Organic Search,12500,340,85,22,44000,0
2026-01-01,Paid Search,8200,280,70,18,36000,12000
2026-01-01,Social,4100,120,30,8,16000,3500
2026-01-01,Email,3200,190,48,12,24000,800
2026-02-01,Organic Search,13800,380,95,25,50000,0
2026-02-01,Paid Search,7900,260,65,17,34000,11500
2026-02-01,Social,4600,140,35,9,18000,4000
2026-02-01,Email,3500,210,53,14,28000,850
```

### Input Validation Rules

1. Must have a time dimension (date, month, week, quarter)
2. At least one numeric metric column required
3. Warn if fewer than 3 time periods (trends need data points)
4. Auto-detect column types (numeric vs categorical vs date)
5. Handle missing values gracefully (show as gaps in charts, not zeros)

### If You Don't Have This Data

- **No analytics access?** Ask your web developer for a GA4 export, or use Google Sheets to manually track key metrics for 2 weeks.
- **No historical data?** Start with the current month. Even 2 weeks of data can reveal patterns.
- **No attribution setup?** Use UTM parameters on all campaign links going forward. This skill can help you design the taxonomy.
- **No BI tool?** Google Sheets with pivot tables covers 80% of dashboard needs for teams under 50 people.

## Process

1. **Analyze input data** — Identify available dimensions and metrics. Report: "Found X periods, Y channels, Z metrics. Building dashboard with [list of charts]."

2. **Select chart types** based on data:
   - **Time series** → Line chart (sessions, leads, revenue over time)
   - **Channel comparison** → Stacked bar or grouped bar chart
   - **Funnel metrics** → Funnel visualization (sessions → leads → MQLs → SQLs → revenue)
   - **Budget/spend** → Donut chart for allocation + bar for ROI
   - **Period comparison** → Side-by-side bars with % change labels
   - **Single KPIs** → Big number cards with trend arrows

3. **Build dashboard layout:**
   - **Row 1:** KPI cards (4-6 big numbers with period change %)
   - **Row 2:** Primary trend chart (line — key metric over time)
   - **Row 3:** Channel breakdown (bar) + budget allocation (donut)
   - **Row 4:** Funnel chart (if funnel data available) + conversion table
   - **Filters:** Date range dropdown, channel selector

4. **Add interactivity:**
   - Dropdown filters that update all charts simultaneously
   - Hover tooltips on all data points
   - Period-over-period % change calculations
   - Color-coded performance (green = up, red = down)

5. **Style the dashboard:**
   - Clean, professional design (dark header, white cards, subtle shadows)
   - Responsive layout (works on desktop and tablet)
   - Consistent color palette per channel across all charts
   - Print-friendly view option

6. **Human checkpoint** — Present the chart plan. Ask: "Does this dashboard layout cover what you need? Any metrics to add or remove?"

7. **Generate self-contained HTML** — Single file with embedded CSS, JS, Chart.js, and data.


> **Benchmark Context**: Marketing teams typically allocate 5-15% of budget to analytics tools. A well-built dashboard should answer 80% of weekly reporting questions without manual queries. GA4 reports average 24-48 hour data lag for standard processing.


### Confidence & Sample Size
> **Confidence Note**: Results are only as reliable as your input data. Small datasets (<50 records or <30 days of data) produce directional insights, not statistically significant conclusions. Always note your sample size when sharing results with stakeholders. Recommendations should be validated with A/B testing or additional data before making major strategic changes.

## Output Contract

### Output Format

| Output | Format | Contents |
|---|---|---|
| Interactive dashboard | HTML | Single self-contained file |
| Data summary | Markdown | Key findings and anomalies |

### Dashboard Components

```
┌─────────────────────────────────────────────────────┐
│  MARKETING DASHBOARD                [Filters ▼]     │
├──────────┬──────────┬──────────┬───────────────────┤
│ Sessions │  Leads   │  MQLs    │  Revenue          │
│  32,100  │   890    │   223    │  $142,000         │
│  ▲ 8.2%  │  ▲ 5.1%  │  ▲ 6.8%  │  ▲ 10.3%         │
├──────────┴──────────┴──────────┴───────────────────┤
│  ╭─── Traffic & Leads Over Time ────────────────╮   │
│  │  [Line chart with dual Y-axis]               │   │
│  ╰──────────────────────────────────────────────╯   │
├─────────────────────────┬───────────────────────────┤
│  Channel Performance    │  Budget Allocation        │
│  [Grouped bar chart]    │  [Donut chart]            │
├─────────────────────────┴───────────────────────────┤
│  ╭─── Marketing Funnel ────────────────────────╮    │
│  │  Sessions → Leads → MQLs → SQLs → Revenue  │    │
│  ╰─────────────────────────────────────────────╯    │
└─────────────────────────────────────────────────────┘
```

### Technical Specs

- Single HTML file, no external dependencies (Chart.js embedded via CDN)
- Data embedded as JavaScript arrays (no server needed)
- Responsive CSS Grid layout
- Chart.js for visualizations
- Vanilla JavaScript for filters and interactivity
- Print CSS media query for clean printing

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
| Only 1 time period | Single snapshot | Build comparison cards only, no trend lines; note more data needed |
| No channel dimension | Aggregate data only | Build trend charts without channel breakdown |
| Too many channels (>10) | Granular source data | Group into top 5 + "Other" for readability |
| Mixed date formats | Inconsistent data | Auto-detect and normalize; warn user |
| Very large dataset (>10,000 rows) | Detailed daily data | Aggregate to weekly/monthly before building charts |
| Missing revenue data | Top-of-funnel only | Build traffic/lead dashboard; note revenue would complete the picture |

## How to Get Your Data

### From Google Analytics 4

1. GA4 → Reports → Acquisition → Traffic acquisition
2. Set date range and comparison period
3. Export → CSV
4. Upload to Claude

### From HubSpot

1. Reports → Analytics Tools → Traffic Analytics
2. Select date range, group by source
3. Export → CSV
4. Also export: Contacts → Lists → All contacts with create date + lifecycle stage

### From Multiple Sources (Most Common)

1. Export traffic data from GA4 (sessions by channel by month)
2. Export lead/pipeline data from CRM (leads, MQLs, SQLs, revenue by month)
3. Export spend data from ad platforms (Google Ads, Meta)
4. Provide all CSVs to Claude — dashboard will merge by date + channel

### From a Spreadsheet

1. If you track marketing KPIs in a spreadsheet, export as CSV
2. Ensure date and metric columns are clearly labeled
3. Upload to Claude

## Example

**User prompt:** "I have 6 months of marketing data across 4 channels. Build me a dashboard I can show my VP of Marketing."

**Claude responds:**

> Analyzed your data: 6 months (Oct 2025 – Mar 2026), 4 channels, 8 metrics.
>
> **Dashboard will include:**
> - KPI cards: Sessions, Leads, MQLs, Revenue (with MoM change)
> - Trend chart: Traffic + leads over 6 months (dual axis)
> - Channel performance: Grouped bar comparing all 4 channels
> - Budget allocation: Donut showing spend distribution
> - ROI table: ROAS and CAC per channel
> - Funnel: Sessions → Leads → MQLs → Revenue with conversion rates
>
> **Key findings:**
> - Organic Search grew 18% but Paid Search declined 4%
> - Email has highest ROI ($28 per $1 spent) but lowest volume
> - Overall MQL-to-Revenue conversion improved from 22% to 26%
>
> Generating the interactive HTML dashboard now...

**Delivers a single HTML file the user can open in any browser and share.**
