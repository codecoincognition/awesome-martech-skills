---
name: short-form-video-planner
description: >
  Plan and script short-form video content for TikTok, Instagram Reels, and YouTube Shorts.
  Use this skill when the user says "plan my Reels", "TikTok content plan", "YouTube Shorts ideas",
  "short-form video strategy", "create Reels scripts", "plan vertical video content", "social
  video content calendar", "short video hooks", "TikTok batch filming plan", "help me plan
  30 days of Reels", "short-form content ideas", or "script a trending video format".
---

# Short-Form Video Planner

Plan, script, and batch-organize short-form video content (15-90 seconds) for TikTok, Instagram Reels, and YouTube Shorts. Generates content calendars, scripts with hooks, trending format adaptations, and batch filming schedules.

## Granularity Check

> Can this be completed in a single Claude session? **Yes — expect ~5 min data prep → ~10 min Claude session → ~30-60 min producing / uploading.** If implementing output in a platform, add 10-20 min for setup. Input is niche + goals. Output is a Markdown content plan with scripts.

## User Intent Mapping

- "Plan 30 days of TikTok content for my [business]" (content calendar)
- "Script 10 Reels about [topic]" (batch scripting)
- "What trending formats can I use for [niche]?" (trend adaptation)
- "Create a batch filming plan for Reels" (production planning)
- "Help me plan educational short-form content" (edutainment)
- "Write hooks for my YouTube Shorts" (hook optimization)
- "Plan a Reels series about [topic]" (series content)
- "Adapt this blog post into 5 Reels" (repurposing)
- "Create short-form scripts for product launches" (promotional)
- "Help me batch-create content for all short-form platforms" (cross-platform)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Niche/Business | Text | What the account is about |
| Content Goal | Text | Grow followers / Drive sales / Educate / Entertain / Build brand |

### If You Don't Have This Data

- **No transcript?** Use Descript (free tier), Otter.ai, or YouTube's auto-captions to generate one from your recording.
- **No channel analytics?** Check YouTube Studio → Analytics for basic metrics, or describe your content goals instead.
- **No brand style?** Provide 2-3 channels you want to emulate. Claude can infer style from references.
- **No keyword data?** Type your video topic into YouTube search and note the autocomplete suggestions. That's your keyword list.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Number of Videos | Number | How many to plan (default: 15) |
| Platform Priority | Text | TikTok / Reels / Shorts / All (default: All) |
| Content Pillars | Text | 3-5 topic categories to rotate |
| Past Top Performers | Text | What content has worked before |
| Products/Services | Text | What to promote |
| Posting Frequency | Text | Daily / 3x week / 5x week |
| Brand Voice | Text | Casual / Professional / Funny / Edgy |

## Process

### Step 1: Content Pillar Framework
If not provided, define 4-5 content pillars:
- **Educational**: Teach something valuable (tips, how-tos, myths busted)
- **Entertaining**: Humor, trends, relatable moments
- **Inspirational**: Results, transformations, motivation
- **Promotional**: Products, offers, social proof
- **Behind-the-scenes**: Process, team, authenticity

Recommended mix: 40% educational, 20% entertaining, 15% inspirational, 15% promotional, 10% BTS.

### Step 2: Format Library
Assign each video a proven format:

| Format | Hook Style | Best For | Duration |
|---|---|---|---|
| Listicle | "3 things you didn't know about..." | Educational | 30-60s |
| POV | "POV: you just [scenario]" | Relatable | 15-30s |
| Story time | "Story time: how I..." | Engagement | 45-90s |
| Tutorial | "Here's how to [result]" | Educational | 30-60s |
| Myth bust | "Stop doing [common mistake]" | Authority | 15-30s |
| Before/After | Visual transformation | Social proof | 15-30s |
| Day in the life | "A day as a [role]" | BTS/Brand | 30-60s |
| Trending audio | Lip-sync or adapted trend | Entertainment | 15-30s |
| Hot take | "Unpopular opinion: ..." | Engagement | 15-30s |
| Duet/Stitch | Response to another creator | Community | 15-45s |

### Step 3: Script Each Video
For each video provide:
- **Hook** (first 1-3 seconds): The most critical element
- **Body**: Key content beats (not full script for spontaneous content)
- **CTA**: What to do next (follow, comment, save, link in bio)
- **On-screen text**: Key text overlays
- **Audio**: Original audio / trending sound / voiceover
- **Visual notes**: Camera angles, transitions, props

### Step 4: Batch Filming Organization
Group videos by:
- Same outfit/location (film together)
- Same setup requirements
- Priority order (evergreen first, timely later)

### Step 5: Posting Schedule
Map videos to calendar with:
- Best posting times per platform
- Pillar rotation for variety
- Trend-responsive slots (leave 2-3 flex spots per week)


### Confidence & Sample Size
> **Confidence Note**: Results are only as reliable as your input data. Small datasets (<50 records or <30 days of data) produce directional insights, not statistically significant conclusions. Always note your sample size when sharing results with stakeholders. Recommendations should be validated with A/B testing or additional data before making major strategic changes.

### ⚠️ Human Checkpoint
> Trending sounds and formats change weekly. Verify current trends on each platform before filming. Claude suggests evergreen formats and proven structures but cannot see real-time trending audio.


> **Benchmark Context**: See YouTube Creator Academy 2024, Edison Research 2024 Podcast Consumer Report, and Wistia 2024 State of Video for current industry benchmarks relevant to this analysis.
## Output Contract

### Deliverable: Markdown Short-Form Content Plan

```markdown
# Short-Form Video Plan: [Business/Niche]

## Strategy Overview
- **Platforms**: [platforms]
- **Posting frequency**: [schedule]
- **Content pillars**: [pillar 1] (40%), [pillar 2] (20%), ...
- **Total videos planned**: [n]

## Content Calendar

### Week 1
| Day | Pillar | Format | Hook | CTA | Platform |
|---|---|---|---|---|---|
| Mon | Educational | Listicle | "3 [topic] mistakes..." | Save this | All |

## Video Scripts

### Video 1: [Title]
- **Pillar**: [category]
- **Format**: [type]
- **Duration**: [seconds]
- **Hook (0-3s)**: [exact opening words/visual]
- **Body**:
  - Beat 1: [content point]
  - Beat 2: [content point]
  - Beat 3: [content point]
- **CTA**: [action]
- **On-screen text**: [text overlays]
- **Audio**: [original / trending sound name]
- **Visual notes**: [camera, props, transitions]
- **Caption**: [platform caption with hashtags]

[... repeat for each video ...]

## Batch Filming Guide
### Session 1: [outfit/location description]
Films: Video 1, 4, 7, 12 (same setup)
Props needed: [list]
Estimated time: [minutes]

## Hashtag Sets
- **Educational**: #[tag1] #[tag2] ...
- **Promotional**: #[tag1] #[tag2] ...
```

## Platform Implementation Steps

### YouTube Studio
1. Navigate to YouTube Studio → Content → Upload/Edit
2. Paste optimized title, description, and tags
3. Add chapter timestamps in the description (00:00 format)
4. Upload custom thumbnail based on the concept brief
5. Set cards and end screens for engagement

### Podcast Hosting (Buzzsprout/Transistor/Anchor)
1. Upload your episode audio file
2. Paste the show notes into the description field
3. Add chapter markers if your host supports them
4. Set the SEO title and tags
5. Publish and distribute to directories

### Descript / CapCut (Editing)
1. Import your raw footage/audio
2. Use the script as a reference for editing cuts
3. Add on-screen text overlays per the script cues
4. Export in platform-appropriate dimensions (16:9, 9:16, 1:1)

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Content too generic | No niche specificity | Ask for unique angles, competitor examples, audience pain points |
| All same format | No variety in structure | Enforce format rotation, max 2 of same format per week |
| Hooks too weak | Generic openings | Rewrite with specific numbers, contrarian angles, curiosity gaps |
| Not platform-optimized | Same content for all platforms | Adapt duration, caption style, and hashtags per platform |

## How to Get Your Data

- **Instagram Insights**: Export top-performing Reels data
- **TikTok Analytics**: Download video performance metrics
- **YouTube Studio**: Export Shorts analytics
- **Content planning tools**: Export from Later, Planoly, or Hootsuite
- **Manual**: List your content pillars, past hits, and product focus areas

## Example

**Input**: Fitness coaching business, goal is grow followers + drive program signups, posting 5x/week, content pillars: workout tips, nutrition myths, client transformations, humor/relatable, program promos.

**Output**: 20-video plan across 4 weeks. Week 1: 5 videos — "3 exercises you're doing wrong" (listicle, educational, 45s), "POV: your trainer catches you skipping leg day" (POV, humor, 20s), "I lost 30 lbs in 6 months — here's what I ate" (story, inspirational, 60s), "Stop believing this protein myth" (myth bust, educational, 30s), "Inside my 12-week program" (BTS, promo, 30s). Batch filming guide: Session 1 films videos 1, 4, 5 in gym clothes. 5 hashtag sets by pillar. Full scripts with hooks, beats, on-screen text, and CTAs.

## Related Skills

- **[Video Script Writer](./video-script-writer.md)** — Script individual short-form video content pieces from your plan.
- **[Video Repurposing Engine](./video-repurposing-engine.md)** — Repurpose existing long-form content into short-form video clips instead of creating from scratch.
- **[Video Thumbnail Concept Generator](./video-thumbnail-concept-generator.md)** — Generate thumbnail concepts for your planned short-form videos.
- **[Social Content Calendar](../social/social-content-calendar.md)** — Integrate short-form video plan into your broader social media content calendar.
