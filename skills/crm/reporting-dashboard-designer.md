---
name: reporting-dashboard-designer
description: >
  Design CRM reporting dashboards with KPIs, metrics, and visualizations for marketing and sales performance.
  Use this skill when the user says "CRM dashboard design", "marketing reporting dashboard", "sales dashboard
  setup", "KPI dashboard for CRM", "executive reporting dashboard", "pipeline reporting", "marketing
  performance dashboard", "CRM analytics setup", "revenue reporting dashboard", "funnel reporting design",
  or "CRM metrics and KPIs". Also trigger for report template design, metric definition, or
  dashboard audience customization.
---

> **How this skill works:** You export your CRM data (HubSpot, Salesforce, Pipedrive, etc.) or describe your reporting needs, and Claude designs a dashboard strategy. Claude cannot build dashboards directly in your CRM or pull live data — you provide the requirements and data, Claude brings the blueprint.

# Reporting Dashboard Designer

Designs CRM reporting dashboards with the right KPIs, metrics, visualizations, and update cadences for different stakeholder audiences.

## Granularity Check

> **Session time**: ~5 min context gathering + ~10 min Claude session. If implementing, add 2-4 hours per dashboard. Input is reporting needs and CRM platform. Output is Markdown dashboard specification with metric definitions and layout.

## User Intent Mapping

- "Design our CRM reporting dashboard" (design)
- "What KPIs should we track?" (KPIs)
- "Executive dashboard for marketing" (executive)
- "Pipeline health dashboard" (pipeline)
- "Marketing funnel report" (funnel)
- "Sales performance dashboard" (sales)
- "Campaign ROI reporting" (ROI)
- "Dashboard for our weekly meeting" (meeting)
- "We're drowning in data — what matters?" (focus)
- "CRM reports aren't useful" (optimization)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| CRM Platform | Text | HubSpot, Salesforce, Pipedrive, etc. |
| Audience | Text | Who will use this dashboard |
| Business Goals | Text | What decisions this dashboard should inform |

### If You Don't Have This Data

- **Not sure what to report?** Claude maps your business goals to the metrics that actually matter and eliminates vanity metrics.
- **Too many reports?** Claude consolidates into 3-5 dashboards by audience (executive, marketing, sales, CS) with shared metrics.
- **CRM data is incomplete?** Claude designs dashboards with available data and flags gaps to fill.
- **No reporting process?** Claude creates a reporting cadence (daily, weekly, monthly, quarterly) with specific dashboards for each.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Current Reports | Text | Existing dashboards and what's not working |
| Team Structure | Text | Marketing, sales, CS team sizes |
| Reporting Cadence | Text | How often you review metrics |
| Integration Data | Text | What tools connect to your CRM |
| Historical Baselines | Text | Current performance benchmarks |

## Process

### Step 1: Dashboard Audience Matrix
| Audience | Purpose | Cadence | Depth | Key Questions |
|---|---|---|---|---|
| CEO/Board | Strategic health | Monthly/Quarterly | High-level | Are we growing? Are we efficient? |
| VP Marketing | Marketing effectiveness | Weekly | Detailed | What's working? Where to invest? |
| Marketing team | Campaign performance | Daily/Weekly | Granular | How are campaigns performing? |
| VP Sales | Pipeline health | Weekly | Detailed | Will we hit target? Where are deals? |
| Sales reps | Daily priorities | Daily | Action-oriented | What should I do today? |
| CS team | Customer health | Weekly | Account-level | Who needs attention? |

### Step 2: Metric Hierarchy
| Level | Metrics | Audience |
|---|---|---|
| North Star | Revenue, Customer count, NRR | Everyone |
| Leading indicators | Pipeline, MQLs, trials, engagement | Leadership |
| Channel metrics | CAC by channel, conversion by source, CTR | Marketing team |
| Activity metrics | Calls, emails, meetings, tasks | Sales management |
| Health metrics | NPS, health scores, ticket volume | CS team |

### Step 3: Dashboard Specifications
**Executive Dashboard**
| Metric | Visualization | Update | Comparison |
|---|---|---|---|
| MRR/ARR | Line chart (trend) | Monthly | vs. target, vs. last year |
| New customers | Bar chart (monthly) | Monthly | vs. target |
| Churn rate | Line chart (trend) | Monthly | vs. benchmark |
| CAC | Single number | Monthly | vs. LTV ratio |
| Pipeline coverage | Gauge/ratio | Weekly | vs. 3x target |

**Marketing Dashboard**
| Metric | Visualization | Update | Comparison |
|---|---|---|---|
| Leads by source | Stacked bar | Weekly | vs. prior period |
| MQL volume | Line chart | Weekly | vs. target |
| MQL-to-SQL rate | Funnel | Weekly | vs. benchmark |
| Campaign performance | Table (sortable) | Weekly | vs. goals |
| Content performance | Table (top 10) | Monthly | vs. averages |

**Sales Dashboard**
| Metric | Visualization | Update | Comparison |
|---|---|---|---|
| Pipeline value | Bar chart by stage | Daily | vs. target coverage |
| Close rate | Trend line | Weekly | vs. benchmark |
| Average deal size | Single number | Weekly | vs. target |
| Sales velocity | Calculated metric | Weekly | vs. prior quarter |
| Rep leaderboard | Ranked table | Weekly | vs. quota |

### Step 4: Metric Definitions
Per metric, define:
- **Name**: Clear, unambiguous name
- **Formula**: Exact calculation (numerator/denominator)
- **Data source**: Where the data comes from
- **Update frequency**: How often it refreshes
- **Owner**: Who is responsible for this metric
- **Target**: What good looks like
- **Alert threshold**: When to escalate

### Step 5: Visualization Best Practices
| Data Type | Best Visualization | Avoid |
|---|---|---|
| Trend over time | Line chart | Pie chart |
| Comparison | Bar chart (horizontal for many items) | 3D charts |
| Proportion | Stacked bar, donut | Pie with 7+ slices |
| Single KPI | Big number with trend arrow | Cluttered gauge |
| Funnel | Funnel chart or waterfall | Tables for funnel data |
| Distribution | Histogram or box plot | Line chart |

Design rules:
- Maximum 8-10 metrics per dashboard
- Group related metrics visually
- Use consistent colors across dashboards
- Include comparison context (vs. target, vs. last period)
- Add data freshness indicator (last updated timestamp)

### Step 6: Reporting Cadence
| Cadence | Dashboard | Format | Audience |
|---|---|---|---|
| Daily | Sales activity, pipeline | In-CRM dashboard | Sales team |
| Weekly | Marketing performance, pipeline health | Email digest + meeting | Marketing + Sales leadership |
| Monthly | Executive summary, campaign ROI | Presentation slides | Executive team |
| Quarterly | Strategic review, trend analysis | Deep-dive report | Board, executive team |

### Confidence & Sample Size

> **Confidence Note**: Dashboard metrics are only as reliable as your underlying data. Before building dashboards, verify data quality in your CRM — incomplete fields, duplicates, and stale data will produce misleading reports. Start with 5-8 metrics per dashboard — more than 10 creates information overload. Review and retire metrics that no one acts on. The best dashboard is the one that changes behavior — if a metric doesn't drive action, remove it.

### ⚠️ Human Checkpoint
> Verify metric definitions with all stakeholders before building — the same word (e.g., "lead") often means different things to different teams. Test dashboards with real data before sharing. Ensure filters work correctly (date ranges, team, source). Validate calculations against manual spot-checks.

> **Benchmark Context**: Companies with well-defined KPIs are 3x more likely to exceed revenue goals. 73% of data in CRM systems is inaccurate within 12 months. Executives who review dashboards weekly make faster strategic decisions. Marketing teams that track attribution see 15-20% improvement in budget efficiency. Only 30% of companies trust their marketing data quality.

## Output Contract

### Deliverable: Markdown Dashboard Specification

```markdown
# CRM Dashboard Design: [Company]

## Dashboard Architecture
| Dashboard | Audience | Cadence | Metrics Count |
|---|---|---|---|

## Dashboard 1: [Name]
### Purpose
[What decisions this informs]

### Metrics
| Metric | Definition | Formula | Source | Target | Visualization |
|---|---|---|---|---|---|

### Layout
[Description of dashboard layout with metric placement]

### Filters
| Filter | Options | Default |
|---|---|---|

[Repeat for each dashboard]

## Metric Definitions
| Metric | Formula | Source | Owner | Target | Alert |
|---|---|---|---|---|---|

## Reporting Cadence
| Cadence | Dashboard | Delivery | Owner |
|---|---|---|---|

## Implementation Steps
| Step | Action | Platform | Timeline |
|---|---|---|---|
```

## Platform Implementation Steps

### HubSpot
1. Navigate to Reports → Dashboards → Create Dashboard
2. Use report builder for custom metrics (Reports → Create Report)
3. Add reports to dashboard with drag-and-drop layout
4. Set up dashboard filters (date range, team, owner)
5. Schedule email delivery for automated reporting
6. Set permissions for dashboard visibility by team

### Salesforce
1. Navigate to Dashboards → New Dashboard
2. Build reports first (Reports → New Report) with required metrics
3. Add report components to dashboard (charts, tables, gauges)
4. Configure dashboard filters for dynamic views
5. Schedule dashboard refresh and email delivery
6. Set up Einstein Analytics for advanced visualizations

### General
1. Define metric calculations before building
2. Create data source connections (CRM + analytics + marketing tools)
3. Build one dashboard per audience with appropriate detail level
4. Test with stakeholders and iterate based on feedback
5. Set up automated delivery and alerting

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Dashboard ignored | Too many metrics, not actionable | Reduce to 5-8 key metrics; tie each to a decision |
| Numbers don't match | Inconsistent metric definitions across tools | Standardize definitions; single source of truth |
| Stale data | Manual updates forgotten | Automate data refresh; add "last updated" timestamp |
| Wrong audience detail | Executive dashboard too granular, or team dashboard too high-level | Redesign per audience matrix; different dashboards for different needs |

## How to Get Your Data

- **CRM metrics**: CRM → built-in reporting → revenue, pipeline, conversion
- **Marketing metrics**: Marketing automation + GA4 → leads, engagement, attribution
- **Sales metrics**: CRM → deal reports → velocity, close rate, quota attainment
- **No reporting yet**: Share your business goals and CRM — Claude designs starter dashboards

## Example

**Input**: "Design CRM dashboards for our B2B SaaS. HubSpot CRM. Teams: 3 marketers, 5 sales reps, 2 CSMs. Need executive dashboard, marketing dashboard, and sales pipeline dashboard. Currently have 15 random reports that nobody looks at."

**Output**: Consolidate 15 reports into 3 focused dashboards: (1) Executive Dashboard (monthly review): MRR trend line, new customers vs. target, churn rate trend, CAC/LTV ratio, pipeline coverage ratio, NPS trend. 6 metrics, all single-number or trend. (2) Marketing Dashboard (weekly review): leads by source (stacked bar), MQL volume vs. target (line), MQL→SQL conversion (funnel), campaign ROI table (top 10), content performance table (top 10), email engagement trend. 6 metrics with drill-down capability. (3) Sales Pipeline Dashboard (daily use): total pipeline value by stage (bar), weighted pipeline vs. quota (gauge), deals closing this month (table), stale deals alert (table, deals with no activity 14+ days), rep activity summary (calls, emails, meetings). 5 metrics, action-oriented. Implementation: archive 15 existing reports. Build 3 new dashboards in HubSpot (1 day each). Set up weekly email delivery for marketing dashboard (Monday AM), monthly delivery for executive dashboard (1st of month). Sales dashboard: pinned as HubSpot homepage for sales team.
