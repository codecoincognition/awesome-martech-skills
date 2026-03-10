---
name: video-repurposing-engine
description: >
  Repurpose long-form video and podcast content into multiple short-form assets across platforms.
  Use this skill when the user says "video repurposing", "repurpose podcast content", "create clips
  from long video", "video to social media content", "podcast to blog post", "content atomization",
  "video content multiplier", "turn webinar into content", "repurpose YouTube video", "video clip
  strategy", or "maximize content from one video". Also trigger for content atomization strategy,
  video-to-text conversion, or multi-platform content adaptation.
---

# Video Repurposing Engine

Repurposes long-form video and podcast content into multiple short-form assets optimized for different platforms and audiences.

## Granularity Check

> **Session time**: ~5 min data prep + ~10 min Claude session. If producing assets, add 2-4 hours per source video. Input is video/podcast transcript or description. Output is Markdown repurposing plan with specific clip timestamps, captions, and platform-specific adaptations.

## User Intent Mapping

- "Repurpose this video for social media" (social)
- "Turn our podcast into blog content" (blog)
- "Create clips from our webinar" (clips)
- "How to get more content from one video" (strategy)
- "Content atomization plan" (atomization)
- "Video to LinkedIn posts" (LinkedIn)
- "YouTube to TikTok/Reels clips" (short-form)
- "Maximize ROI from video production" (ROI)
- "Repurpose podcast episodes" (podcast)
- "Turn one piece of content into 10" (multiplier)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Source Content | Text/Transcript | Video or podcast transcript, or description of key moments |
| Target Platforms | Text | Where you want to distribute repurposed content |
| Content Goals | Text | What repurposed content should achieve |

### If You Don't Have This Data

- **No transcript?** Claude recommends transcription tools (Descript, Otter.ai, Riverside, YouTube auto-captions) and works with your description of key moments.
- **Not sure which platforms?** Claude recommends platforms based on your audience and content type.
- **Don't know what clips to pull?** Claude identifies "clip-worthy" moments from transcripts based on shareability, insight density, and emotional hooks.
- **No video editing skills?** Claude recommends tools (Descript, Opus Clip, Kapwing) that auto-generate clips from long-form content.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Timestamps | Text | Key moments with timestamps |
| Platform Analytics | Text | Which platforms drive the most engagement |
| Brand Guidelines | Text | Visual and tone guidelines |
| Past Performance | Text | Which repurposed content performed best |
| Audience Data | Text | Platform-specific audience demographics |

## Process

### Step 1: Content Atomization Map
From one long-form piece, create:
| Asset Type | Count | Platform | Effort |
|---|---|---|---|
| Short clips (30-60s) | 5-10 | TikTok, Reels, Shorts | Low |
| Medium clips (2-5 min) | 3-5 | LinkedIn, Twitter/X | Low-Medium |
| Quote graphics | 5-8 | Instagram, LinkedIn, Twitter | Low |
| Blog post | 1-2 | Website, Medium | Medium |
| Newsletter excerpt | 1 | Email | Low |
| Audiogram | 3-5 | Instagram Stories, Twitter | Low |
| Carousel/slides | 2-3 | Instagram, LinkedIn | Medium |
| Thread | 1-2 | Twitter/X, LinkedIn | Low |

### Step 2: Clip-Worthy Moment Identification
Look for moments that are:
- **Insightful**: A non-obvious take or framework
- **Emotional**: Passionate delivery, vulnerability, humor
- **Tactical**: Specific, actionable advice
- **Contrarian**: Challenges conventional wisdom
- **Story-driven**: A compelling anecdote with a lesson
- **Quotable**: A concise, memorable statement

### Step 3: Platform-Specific Adaptation
| Platform | Format | Length | Style | Caption |
|---|---|---|---|---|
| TikTok | Vertical 9:16 | 30-60s | Fast-paced, hook in 3s | On-screen captions, emoji |
| Instagram Reels | Vertical 9:16 | 30-90s | Visual, trending audio | On-screen + caption |
| YouTube Shorts | Vertical 9:16 | 30-60s | Hook + value + CTA | On-screen captions |
| LinkedIn | Square or horizontal | 1-5 min | Professional, insight-led | Long-form text post + video |
| Twitter/X | Square or horizontal | 30s-2 min | Punchy, conversational | Short text + video |
| Blog | N/A (text) | 800-2000 words | SEO-optimized, structured | N/A |

### Step 4: Caption/Copy Writing
Per clip:
- **Hook** (first line): Stop-scrolling statement or question
- **Context**: Brief setup (1-2 sentences)
- **Value statement**: What the viewer will learn
- **CTA**: What to do next (follow, subscribe, link in bio)
- **Hashtags**: Platform-appropriate (3-5 on Instagram, 1-2 on LinkedIn)

### Step 5: Distribution Timeline
| Day | Action | Platforms |
|---|---|---|
| Day 0 | Publish full episode | YouTube, podcast platforms |
| Day 1 | Best clip + blog post | All social + website |
| Day 2-3 | Second best clip | TikTok, Reels, Shorts |
| Day 4-5 | Quote graphic + thread | Instagram, LinkedIn, Twitter |
| Day 7 | Third clip + newsletter mention | Social + email |
| Day 10-14 | Remaining clips | Stagger across platforms |
| Day 21+ | Evergreen clips (reshare) | Best-performing platforms |

### Step 6: Performance Tracking
| Metric | By Platform | Action |
|---|---|---|
| Views | Per clip per platform | Double down on high-view clips |
| Engagement rate | Likes + comments / views | Refine content style for high-engagement |
| Click-through | Link clicks from repurposed content | Optimize CTAs |
| Full episode traffic | Referrals from clips to full video | Validate repurposing drives consumption |

### Confidence & Sample Size

> **Confidence Note**: Repurposed short-form clips typically get 3-10x the views of the original long-form content. The first 3 seconds determine whether someone watches — invest heavily in the hook. Not every moment is clip-worthy — quality over quantity. A single 60-minute podcast can yield 15-25 repurposed assets across platforms. Clips with on-screen captions get 80% more engagement than those without.

### ⚠️ Human Checkpoint
> Review all clips for context — ensure excerpts don't misrepresent the full conversation. Verify clips don't include guest statements taken out of context. Check that music/audio in clips doesn't violate platform copyright rules.

> **Benchmark Context**: Short-form video is the highest-ROI content format for social media. Repurposed content generates 3x more engagement per dollar than original content. Videos with captions get 80% more views. The average podcast episode can generate 15-25 content pieces. LinkedIn video posts get 5x more engagement than text-only posts.

## Output Contract

### Deliverable: Markdown Repurposing Plan

```markdown
# Content Repurposing Plan: [Episode/Video Title]

## Source Content
- Type: [podcast/webinar/video]
- Length: [duration]
- Key themes: [topics covered]

## Clip Schedule
| Clip # | Timestamp | Topic | Hook | Platform | Length |
|---|---|---|---|---|---|

## Platform-Specific Assets
### [Platform Name]
| Asset | Content | Caption | Hashtags | Publish Date |
|---|---|---|---|---|

## Blog Post Outline
- Title: [SEO-optimized]
- Sections: [based on video content]
- Key quotes: [embedded from transcript]

## Social Copy
### Clip 1: [Title]
- Hook: [first line]
- Caption: [full caption]
- CTA: [action]

[Repeat for each clip]

## Distribution Timeline
| Day | Asset | Platform | Time |
|---|---|---|---|
```

## Platform Implementation Steps

### Video Editing Tools
1. Upload transcript to Descript or Opus Clip for AI-generated clips
2. Review suggested clips and select top 5-10
3. Add captions (burned-in for social, SRT for YouTube)
4. Resize for platform dimensions (9:16, 1:1, 16:9)
5. Add intro hook text and outro CTA overlay

### Social Scheduling
1. Batch-create all assets after episode publication
2. Schedule staggered posting using Buffer, Later, or Hootsuite
3. Customize captions per platform (don't cross-post identical content)
4. Monitor engagement in first 24 hours per clip
5. Boost top-performing clips with paid promotion

### Blog/Newsletter
1. Convert transcript to blog post (clean up spoken language, add headers)
2. Embed key clips within blog post
3. Include blog link in newsletter with episode highlight
4. Cross-link between blog and full episode

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Clips get no views | Weak hooks, wrong platform, bad timing | Test different hooks; analyze when your audience is online |
| Clips misrepresent content | Taken out of context | Review clips for accuracy; add context in caption |
| Too much work per episode | Trying to create 20+ assets | Focus on 5-8 highest-impact assets; batch production |
| Low click-through to full episode | Clips are self-contained (no reason to watch more) | End clips on cliffhangers; tease additional content |

## How to Get Your Data

- **Transcript**: YouTube auto-captions → download SRT; Descript/Otter.ai transcription
- **Clip suggestions**: Opus Clip, Descript, or manual review of transcript for key moments
- **Performance data**: Platform native analytics → views, engagement per clip
- **No video yet**: Describe your upcoming content — Claude creates the repurposing plan in advance

## Example

**Input**: "Repurposing plan for our 45-minute podcast episode about 'The Future of AI in Marketing.' Guest discussed: AI content generation, personalization at scale, AI ethics in marketing, and practical tools to start with. Our platforms: LinkedIn (primary), Twitter, YouTube, Instagram."

**Output**: 12 assets from one episode: (1-3) Three 60-second clips — "The one AI tool every marketer needs" (tools segment), "Why AI personalization is the new A/B testing" (personalization segment), "The ethical line AI marketers shouldn't cross" (ethics segment, contrarian angle). (4-5) Two LinkedIn text posts — thread on "5 ways AI changes marketing in 2026" with episode link; guest quote graphic with key insight. (6) Twitter thread — 8-tweet thread summarizing practical AI tools with screenshots. (7-8) Two Instagram carousels — "AI Marketing Tools Ranked" (5 slides), "AI Ethics Checklist for Marketers" (6 slides). (9) Blog post — "The Future of AI in Marketing: Key Takeaways from [Guest Name]" (1,500 words, SEO-optimized). (10) Newsletter excerpt — top 3 insights with link to full episode. (11-12) Two YouTube Shorts — best 45-second moments with on-screen captions. Distribution: Days 0-3 stagger clips and thread. Days 4-7 carousels and blog post. Day 10+ reshare evergreen clips.
