---
name: social-ad-creative-brief
description: >
  Create creative briefs for social media ads — visual concepts, copy direction, and format specs.
  Use this skill when the user says "social ad brief", "ad creative brief", "social ad concept",
  "creative direction for social ads", "ad visual ideas", "social ad storyboard", "Instagram ad
  creative", "TikTok ad concept", "Facebook ad creative brief", "ad creative strategy",
  or "social ad campaign creative". Also trigger for UGC ad briefs, influencer ad concepts,
  or social ad format recommendations.
---

# Social Ad Creative Brief

Creates detailed creative briefs for paid social ads with visual concepts, copy direction, format specifications, and A/B test plans. Covers Meta, TikTok, LinkedIn, Pinterest, and YouTube ad formats.

## Granularity Check

> **Time**: ~5 min data prep → ~10 min Claude session → ~20-40 min scheduling in Buffer / Hootsuite / native platform. If implementing output in a platform, add 20-30 min for design handoff. Input is product info and campaign objective. Output is Markdown creative brief with 3+ concept directions.

## User Intent Mapping

- "Create an ad creative brief for Facebook ads" (platform-specific)
- "I need TikTok ad concepts for our app" (platform-specific)
- "What should our Instagram ad look like?" (visual direction)
- "Ad creative ideas for a product launch" (campaign)
- "Brief our designer on social ad creatives" (handoff)
- "UGC-style ad concepts for Meta" (format-specific)
- "Video ad script for TikTok" (video ads)
- "A/B test plan for ad creatives" (testing)
- "Static vs. video — what ad format works better?" (format decision)
- "Creative refresh — our ad fatigue is high" (optimization)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Product/Service | Text | What you're advertising and key value proposition |
| Campaign Objective | Text | awareness, traffic, conversions, app installs, leads |
| Platform(s) | Text | Meta, TikTok, LinkedIn, Pinterest, YouTube, or all |

### If You Don't Have This Data

- **No creative assets?** This skill generates the concept brief — your designer executes it. Or use Canva templates.
- **No brand guidelines?** Share your website URL and 3 adjectives describing your brand aesthetic.
- **No past ad data?** Claude uses platform benchmarks. After running, compare results.
- **No budget info?** The brief works regardless of budget — focus on the creative.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Target Audience | Text | Demographics, interests, pain points |
| Budget | Text | Daily or campaign budget (affects format recommendations) |
| Brand Guidelines | Text | Colors, fonts, tone, logo rules |
| Past Top Performers | Text | Describe or link previous successful ads |
| Competitor Ads | Text | Examples of competitor creative |

## Process

### Step 1: Format Selection
Match ad format to objective and platform:

| Objective | Best Formats | Platform Notes |
|---|---|---|
| Awareness | Video (6-15s), Carousel | TikTok: 9:16 video. Meta: Reels + Feed |
| Traffic | Single image, Carousel | LinkedIn: Single image. Meta: Link ads |
| Conversions | UGC-style video, Before/After | Meta: Dynamic. TikTok: Spark Ads |
| App Installs | Demo video, Screenshots | TikTok: Playable. Meta: App Install format |
| Leads | Lead form + Video | LinkedIn: Lead Gen Forms. Meta: Instant Forms |

### Step 2: Concept Development (3 Directions)
For each concept, define:
- **Visual direction**: What the viewer sees (composition, style, mood)
- **Copy direction**: Headline, body, CTA text
- **Hook** (first 3 seconds for video): What stops the scroll
- **Format specs**: Dimensions, duration, file type
- **Talent/asset needs**: UGC creators, product shots, graphics

### Step 3: Platform Specs
| Platform | Dimensions | Duration | File |
|---|---|---|---|
| Meta Feed | 1080×1080 or 1080×1350 | 15-30s (video) | MP4, JPG, PNG |
| Meta Reels | 1080×1920 | 15-60s | MP4 |
| TikTok | 1080×1920 | 9-30s | MP4 |
| LinkedIn | 1200×627 | 15-30s (video) | MP4, JPG, PNG |
| Pinterest | 1000×1500 | 6-15s (video) | MP4, JPG, PNG |

### Step 4: A/B Test Plan
- Test 1: Creative concept A vs. B (visual style)
- Test 2: Hook variant 1 vs. 2 (first 3 seconds)
- Test 3: CTA text variant (action-focused vs. benefit-focused)
- Minimum budget per variant: $50-100/day for 5-7 days

### Confidence & Sample Size
> **Confidence Note**: Creative performance is highly variable. Test minimum 3 concepts per campaign. A winning ad typically emerges after $200-$500 in test spend. Refresh creatives every 2-4 weeks to combat ad fatigue.

### ⚠️ Human Checkpoint
> Review concepts for brand safety, legal compliance (disclaimers, disclosures), and platform-specific ad policies before production.

> **Benchmark Context**: UGC-style ads outperform polished branded content by 2-4x on Meta and TikTok (Buffer 2024 State of Social). Video ads convert 20-30% better than static on Meta. Average ad creative fatigue sets in after 2-4 weeks. Top-performing ads use a strong hook in the first 1-3 seconds. (Buffer 2024 State of Social).
## Output Contract

### Deliverable: Markdown Creative Brief

```markdown
# Social Ad Creative Brief: [Campaign Name]

## Campaign Overview
- Product: [product]
- Objective: [objective]
- Platforms: [platforms]
- Budget: [budget]

## Concept 1: [Name]
- **Visual**: [description]
- **Hook** (first 3s): [description]
- **Copy**: Headline: [text] | Body: [text] | CTA: [text]
- **Format**: [specs]
- **Assets needed**: [list]

## Concept 2: [Name]
...

## A/B Test Plan
| Test | Variable | Variant A | Variant B |
|---|---|---|---|

## Production Checklist
- [ ] Assets created per specs
- [ ] Copy reviewed for compliance
- [ ] Tracking pixels/UTMs configured
- [ ] Audience targeting set
```

## Platform Implementation Steps

### Meta Ads Manager
1. Create campaign with objective matching the brief
2. Upload creatives at the Ad level
3. Set up A/B test using Meta's Experiments feature
4. Enable Dynamic Creative for automated variant testing

### TikTok Ads Manager
1. Create campaign → Ad Group → select Spark Ads or standard
2. Upload 9:16 video assets
3. Use TikTok Creative Center for inspiration on trending formats
4. Enable Smart Creative for automated optimization

### Canva (Design Execution)
1. Use the specs from the brief to set canvas dimensions
2. Follow the visual direction for each concept
3. Export in correct format and resolution
4. Create 2-3 variants per concept for testing

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Ad rejected by platform | Policy violation (claims, imagery) | Review platform ad policies; remove prohibited elements |
| Low CTR | Weak hook or irrelevant creative | Test new hooks; check audience targeting alignment |
| High CPC | Creative fatigue or broad targeting | Refresh creatives; narrow audience segments |
| Good clicks, no conversions | Ad-to-landing page mismatch | Align landing page messaging with ad copy |

## How to Get Your Data

- **No data needed**: Describe product, audience, and objective — Claude generates the brief
- **Meta Ad Library**: facebook.com/ads/library — search competitor ads for inspiration
- **TikTok Creative Center**: ads.tiktok.com/business/creativecenter — trending ad formats

## Example

**Input**: "Ad creative brief for a $49/mo meal planning app. Objective: app installs. Platforms: TikTok + Meta Reels. Target: busy parents 28-40."

**Output**: 3 concepts. Concept 1 ("Fridge Panic"): UGC-style video opening with someone staring at empty fridge, then showing app solving it in 30 seconds. Hook: "It's 5:30 PM and you have NO idea what's for dinner." Concept 2 ("Sunday Prep"): Before/after split screen — chaos vs. organized meal prep powered by app. Concept 3 ("Kid-Approved"): Testimonial-style with real parent showing kid eating a meal planned by app. A/B test: Concept 1 hook vs. Concept 2 hook, same CTA ("Try free for 7 days").

## Related Skills

- **[Social Content Calendar](./social-content-calendar.md)** — Use to plan organic content that complements your paid social ad creative.
- **[Influencer Outreach Brief](./influencer-outreach-brief.md)** — Use to align paid creative briefs with influencer collaboration requirements.
- **[Meta Ads Campaign Builder](../ads/meta-ads-campaign-builder.md)** — Use to execute the creative briefs with actual ad setup on Meta platforms.
- **[Campaign Brief Synthesizer](../content/campaign-brief-synthesizer.md)** — Use to align social ad creative with broader campaign messaging.
