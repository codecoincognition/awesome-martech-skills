---
name: podcast-show-notes-generator
description: >
  Generate structured podcast show notes with timestamps, key takeaways, links, and SEO-optimized
  descriptions. Use this skill when the user says "create show notes", "podcast show notes",
  "write show notes for my episode", "podcast episode summary", "generate podcast description",
  "podcast timestamps", "episode notes with links", "show notes from transcript", "podcast SEO
  description", "Apple Podcasts description", "Spotify episode notes", or "summarize this podcast
  episode for the description".
---

# Podcast Show Notes Generator

Generate comprehensive podcast show notes from transcripts or episode outlines. Includes SEO-optimized descriptions, chapter timestamps, key takeaways, guest bios, resource links, and platform-specific formatting for Apple Podcasts, Spotify, and web publishing.

## Granularity Check

> Can this be completed in a single Claude session? **Yes — expect ~5 min data prep → ~10 min Claude session → ~30-60 min producing / uploading.** If implementing output in a platform, add 10-20 min for setup. Input is transcript or outline. Output is a Markdown show notes document. No audio tools needed.

## User Intent Mapping

- "Write show notes for this episode transcript" (from transcript)
- "Create a podcast description for Apple/Spotify" (platform-specific)
- "Generate timestamps for my podcast episode" (chapter markers)
- "Summarize the key takeaways from this episode" (highlights)
- "Write a guest bio for my podcast page" (guest content)
- "Create a blog post from this podcast episode" (repurpose)
- "Help me write SEO-friendly podcast descriptions" (discoverability)
- "Generate social media clips list from this episode" (clip identification)
- "Create a resource list for this episode" (links and references)
- "Write show notes in my podcast's style" (brand-consistent)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Episode Content | Text | Full transcript, detailed outline, or recording notes |
| Episode Title | Text | Working or final episode title |

### If You Don't Have This Data

- **No transcript?** Use Descript (free tier), Otter.ai, or YouTube's auto-captions to generate one from your recording.
- **No channel analytics?** Check YouTube Studio → Analytics for basic metrics, or describe your content goals instead.
- **No brand style?** Provide 2-3 channels you want to emulate. Claude can infer style from references.
- **No keyword data?** Type your video topic into YouTube search and note the autocomplete suggestions. That's your keyword list.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Guest Info | Text | Guest name, title, company, bio, links |
| Episode Number | Text | Season/episode numbering |
| Podcast Name | Text | Show name for branding |
| Target Keywords | Text | SEO keywords to weave in |
| Show Notes Style | Text | Brief / Detailed / Blog-style |
| Timestamps | Text | If known, rough timestamps for key moments |
| Resources Mentioned | Text | Links, books, tools mentioned in episode |

## Process

### Step 1: Content Analysis
Parse transcript or outline to identify:
- Main topic and sub-topics discussed
- Key arguments, insights, and quotable moments
- Guest expertise areas and stories shared
- Resources, tools, books, and people mentioned
- Natural chapter break points
- Potential social media clip moments (high-energy, controversial, or quotable)

### Step 2: Description Tiers
Generate 3 description lengths:

**Short (150 chars)**: One-line for Spotify/Apple preview
**Medium (500 chars)**: Platform description field
**Long (1000-2000 chars)**: Website/blog show notes

Each tier front-loads the most compelling hook and includes target keywords naturally.

### Step 3: Chapter Timestamps
Create chapter markers with:
- `[HH:MM:SS]` format for podcast players
- Descriptive, keyword-rich chapter titles
- Minimum 3 chapters for episodes > 20 min
- Include "Intro" and a specific topic for each chapter (not generic "Discussion")

### Step 4: Key Takeaways
Extract 5-7 actionable takeaways:
- Written as standalone insights (make sense without listening)
- Each tied to a specific timestamp
- Formatted for social media sharing

### Step 5: Resource Compilation
Compile all mentioned resources:
- Books (with Amazon/Bookshop links format)
- Tools and software
- People and their profiles
- Articles and reports
- Guest's website, social, and content

### Step 6: Social & Clip Identification
Identify 3-5 moments that make good social clips:
- Timestamp range
- Clip topic/hook
- Suggested caption
- Best platform for each clip


### Confidence & Sample Size
> **Confidence Note**: Results are only as reliable as your input data. Small datasets (<50 records or <30 days of data) produce directional insights, not statistically significant conclusions. Always note your sample size when sharing results with stakeholders. Recommendations should be validated with A/B testing or additional data before making major strategic changes.

### ⚠️ Human Checkpoint
> Verify all timestamps against the actual recording. Claude estimates based on transcript position but actual timing varies with pacing, pauses, and edits.


> **Benchmark Context**: See YouTube Creator Academy 2024, Edison Research 2024 Podcast Consumer Report, and Wistia 2024 State of Video for current industry benchmarks relevant to this analysis.
## Output Contract

### Deliverable: Markdown Show Notes

```markdown
# [Podcast Name] — Episode [#]: [Title]

## Episode Description

### Short (Spotify/Apple preview)
[150 chars max]

### Medium (Platform description)
[500 chars]

### Full Show Notes
[1000-2000 chars with keywords naturally woven in]

## Guest
**[Name]** — [Title] at [Company]
[2-3 sentence bio]
- Website: [url]
- LinkedIn: [url]
- Twitter/X: [handle]

## Chapters
- [00:00:00] Introduction and guest welcome
- [00:02:30] [Topic 1 title]
- [00:12:00] [Topic 2 title]
- [00:25:00] [Topic 3 title]
- [00:38:00] Key advice and rapid fire
- [00:42:00] Where to find [guest] + outro

## Key Takeaways
1. **[Takeaway title]** — [1-2 sentence explanation] [timestamp]
2. ...

## Resources Mentioned
- 📚 [Book title] by [Author]
- 🔧 [Tool name] — [one-line description] — [url]
- 📄 [Article title] — [url]
- 🎙️ [Related episode] — [url]

## Quotable Moments
> "[Direct quote from guest]" — [Guest Name], [timestamp]

## Social Media Clips
| Clip | Timestamp | Hook | Best Platform |
|---|---|---|---|
| [topic] | [start-end] | [caption] | [platform] |

## SEO Tags
[tag1], [tag2], [tag3], ...
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
| Timestamps way off | Transcript doesn't include timing | Note timestamps are estimates, provide chapter topics only |
| Missing context | Outline too sparse | Ask for more detail on key topics discussed |
| Guest info incomplete | No bio provided | Generate placeholder, flag for user to fill in |
| Too many takeaways | Dense episode | Limit to top 7, group related points |

## How to Get Your Data

- **Descript**: Export transcript with timestamps
- **Otter.ai**: Export meeting/recording transcript
- **Riverside/Zencastr**: Download episode transcript
- **Buzzsprout/Transistor**: Copy existing episode notes as starting point
- **Manual**: Paste recording outline or topic list with rough timestamps

## Example

**Input**: Transcript of 45-minute episode "#47: Content Marketing in 2025" with guest Sarah Chen (VP Marketing at TechCo). Topics covered: AI content tools, content distribution strategy, measuring content ROI, and the future of long-form.

**Output**: Short description (148 chars), medium description (480 chars), full show notes (1,400 chars with "content marketing", "content strategy", "AI content" keywords), 6 chapter timestamps, 5 key takeaways with timestamps, 8 resources mentioned, 3 quotable moments, 4 social clip recommendations with captions.

## Related Skills

- **[Video Repurposing Engine](./video-repurposing-engine.md)** — Repurpose podcast show notes into blog posts and social media content.
- **[Content Repurposer](../content/content-repurposer.md)** — Extend podcast repurposing beyond show notes to full content atomization.
- **[SEO Content Strategy](../seo/seo-content-strategy.md)** — Optimize podcast show notes for SEO to drive search traffic.
- **[Podcast Guest Research Brief](./podcast-guest-research-brief.md)** — Use guest research when creating show notes to add context and authenticity.
