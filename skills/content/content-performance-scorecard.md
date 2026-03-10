---
name: content-performance-scorecard
description: >
  Score and rank content performance across engagement, SEO, conversion, and business impact metrics.
  Use this skill when the user says "content performance scorecard", "content ROI analysis",
  "which content performs best", "content metrics dashboard", "content performance ranking",
  "content effectiveness report", "content attribution analysis", "content engagement analysis",
  "content conversion tracking", "top performing content report", or "content impact measurement".
  Also trigger for content portfolio analysis, content investment ROI, or content decay tracking.
---

> **How this skill works:** You export your content analytics data (from Google Analytics, CMS, content management platforms, etc.) as a CSV or spreadsheet, and Claude scores it. Claude cannot connect to live content platforms or pull data directly — you bring the data, Claude brings the scoring and analysis.

# Content Performance Scorecard

Scores and ranks content across engagement, SEO, conversion, and business impact metrics to identify top performers, underperformers, and optimization opportunities.

## Granularity Check

> **Session time**: ~10 min data prep + ~10 min Claude session. Input is content analytics exports. Output is Markdown scorecard with rankings and recommendations.

## User Intent Mapping

- "Which blog posts are performing best?" (ranking)
- "Content ROI — what's working?" (ROI)
- "Score our content library" (scoring)
- "Content performance report for leadership" (executive report)
- "Which content drives the most leads?" (conversion)
- "Our content metrics are all over the place" (framework)
- "Content attribution — what's driving revenue?" (attribution)
- "Content decay — which posts are losing traffic?" (decay)
- "Content portfolio analysis" (portfolio)
- "Benchmark our content performance" (benchmarking)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Content Data | CSV/Text | URLs, traffic, engagement metrics per piece |
| Business Goals | Text | What success looks like (traffic, leads, revenue) |
| Time Period | Text | Reporting period |

### If You Don't Have This Data

- **No analytics export?** Pull top 20 pages from Google Analytics and paste traffic + engagement metrics. Claude scores from there.
- **No conversion tracking?** Claude scores on engagement and SEO metrics, and recommends conversion tracking setup.
- **No revenue attribution?** Claude uses proxy metrics (leads, signups) and recommends attribution model setup.
- **First time measuring?** Claude creates a scoring framework and baseline for future comparison.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Conversion Data | CSV | Leads, signups, or revenue per content piece |
| SEO Rankings | CSV | Keyword rankings and search traffic per page |
| Social Shares | CSV | Share counts by platform |
| Production Cost | Text | Time or money invested per content piece |
| Content Type Tags | Text | Blog, video, whitepaper, etc. |

## Process

### Step 1: Scoring Framework
| Dimension | Weight | Metrics | Scoring |
|---|---|---|---|
| Engagement | 25% | Time on page, scroll depth, bounce rate | 1-10 scale |
| SEO | 25% | Organic traffic, rankings, impressions | 1-10 scale |
| Conversion | 30% | Leads, signups, downloads, revenue | 1-10 scale |
| Efficiency | 20% | Cost per lead, ROI, production time | 1-10 scale |

### Step 2: Content Scoring
Per content piece:
- Calculate composite score (weighted average of dimensions)
- Rank within content type (blog vs. blog, video vs. video)
- Identify trend (growing, stable, declining)
- Flag anomalies (high traffic but zero conversions, low traffic but high conversion rate)

### Step 3: Portfolio Analysis
- Content type performance comparison
- Topic/category performance
- Author performance (if applicable)
- Publish date vs. performance (evergreen vs. time-sensitive)
- Content length vs. performance correlation

### Step 4: Decay Detection
- Month-over-month traffic decline > 20% = flagged
- Ranking drops > 5 positions = flagged
- Content older than 12 months without update = review candidate
- Conversion rate declining while traffic stable = CTA/offer issue

### Step 5: Recommendations
- **Double down**: Top 10% performers — create more like these, update and expand
- **Optimize**: Middle 50% — improve CTAs, update content, add internal links
- **Consolidate**: Bottom 20% with overlap — merge into stronger pieces
- **Retire**: Bottom 10% with no traffic and no conversions — redirect or remove

### Confidence & Sample Size

> **Confidence Note**: Content scoring requires at least 30 days of data per piece for reliable engagement metrics. New content (<90 days old) should be scored separately — it hasn't reached full SEO potential. Conversion attribution depends on your model (first-touch, last-touch, multi-touch) — be consistent. Scores are relative to your library, not absolute benchmarks.

### ⚠️ Human Checkpoint
> Verify data accuracy before sharing scorecards with stakeholders. Context matters: seasonal content, campaign-specific pieces, and brand-building content may score low on conversion but serve other strategic purposes.

> **Benchmark Context**: Top 10% of content generates 90% of traffic for most sites. Average blog post takes 6-12 months to reach full SEO potential. Content with 10+ internal links gets 40% more organic traffic. Updated content sees an average 106% traffic increase. 60-70% of content published by companies gets zero organic traffic.

## Output Contract

### Deliverable: Markdown Content Scorecard

```markdown
# Content Performance Scorecard: [Period]

## Executive Summary
- Total pieces scored: [number]
- Average score: [X/10]
- Top performer: [title]
- Biggest opportunity: [finding]

## Scorecard
| Rank | Content | Type | Engagement | SEO | Conversion | Efficiency | Score |
|---|---|---|---|---|---|---|---|

## Top Performers (Top 10%)
| Content | Score | Key Strength | Action |
|---|---|---|---|

## Optimization Candidates (Middle 50%)
| Content | Score | Weakness | Fix |
|---|---|---|---|

## Decay Alerts
| Content | Traffic Change | Ranking Change | Action |
|---|---|---|---|

## Portfolio Insights
- Best content type: [type] (avg score: X)
- Best topic: [topic] (avg score: X)
- Content ROI: [metric]

## Recommendations
1. [Action] — Expected impact: [metric]
```

## Platform Implementation Steps

### Google Analytics
1. Export top pages report for the period (Behavior → Site Content → All Pages)
2. Add conversion goals or events to track content-driven leads
3. Set up content groupings by type, topic, and author
4. Create custom report combining traffic, engagement, and conversion metrics

### Search Console
1. Export Performance report filtered by page
2. Map pages to clicks, impressions, CTR, and average position
3. Identify pages with high impressions but low CTR (title/meta optimization)

### CRM/Marketing Automation
1. Set up content attribution tracking (UTM parameters on all content links)
2. Export leads attributed to content pages
3. Track content-influenced pipeline and revenue

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Misleading scores | Incomplete data or wrong attribution model | Verify data sources; standardize attribution; score with available data only |
| New content scores low | Not enough time for SEO/distribution | Score new content separately; compare at 90-day mark |
| All scores similar | Scoring weights don't differentiate | Adjust weights to emphasize business-critical metrics |
| Stakeholder disagreement | Different teams value different metrics | Customize scorecards per stakeholder; use dimension scores, not just composite |

## How to Get Your Data

- **Traffic**: Google Analytics → Behavior → Site Content → All Pages → Export
- **SEO**: Google Search Console → Performance → Pages → Export
- **Conversions**: CRM or marketing automation → leads by content source
- **No export**: List your top 10-20 pieces with approximate traffic and any conversion data — Claude scores from there

## Example

**Input**: "Score our blog content. 85 posts published over 18 months. Google Analytics export with pageviews, avg time on page, bounce rate. Search Console export with clicks and impressions. No conversion tracking yet. B2B SaaS, goal is lead generation."

**Output**: Scored 85 posts on engagement (40% weight — no conversion data) and SEO (60% weight). Top 5: (1) "Complete Guide to [Topic]" — Score 9.2, 12K monthly organic, 4:30 avg time, growing 15% MoM. (2) "How to [Task]" — Score 8.7, 8K monthly organic, 3:45 avg time. Bottom 10: all under 50 monthly visits, published 12+ months ago. Decay alerts: 8 posts lost >30% traffic in last 3 months — all need content refresh. Portfolio insights: "How to" posts average 3.2x more traffic than news/opinion posts. Posts over 2,000 words score 2.1x higher than posts under 1,000 words. Recommendations: (1) URGENT — add lead capture (CTA, content upgrade) to top 10 posts — these get 60% of all traffic but capture zero leads. (2) Refresh 8 decaying posts — update stats, add new sections, republish. (3) Consolidate 12 low-performing posts into 4 comprehensive guides. (4) Set up conversion tracking before next scorecard.
