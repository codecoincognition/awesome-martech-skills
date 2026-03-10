---
name: youtube-seo-optimizer
description: >
  Optimize YouTube video metadata for search rankings and click-through rate. Use this skill when
  the user says "optimize my YouTube video", "YouTube SEO", "help with video title and description",
  "YouTube tags", "video metadata optimization", "improve my video rankings", "YouTube search
  optimization", "write a YouTube description", "optimize my video thumbnail title", "YouTube
  keyword research", "help my video rank higher", or "audit my YouTube channel SEO".
---

# YouTube SEO Optimizer

Optimize YouTube video titles, descriptions, tags, chapters, and thumbnails for search visibility and CTR. Analyzes keyword opportunities, generates metadata variants, and scores existing metadata against best practices.

## Granularity Check

> Can this be completed in a single Claude session? **Yes — expect ~5 min data prep → ~10 min Claude session → ~30-60 min producing / uploading.** If implementing output in a platform, add 10-20 min for setup. Input is video topic + optional current metadata. Output is optimized metadata package in Markdown.

## User Intent Mapping

- "Optimize the SEO for my YouTube video about [topic]" (full optimization)
- "Write a YouTube title and description for [topic]" (metadata creation)
- "What tags should I use for a video about [topic]?" (tag research)
- "Audit my existing YouTube video metadata" (optimization audit)
- "Help me rank for [keyword] on YouTube" (keyword targeting)
- "Create chapter timestamps for my video" (chapters)
- "Write a YouTube description with links and timestamps" (full description)
- "Compare my metadata against top-ranking videos" (competitive)
- "Generate 10 title options for my video" (title testing)
- "Optimize my YouTube Shorts metadata" (short-form specific)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Video Topic | Text | What the video covers |
| Target Keywords | Text | 1-3 primary keywords to rank for |

### If You Don't Have This Data

- **No transcript?** Use Descript (free tier), Otter.ai, or YouTube's auto-captions to generate one from your recording.
- **No channel analytics?** Check YouTube Studio → Analytics for basic metrics, or describe your content goals instead.
- **No brand style?** Provide 2-3 channels you want to emulate. Claude can infer style from references.
- **No keyword data?** Type your video topic into YouTube search and note the autocomplete suggestions. That's your keyword list.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Current Title | Text | Existing title to audit/improve |
| Current Description | Text | Existing description to audit |
| Current Tags | Text | Existing tags to audit |
| Video Length | Text | Duration (for chapter planning) |
| Channel Niche | Text | Channel topic area for context |
| Competitor Videos | Text | Titles/URLs of top-ranking videos for target keyword |
| Video Type | Text | Long-form / Shorts / Live / Tutorial / Vlog |

## Process

### Step 1: Keyword Analysis
For each target keyword:
- Primary keyword: exact phrase to target
- Secondary keywords: related phrases and long-tail variations
- Question keywords: "how to", "what is", "why does" variations
- YouTube autocomplete suggestions (user can verify)
- Search intent: Tutorial / Entertainment / Review / Comparison / News

### Step 2: Title Optimization
Generate 10 title options applying these principles:
- **Front-load keyword**: Primary keyword in first 40 characters
- **Under 60 characters**: Full visibility on all devices
- **Power words**: Include curiosity/emotion triggers (Secret, Proven, Actually, Nobody)
- **Numbers**: Specific numbers outperform vague claims
- **Brackets/parentheses**: [Tutorial] or (2025 Updated) boost CTR 33%
- **Avoid clickbait**: Deliver on the promise

Score each title on: Keyword placement (1-5), CTR potential (1-5), Accuracy (1-5).

### Step 3: Description Optimization
Structure the description in 3 zones:

**Zone 1 — Above the fold (first 2-3 lines, ~150 chars)**:
- Hook with primary keyword
- Value proposition
- This appears in search results — make it count

**Zone 2 — Expanded content**:
- Detailed summary (200-300 words) naturally incorporating keywords
- Timestamps/chapters (if video > 5 min)
- Key takeaways or bullet points

**Zone 3 — Links and resources**:
- Relevant links mentioned in video
- Social media links
- Related video links
- Hashtags (3-5 relevant)

### Step 4: Tags & Hashtags
Generate tags in priority order:
1. Exact target keyword
2. Long-tail variations
3. Related topics
4. Channel name / brand
5. Broad category terms

Rules: 500-character limit, mix of broad and specific, include common misspellings if relevant.

### Step 5: Chapter Markers
If video length provided, suggest chapter structure:
- 00:00 — Intro (always include)
- Key segments with descriptive, keyword-rich titles
- Minimum 3 chapters, 10 seconds+ each

### Step 6: Metadata Audit (if existing metadata provided)
Score current metadata on:
- Keyword presence and placement
- Character count efficiency
- CTR trigger elements
- Description completeness
- Tag coverage


### Confidence & Sample Size
> **Confidence Note**: Results are only as reliable as your input data. Small datasets (<50 records or <30 days of data) produce directional insights, not statistically significant conclusions. Always note your sample size when sharing results with stakeholders. Recommendations should be validated with A/B testing or additional data before making major strategic changes.

### ⚠️ Human Checkpoint
> Verify keyword search volume using YouTube search autocomplete or TubeBuddy/vidIQ. Claude generates keyword suggestions based on relevance but cannot verify actual search volume.


> **Benchmark Context**: Average YouTube CTR is 2-10% (4-5% is good for most niches) (YouTube Creator Academy 2024) Videos over 10 minutes can include mid-roll ads. . Podcast episode completion rate averages 60-80% (Edison Research 2024 Podcast Consumer Report) YouTube Shorts average 2-5% CTR (YouTube Creator Academy 2024) Chapters increase average view duration by 5-10% (Wistia 2024 State of Video) (Edison Research 2024 Podcast Consumer Report).
## Output Contract

### Deliverable: Markdown YouTube SEO Package

```markdown
# YouTube SEO Package: [Video Topic]

## Target Keywords
- Primary: [keyword] — estimated intent: [type]
- Secondary: [keyword 1], [keyword 2]
- Long-tail: [phrase 1], [phrase 2], [phrase 3]

## Title Options (Ranked)
| # | Title | Chars | Keyword Position | CTR Score | Notes |
|---|---|---|---|---|---|
| 1 | [title] | [n] | [position] | [1-5] | Recommended |

## Optimized Description
[Full description text with all 3 zones]

## Tags (copy-paste ready)
[tag1], [tag2], [tag3], ...
Character count: [n]/500

## Chapters
00:00 - [Chapter 1]
[timestamp] - [Chapter 2]
...

## Thumbnail Text Suggestions
- [Option 1: 3-4 words max]
- [Option 2]
- [Option 3]

## Audit Results (if applicable)
| Element | Current Score | Optimized Score | Key Change |
|---|---|---|---|
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
| Keywords too competitive | Targeting head terms with billions of results | Suggest long-tail alternatives with lower competition |
| Title too long | Exceeds 60 characters | Trim while preserving keyword and hook |
| Description keyword-stuffed | Over-optimization | Rewrite for natural readability, 2-3% keyword density max |
| Tags irrelevant | Broad category tags dilute focus | Prioritize specific, relevant tags |

## How to Get Your Data

- **YouTube Studio**: Export current video metadata from Content tab
- **YouTube Search**: Type target keyword to see autocomplete suggestions
- **TubeBuddy/vidIQ**: Export keyword scores and competitor tag data
- **Competitor analysis**: Copy titles/descriptions of top 5 ranking videos for target keyword

## Example

**Input**: Video about "email marketing for beginners", targeting small business owners. 12-minute tutorial. Current title: "Email Marketing Tips".

**Output**: Recommended title: "Email Marketing for Beginners: 7 Steps to Your First Campaign (2025 Guide)" (62 chars, keyword front-loaded, number + brackets). Description with keyword-rich above-fold hook, 8 chapter markers, 15 optimized tags within 420/500 chars. Audit of current title: 2/5 (too vague, no keyword specificity, no CTR triggers, missing year).

## Related Skills

- **[Video Script Writer](./video-script-writer.md)** — Script videos with keyword targets in mind before scripting content.
- **[Keyword Cluster Analyzer](../seo/keyword-cluster-analyzer.md)** — Research keyword clusters for your YouTube channel and target videos.
- **[SEO Content Strategy](../seo/seo-content-strategy.md)** — Build overall YouTube SEO strategy that integrates with broader SEO strategy.
- **[Video Thumbnail Concept Generator](./video-thumbnail-concept-generator.md)** — Ensure thumbnail design aligns with SEO keywords and CTR goals.
