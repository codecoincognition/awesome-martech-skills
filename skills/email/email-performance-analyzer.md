---
name: email-performance-analyzer
description: >
  Analyze email campaign performance with benchmarking, trend analysis, and optimization recommendations.
  Use this skill when the user says "email performance analysis", "email campaign report",
  "email metrics review", "email KPI dashboard", "email engagement analysis", "email ROI
  report", "email campaign comparison", "email performance benchmarks", "why are our email
  metrics declining", "email analytics review", or "email performance trends". Also trigger
  for email revenue attribution, campaign-level analysis, or email program health assessment.
---

> **How this skill works:** You export your email campaign performance data from your ESP (Mailchimp, Klaviyo, HubSpot, Braze, etc.) as a CSV, and Claude analyzes it. Claude cannot connect to live email platforms or pull data directly — you bring the data, Claude brings the analysis.

# Email Performance Analyzer

Analyzes email campaign performance with metric benchmarking, trend identification, segment-level insights, and actionable optimization recommendations for improving email program ROI.

## Granularity Check

> **Session time**: ~5 min data prep + ~10 min Claude session. If implementing recommendations, add 1-3 hours. Input is email performance exports from your ESP. Output is Markdown performance analysis with optimization plan.

## User Intent Mapping

- "Analyze our email performance for this quarter" (period analysis)
- "Why are our open rates declining?" (diagnosis)
- "Email campaign report for the board" (executive report)
- "Compare our email metrics to industry benchmarks" (benchmarking)
- "Which email campaigns performed best?" (campaign ranking)
- "Email ROI analysis" (ROI)
- "Segment-level email performance" (segmentation)
- "Our click rates are low — what's wrong?" (metric diagnosis)
- "Email program health check" (health assessment)
- "Month-over-month email trends" (trends)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Campaign Data | CSV/Text | Campaign name, date, sends, opens, clicks, conversions, revenue |
| Time Period | Text | Reporting period and comparison period |
| Industry | Text | For relevant benchmarking |

### If You Don't Have This Data

- **No export?** Summarize your last 5-10 campaigns with sends, opens, clicks, and any conversion data. Claude can work with manual data.
- **No revenue attribution?** Claude analyzes engagement metrics (opens, clicks, unsubscribes) and recommends conversion tracking setup.
- **No historical data?** This analysis becomes your baseline. Claude sets targets based on industry benchmarks.
- **No segmented data?** Claude analyzes aggregate data and recommends segmentation as an improvement.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Segment Performance | CSV | Metrics broken down by subscriber segment |
| Automation Performance | CSV | Flow-level metrics for automated emails |
| Revenue Data | CSV | Revenue attributed to email campaigns |
| List Growth | Text | Subscriber growth and churn rates |
| Competitor Benchmarks | Text | Known competitor email metrics |

## Process

### Step 1: Metric Overview
| Metric | Formula | Your Rate | Industry Avg | Status |
|---|---|---|---|---|
| Open Rate | Opens / Delivered | [%] | 21.3% | [above/below] |
| Click Rate | Clicks / Delivered | [%] | 2.6% | [above/below] |
| CTOR | Clicks / Opens | [%] | 12.2% | [above/below] |
| Unsubscribe Rate | Unsubs / Delivered | [%] | 0.1% | [above/below] |
| Bounce Rate | Bounces / Sent | [%] | 0.4% | [above/below] |
| Conversion Rate | Conversions / Clicks | [%] | 15.2% | [above/below] |

### Step 2: Trend Analysis
- Month-over-month metric trends (3-6 month view)
- Seasonal patterns identification
- Correlation between send volume and engagement
- List growth vs. engagement relationship
- Campaign type performance comparison

### Step 3: Campaign-Level Analysis
- Top 5 and bottom 5 campaigns by primary metric
- Common characteristics of high performers (subject line style, content type, send day)
- Campaign type benchmarking (newsletter vs. promotional vs. automated)
- Send time analysis across campaigns

### Step 4: Diagnostic Framework
| Symptom | Likely Causes | Investigation |
|---|---|---|
| Low open rate | Poor subject lines, bad send time, deliverability issues | Test subjects; check spam rate; review sender reputation |
| Low click rate | Weak CTAs, irrelevant content, poor design | Audit CTA placement; check mobile rendering; review content relevance |
| High unsubscribe | Over-emailing, irrelevant content, expectations mismatch | Check frequency; segment audience; review signup promise |
| High bounce | Stale list, bad data sources | Clean list; verify acquisition channels; remove role addresses |

### Step 5: Recommendations
Prioritize by impact and effort:
- Quick wins (< 1 hour, immediate impact)
- Medium-term improvements (1-2 weeks)
- Strategic initiatives (1-3 months)

### Confidence & Sample Size
> **Confidence Note**: Open rates are less reliable since Apple MPP (Mail Privacy Protection) — inflated by 10-30% for audiences with high Apple Mail usage. Use click rate as primary engagement metric. Single campaign metrics have high variance — judge by 10+ campaign averages. Industry benchmarks vary significantly by sub-industry, list quality, and send frequency.

### ⚠️ Human Checkpoint
> Verify data accuracy before sharing reports with stakeholders. Context matters: algorithm changes, seasonal effects, and list growth affect metrics independently of campaign quality.

> **Benchmark Context**: Average email ROI is $36-42 per dollar spent. Top-performing email programs achieve 25%+ open rates and 4%+ click rates. Automated emails outperform campaigns 3x on click rate. Lists that grow organically outperform purchased lists by 5x on engagement. The optimal sending frequency is 1-3 emails per week for most B2C brands.

## Output Contract

### Deliverable: Markdown Performance Analysis

```markdown
# Email Performance Analysis: [Period]

## Executive Summary
- Overall health: [good/needs attention/critical]
- Key highlight: [best achievement]
- Key concern: [biggest issue]

## Metric Overview
| Metric | This Period | Previous | Change | Benchmark | Status |
|---|---|---|---|---|---|

## Trend Analysis
[Chart description or data table showing trends]

## Top Campaigns
| Campaign | Date | Sends | Open | Click | Revenue |
|---|---|---|---|---|---|

## Diagnostic Findings
1. [Finding with data and recommendation]

## Optimization Recommendations
### Quick Wins
1. [Action] — Expected impact: [metric improvement]

### Strategic Initiatives
1. [Action] — Expected impact: [metric improvement]

## Next Period Targets
| Metric | Current | Target | Strategy |
|---|---|---|---|
```

## Platform Implementation Steps

### Data Collection
1. Export campaign data from ESP (all campaigns for the period)
2. Export automation/flow performance data separately
3. Pull revenue attribution data from e-commerce platform or CRM
4. Export list growth data (new subscribers, unsubscribes, bounces)

### Reporting Setup
1. Create a reporting template in Google Sheets or Looker Studio
2. Set up automated ESP data exports (weekly or monthly)
3. Build comparison views: MoM, YoY, campaign type, segment
4. Schedule recurring analysis cadence (monthly recommended)

### ESP-Specific Exports
- **Mailchimp**: Reports → Export to CSV; Audience → Growth History
- **Klaviyo**: Analytics → Metrics → Export; Flows → Analytics
- **HubSpot**: Marketing → Email → Analyze; Export performance data
- **SendGrid**: Statistics → Category Comparison → Export

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Misleading open rates | Apple MPP inflation | Use click rate as primary metric; segment Apple Mail users |
| Revenue misattribution | Wrong attribution window or model | Standardize attribution window (24h click, 7-day open); document model |
| Comparing incomparable campaigns | Different segments, goals, or send sizes | Normalize by segment and campaign type; compare like-to-like |
| Analysis paralysis | Too many metrics without prioritization | Focus on 3-5 KPIs aligned with business goals |

## How to Get Your Data

- **ESP export**: Campaign reports → export all campaigns for the period as CSV
- **Revenue**: E-commerce platform → orders attributed to email; or ESP revenue tracking
- **Benchmarks**: Mailchimp publishes industry benchmarks; Campaign Monitor annual report
- **No export**: Manually compile last 10 campaign metrics from ESP dashboard

## Example

**Input**: "Analyze Q4 email performance. E-commerce (home goods). 45 campaigns sent. Average open rate dropped from 28% to 22%. Click rate steady at 3.1%. Revenue from email: $180K. List: 65K subscribers."

**Output**: Health: needs attention — open rate decline is concerning but click rate holding suggests engaged readers are still engaging. Diagnosis: open rate decline likely driven by 3 factors: (1) Apple MPP adoption increasing (estimate 15% of opens are auto-opens), (2) list grew 18% in Q4 from holiday promotions — new subscribers haven't been segmented, (3) increased send frequency (3.5x/week in Q4 vs. 2x in Q3). Top campaigns: Holiday Gift Guide (38% open, 6.2% click, $32K revenue), Black Friday Preview (31% open, 5.8% click, $28K revenue). Bottom: weekly newsletters sent Tuesday had consistently lowest engagement. Revenue per email: $4K average — top quartile campaigns averaged $8.5K. Recommendations: (1) Segment Q4 holiday signups into separate nurture flow (quick win), (2) Reduce sending frequency to 2x/week for non-VIP segments, (3) Shift primary metric from opens to clicks given MPP impact, (4) A/B test send day — current Tuesday performance is 25% below Thursday sends. Q1 targets: click rate 3.5%, email revenue $200K, unsubscribe rate <0.15%.
