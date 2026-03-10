---
name: social-engagement-analyzer
description: >
  Analyze social media engagement data to find what content performs best and why.
  Use this skill when the user says "analyze my social media performance", "social engagement
  report", "which posts perform best", "social media analytics", "engagement rate analysis",
  "content performance report", "what's working on social", "social media ROI", "post
  performance analysis", "best performing posts", or "social analytics dashboard". Also
  trigger for platform-specific engagement analysis or social A/B test results.
---

> **How this skill works:** You export your social platform analytics data (from Meta Insights, TweetDeck, LinkedIn Analytics, TikTok Creator Studio, etc.) or a social management tool as a CSV, and Claude analyzes it. Claude cannot connect to social platforms or pull live data directly — you bring the data, Claude brings the analysis.

# Social Engagement Analyzer

Analyzes social media post performance data to identify winning content patterns, optimal posting times, and engagement drivers. Produces an actionable report with content strategy recommendations.

## Granularity Check

> **Session time**: ~5 min data prep + ~10 min Claude session. If implementing output in a platform, add 10-15 min for implementation. Input is exported post performance CSV. Output is XLSX analysis + Markdown strategy.

## User Intent Mapping

- "Which of my posts performed best this month?" (ranking)
- "Analyze my Instagram engagement rate trends" (platform-specific)
- "Why did this post go viral?" (post-specific)
- "What content type gets the most engagement?" (pattern finding)
- "When should I post for maximum reach?" (timing optimization)
- "Social media performance report for Q1" (periodic)
- "Compare engagement across platforms" (cross-platform)
- "What hashtags drive the most reach?" (tactical)
- "Our engagement rate is dropping — diagnose why" (problem solving)
- "Social content audit — what should we do more of?" (strategic)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Post Performance Data | CSV | Columns: date, platform, post_type, caption/topic, impressions, reach, likes, comments, shares, saves, link_clicks |

### If You Don't Have This Data

- **No CSV export?** Most platforms let you export. See "How to Get Your Data" below. Even screenshots of your last 20 posts' analytics work.
- **No impressions data?** Use likes + comments + shares as an engagement proxy.
- **No saves/bookmark data?** Exclude from analysis — focus on likes, comments, shares.
- **No cross-platform data?** Analyze one platform at a time. Start with your primary channel.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Time Period | Text | Analysis window (e.g., "Jan-Mar 2026") |
| Goals | Text | What you're optimizing for: reach, engagement, conversions, followers |
| Competitor Benchmarks | CSV | Competitor post performance for comparison |
| Content Categories | Text list | Tags for content types (e.g., "educational", "promotional", "behind-the-scenes") |

## Process

### Step 1: Data Profiling
- Calculate per-post engagement rate: (likes + comments + shares) / reach × 100
- Segment by: platform, content type, day of week, time of day
- Identify outliers (top 10% and bottom 10% performers)
- Flag data quality issues (missing fields, suspicious zeros)

### Step 2: Content Pattern Analysis
- Rank content types by average engagement rate
- Identify top-performing topics and themes
- Analyze caption length correlation with engagement
- Evaluate media type performance (image, video, carousel, text-only)
- Find the "golden ratio" — content mix that maximizes overall engagement

### Step 3: Timing Analysis
- Map engagement by day of week (heatmap)
- Map engagement by hour of day
- Find the intersection: best day + best time
- Identify timing patterns for different content types

### Step 4: Growth Metrics
- Follower growth rate trend
- Engagement rate trend (is it growing or declining?)
- Reach trend (organic vs. paid if available)
- Virality coefficient: shares / reach (what percentage gets amplified?)

### Step 5: Recommendations
- Top 3 content types to double down on
- Optimal posting schedule (days + times)
- Content to stop producing (consistent underperformers)
- Quick wins for the next 30 days

### Confidence & Sample Size
> **Confidence Note**: Minimum 30 posts needed for reliable pattern detection. Fewer than 30 posts produces directional insights only. Engagement rates are influenced by algorithm changes — compare within the same time period.

### ⚠️ Human Checkpoint
> Check if top-performing posts had external amplification (paid boost, influencer share, news cycle) that skews organic performance data.

> **Benchmark Context**: Average engagement rates by platform (2025-2026): Instagram 0.60-0.80%, LinkedIn 0.35-0.50%, Twitter/X 0.03-0.05%, Facebook 0.06-0.08%, TikTok 3-6%. Engagement rates decline as follower count increases. Video content averages 2-3x higher engagement than static images across all platforms.

## Output Contract

### Deliverable: Structured Analysis Tables in Markdown + Summary

**Table 1: Post Scorecard**
Columns: `date | platform | post_type | topic | impressions | reach | engagement_rate | performance_tier | key_driver`

**Table 2: Pattern Analysis**
Columns: `dimension | value | avg_engagement_rate | post_count | recommendation`

**Table 3: Action Plan**
Columns: `priority | action | expected_impact | effort | timeline`

**Markdown: Executive Summary**

## Platform Implementation Steps

### Sprout Social / Hootsuite
1. Navigate to Reports → Post Performance
2. Export as CSV for the analysis period
3. Import Claude's recommendations into your content calendar
4. Set up recurring monthly exports for trend tracking

### Google Sheets (Manual Dashboard)
1. Import the output XLSX
2. Create pivot tables by content type and day of week
3. Build charts for engagement rate trends
4. Share dashboard with team

### Notion (Strategy Doc)
1. Create a "Social Strategy" page
2. Paste the Markdown summary
3. Create a linked database from the action plan
4. Review and update monthly

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Too few posts | <15 posts in the period | Extend time range or combine platforms |
| Inconsistent metrics | Different platforms report differently | Normalize to engagement rate formula: (likes+comments+shares)/reach |
| Paid vs. organic mixed | Boosted posts skew averages | Separate paid and organic in analysis; note which posts were boosted |
| Algorithm change mid-period | Engagement drop not content-related | Split analysis into pre/post algorithm change periods |

## How to Get Your Data

- **Instagram**: Professional Dashboard → Content → Export
- **LinkedIn**: Analytics → Content → Export (Creator Mode required)
- **Twitter/X**: Analytics → Tweets → Export
- **Facebook**: Meta Business Suite → Content → Export
- **TikTok**: Analytics → Content → (manual capture, no CSV export yet)
- **Sprout/Hootsuite/Buffer**: Reports → Post Performance → Export CSV

## Example

**Input**: 90 posts across Instagram and LinkedIn over 3 months (Jan-Mar 2026).

**Output**: Top content type: Carousel posts (4.2% engagement rate vs. 1.1% average). Best posting day: Tuesday (2.3x avg engagement). Worst: Sunday (0.4x avg). Optimal time: 9:15 AM ET (LinkedIn), 12:30 PM ET (Instagram). Recommendation: Shift to 60% carousel, 30% Reels, 10% single image. Stop: Quote graphics (0.3% avg engagement, consistent underperformer). Quick win: Repurpose top 5 LinkedIn carousels as Instagram carousels — estimated 3x reach expansion.
