---
name: video-thumbnail-concept-generator
description: >
  Generate video thumbnail concepts with layout, text, colors, and expression direction. Use this
  skill when the user says "thumbnail ideas", "design a YouTube thumbnail", "thumbnail concept",
  "what should my thumbnail look like", "YouTube thumbnail strategy", "thumbnail A/B test ideas",
  "create thumbnail briefs", "thumbnail text and layout", "improve my thumbnail CTR",
  "video cover image ideas", or "thumbnail design brief for my designer".
---

# Video Thumbnail Concept Generator

Generate detailed thumbnail concepts for YouTube, course platforms, and video content. Includes layout descriptions, text overlays, color palettes, facial expression direction, and A/B test variants. Outputs a design brief — not the image itself.

## Granularity Check

> Can this be completed in a single Claude session? **Yes — expect ~5 min data prep → ~10 min Claude session → ~30-60 min producing / uploading.** If implementing output in a platform, add 10-20 min for setup. Input is video topic and style preferences. Output is a Markdown design brief. No design tools needed.

## User Intent Mapping

- "Create 5 thumbnail concepts for my video about [topic]" (batch concepts)
- "What should my YouTube thumbnail look like?" (strategy)
- "Design brief for a thumbnail showing [scene]" (specific brief)
- "Help me improve my thumbnail click-through rate" (optimization)
- "A/B test ideas for my video thumbnails" (testing)
- "Create thumbnail concepts for my course" (education platform)
- "What text should go on my thumbnail?" (copy optimization)
- "Thumbnail style guide for my channel" (brand consistency)
- "Analyze what makes top thumbnails in [niche] work" (competitive)
- "Batch thumbnail briefs for my next 10 videos" (production)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Video Title/Topic | Text | What the video is about |
| Content Category | Text | Tutorial / Vlog / Review / News / Entertainment / Business |

### If You Don't Have This Data

- **No transcript?** Use Descript (free tier), Otter.ai, or YouTube's auto-captions to generate one from your recording.
- **No channel analytics?** Check YouTube Studio → Analytics for basic metrics, or describe your content goals instead.
- **No brand style?** Provide 2-3 channels you want to emulate. Claude can infer style from references.
- **No keyword data?** Type your video topic into YouTube search and note the autocomplete suggestions. That's your keyword list.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Channel Style | Text | Current visual brand (colors, fonts, patterns) |
| Face on Thumbnail | Text | Yes (presenter) / No (graphic only) / Optional |
| Competitor Thumbnails | Text | Description of what top creators in niche use |
| Thumbnail Dimensions | Text | Default: 1280x720 (16:9 YouTube standard) |
| Number of Concepts | Number | Default: 3 |
| A/B Testing | Boolean | Generate variant pairs for testing |

## Process

### Step 1: Thumbnail Psychology Analysis
Apply proven CTR principles:
- **Curiosity gap**: Show partial information that demands a click
- **Emotion**: Strong facial expressions increase CTR 30%+
- **Contrast**: Bold colors that pop against YouTube's white/dark UI
- **Simplicity**: 3 elements max (face, text, one visual element)
- **Text**: 3-5 words maximum, large enough to read on mobile

### Step 2: Concept Generation
For each concept provide:
- **Layout sketch** (described in text): Left/right/center composition
- **Text overlay**: Exact words, font style suggestion, color
- **Background**: Color, gradient, image description
- **Facial expression** (if applicable): Specific emotion and direction
- **Visual elements**: Icons, arrows, props, screenshots
- **Color palette**: 2-3 dominant colors with hex codes

### Step 3: Niche-Specific Patterns
Apply category-specific thumbnail conventions:

| Category | What Works | What to Avoid |
|---|---|---|
| Tutorial | Before/after, step numbers, tool logos | Cluttered screenshots |
| Business | Clean backgrounds, authority poses, results numbers | Stock photo vibes |
| Entertainment | Extreme expressions, bright colors, action shots | Too much text |
| Review | Product hero shot, rating visual, comparison | Generic product images |
| News/Commentary | Reaction face, topic image, bold text | Boring screenshots |

### Step 4: A/B Variant Design
If testing requested, create variant pairs that change only ONE element:
- Variant A vs B: Different text
- Variant A vs C: Different expression/emotion
- Variant A vs D: Different color scheme
- Variant A vs E: With vs without face


### Confidence & Sample Size
> **Confidence Note**: Results are only as reliable as your input data. Small datasets (<50 records or <30 days of data) produce directional insights, not statistically significant conclusions. Always note your sample size when sharing results with stakeholders. Recommendations should be validated with A/B testing or additional data before making major strategic changes.

### ⚠️ Human Checkpoint
> These are design briefs, not finished thumbnails. Hand to a designer or use Canva/Photoshop. Test multiple variants — even small changes in text or expression can swing CTR 20%+.


> **Benchmark Context**: Average YouTube CTR is 2-10% (4-5% is good for most niches) (YouTube Creator Academy 2024) Videos over 10 minutes can include mid-roll ads. . Podcast episode completion rate averages 60-80% (Edison Research 2024 Podcast Consumer Report) YouTube Shorts average 2-5% CTR (YouTube Creator Academy 2024) Chapters increase average view duration by 5-10% (Wistia 2024 State of Video) (Edison Research 2024 Podcast Consumer Report).
## Output Contract

### Deliverable: Markdown Thumbnail Brief

```markdown
# Thumbnail Concepts: [Video Title]

## Concept 1: [Concept Name]
- **Layout**: [description — e.g., "Face left 40%, text right 60%"]
- **Text**: "[3-5 words]" — [font style] — [color hex]
- **Background**: [description — color/gradient/image]
- **Face/Expression**: [emotion — e.g., "Shocked, mouth open, eyes wide, looking at text"]
- **Visual Elements**: [icons, arrows, props]
- **Color Palette**: [Primary hex], [Secondary hex], [Accent hex]
- **Mobile Preview Note**: [How it reads at small size]
- **Mood**: [One-word mood: Urgent / Curious / Exciting / Clean]

## Concept 2: [Concept Name]
[...]

## A/B Test Plan
| Test | Variable Changed | Hypothesis |
|---|---|---|
| A vs B | [element] | [expected impact] |

## General Guidelines
- Text size: Readable at 150px wide (mobile search)
- File format: PNG or JPG, under 2MB
- Safe zones: Keep key elements away from timestamp overlay (bottom right)
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
| Too much text | Trying to explain the whole video | Cut to 3-5 impactful words |
| Low contrast | Colors blend together | Use complementary colors, test in grayscale |
| Generic concept | Not niche-specific | Study top performers in specific niche, adapt their patterns |
| Not mobile-optimized | Designed for desktop only | Verify all text readable at thumbnail size (120x68px) |

## How to Get Your Data

- **YouTube Studio**: Check CTR of existing thumbnails in Analytics > Content
- **Competitor analysis**: Screenshot top-ranking video thumbnails in your niche
- **Canva**: Use as design tool for executing the briefs
- **TubeBuddy/vidIQ**: Compare thumbnail CTR data across your videos

## Example

**Input**: Video titled "I Tried the $1 vs $1000 Marketing Tool", business/review category, presenter on thumbnail, channel brand uses blue + yellow.

**Output**: Concept 1 — "Split composition: face center with shocked expression, left side shows basic tool UI (muted/gray), right side shows premium tool UI (glowing/vibrant). Text: '$1 vs $1000' in bold Impact font, yellow on dark blue. Arrow pointing from cheap to expensive." Concept 2 — "Face left (excited, pointing right), right side shows two price tags ($1 crossed out in red, $1000 in gold). Text: 'WORTH IT?' in white with red underline." Plus A/B variant swapping the expression from shocked to skeptical.

## Related Skills

- **[Video Script Writer](./video-script-writer.md)** — Script video content before generating thumbnails to ensure alignment.
- **[Hook Stress Tester](../insights/hook-stress-tester.md)** — Stress-test thumbnail text and messaging using the same evaluation framework.
- **[Short-Form Video Planner](./short-form-video-planner.md)** — Generate thumbnails for all short-form videos in your content plan.
- **[YouTube SEO Optimizer](./youtube-seo-optimizer.md)** — Optimize thumbnails as part of broader YouTube optimization strategy.
