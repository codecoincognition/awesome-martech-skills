---
name: content-distribution-strategy
description: >
  Plan multi-channel content distribution — organic, paid, earned, and owned channels with timing and budget allocation.
  Use this skill when the user says "content distribution strategy", "where to distribute content",
  "content promotion plan", "content amplification strategy", "multi-channel content distribution",
  "content syndication plan", "paid content promotion", "organic content distribution", "content
  reach optimization", "content distribution calendar", or "how to promote our content". Also
  trigger for content seeding strategy, influencer distribution, or channel mix optimization.
---

# Content Distribution Strategy

Plans multi-channel content distribution across organic, paid, earned, and owned channels with timing optimization, budget allocation, and performance tracking for maximum content reach and engagement.

## Granularity Check

> **Time**: ~5 min data prep → ~10 min Claude session → ~60-120 min building in your project management tool. If implementing, add 2-4 hours for channel setup. Input is content inventory and channel access. Output is Markdown distribution plan with channel-specific tactics.

## User Intent Mapping

- "Where should we distribute this blog post?" (single piece)
- "Content distribution strategy for Q2" (quarterly plan)
- "How to promote content without a big budget" (budget-conscious)
- "Content syndication — where and how" (syndication)
- "Paid content promotion strategy" (paid)
- "Organic content distribution playbook" (organic)
- "Content amplification across channels" (amplification)
- "Content distribution calendar" (scheduling)
- "Which channels drive the most traffic for our content?" (channel analysis)
- "Content seeding strategy for launch" (launch)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Content Type | Text | Blog, video, whitepaper, podcast, infographic, etc. |
| Target Audience | Text | Who you're trying to reach |
| Available Channels | Text | Which channels you have access to |

### If You Don't Have This Data

- **Not sure which channels?** Claude maps your audience to the highest-impact channels and recommends where to start.
- **No budget for paid?** Claude focuses on organic and earned distribution strategies that cost zero.
- **No distribution process?** Claude provides a repeatable distribution checklist you can use for every piece of content.
- **No performance data?** Claude recommends tracking setup and benchmarks to measure from day one.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Budget | Text | Monthly or per-piece promotion budget |
| Past Performance | CSV/Text | Which channels have driven the most traffic |
| Content Calendar | Text | Publishing schedule and frequency |
| Team Size | Text | Who handles distribution |
| Competitor Channels | Text | Where competitors distribute content |

## Process

### Step 1: Channel Mapping
| Channel Type | Examples | Cost | Reach | Control |
|---|---|---|---|---|
| Owned | Blog, email, app | Low | Medium | High |
| Earned | PR, guest posts, shares | Low | High | Low |
| Paid | Social ads, native ads, SEM | High | High | High |
| Shared | Social organic, communities, partnerships | Low | Medium | Medium |

### Step 2: Content-Channel Fit
- Blog posts → email newsletter, social, syndication, SEO
- Videos → YouTube, social native, email embed, blog embed
- Whitepapers → email, LinkedIn, paid social, partner distribution
- Infographics → Pinterest, social, blog, PR outreach
- Podcasts → Apple/Spotify, social clips, email, blog recap
- Case studies → sales enablement, email, LinkedIn, website

### Step 3: Distribution Timeline
- **Day 0 (publish)**: Email list, social channels, internal Slack
- **Day 1-3**: Community posting, employee amplification, influencer outreach
- **Week 1**: Syndication, guest post pitches, forum seeding
- **Week 2-4**: Paid promotion (if budget), retargeting, partner sharing
- **Month 2-3**: Repurpose and redistribute (new format, new channels)

### Step 4: Channel-Specific Tactics
- **Email**: Segment by topic interest; feature in newsletter; dedicated send for high-value pieces
- **LinkedIn**: Native post (not just link); personal profiles outperform company pages 3x; comment engagement
- **Twitter/X**: Thread format; quote-tweet with insight; schedule 3-5 tweets per piece over 2 weeks
- **Reddit/Communities**: Add genuine value; don't just drop links; engage in comments
- **Paid social**: Promote top 10% of organic performers; lookalike audiences; retargeting
- **SEO**: Internal linking from existing content; update older posts to link to new content

### Step 5: Budget Allocation
- **No budget**: 100% organic — email, social, communities, SEO, repurposing
- **$500-1K/month**: 70% organic, 30% paid boosting of top performers
- **$1-5K/month**: 50% organic, 50% paid — social ads + native advertising
- **$5K+/month**: 40% organic, 40% paid, 20% influencer/partnership

### Confidence & Sample Size

> **Confidence Note**: Distribution effectiveness varies dramatically by industry and audience. What works for B2B (LinkedIn, email) differs from B2C (Instagram, TikTok). Test 2-3 channels deeply before spreading thin across many. The 80/20 rule applies: 80% of results will come from 20% of channels. Measure by conversions, not just traffic.

### ⚠️ Human Checkpoint
> Review distribution plan for brand safety (which communities/platforms align with your brand). Verify budget allocation against actual channel performance before committing spend.

> **Benchmark Context**: Consult current industry reports for up-to-date benchmarks relevant to this analysis.

## Output Contract

### Deliverable: Markdown Distribution Plan

```markdown
# Content Distribution Strategy: [Content/Campaign]

## Channel Matrix
| Channel | Type | Audience Fit | Cost | Priority |
|---|---|---|---|---|

## Distribution Timeline
| Timing | Channel | Action | Owner |
|---|---|---|---|

## Channel Playbooks
### [Channel Name]
- Format: [how to adapt content]
- Timing: [when to post]
- Frequency: [how often]
- CTA: [what action to drive]

## Budget Allocation
| Channel | Monthly Budget | Expected Reach | Expected Clicks | CPA |
|---|---|---|---|---|

## Measurement Plan
| Channel | Primary Metric | Target | Tracking Method |
|---|---|---|---|
```

## Platform Implementation Steps

### Social Media
1. Adapt content format for each platform (native > links)
2. Schedule posts using Buffer, Hootsuite, or native schedulers
3. Enable employee amplification through advocacy tools
4. Set up UTM parameters for every link shared

### Email
1. Segment list by content topic interest
2. A/B test subject lines featuring the content
3. Schedule dedicated sends for high-value pieces
4. Include content in regular newsletter roundups

### Paid Promotion
1. Wait 48-72 hours to identify organic top performers
2. Set up campaigns on Meta, LinkedIn, or Google based on audience
3. Start with small budgets ($20-50/day) and scale winners
4. Use retargeting pixels to capture content readers

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Low reach despite multi-channel | Spreading too thin; no channel depth | Focus on 2-3 highest-performing channels |
| High traffic, low conversions | Wrong audience or weak CTA | Review targeting; add clear next-step CTAs |
| Community backlash | Self-promotional posting without value | Lead with value; engage genuinely; reduce frequency |
| Budget wasted on paid | Promoting underperforming content | Only boost content that performs organically first |

## How to Get Your Data

- **Channel performance**: Google Analytics → Acquisition → Source/Medium for content traffic by channel
- **Social metrics**: Native analytics from each platform or social management tool
- **Email performance**: ESP → campaign reports filtered by content-focused sends
- **No data**: Describe your audience and available channels — Claude recommends a starter distribution plan

## Example

**Input**: "Content distribution strategy for a B2B SaaS blog. Publishing 2 posts/week. Channels: email (12K subscribers), LinkedIn company page (5K followers), Twitter (2K followers). No paid budget. Team of 1 marketer."

**Output**: Priority channels: (1) Email — highest ROI for B2B; segment by topic; feature each post in weekly digest + 1 dedicated send/month for pillar content. (2) LinkedIn — post as personal profile (CEO or marketer), not company page; native text post with key insight + link in first comment; 3x posts per blog post (publish day, 3 days later with different angle, 1 week later with data point). (3) Twitter — thread summarizing key points; schedule 4 tweets over 2 weeks per post. (4) FREE additions: repurpose to LinkedIn newsletter (algorithmic boost), submit to relevant Slack communities and subreddits (genuine value, not link-dropping), internal links from older blog posts. Distribution checklist per post: Day 0 — publish, email to segment, LinkedIn post (personal), Twitter thread. Day 1 — share in 2 communities. Day 3 — LinkedIn repost with new angle. Week 2 — Twitter reminder. Month 2 — repurpose as infographic or carousel. Expected results: email drives 40-50% of traffic, LinkedIn 20-30%, organic search 15-20% (growing over time).

## Related Skills

- **[Content Pillar Strategy](./content-pillar-strategy.md)** — Use to understand your content hierarchy before planning distribution; pillar pages need different distribution than cluster content.
- **[Content Repurposer](./content-repurposer.md)** — Use to create multiple derivative assets from each piece of content before distributing across channels.
- **[Social Content Calendar](../social/social-content-calendar.md)** — Use to align your organic and paid social distribution with your broader content distribution strategy.
- **[Editorial Calendar Builder](./editorial-calendar-builder.md)** — Use to embed distribution timelines and channel requirements into your content calendar.
