---
name: instagram-caption-writer
description: >
  Write engaging Instagram captions with hooks, storytelling, hashtags, and CTAs.
  Use this skill when the user says "write an Instagram caption", "Instagram post copy",
  "IG caption ideas", "Instagram hashtag strategy", "help me write captions", "Instagram
  content writing", "carousel caption", "Reel caption", "Instagram engagement copy",
  "caption for my Instagram post", or "optimize my Instagram captions". Also trigger for
  Instagram story text, bio optimization, or Instagram content planning.
---

# Instagram Caption Writer

Writes scroll-stopping Instagram captions with optimized hooks, storytelling structure, strategic hashtags, and clear CTAs. Supports feed posts, carousels, Reels, and Stories.

## Granularity Check

> **Session time**: ~5 min data prep + ~10 min Claude session. If implementing output in a platform, add 5 min for posting. Input is post concept or image description. Output is 3+ caption variants with hashtag sets.

## User Intent Mapping

- "Write a caption for my product photo" (direct creation)
- "Instagram caption ideas for a fitness brand" (batch ideation)
- "Optimize my Instagram captions for engagement" (improvement)
- "Write carousel captions about skincare tips" (format-specific)
- "What hashtags should I use for [niche]?" (hashtag strategy)
- "Caption for a behind-the-scenes Reel" (Reel-specific)
- "Write 5 Instagram captions for this week" (batch creation)
- "My captions don't get engagement" (diagnosis)
- "Instagram caption for a product launch" (event-specific)
- "Turn this blog post into Instagram captions" (repurposing)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Post Concept | Text | What the post is about — product, topic, image description, or content idea |

### If You Don't Have This Data

- **No image yet?** Describe what you plan to photograph or design. Claude writes the caption, then you create the visual to match.
- **No brand voice?** Share 2-3 accounts whose tone you admire. Claude can match the style.
- **No hashtag research?** Claude generates hashtags based on your niche. Refine after seeing which ones drive discovery.
- **No analytics?** Post 3 variants over 2 weeks and compare reach/engagement to establish your baseline.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Brand Voice | Text | Tone descriptors: playful, minimal, educational, luxury, etc. |
| Format | Text | feed post, carousel, Reel, Story |
| Goal | Text | engagement, saves, shares, link clicks, DMs |
| Audience | Text | Target demographic and interests |
| CTA Type | Text | comment, save, share, DM, link in bio |

## Process

### Step 1: Hook Creation
First line determines 90% of whether someone reads the full caption:
- **Pattern interrupt**: "Stop scrolling if you [X]"
- **Bold statement**: "This changed everything about how I [X]"
- **Question**: "Want to know the secret to [X]?"
- **Stat/number**: "73% of [audience] get this wrong"
- **List tease**: "3 things nobody tells you about [X]"

### Step 2: Body Copy
- Match format to content type:
  - **Storytelling** (personal, behind-the-scenes): First person, emotional beats
  - **Educational** (tips, how-tos): Numbered steps, clear structure
  - **Promotional** (product, launch): Benefit-led, social proof, urgency
  - **Community** (questions, polls): Conversational, inclusive language
- Keep paragraphs to 1-2 sentences
- Use line breaks for readability
- Optimal length: 150-300 characters for engagement, up to 2,200 for SEO/saves

### Step 3: CTA Optimization
- Match CTA to goal:
  - **Engagement**: "Double tap if you agree" / "Tag someone who needs this"
  - **Saves**: "Save this for later" / "Bookmark this list"
  - **Shares**: "Share this with a friend who [X]"
  - **DMs**: "DM me [keyword] for the free guide"
  - **Link clicks**: "Link in bio for the full guide"

### Step 4: Hashtag Strategy
- Use 20-30 hashtags in first comment (not caption)
- Mix: 5 broad (500K+ posts), 10 medium (50K-500K), 10 niche (<50K)
- Include 1-2 branded hashtags
- Rotate hashtag sets to avoid shadowban risk

### Confidence & Sample Size
> **Confidence Note**: Instagram engagement varies by niche, follower count, and posting time. Test 3+ variants per format before drawing conclusions. Algorithm changes frequently — what works today may shift quarterly.

### ⚠️ Human Checkpoint
> Review captions for authenticity and brand alignment. Add personal details or real experiences to avoid generic-sounding content.

> **Benchmark Context**: Average Instagram feed post engagement rate is 0.60-0.80%. Carousel posts get 1.4x more reach than single images. Reels average 2-3x more reach than feed posts. Captions under 150 characters get 15% more engagement. Posting 3-7x/week is optimal.

## Output Contract

### Deliverable: Markdown with Caption Variants

```markdown
## Caption Variant A: [Style]
[Full caption with line breaks]

**CTA**: [call to action]
**Best for**: [feed/carousel/Reel]

## Caption Variant B: [Style]
[Full caption with line breaks]

## Hashtag Sets
### Set 1 (Broad + Niche Mix)
[20-30 hashtags]

### Set 2 (Alternate Rotation)
[20-30 hashtags]

## Posting Notes
- Best time: [day/time for your audience]
- Add hashtags in first comment, not caption
- Respond to comments in first 30 minutes
```

## Platform Implementation Steps

### Instagram (Direct)
1. Open Instagram → Create new post/Reel
2. Paste caption text (preserve line breaks — use Notes app as intermediary)
3. Post, then immediately comment with hashtags
4. Engage with comments in the first 30 minutes

### Later / Planoly / Buffer
1. Create new post → Upload media
2. Paste caption in the caption field
3. Add hashtags in the "First Comment" field
4. Schedule for recommended time

### Content Calendar (Batch Planning)
1. Generate 5-10 captions at once
2. Log in Google Sheets: date, format, caption, hashtag set, goal
3. Schedule across the week
4. Review performance after 48 hours per post

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Caption feels salesy | Too much product push | Lead with value or story, mention product at the end only |
| Low engagement | Hook isn't strong enough | Test 3 different hooks for the same content |
| Hashtag shadowban | Using banned or repetitive hashtags | Rotate sets, check hashtags aren't banned, mix sizes |
| Wrong tone for audience | Mismatch between voice and followers | Survey audience or check what competitors' tone looks like |

## How to Get Your Data

- **Instagram Insights**: Profile → Professional Dashboard → Content → See All
- **No analytics**: Describe your niche and audience — Claude generates from scratch
- **Competitor research**: Screenshot 5 top-performing posts in your niche for reference

## Example

**Input**: "Product launch post for an organic skincare serum. Target: women 25-40 interested in clean beauty. Tone: warm, educational."

**Output**:

> **Variant A (Educational Hook)**
>
> Your skin barrier is everything.
>
> And most serums actually damage it.
>
> That's why we spent 14 months formulating our new Barrier Repair Serum with:
> ✨ Ceramides (restore what cleansers strip away)
> ✨ Niacinamide (calm inflammation in 48 hours)
> ✨ Squalane (hydrate without clogging pores)
>
> No fragrance. No essential oils. No BS.
>
> Just science-backed ingredients your skin actually needs.
>
> Save this for your next skincare restock 🧴
>
> **CTA**: Save this post | Link in bio to shop
