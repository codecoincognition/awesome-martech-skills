---
name: video-analytics-interpreter
description: >
  Interpret video and podcast analytics to optimize content strategy, audience growth, and engagement.
  Use this skill when the user says "video analytics interpretation", "YouTube analytics review",
  "podcast analytics analysis", "video performance metrics", "audience retention analysis", "video
  CTR optimization", "podcast download trends", "video engagement metrics", "watch time analysis",
  "subscriber growth analysis", or "content performance by video type". Also trigger for video
  funnel analysis, podcast listener behavior analysis, or video algorithm optimization.
---

# Video Analytics Interpreter

Interprets video and podcast analytics data to identify performance patterns, audience behavior insights, and optimization opportunities for content strategy.

## Granularity Check

> **Session time**: ~5 min data export + ~10 min Claude session. If implementing strategy changes, add 2-4 weeks to measure impact. Input is analytics exports or screenshots from video/podcast platforms. Output is Markdown analysis with performance insights, content recommendations, and growth strategy.

## User Intent Mapping

- "What do our YouTube analytics mean?" (interpretation)
- "Why are our videos underperforming?" (diagnosis)
- "Which video topics perform best?" (content strategy)
- "Audience retention is dropping" (retention)
- "Low click-through rate on thumbnails" (CTR)
- "Podcast download trends declining" (podcast)
- "How to grow our channel" (growth)
- "Video SEO — what's working?" (discovery)
- "Compare performance across video types" (comparison)
- "Algorithm optimization for our channel" (algorithm)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Analytics Data | Text/CSV/Screenshot | Platform analytics (views, watch time, retention, engagement) |
| Content Type | Text | What kind of video/podcast content you produce |
| Goals | Text | What you want to improve (views, subscribers, leads, revenue) |

### If You Don't Have This Data

- **No analytics export?** Claude walks you through exporting data from YouTube Studio, Spotify for Podcasters, Apple Podcasts Connect, or other platforms — takes 2-5 minutes.
- **New channel with little data?** Claude provides benchmarks for your category and recommends content experiments to generate data faster.
- **Multiple platforms?** Claude helps you compare cross-platform performance and identify which platform deserves more investment.
- **Only vanity metrics?** Claude shows you which metrics actually predict growth and how to access them in your platform.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Historical Data | CSV | 3-12 months of performance data for trend analysis |
| Audience Demographics | Text | Viewer age, gender, location, device data |
| Content Calendar | Text | Past content with topics, formats, and publish dates |
| Revenue Data | Text | Ad revenue, sponsorship, affiliate, or conversion data |
| Competitor Channels | Text | Competitor channels for benchmarking |

## Process

### Step 1: Core Metrics Framework

| Metric | What It Measures | Healthy Range | Red Flag |
|---|---|---|---|
| Views | Reach / discovery | Growing month-over-month | Declining 3+ months |
| Watch time | Total engagement | Growing faster than views | Flat while views grow |
| Average view duration | Content quality | 40-60% of video length | Below 30% |
| Audience retention | Moment-by-moment quality | Gradual decline curve | Sharp early drop-offs |
| CTR (impressions → clicks) | Thumbnail + title effectiveness | 4-10% | Below 2% |
| Subscriber conversion | Channel loyalty | 1-3% of viewers subscribe | Below 0.5% |
| Engagement rate | Community connection | 4-8% (likes + comments / views) | Below 2% |

### Step 2: Audience Retention Analysis

| Pattern | Meaning | Action |
|---|---|---|
| Sharp drop at 0-30 seconds | Weak hook or misleading title/thumbnail | Rewrite opening — deliver value in first 15 seconds |
| Gradual steady decline | Normal viewing pattern | Content is performing well |
| Drop at specific timestamp | Boring section or topic shift | Cut or restructure that segment |
| Spike at specific timestamp | Viewers seeking specific moment | Create standalone content around that topic |
| Flat retention (unusual) | Highly engaged niche audience | Double down on this format/topic |
| Re-watches (retention >100%) | Tutorial or reference content | Optimize for search, add chapters |

### Step 3: Content Performance Matrix

| Dimension | How to Analyze | What It Reveals |
|---|---|---|
| Topic | Group videos by subject | Which topics your audience wants |
| Format | Compare tutorials vs. vlogs vs. interviews | Which formats retain viewers |
| Length | Plot watch time vs. video length | Optimal duration for your audience |
| Publish day/time | Views by day of week and hour | When your audience is active |
| Thumbnail style | CTR by thumbnail type | Which visual approach drives clicks |
| Title pattern | CTR by title formula | Which framing hooks viewers |

### Step 4: Podcast-Specific Metrics

| Metric | What It Measures | Benchmark | Action |
|---|---|---|---|
| Downloads per episode | Reach | Varies by niche | Track trend, not absolute |
| Completion rate | Content quality | 60-80% is strong | Below 50% = too long or weak content |
| Listener retention (ep to ep) | Loyalty | 60-70% return rate | Below 40% = audience not hooked |
| Subscriber growth | Channel health | 5-10% monthly | Flat = discovery issue |
| Drop-off timestamp | Engagement pattern | Gradual decline | Sharp drops = specific content issue |
| Platform distribution | Audience reach | Apple 40%, Spotify 30%, other 30% | Over-reliance on one platform |

### Step 5: Growth Diagnosis

| Symptom | Likely Cause | Fix |
|---|---|---|
| Views flat, good retention | Discovery/SEO issue | Improve titles, thumbnails, SEO, posting frequency |
| Views growing, retention dropping | Clickbait or wrong audience | Align content with title/thumbnail promise |
| High views, low subscribers | No subscribe CTA or weak channel identity | Add CTA, create series/playlists, define channel value |
| Good metrics but no revenue | Monetization not set up or wrong audience | Add CTAs, affiliate links, sponsorship, or product offers |
| Engagement dropping | Content fatigue or algorithm shift | Experiment with new formats, topics, or collaborations |
| New videos underperform old ones | Algorithm favoring library over new | Refresh old content, link new to old, update thumbnails |

### Step 6: Algorithm Optimization

| Factor | YouTube | Spotify/Apple Podcasts | LinkedIn Video |
|---|---|---|---|
| Discovery driver | Watch time + CTR + retention | Listener completion + saves | Engagement rate + dwell time |
| Optimal frequency | 1-3x/week consistent | Weekly at same day/time | 3-5x/week short-form |
| Title optimization | Curiosity + keyword + under 60 chars | Clear topic + guest name | Hook question or stat |
| Thumbnail/cover | High contrast, face, emotion, text overlay | Consistent branding | N/A (auto-generated) |
| Description | Keywords in first 2 lines, chapters | Episode notes with keywords | Full post as description |
| Engagement signals | Likes, comments, shares, saves | Reviews, follows, shares | Reactions, comments, reposts |

### Confidence & Sample Size

> **Confidence Note**: Video analytics require at least 10-20 published videos to identify reliable patterns. Individual video performance is heavily influenced by external factors (trending topics, algorithm changes, competitor activity). Trends over 3+ months are more reliable than week-to-week fluctuations. YouTube analytics take 48-72 hours to stabilize — don't make decisions based on first-day performance. Podcast analytics are inherently less precise due to RSS-based delivery — downloads ≠ listens.

### ⚠️ Human Checkpoint
> Validate analytics insights against your own content knowledge — data alone can miss context like seasonal topics, one-time viral moments, or algorithm experiments. Before making major strategy changes based on data, test with 3-5 videos/episodes to confirm the pattern holds.

> **Benchmark Context**: Average YouTube CTR across all channels is 2-10% depending on category. Average audience retention is 50-60% for videos under 10 minutes and 40-50% for longer content. Channels posting 1-3x per week grow subscribers 2-4x faster than monthly posters. The top 10% of podcast episodes account for 50% of total downloads. 70% of YouTube views come from algorithmic recommendations (Browse, Suggested, Shorts feed), not search.

## Output Contract

### Deliverable: Markdown Analytics Report

```markdown
# Video/Podcast Analytics Report: [Channel Name]

## Performance Summary
| Metric | Current | Previous Period | Trend |
|---|---|---|---|

## Top Performing Content
| Title | Views | Retention | CTR | Engagement | Why It Worked |
|---|---|---|---|---|---|

## Underperforming Content
| Title | Views | Retention | CTR | Issue | Fix |
|---|---|---|---|---|---|

## Audience Insights
- Demographics: [key audience data]
- Behavior: [viewing patterns]
- Growth: [subscriber/follower trends]

## Content Strategy Recommendations
| Priority | Recommendation | Rationale | Expected Impact |
|---|---|---|---|

## Growth Plan
| Action | Timeline | Metric to Track | Target |
|---|---|---|---|

## Algorithm Optimization
| Factor | Current | Recommended | Priority |
|---|---|---|---|
```

## Platform Implementation Steps

### YouTube Studio
1. Navigate to YouTube Studio → Analytics → Overview for channel-level metrics
2. Check Advanced Mode for custom date ranges and comparison periods
3. Export data: Analytics → Advanced Mode → Export (top-right) → CSV
4. Review Audience tab for viewer demographics and when they're online
5. Check Revenue tab (if monetized) for RPM trends and top-earning videos

### Spotify for Podcasters / Apple Podcasts Connect
1. Review episode-level performance (starts, streams, completion rate)
2. Check audience demographics (age, gender, location, listening platform)
3. Export data from the analytics dashboard for trend analysis
4. Monitor follower growth rate and episode-to-episode retention
5. Compare performance across platforms to identify growth opportunities

### Cross-Platform Analytics
1. Create a unified tracking spreadsheet with metrics from all platforms
2. Normalize metrics for comparison (views, engagement rate, growth rate)
3. Identify which platforms drive the best ROI for your content type
4. Track content repurposing performance (which clips drive discovery)
5. Monthly review cadence to adjust strategy based on cross-platform trends

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Over-optimizing for one metric | Chasing views at expense of retention or engagement | Balance growth metrics with quality metrics |
| Analysis paralysis | Too much data, no clear action | Focus on 3-5 key metrics; make one change at a time |
| Ignoring qualitative signals | Data doesn't capture sentiment or community feel | Read comments, survey audience, monitor social mentions |
| Copying competitor strategy | What works for them may not work for your audience | Test competitor tactics in small experiments before committing |

## How to Get Your Data

- **YouTube**: YouTube Studio → Analytics → Advanced Mode → Export CSV
- **Podcast (Spotify)**: Spotify for Podcasters → Analytics → Episodes → Export
- **Podcast (Apple)**: Apple Podcasts Connect → Analytics → Trends
- **LinkedIn Video**: LinkedIn page analytics → Content → filter by video
- **No export available**: Screenshot analytics dashboards — Claude interprets visual data
- **No data yet**: Describe your content and goals — Claude provides benchmarks and a measurement plan

## Example

**Input**: "YouTube analytics review for our B2B marketing channel. 45 videos, 2,800 subscribers. Average views: 850. Average CTR: 3.2%. Average retention: 38%. Best video: '5 LinkedIn Ads Mistakes' (12K views, 52% retention, 8.1% CTR). Worst videos: interview-format content (200-400 views, 25% retention). We post 2x/month."

**Output**: Key findings: (1) CTR at 3.2% is below B2B average (4-6%) — thumbnails and titles need work. Your best video at 8.1% CTR proves you can do better. (2) Retention at 38% is concerning — viewers leave before halfway. Your best video at 52% shows tactical, mistake-focused content retains viewers. (3) Interviews underperform significantly — 25% retention means viewers aren't connecting with the format. Recommendations: (1) P0 — Increase posting to weekly. At 2x/month, the algorithm deprioritizes your channel. Expected: 30-50% view increase within 8 weeks. (2) P0 — Double down on the "mistakes/errors" format that drove your best video. Create a series: "X Mistakes in [Channel]" for each marketing platform. (3) P1 — Thumbnail overhaul: use the style from your 8.1% CTR video across all new uploads. Test face + text overlay + high contrast. (4) P1 — Fix retention: restructure video openings — deliver the first insight within 30 seconds (not 2 minutes of intro). Add chapters for longer content. (5) P2 — Pause interviews or restructure them as "rapid fire" format (shorter, more energy, specific tactical questions). (6) P2 — Refresh top 10 performing videos with new thumbnails — YouTube re-tests old content with new thumbnails. Expected growth: subscribers from 2,800 to 5,000+ in 6 months with weekly tactical content and improved CTR/retention.
