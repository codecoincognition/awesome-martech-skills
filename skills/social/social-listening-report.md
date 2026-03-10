---
name: social-listening-report
description: >
  Analyze social media mentions, sentiment, and conversation themes for your brand or topic.
  Use this skill when the user says "social listening report", "what are people saying about us",
  "brand sentiment analysis", "social mentions report", "track brand mentions", "social media
  monitoring", "analyze social conversations", "what's the buzz around our brand", "competitor
  social analysis", "social sentiment tracker", or "monitor our social presence". Also trigger
  for hashtag analysis, share of voice reports, or social conversation mining.
---

> **How this skill works:** You export social mentions data from your listening platform (Brandwatch, Sprout Social, Hootsuite, etc.) or manually compile mentions as a CSV, and Claude analyzes it. Claude cannot connect to social platforms or pull live listening data directly — you bring the data, Claude brings the analysis.

# Social Listening Report

Analyzes social media mention data to surface sentiment trends, conversation themes, key influencers, and competitive share of voice. Produces an actionable report with response recommendations.

## Granularity Check

> **Time**: ~5 min data prep → ~10 min Claude session → ~20-40 min scheduling in Buffer / Hootsuite / native platform. If implementing output in a platform, add 10-20 min for setup. Input is exported mentions CSV. Output is Markdown report with sentiment breakdown and response plan.

## User Intent Mapping

- "What are people saying about us on social?" (brand monitoring)
- "Analyze sentiment around our product launch" (event-specific)
- "Social listening report for Q1" (periodic review)
- "What's our share of voice vs. competitors?" (competitive)
- "Find trending conversations in our industry" (market intelligence)
- "Track mentions of our rebrand" (campaign monitoring)
- "Who are the top influencers talking about us?" (influencer identification)
- "Analyze hashtag performance for our campaign" (hashtag analysis)
- "What complaints are trending on social?" (crisis detection)
- "Summarize social conversations about [topic]" (topic analysis)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Mentions Data | CSV | Columns: date, platform, author, text, likes, shares, sentiment (if available), source_url |

### If You Don't Have This Data

- **No social listening tool?** Search your brand name on Twitter/X, Reddit, LinkedIn manually. Copy 20-50 recent mentions into a spreadsheet.
- **No sentiment labels?** That's fine — Claude will classify sentiment from the text content.
- **No competitor data?** Search competitor brand names the same way. Even 20 mentions per competitor gives directional insights.
- **No historical data?** Start tracking now. Export weekly for 4 weeks to establish a baseline.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Competitor Mentions | CSV | Same format as above for 1-3 competitors |
| Time Period | Text | Analysis window (e.g., "March 2026") |
| Topics of Interest | Text list | Specific themes to track (e.g., "pricing", "customer support") |
| Previous Report | Markdown | Prior report for trend comparison |

## Process

### Step 1: Data Cleaning & Classification
- Deduplicate mentions (same text from syndicated posts)
- Classify sentiment: Positive / Neutral / Negative / Mixed
- Tag by platform: Twitter/X, LinkedIn, Reddit, Instagram, Facebook, TikTok
- Flag spam, bot accounts, and irrelevant mentions

### Step 2: Sentiment Analysis
- Overall sentiment distribution (% positive, neutral, negative)
- Sentiment trend over time (daily/weekly)
- Sentiment by platform (where are positive vs. negative conversations happening?)
- Top positive and negative mentions by engagement

### Step 3: Theme Extraction
- Cluster mentions into 5-10 conversation themes
- Rank themes by volume and sentiment
- Identify emerging topics (growing in mentions week-over-week)
- Flag potential crisis signals (sudden negative spikes)

### Step 4: Influencer & Reach Analysis
- Top 10 accounts by engagement on brand mentions
- Identify potential brand advocates (positive, high-reach, frequent)
- Flag detractors (negative, high-reach)
- Calculate approximate total reach

### Step 5: Competitive Share of Voice (if competitor data provided)
- Mention volume: your brand vs. competitors
- Sentiment comparison across brands
- Topic comparison (what conversations are competitors dominating?)

### Confidence & Sample Size
> **Confidence Note**: Results are only as reliable as your input data. Small datasets (<50 records or <30 days of data) produce directional insights, not statistically significant conclusions. Always note your sample size when sharing results with stakeholders.

### ⚠️ Human Checkpoint
> Review sentiment classifications for accuracy — automated sentiment analysis is ~70-80% accurate. Context, sarcasm, and industry jargon can be misclassified.

> **Benchmark Context**: Average brand mention sentiment splits roughly 60% neutral, 25% positive, 15% negative. Response rate to social mentions averages 25% across brands (Hootsuite 2024 Social Trends Report). Responding within 1 hour increases positive sentiment by 20%.
## Output Contract

### Deliverable: Markdown Report

```markdown
# Social Listening Report: [Brand] — [Period]

## Executive Summary
- Total mentions: [count]
- Sentiment: [% pos] positive, [% neutral] neutral, [% neg] negative
- Top theme: [theme]
- Key alert: [if any]

## Sentiment Breakdown
| Metric | Value | Trend |
|---|---|---|
| Positive | X% | ↑/↓ |
| Neutral | X% | ↑/↓ |
| Negative | X% | ↑/↓ |

## Top Themes
1. [Theme]: [volume] mentions, [sentiment] sentiment — [insight]

## Response Recommendations
1. [Priority action]
```

## Platform Implementation Steps

### Brandwatch / Sprout Social / Hootsuite
1. Navigate to Listening/Monitoring → select your query
2. Set date range to match analysis period
3. Export mentions as CSV (include all available fields)
4. Import Claude's output themes into your tagging taxonomy

### Google Sheets (Manual Tracking)
1. Create a spreadsheet with columns: Date, Platform, Author, Text, Sentiment, Theme
2. Paste Claude's classified mentions back into the sheet
3. Create pivot tables for sentiment by theme and platform
4. Set up a weekly refresh cadence

### Slack (Team Distribution)
1. Copy the Executive Summary section
2. Post to your #marketing or #social channel
3. Tag relevant team members on action items
4. Set up a weekly posting cadence

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Too few mentions | Small brand or niche industry | Expand search to industry terms, not just brand name |
| Sarcasm misclassification | Ironic positive language scored as positive | Review top negative and positive manually |
| Bot/spam noise | Automated mentions inflate volume | Filter by engagement (remove 0-engagement accounts) |
| Platform bias | Data from one platform only | Note platform limitations; recommend multi-platform tracking |

## How to Get Your Data

- **Brandwatch**: Queries → Export → CSV
- **Sprout Social**: Listening → Reports → Export
- **Hootsuite**: Streams → Export mentions
- **Twitter/X**: Search brand name → use TweetDeck or manual copy
- **Reddit**: Search brand name → sort by recent → copy posts/comments
- **Manual**: Google "[brand name]" + site:twitter.com/reddit.com/linkedin.com

## Example

**Input**: 340 mentions of "DataSync Pro" across Twitter, LinkedIn, and Reddit over 30 days.

**Output**: Sentiment: 31% positive, 52% neutral, 17% negative. Top theme: "integration issues" (45 mentions, 78% negative) — recommend public response addressing API stability. Hidden gem: 28 organic testimonials on LinkedIn (all positive) — reshare the best 5. Key influencer: @TechReviewerMike (12K followers, 3 positive mentions) — engage for potential partnership. Share of voice vs. CompetitorX: 60/40 in our favor, but CompetitorX dominates "enterprise" conversations.

## Related Skills

- **[Social Engagement Analyzer](./social-engagement-analyzer.md)** — Use alongside listening to understand which conversations drive the most engagement.
- **[Community Management Playbook](./community-management-playbook.md)** — Use to respond to identified brand mentions and community conversations in your playbook.
- **[Social Crisis Response Plan](./social-crisis-response-plan.md)** — Use to identify emerging crises and negative sentiment that require immediate response.
- **[Voice of Customer Miner](../insights/voice-of-customer-miner.md)** — Use to extract customer insights from social listening data.
