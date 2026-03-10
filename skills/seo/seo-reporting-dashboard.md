---
name: seo-reporting-dashboard
description: >
  Build SEO performance reports with rankings, traffic, conversions, and actionable insights.
  Use this skill when the user says "SEO report", "SEO performance dashboard", "monthly SEO
  reporting", "organic traffic report", "ranking report", "SEO KPI tracking", "SEO ROI report",
  "search visibility report", "SEO progress report", "keyword ranking dashboard", or "organic
  search analytics". Also trigger for SEO executive reporting, SEO client reporting, or
  search performance trend analysis.
---

# SEO Reporting Dashboard

Builds comprehensive SEO performance reports with rankings, traffic trends, conversion data, competitive visibility, and actionable recommendations for stakeholders.

## Granularity Check

> **Session time**: ~5 min data prep + ~10 min Claude session. If building recurring reports, add 30-60 min for template setup. Input is GSC/analytics/ranking tool exports. Output is Markdown report with insights and recommendations.

## User Intent Mapping

- "Monthly SEO report for the team" (recurring report)
- "SEO performance dashboard for executives" (executive summary)
- "Show me our ranking progress" (rankings)
- "Organic traffic trends and analysis" (traffic)
- "SEO ROI — is our investment paying off?" (ROI)
- "Client SEO report" (agency/client)
- "Which pages are winning and losing traffic?" (page analysis)
- "Search visibility vs. competitors" (competitive)
- "SEO KPIs — what should we track?" (KPI framework)
- "Quarterly SEO review" (quarterly)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| GSC Data | CSV | Search Console Performance export (queries, pages, clicks, impressions) |
| Time Period | Text | Reporting period (month, quarter) and comparison period |
| Audience | Text | Who receives the report (exec, marketing, client, technical team) |

### If You Don't Have This Data

- **No GSC data?** Set up Google Search Console today (free). Claude can build a report from any analytics data you have.
- **No ranking tool?** Use GSC average position data as a starting point. For competitive data, manually check key rankings.
- **No conversion tracking?** Set up GA4 goals for organic traffic. Claude includes recommendations for conversion tracking setup.
- **No historical baseline?** This month's report becomes your baseline. Claude establishes a measurement framework for future comparison.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| GA4 Data | CSV | Organic traffic, conversions, bounce rate, session duration |
| Ranking Data | CSV | Keyword positions from Ahrefs, Semrush, or similar |
| Backlink Data | CSV | New/lost referring domains |
| Competitor Data | CSV | Competitor visibility scores or rankings |
| Business Data | Text | Revenue from organic, leads generated |

## Process

### Step 1: KPI Framework
| KPI | Data Source | Frequency | Audience |
|---|---|---|---|
| Organic sessions | GA4 | Monthly | All |
| Keyword rankings | Rank tracker | Weekly | SEO team |
| Click-through rate | GSC | Monthly | SEO team |
| Organic conversions | GA4 | Monthly | Leadership |
| Search visibility score | Semrush/Ahrefs | Monthly | All |
| Backlinks acquired | Ahrefs/Moz | Monthly | SEO team |
| Core Web Vitals | CrUX/GSC | Monthly | Technical |
| Organic revenue/leads | GA4/CRM | Monthly | Leadership |

### Step 2: Traffic Analysis
- Total organic sessions vs. previous period and YoY
- Traffic by landing page (top gainers and losers)
- Traffic by device (mobile vs. desktop trends)
- Traffic by country/region
- New vs. returning organic visitors

### Step 3: Ranking Analysis
- Keyword position changes (improved, declined, new, lost)
- Top 10 rankings gained and lost
- Average position trend
- SERP feature wins and losses
- Keyword distribution by position bucket (1-3, 4-10, 11-20, 21-50, 50+)

### Step 4: Content Performance
- Top-performing pages by organic traffic
- Pages with biggest traffic changes
- New content published and early performance
- Content with declining traffic (refresh candidates)
- Page-level CTR optimization opportunities (high impressions, low CTR)

### Step 5: Competitive Analysis
- Search visibility share vs. competitors
- Competitor ranking changes on your target keywords
- Competitor content published this period
- Share of voice trend

### Step 6: Recommendations
- Top 3 priorities for next period
- Quick wins identified from data
- Risks or declining trends to address
- Content opportunities from data
- Technical issues requiring attention

### Confidence & Sample Size
> **Confidence Note**: GSC data has a 2-3 day lag and samples data for high-impression queries. Month-to-month SEO comparisons can be misleading due to seasonality — always include YoY comparison. Ranking data varies by tool, location, and device — use consistent measurement. Attribution of revenue to SEO should account for multi-touch journeys.

### ⚠️ Human Checkpoint
> Review data accuracy before sharing reports with stakeholders. Verify conversion data attribution is correct. Add qualitative context (algorithm updates, site changes, market events) that data alone doesn't explain.

> **Benchmark Context**: Average organic CTR for position 1 is 27.6%, position 2 is 15.8%, position 3 is 11%. Year-over-year comparison is more reliable than month-over-month for SEO. Pages ranking 4-10 with high impressions are the biggest CTR optimization opportunities. Organic search drives 53% of all website traffic on average. SEO ROI typically appears 6-12 months after investment begins.

## Output Contract

### Deliverable: Markdown SEO Report

```markdown
# SEO Performance Report: [Period]

## Executive Summary
- Organic traffic: [number] ([% change] vs. previous period)
- Conversions: [number] ([% change])
- Top achievement: [highlight]
- Key risk: [concern]

## Traffic Overview
| Metric | This Period | Previous Period | Change | YoY |
|---|---|---|---|---|

## Ranking Summary
| Category | Count | Change |
|---|---|---|
| Top 3 rankings | [n] | [+/-] |
| Top 10 rankings | [n] | [+/-] |
| Top 20 rankings | [n] | [+/-] |

## Top Pages
| Page | Clicks | Impressions | CTR | Avg Position |
|---|---|---|---|---|

## Key Wins
1. [Achievement with data]

## Areas of Concern
1. [Issue with data and recommendation]

## Recommendations for Next Period
1. [Priority action with expected impact]

## Competitive Snapshot
| Competitor | Visibility Score | Trend |
|---|---|---|
```

## Platform Implementation Steps

### Google Search Console
1. Performance → set date range → export queries and pages
2. Coverage → check for new indexing issues
3. Core Web Vitals → note any failing pages
4. Manual Actions → confirm no penalties

### Google Analytics 4
1. Reports → Acquisition → Traffic acquisition → filter Organic Search
2. Export: sessions, users, conversions, bounce rate, engagement rate
3. Create exploration report for organic landing page performance
4. Set up monthly automated email report

### Rank Tracking (Semrush/Ahrefs/Moz)
1. Create a project with your target keywords
2. Set up weekly rank tracking with location targeting
3. Export position data for reporting period
4. Compare positions to previous period for change analysis

### Reporting Automation
1. Use Google Looker Studio for live dashboard (free)
2. Connect GSC, GA4, and rank tracker data sources
3. Set up automated monthly email delivery
4. Create executive view (summary) and detail view (full data)

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Report shows wrong data | Date range or filter misconfiguration | Double-check all date ranges and segment filters |
| Stakeholders don't read the report | Too long or too technical | Create executive summary version; lead with insights, not data |
| Missing attribution | Conversion tracking not set up | Implement GA4 goals; add UTM parameters for SEO landing pages |
| Data discrepancies between tools | Different data sources measure differently | Pick one source of truth per metric; note methodology in reports |

## How to Get Your Data

- **GSC**: Performance → Export → CSV (queries tab and pages tab)
- **GA4**: Explore → Free Form → add organic traffic metrics → Export
- **Rank tracker**: Export positions for tracked keywords
- **No tools beyond GSC**: Claude builds a complete report from GSC data alone — it's the most reliable source

## Example

**Input**: "Monthly SEO report for February. GSC data export attached. 85K organic clicks (+12% MoM), 2.1M impressions (+8%). 15 new top-10 rankings, 3 lost. Audience: marketing director who wants actionable insights, not just data."

**Output**: Executive summary: Strong month — organic clicks up 12% driven by 15 new top-10 rankings. Content refresh initiative delivered 40% of gains (3 updated articles entered top 5). Risk: 3 lost rankings on commercial keywords — competitor published new comparison pages. Top win: "best project management tools" moved from #12 to #4 (est. +2,800 clicks/month). Content performance: top 5 pages drive 35% of traffic — healthy distribution. CTR opportunity: 8 keywords with 1,000+ impressions and <2% CTR — title tag optimization could add 500+ clicks/month. Recommendations: (1) Create comparison content targeting 3 lost commercial keywords, (2) A/B test title tags on 8 low-CTR pages, (3) Continue content refresh cadence — 5 more posts identified for update. Competitive note: main competitor launched 12 new blog posts this month vs. our 6 — consider increasing publishing cadence.
