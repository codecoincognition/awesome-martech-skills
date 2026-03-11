---
name: dashboard-requirement-gatherer
description: >
  Gather and structure dashboard requirements — KPI definitions, data sources, audience needs,
  and visualization preferences — before building a marketing dashboard. Use this skill when
  the user says "plan a dashboard", "what should be on my dashboard", "dashboard requirements",
  "define dashboard KPIs", "what metrics should I track", "dashboard planning", "report
  requirements gathering", "marketing metrics framework", "help me think through my dashboard",
  or "what data do I need for a dashboard". Use BEFORE marketing-dashboard-builder to ensure
  the right metrics are tracked.
---

# Dashboard Requirement Gatherer

Structures the requirements-gathering process for marketing dashboards — defining audiences, KPIs, data sources, update frequency, and visualization preferences. Produces a dashboard specification document that feeds directly into the marketing-dashboard-builder skill.

## Granularity Check

> Can this be completed in a single Claude session? **Yes — expect ~5 min data prep → ~10 min Claude session → ~60-120 min building in your BI tool.** If implementing output in a platform, add 10-20 min for setup. Input is business context via conversation. Output is a Markdown dashboard spec. No data access needed — this is the planning step.

## User Intent Mapping

This skill should trigger when the user says things like:

- "I need a marketing dashboard but don't know where to start" (beginner)
- "What KPIs should be on our executive dashboard?" (audience-specific)
- "Help me define what to track before building the dashboard" (planning)
- "What data sources do I need to connect?" (technical planning)
- "Our current dashboard is a mess — help me rethink it" (redesign)
- "Define metrics for our demand gen dashboard" (function-specific)
- "What should a content marketing dashboard track?" (topic-specific)
- "Dashboard requirements for the CMO vs. the team" (multi-audience)
- "Map our KPIs to data sources" (technical mapping)
- "How often should we refresh our marketing reports?" (cadence planning)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Business Type | Text | B2B/B2C, industry, go-to-market model |
| Dashboard Purpose | Text | What decisions should this dashboard support? |

### If You Don't Have This Data

- **No analytics access?** Ask your web developer for a GA4 export, or use Google Sheets to manually track key metrics for 2 weeks.
- **No historical data?** Start with the current month. Even 2 weeks of data can reveal patterns.
- **No attribution setup?** Use UTM parameters on all campaign links going forward. This skill can help you design the taxonomy.
- **No BI tool?** Google Sheets with pivot tables covers 80% of dashboard needs for teams under 50 people.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Primary Audience | Text | Who will use this dashboard (CMO, demand gen team, board) |
| Current Tools | Text | Marketing platforms in use (GA4, HubSpot, Google Ads, etc.) |
| Known Pain Points | Text | What's wrong with current reporting |
| Existing Metrics | Text | What they currently track (to build on, not start from scratch) |
| Reporting Cadence | Text | Daily, weekly, monthly, real-time |

## Process

### Step 1: Audience Analysis
Define each dashboard consumer:
- **Who**: Role and seniority
- **What decisions**: What they use data to decide
- **Frequency**: How often they check the dashboard
- **Depth**: Summary metrics vs. drill-down detail
- **Format**: Live dashboard vs. static report vs. email digest

### Step 2: KPI Framework
Build a metric hierarchy:

**Level 1 — North Star Metrics** (1-3 metrics the business optimizes for):
- Revenue, pipeline, customer acquisition cost, LTV

**Level 2 — Channel/Function KPIs** (5-10 metrics per function):
- Demand gen: MQLs, SQLs, conversion rates, cost per lead
- Content: Traffic, engagement, content-influenced pipeline
- Paid: ROAS, CPA, impression share, CTR
- Email: Open rate, click rate, unsubscribe rate, revenue per send

**Level 3 — Diagnostic Metrics** (drill-down for investigation):
- Campaign-level performance, A/B test results, cohort analysis

### Step 3: Data Source Mapping
For each KPI, identify:
- Source system (GA4, HubSpot, Google Ads, Salesforce, etc.)
- Export method (API, CSV export, manual entry)
- Update frequency (real-time, daily, weekly)
- Data quality assessment (reliable, needs cleaning, manual)
- Owner (who maintains this data)

### Step 4: Visualization Recommendations
For each KPI, recommend chart type:

| Metric Type | Best Visualization |
|---|---|
| Single number + trend | KPI card with sparkline |
| Over time | Line chart |
| By category | Bar chart (horizontal for many categories) |
| Part of whole | Donut chart |
| Funnel progression | Funnel chart |
| Goal tracking | Gauge or progress bar |
| Comparison | Grouped bar or side-by-side KPI cards |

### Step 5: Dashboard Architecture
Recommend dashboard structure:
- Number of dashboards (separate by audience or function?)
- Section layout (above-the-fold summary, then drill-down sections)
- Filter requirements (date range, channel, campaign, region)
- Interactivity needs (clickable drill-downs, hover details)


### Confidence & Sample Size
> **Confidence Note**: Results are only as reliable as your input data. Small datasets (<50 records or <30 days of data) produce directional insights, not statistically significant conclusions. Always note your sample size when sharing results with stakeholders. Recommendations should be validated with A/B testing or additional data before making major strategic changes.

### ⚠️ Human Checkpoint
> Review the KPI framework with stakeholders before building. Dashboards built without stakeholder input get ignored. Ask: "If you could only see 3 numbers every morning, what would they be?"


> **Benchmark Context**: See Google 2024 Marketing Measurement Guide for current industry benchmarks relevant to this analysis.
## Output Contract

### Deliverable: Markdown Dashboard Specification

```markdown
# Dashboard Specification: [Dashboard Name]

## Audience
| Audience | Role | Decisions Supported | Cadence | Format |
|---|---|---|---|---|

## KPI Framework

### North Star Metrics
| KPI | Definition | Target | Source | Update Frequency |
|---|---|---|---|---|

### Channel KPIs
| KPI | Definition | Target | Source | Visualization |
|---|---|---|---|---|

### Diagnostic Metrics
| KPI | Definition | Source | When to Use |
|---|---|---|---|

## Data Source Inventory
| Source | KPIs Served | Export Method | Refresh | Quality | Owner |
|---|---|---|---|---|---|

## Dashboard Layout
[Section-by-section description with recommended visualizations]

## Filter Requirements
- Date range (default: last 30 days, options: 7d, 30d, 90d, YTD, custom)
- Channel filter
- Campaign filter

## Technical Requirements
- Refresh frequency
- Access control
- Mobile compatibility
- Export capability

## Next Step
→ Feed this spec into `marketing-dashboard-builder` to generate the interactive HTML dashboard.
```

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
| Too many metrics | User wants to track everything | Apply the "3 metrics on a desert island" filter, create hierarchy |
| No clear audience | "Everyone" uses the dashboard | Recommend separate views — executive summary + operational detail |
| Unknown data sources | User doesn't know where data lives | List common sources per KPI, ask team to identify |
| Vanity metrics | User wants to track impressions and likes only | Guide toward actionable metrics, keep vanity as secondary |

## How to Get Your Data

This skill doesn't need exported data — it needs your thinking:
- What decisions do you need data to make?
- Who needs to see what?
- What tools do you use for marketing? (list all platforms)
- What do you currently track that's useful?
- What questions can't you answer with current reporting?

## Example

**Input**: B2B SaaS company, demand gen team dashboard. Tools: GA4, HubSpot, Google Ads, LinkedIn Ads, Salesforce. Pain point: "We have data everywhere but no single view of pipeline performance."

**Output**: Dashboard spec with 3 audiences (CMO: monthly strategic view, Demand Gen Manager: weekly operational view, paid media specialist: daily tactical view). North star: pipeline generated, CAC, MQL-to-SQL conversion rate. 12 channel KPIs mapped to 5 data sources. Layout: top row = 4 KPI cards (pipeline, MQLs, CAC, conversion rate), second row = pipeline trend line + channel mix donut, third row = campaign performance table with sorting. Filters: date range, channel, campaign. Data source map showing GA4 provides traffic metrics, HubSpot provides lead metrics, Salesforce provides pipeline, ad platforms provide spend. Next step: export HubSpot + Salesforce data as CSV and feed into marketing-dashboard-builder.

## Related Skills

- **[marketing-dashboard-builder](./marketing-dashboard-builder.md)** — Use this skill after gathering requirements to build the interactive dashboard.
- **[marketing-roi-calculator](./marketing-roi-calculator.md)** — Complement dashboard planning with ROI metric calculations.
- **[ab-test-result-analyzer](./ab-test-result-analyzer.md)** — Include A/B test results as KPIs in your dashboard requirements.
- **[growth-experiment-designer](../growth/growth-experiment-designer.md)** — Track experiment metrics defined in dashboard requirements.
