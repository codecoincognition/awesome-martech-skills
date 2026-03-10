---
name: video-script-writer
description: >
  Write structured video scripts with hooks, segments, CTAs, and timing for YouTube, ads, or social.
  Use this skill when the user says "write a video script", "YouTube script", "create a script for
  my video", "video outline with timestamps", "ad script", "explainer video script", "talking head
  script", "video content script", "script for a product demo", "help me script this video idea",
  or "write a script for a 5 minute video".
---

# Video Script Writer

Create structured video scripts with attention hooks, segment breakdowns, B-roll suggestions, on-screen text cues, and CTAs. Supports YouTube long-form, short-form (Reels/Shorts/TikTok), product demos, and ad scripts.

## Granularity Check

> Can this be completed in a single Claude session? **Yes — expect ~5 min data prep → ~10 min Claude session → ~30-60 min producing / uploading.** If implementing output in a platform, add 10-20 min for setup. Input is topic + format details. Output is a Markdown script document. No video tools needed.

## User Intent Mapping

- "Write a YouTube script about [topic]" (long-form)
- "Create a 60-second ad script for [product]" (short-form ad)
- "Script a product demo video" (product marketing)
- "I need a talking head script with B-roll notes" (production-ready)
- "Help me outline a 10-minute explainer video" (educational)
- "Write a script for a TikTok/Reel about [topic]" (short-form social)
- "Create a webinar opening script" (event content)
- "Script a customer testimonial video" (social proof)
- "Write an internal training video script" (corporate)
- "Help me script a video series on [topic]" (series planning)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Topic/Subject | Text | What the video is about |
| Video Format | Text | YouTube long-form / Short-form (Reel/Short/TikTok) / Ad / Demo / Explainer / Testimonial |

### If You Don't Have This Data

- **No transcript?** Use Descript (free tier), Otter.ai, or YouTube's auto-captions to generate one from your recording.
- **No channel analytics?** Check YouTube Studio → Analytics for basic metrics, or describe your content goals instead.
- **No brand style?** Provide 2-3 channels you want to emulate. Claude can infer style from references.
- **No keyword data?** Type your video topic into YouTube search and note the autocomplete suggestions. That's your keyword list.

### Optional Inputs

| Input | Format | Default | Description |
|---|---|---|---|
| Target Length | Text | 8-10 min | Desired duration or word count |
| Target Audience | Text | General | Who's watching |
| Key Messages | Text | Derived from topic | 3-5 points to cover |
| Brand Voice | Text | Professional | Tone and style |
| CTA | Text | Subscribe + link | What viewers should do after watching |
| Platform | Text | YouTube | YouTube / Instagram / TikTok / LinkedIn / Internal |
| Speaker | Text | Single presenter | Solo / Interview / Multi-host |

## Process

### Step 1: Format Calibration
Set parameters based on video format:

| Format | Typical Length | Hook Window | Structure |
|---|---|---|---|
| YouTube long-form | 8-15 min | 5-8 seconds | Hook → Intro → Segments → CTA → Outro |
| Short-form | 15-60 sec | 1-3 seconds | Hook → Value → CTA |
| Ad | 15-30 sec | 2-3 seconds | Problem → Solution → Proof → CTA |
| Demo | 3-7 min | 5 seconds | Pain → Feature → Benefit → Next steps |
| Explainer | 5-10 min | 5-8 seconds | Why → What → How → Summary |

### Step 2: Hook Construction
Write 3 hook options using proven patterns:
- **Question hook**: Open with a question that triggers curiosity
- **Stat hook**: Lead with a surprising data point
- **Story hook**: Start mid-action with a relatable scenario
- **Contrarian hook**: Challenge a common assumption
- **Result hook**: Show the end result first, then explain how

### Step 3: Script Body
For each segment, provide:
- **On-camera dialogue**: Exact words for the speaker (conversational, not essay-style)
- **Timing**: Approximate timestamp for each segment
- **B-roll cues**: `[B-ROLL: description of visual]`
- **On-screen text**: `[TEXT ON SCREEN: key phrase]`
- **Transition notes**: How to move between segments
- **Engagement hooks**: Pattern interrupts every 2-3 minutes (for long-form)

### Step 4: CTA & Retention Elements
- Mid-roll CTA (for long-form): Natural ask at the value peak
- End CTA: Clear next action
- Retention hooks: "Stay until the end for..." / "Coming up next..."
- Pattern interrupts: Visual/tonal changes to maintain attention


### Confidence & Sample Size
> **Confidence Note**: Results are only as reliable as your input data. Small datasets (<50 records or <30 days of data) produce directional insights, not statistically significant conclusions. Always note your sample size when sharing results with stakeholders. Recommendations should be validated with A/B testing or additional data before making major strategic changes.

### ⚠️ Human Checkpoint
> Review the script for brand accuracy, legal claims, and on-camera comfort. Scripts should sound natural when read aloud — test by reading them.


> **Benchmark Context**: Average YouTube CTR is 2-10% (4-5% is good for most niches) (YouTube Creator Academy 2024) Videos over 10 minutes can include mid-roll ads. . Podcast episode completion rate averages 60-80% (Edison Research 2024 Podcast Consumer Report) YouTube Shorts average 2-5% CTR (YouTube Creator Academy 2024) Chapters increase average view duration by 5-10% (Wistia 2024 State of Video) (Edison Research 2024 Podcast Consumer Report).
## Output Contract

### Deliverable: Markdown Video Script

```markdown
# Video Script: [Title]

## Metadata
- **Format**: [type]
- **Target Length**: [duration] (~[word count] words)
- **Platform**: [platform]
- **Audience**: [who]

## Hook Options (pick one)
1. [Question hook]
2. [Stat hook]
3. [Story hook]

## Full Script

### [00:00-00:08] HOOK
[Speaker dialogue]
[B-ROLL: description]
[TEXT ON SCREEN: key phrase]

### [00:08-00:30] INTRO
[Speaker dialogue with context setting]

### [00:30-03:00] SEGMENT 1: [Title]
[Speaker dialogue]
[B-ROLL: description]
[TEXT ON SCREEN: key stat or phrase]

### [03:00-03:15] TRANSITION + ENGAGEMENT
[Pattern interrupt / engagement ask]

[... additional segments ...]

### [TIMESTAMP] CTA
[Speaker dialogue with clear ask]
[TEXT ON SCREEN: URL or action]

### [TIMESTAMP] OUTRO
[Closing remarks]

## Production Notes
- **Thumbnail concept**: [description]
- **Title options**: [3 title variations]
- **Description/caption**: [platform-optimized text]
- **Tags/hashtags**: [relevant tags]
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
| Script sounds robotic | Written like an essay, not speech | Rewrite in conversational tone, add filler words, contractions |
| Too long for format | Word count exceeds format norms | Trim to ~150 words/minute for natural pacing |
| No clear structure | Topic too broad | Narrow to 3-5 key points maximum |
| Weak hook | Generic opening | Rewrite using specific hook formulas above |

## How to Get Your Data

- **Topic research**: Provide your content brief, blog post, or key talking points
- **Brand guidelines**: Share voice/tone docs for consistency
- **Competitor videos**: Share links to videos you want to match in style
- **Past scripts**: Share previous scripts that worked well

## Example

**Input**: YouTube long-form video about "5 Google Ads mistakes small businesses make", targeting small business owners, 8-10 minutes, conversational tone.

**Output**: Script with stat hook ("87% of small businesses waste their first $500 on Google Ads"), 5 mistake segments with B-roll cues (screen recordings of Google Ads interface), pattern interrupts at minute 3 and 6, mid-roll CTA at minute 5 (subscribe), end CTA (download free Google Ads checklist), plus thumbnail concept, 3 title options, and YouTube description with timestamps.

## Related Skills

- **[Video Thumbnail Concept Generator](./video-thumbnail-concept-generator.md)** — Generate thumbnails after scripting video to align visuals with script messaging.
- **[Hook Stress Tester](../insights/hook-stress-tester.md)** — Evaluate and improve video hook/opening lines before production.
- **[Video Repurposing Engine](./video-repurposing-engine.md)** — Script primary source video, then repurpose into multiple short-form clips.
- **[AI Content Generator](../ai-marketing/ai-content-generator.md)** — Use AI to generate initial script drafts that you refine and customize.
