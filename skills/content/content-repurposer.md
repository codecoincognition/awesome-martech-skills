---
name: content-repurposer
description: >
  Turn long-form content into multiple derivative assets across channels. Use this skill whenever
  the user mentions content repurposing, content recycling, turning a blog post into social posts,
  repurpose a webinar, create social snippets from an article, turn a whitepaper into emails,
  "get more mileage from this content", content atomization, content derivatives, micro-content,
  "break this down into smaller pieces", or any request to transform one content piece into
  multiple formats. Also trigger when the user says "I wrote this blog post, now help me promote it"
  or "create social posts from this article" or "turn this into an email series".
---

# Content Repurposer

Take a single long-form content piece (blog post, whitepaper, webinar transcript, podcast notes) and generate derivative assets for multiple channels: social posts, email snippets, infographic scripts, video scripts, and quote cards.

## Granularity Check

> Can this be completed in a single 10-minute Claude session? **Yes.** Input is one content piece. Output is a multi-format content pack. No external tools needed.

## User Intent Mapping

Trigger when the user says:

- "Turn this blog post into social media content" (direct transformation)
- "I need to get more out of this article" (maximize ROI)
- "Create LinkedIn posts from this whitepaper" (platform-specific)
- "Help me atomize this content" (content strategy term)
- "I recorded a webinar, now create promotional content" (post-event)
- "What formats can I repurpose this into?" (exploration)
- "Generate 10 social posts from this blog" (quantity request)
- "Create email teasers from this report" (channel-specific)
- "Break this down into quote cards and thread content" (format-specific)
- "I need a content distribution plan for this piece" (strategic)

## Input Contract

### Required Input

| Field | Type | Description |
|---|---|---|
| `source_content` | text | The original content (article, transcript, report) |
| `content_type` | string | Blog post / Whitepaper / Webinar transcript / Podcast notes / Case study |

### Optional Input

| Field | Type | Default | Description |
|---|---|---|---|
| `brand_voice` | string | Professional | Tone: Professional / Casual / Authoritative / Conversational |
| `target_platforms` | list | All | LinkedIn / Twitter/X / Instagram / Facebook / Email / Thread |
| `audience` | string | General B2B | Target audience description |
| `key_cta` | string | Read the full article | Call-to-action for derivative content |
| `source_url` | string | null | Link back to original content |

### Input Validation Rules

1. Source content must be >300 words (too short = not enough to repurpose)
2. Content type helps tailor output formats (e.g., webinar → video clips, not infographic)
3. If no platforms specified, generate for all major platforms
4. Flag if content appears to be a draft (incomplete sentences, notes)

## Process

1. **Analyze source** — Identify: core thesis, 3-5 key takeaways, quotable statistics, controversial/interesting claims, frameworks/models, story hooks.

2. **Extract repurposable elements:**
   - **Data points** — Stats, percentages, comparisons → infographic/quote cards
   - **Key arguments** — Thesis + supporting points → LinkedIn posts, threads
   - **Stories/examples** — Anecdotes, case studies → narrative social posts
   - **Frameworks** — Step-by-step processes → carousel/thread content
   - **Quotes** — Expert quotes, bold claims → quote cards, tweet-style posts
   - **Questions** — Provocative questions → engagement posts, polls

3. **Generate per-platform derivatives:**

   **LinkedIn (3-5 posts):**
   - Hook + story + insight format (1,200-1,500 chars)
   - Include line breaks for readability
   - End with question or CTA

   **Twitter/X (5-8 posts):**
   - Single tweets (≤280 chars) with hooks
   - One thread (5-8 tweets) unpacking a key concept
   - Data point tweets with context

   **Instagram (2-3 captions):**
   - Carousel content (10-slide breakdown)
   - Story poll/question prompts
   - Caption with hashtag suggestions (20-30 relevant tags)

   **Email (2-3 snippets):**
   - Newsletter teaser (50-100 words)
   - Full email featuring key insight
   - Subject line options (5 variants)

   **Video/Audio scripts (1-2):**
   - 60-second short-form video script
   - 2-minute explainer script with visual cues

4. **Human checkpoint** — Present the element extraction summary. Ask: "These are the key elements I'll repurpose. Any angles to emphasize or avoid?"

5. **Generate output** — Complete content pack organized by platform.

## Output Contract

### Output Format

| Output | Format | Contents |
|---|---|---|
| Content pack | Markdown | All derivatives organized by platform |
| Social calendar | Markdown | 2-week posting schedule |

### Content Pack Structure

```markdown
# Content Repurposing Pack
Source: [Title]
Generated: [Date]
Platforms: LinkedIn, Twitter/X, Instagram, Email, Video

## Key Elements Extracted
- Core thesis: [one sentence]
- Key stats: [list]
- Quotable lines: [list]

## LinkedIn Posts (5)
### Post 1: [Hook type — Story / Data / Contrarian / Question]
[Full post text, formatted with line breaks]
Suggested image: [description]
Best time: Tuesday-Thursday, 8-10am

[Repeat for each post]

## Twitter/X Content (8)
### Thread: [Title]
Tweet 1/6: [text]
Tweet 2/6: [text]
...

### Standalone Tweets
1. [tweet text]
2. [tweet text]

## Email Snippets (3)
### Newsletter Teaser
Subject line options: [5 variants]
Preview text: [40 chars]
Body: [teaser text]

## Video Scripts (2)
### 60-Second Short
[HOOK - 5 sec] [text]
[PROBLEM - 10 sec] [text]
[SOLUTION - 30 sec] [text]
[CTA - 15 sec] [text]

## 2-Week Posting Schedule
| Day | Platform | Content | Format |
|---|---|---|---|
| Mon | LinkedIn | Post 1 | Text + Image |
| Tue | Twitter | Thread | Text thread |
...
```

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Content too short (<300 words) | Brief article | Extract what's there; suggest combining with other content |
| No clear data points | Opinion/thought piece | Focus on quotes, questions, and contrarian takes instead |
| Highly technical content | Dense jargon | Simplify for social; keep technical depth for email/LinkedIn |
| Content is time-sensitive | News/event coverage | Flag that derivatives should be published quickly; prioritize speed |
| Multiple topics in one piece | Unfocused source | Suggest splitting repurposing by topic; create separate derivative sets |

## How to Get Your Data

### From Your Blog

1. Open your published blog post
2. Select all content (Ctrl+A or Cmd+A)
3. Copy and paste into Claude
4. Include the URL for link-back in derivatives

### From a Webinar Recording

1. Download the auto-generated transcript (Zoom, Teams, etc.)
2. Paste transcript into Claude
3. Specify: "This is a webinar transcript. Repurpose it."

### From a Whitepaper/Report

1. Copy the text content (excluding table of contents and references)
2. Paste into Claude
3. Include any key charts/data as descriptions

## Example

**User prompt:** "I just published a 2,000-word blog post about why traditional project management is broken. Turn it into social content for LinkedIn and Twitter."

**Claude responds:**

> I've analyzed your post and extracted these repurposable elements:
> - **Core thesis:** Traditional PM forces teams to plan everything upfront, which is the opposite of how successful teams actually work
> - **Key stat:** "67% of projects using waterfall methodology exceed their budget"
> - **Contrarian claim:** "Gantt charts are comforting fictions"
> - **Framework:** 4-step "Adaptive Planning" process
> - **Story:** The failed ERP implementation example
>
> Here's your content pack:
>
> **LinkedIn Posts (4):**
> 1. Contrarian hook — "Gantt charts are comforting fictions..." (story + data format)
> 2. Data-led — "67% of waterfall projects exceed budget..." (stat + framework)
> 3. Question — "When was the last time a project went according to plan?"
> 4. Framework post — "4 steps to Adaptive Planning" (step-by-step)
>
> **Twitter/X (6):**
> - 1 thread (6 tweets unpacking Adaptive Planning)
> - 5 standalone tweets (data points, quotes, questions)
>
> **Posting schedule:** Spread across 2 weeks, starting with the contrarian LinkedIn post on Tuesday.
>
> [Full derivatives below]
