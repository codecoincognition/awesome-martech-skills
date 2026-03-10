---
name: hashtag-strategy-builder
description: >
  Build data-driven hashtag strategies for any platform — Instagram, TikTok, LinkedIn, Twitter/X.
  Use this skill when the user says "hashtag strategy", "which hashtags should I use",
  "hashtag research", "find hashtags for my niche", "hashtag performance analysis",
  "optimize my hashtags", "best hashtags for [topic]", "hashtag sets", "banned hashtags
  check", "hashtag rotation plan", or "how many hashtags should I use". Also trigger for
  hashtag audits, branded hashtag creation, or hashtag tracking setup.
---

# Hashtag Strategy Builder

Creates platform-specific hashtag strategies with researched sets organized by size, niche relevance, and rotation schedules. Includes branded hashtag recommendations and performance tracking frameworks.

## Granularity Check

> **Time**: ~5 min data prep → ~10 min Claude session → ~60-90 min implementing across platforms. If implementing output in a platform, add 5-10 min for setup. Input is niche/topic description. Output is Markdown with categorized hashtag sets and rotation plan.

## User Intent Mapping

- "What hashtags should I use for [niche]?" (discovery)
- "Build a hashtag strategy for Instagram" (platform-specific)
- "My hashtags aren't driving reach anymore" (optimization)
- "Create hashtag sets I can rotate weekly" (rotation planning)
- "Should I create a branded hashtag?" (branding)
- "How many hashtags should I use on [platform]?" (best practices)
- "Audit my current hashtags" (review)
- "Find trending hashtags in [industry]" (trend discovery)
- "TikTok hashtag strategy" (platform-specific)
- "Hashtag tracking and reporting setup" (measurement)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Niche/Industry | Text | Your business area (e.g., "B2B SaaS", "organic skincare", "fitness coaching") |
| Platform | Text | instagram, tiktok, linkedin, twitter, or all |

### If You Don't Have This Data

- **No niche defined?** Describe what you sell and who buys it. That's your niche.
- **No current hashtags?** That's the point — this skill creates them from scratch.
- **No performance data?** Start using the generated sets and track reach for 2 weeks.
- **No competitor info?** Check 3 competitors' posts — note their top hashtags.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Current Hashtags | Text list | Hashtags you currently use |
| Competitors | Text list | Competitor accounts to analyze |
| Content Pillars | Text list | Your main content themes |
| Brand Name | Text | For branded hashtag creation |
| Audience Location | Text | Geographic targeting for local hashtags |

## Process

### Step 1: Niche Hashtag Research
- Identify 50-100 relevant hashtags across size tiers:
  - **Mega** (1M+ posts): High competition, broad reach, low discovery
  - **Large** (100K-1M posts): Moderate competition, good for established accounts
  - **Medium** (10K-100K posts): Best discovery zone for most accounts
  - **Small/Niche** (1K-10K posts): Low competition, high relevance, best for growth
- Filter out banned, spammy, or irrelevant hashtags

### Step 2: Platform-Specific Strategy
| Platform | Optimal Count | Placement | Notes |
|---|---|---|---|
| Instagram | 20-30 | First comment | Mix all tiers; rotate sets |
| TikTok | 3-5 | In caption | Use trending + niche only |
| LinkedIn | 3-5 | Bottom of post | Professional/industry terms |
| Twitter/X | 1-2 | Inline or end | Only if natural; less is more |

### Step 3: Build Rotation Sets
- Create 4-6 hashtag sets to rotate weekly
- Each set maintains the tier distribution (30% large, 40% medium, 30% niche)
- Rotating prevents algorithm suppression from repetition
- Align sets to content pillars (e.g., Set A for educational, Set B for promotional)

### Step 4: Branded Hashtag Recommendations
- Primary branded hashtag: #[BrandName] (for all posts)
- Campaign hashtags: #[BrandCampaign] (time-limited)
- Community hashtags: #[BrandCommunity] (for UGC)
- Check availability and existing usage before recommending

### Confidence & Sample Size
> **Confidence Note**: Hashtag effectiveness changes frequently with algorithm updates. Audit and refresh your strategy every 60-90 days. What works for one account may not work for another — test and measure.

### ⚠️ Human Checkpoint
> Verify hashtags are not banned, offensive, or associated with content that conflicts with your brand. Search each hashtag manually before using.

> **Benchmark Context**: Instagram posts with 20-30 hashtags get 12 (Later 2024 Social Media Industry Report). 6% more engagement than those with none (Later 2024 Social Media Industry Report) TikTok posts with 3-5 hashtags outperform those with 10+ (Buffer 2024 State of Social) LinkedIn posts with 3 hashtags get the highest reach. . Hashtag-driven discovery accounts for 30-40% of Instagram impressions for accounts under 10K followers (Later 2024 Social Media Industry Report) (Later 2024 Social Media Industry Report).
## Output Contract

### Deliverable: Markdown Hashtag Strategy

```markdown
# Hashtag Strategy: [Niche] — [Platform]

## Core Sets (Rotate Weekly)

### Set A: [Content Pillar 1]
[hashtags organized by tier]

### Set B: [Content Pillar 2]
[hashtags organized by tier]

## Branded Hashtags
- Primary: #[brand]
- Campaign: #[campaign]
- Community: #[community]

## Platform Best Practices
[platform-specific guidance]

## Rotation Schedule
| Week | Set | Content Type |
|---|---|---|

## Tracking Plan
- Check reach from hashtags in Insights weekly
- Replace underperformers monthly
- Full audit every 90 days
```

## Platform Implementation Steps

### Instagram
1. Save hashtag sets in Notes app or scheduling tool
2. Post content, then immediately paste hashtags as first comment
3. Track "Impressions from Hashtags" in Instagram Insights
4. Replace bottom-performing hashtags monthly

### TikTok
1. Include 3-5 hashtags directly in caption
2. Mix 1-2 trending + 2-3 niche hashtags
3. Check Trending tab for timely additions
4. Track views from "For You" page (hashtag discovery signal)

### Scheduling Tools (Buffer/Later/Planoly)
1. Save hashtag sets as templates
2. Auto-apply to posts by content type
3. Rotate sets weekly using the calendar
4. Review analytics monthly

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Shadowban suspected | Using banned hashtags | Audit all hashtags against current banned list |
| No reach increase | Hashtags too competitive (all mega) | Shift to 70% medium/niche hashtags |
| Irrelevant audience | Hashtags too broad | Narrow to niche-specific terms |
| Repetition penalty | Same hashtags every post | Implement rotation schedule — minimum 4 sets |

## How to Get Your Data

- **Instagram Insights**: Post → View Insights → Impressions from Hashtags
- **Competitor research**: View competitor posts → note their hashtags
- **Hashtag tools**: Display Purposes (free), Hashtagify, All Hashtag
- **No tools needed**: Describe your niche — Claude generates hashtags from knowledge

## Example

**Input**: "Organic skincare brand on Instagram. Content pillars: ingredients education, behind-the-scenes, product launches."

**Output**: 4 rotation sets of 25 hashtags each. Set A (Education): #skincarescience #ingredientsmatter #cleanbeautyeducation + 22 more. Set B (BTS): #smallbusinesslife #handmadewithcare #behindthebrand + 22 more. Branded: #[BrandName] (all posts), #[Brand]Glow (UGC campaign). Rotation: Week 1 = Set A, Week 2 = Set B, Week 3 = Set C, Week 4 = Set D. Review after 30 days — replace any hashtag driving <100 impressions.

## Related Skills

- **[Social Content Calendar](./social-content-calendar.md)** — Use to apply your hashtag strategy across all posts in your social calendar.
- **[Instagram Caption Writer](./instagram-caption-writer.md)** — Use to incorporate hashtags into Instagram captions alongside compelling copy.
- **[Social Engagement Analyzer](./social-engagement-analyzer.md)** — Use to measure hashtag performance and refine your strategy over time.
- **[Tiktok Content Strategy](./tiktok-content-strategy.md)** — Use to incorporate platform-specific hashtag approaches for TikTok growth.
