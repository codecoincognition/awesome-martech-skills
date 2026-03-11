---
name: influencer-outreach-brief
description: >
  Create influencer collaboration briefs with targeting criteria, outreach templates, and ROI frameworks.
  Use this skill when the user says "influencer outreach", "find influencers", "influencer brief",
  "creator collaboration", "influencer marketing plan", "influencer campaign", "brand ambassador
  program", "micro-influencer strategy", "creator partnership", "influencer contract brief",
  or "UGC creator outreach". Also trigger for influencer vetting criteria, rate card analysis,
  or influencer performance benchmarks.
---

# Influencer Outreach Brief

Creates structured influencer collaboration briefs with targeting criteria, outreach templates, compensation frameworks, and performance tracking plans. Covers micro to macro influencers across platforms.

## Granularity Check

> **Time**: ~5 min data prep → ~10 min Claude session → ~20-40 min scheduling in Buffer / Hootsuite / native platform. If implementing output in a platform, add 15-20 min for outreach setup. Input is campaign goals and brand info. Output is Markdown brief with outreach templates.

## User Intent Mapping

- "Create an influencer brief for our product launch" (campaign-specific)
- "Find micro-influencers in [niche]" (discovery)
- "Write influencer outreach emails" (outreach)
- "How much should we pay influencers?" (compensation)
- "Influencer marketing strategy for a small budget" (strategic)
- "Create a UGC creator brief" (UGC-specific)
- "Influencer campaign ROI framework" (measurement)
- "Brand ambassador program structure" (long-term)
- "Vet this influencer for brand fit" (evaluation)
- "Influencer contract terms and deliverables" (legal/ops)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Brand/Product | Text | What you're promoting and key selling points |
| Campaign Goal | Text | awareness, conversions, content creation, launch buzz |
| Budget Range | Text | Total budget or per-influencer range |

### If You Don't Have This Data

- **No budget defined?** Start with $500-$2,000 for a micro-influencer test campaign. This skill helps you allocate it.
- **No brand guidelines?** Describe your brand in 3 adjectives and share your website URL. Claude infers the rest.
- **No influencer list?** This skill creates the targeting criteria — you then use them to search on Creator.co, Upfluence, or manually on social.
- **No past influencer data?** Industry benchmarks are included to help you set expectations.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Target Audience | Text | Demographics, interests, platforms |
| Platform Focus | Text | Instagram, TikTok, YouTube, Twitter, LinkedIn |
| Influencer Tier | Text | nano (<5K), micro (5K-50K), mid (50K-500K), macro (500K+) |
| Content Requirements | Text | Post types, quantity, exclusivity period |
| Past Campaigns | Text | Previous influencer results for benchmarking |

## Process

### Step 1: Campaign Framework
- Define campaign objectives and KPIs
- Set content deliverables (posts, Stories, Reels, videos)
- Establish timeline and key dates
- Define brand guidelines and do/don't messaging

### Step 2: Influencer Targeting Criteria
- Platform and follower range
- Engagement rate minimum (by tier: nano >5%, micro >3%, mid >2%, macro >1%)
- Content style alignment
- Audience demographics match
- Brand safety requirements
- Red flags to screen for

### Step 3: Compensation Framework
| Tier | Followers | Typical Rate (per post) | Alternative Models |
|---|---|---|---|
| Nano | 1K-5K | $50-$250 | Product gifting, affiliate |
| Micro | 5K-50K | $250-$1,500 | Flat fee + affiliate |
| Mid | 50K-500K | $1,500-$10,000 | Flat fee + usage rights |
| Macro | 500K+ | $10,000-$100,000+ | Campaign packages |

### Step 4: Outreach Templates
- Initial DM (platform-native, 2-3 sentences)
- Follow-up email (detailed brief, compensation, timeline)
- Negotiation guidelines (rate flexibility, content add-ons)
- Contract key terms checklist

### Step 5: Performance Tracking Plan
- Metrics to track per influencer: impressions, reach, engagement, link clicks, conversions
- Attribution method: unique discount codes, UTM links, landing pages
- ROI calculation: (revenue generated - campaign cost) / campaign cost × 100
- Reporting cadence and template

### Confidence & Sample Size
> **Confidence Note**: Influencer marketing ROI varies widely. Industry average is $5.78 return per $1 spent, but ranges from negative to 20x+ depending on niche, product-audience fit, and content quality. Test with 3-5 influencers before scaling.

### ⚠️ Human Checkpoint
> Review influencer selections for brand safety. Check recent content (last 30 days) for controversial posts, fake follower indicators (engagement rate vs. follower count ratio), and audience authenticity.

> **Benchmark Context**: See Sprout Social 2024 Index, Later 2024 Social Media Industry Report, and Buffer 2024 State of Social for current industry benchmarks relevant to this analysis.
## Output Contract

### Deliverable: Markdown Brief

```markdown
# Influencer Campaign Brief: [Campaign Name]

## Campaign Overview
- Objective: [goal]
- Budget: [range]
- Timeline: [dates]
- Platforms: [platforms]

## Targeting Criteria
- Follower range: [X-Y]
- Minimum engagement rate: [X%]
- Content style: [description]
- Audience match: [demographics]

## Content Deliverables
| Deliverable | Quantity | Specs |
|---|---|---|

## Compensation
| Tier | Rate | Model |
|---|---|---|

## Outreach Templates
### Initial DM
[template]

### Follow-up Email
[template]

## Performance Tracking
| Metric | Target | Tracking Method |
|---|---|---|
```

## Platform Implementation Steps

### Creator.co / Upfluence / AspireIQ
1. Create a new campaign with the brief details
2. Set targeting filters matching the criteria
3. Use the outreach templates for initial contact
4. Track deliverables and performance in-platform

### Google Sheets (Manual Tracking)
1. Create a tracker: Influencer Name, Platform, Followers, ER, Rate, Status, Deliverables, Performance
2. Log outreach status (contacted, responded, negotiating, confirmed, posted)
3. Track unique discount code usage per influencer
4. Calculate ROI per influencer post-campaign

### Email (Direct Outreach)
1. Personalize the email template for each influencer
2. Attach a 1-page PDF brief (created from the output)
3. Follow up after 3-5 business days if no response
4. Average response rate: 15-25% for personalized outreach

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Low response rate | Generic outreach | Personalize first line — reference specific content they've created |
| Budget mismatch | Influencer rates higher than expected | Negotiate with content usage rights trade-offs, or target smaller tier |
| Poor content quality | Unclear brief | Provide visual examples, mood boards, and specific do/don't lists |
| No trackable ROI | Missing attribution | Always use unique codes + UTM links; set up before campaign launches |

## How to Get Your Data

- **No tools needed**: Describe your brand, budget, and goals — Claude creates the brief
- **Past campaigns**: Export results from your influencer platform or manually note performance per influencer
- **Influencer discovery**: Search hashtags on Instagram/TikTok, use Creator.co free search, or check competitors' tagged posts

## Example

**Input**: "Influencer campaign for a $79 fitness app. $5,000 budget. Target: women 25-35, fitness enthusiasts. Platform: Instagram + TikTok."

**Output**: Target 10-15 micro-influencers (10K-50K followers, 3%+ engagement rate). Budget: $300-500/influencer for 1 Reel + 2 Stories. Targeting: fitness, wellness, home workout niches. Avoid: influencers who promote competing apps. Outreach DM: "Hey [name] — love your [specific recent post]. We're launching [app] and think your audience would genuinely benefit. Would you be open to a paid collab? DM me and I'll send details!" Attribution: unique discount code per influencer (CREATOR15). Expected: 50K-150K total reach, 2-5% engagement rate, 50-200 app installs at $25-100 CPA.

## Related Skills

- **[Social Ad Creative Brief](./social-ad-creative-brief.md)** — Use alongside this skill to align influencer creative requirements with your broader social ad strategy.
- **[Social Listening Report](./social-listening-report.md)** — Use to identify potential influencers and understand audience sentiment about collaborations.
- **[Content Repurposer](../content/content-repurposer.md)** — Use to amplify influencer-created content across your owned channels.
- **[Campaign Brief Synthesizer](../content/campaign-brief-synthesizer.md)** — Use to align influencer outreach with broader campaign requirements.
