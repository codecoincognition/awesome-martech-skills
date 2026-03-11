---
name: linkedin-post-optimizer
description: >
  Optimize LinkedIn posts for engagement — hooks, formatting, hashtags, and CTAs.
  Use this skill when the user says "optimize my LinkedIn post", "write a LinkedIn post",
  "LinkedIn content strategy", "improve my LinkedIn engagement", "LinkedIn hook", "LinkedIn
  carousel ideas", "help me write for LinkedIn", "LinkedIn thought leadership post",
  "LinkedIn post format", "best LinkedIn post structure", or "my LinkedIn posts don't get
  engagement". Also trigger for LinkedIn article optimization or LinkedIn newsletter content.
---

# LinkedIn Post Optimizer

Analyzes and optimizes LinkedIn posts for maximum engagement using proven formatting patterns, hook formulas, and engagement triggers. Scores existing posts and generates optimized variants.

## Granularity Check

> **Time**: ~5 min data prep → ~10 min Claude session → ~20-40 min scheduling in Buffer / Hootsuite / native platform. If implementing output in a platform, add 5-10 min for scheduling. Input is draft post or topic. Output is optimized post variants with scoring.

## User Intent Mapping

- "Help me write a LinkedIn post about [topic]" (creation)
- "Optimize this LinkedIn post for engagement" (improvement)
- "Why don't my LinkedIn posts get likes?" (diagnosis)
- "Write a thought leadership post about AI" (topic-specific)
- "Create a LinkedIn carousel outline" (format-specific)
- "What's the best LinkedIn post format?" (education)
- "Generate 5 LinkedIn post ideas for this week" (batch planning)
- "Turn this blog post into a LinkedIn post" (repurposing)
- "Write a LinkedIn post announcing our new feature" (announcement)
- "LinkedIn post hooks that grab attention" (technique-specific)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Post Topic or Draft | Text | What you want to post about, or existing draft to optimize |

### If You Don't Have This Data

- **No topic ideas?** Share 3 things you learned at work this week. Each is a potential post.
- **No draft?** Just describe the key insight in 2-3 sentences. Claude will structure it.
- **No engagement data?** That's fine — this skill generates optimized posts from scratch. Check your analytics after posting.
- **No audience info?** Describe your job title and who you want to reach. That's enough.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Target Audience | Text | Who you're trying to reach (e.g., "B2B SaaS founders") |
| Tone | Text | professional, conversational, provocative, inspirational |
| Post Goal | Text | engagement, lead gen, brand awareness, hiring |
| Past Performance | Text | Average likes/comments on recent posts |
| Content Pillar | Text | Theme this post belongs to (e.g., "leadership", "product updates") |

## Process

### Step 1: Analyze & Structure
- Identify the core insight or value proposition of the post
- Choose optimal post format:
  - **Story arc**: Personal experience → lesson → takeaway
  - **List post**: "X things I learned about Y"
  - **Contrarian take**: Challenge conventional wisdom
  - **How-to**: Step-by-step tactical advice
  - **Data/stat-led**: Lead with a surprising number
  - **Before/after**: Transformation narrative

### Step 2: Write the Hook (First 2 Lines)
The hook appears before "...see more" and determines 80% of engagement:
- Use pattern interrupts: unexpected stats, bold claims, personal vulnerability
- Keep under 150 characters for full visibility
- Avoid questions as openers (lower CTR than statements)
- Test formats: "I [did X]. Here's what happened." / "[Stat] that changes everything."

### Step 3: Optimize Body
- Use short paragraphs (1-2 sentences max)
- Add line breaks between every paragraph (LinkedIn algorithm rewards scroll depth)
- Include a "scroll stopper" at the midpoint (bold claim, surprising data)
- Write at 8th-grade reading level
- Target 1,200-1,500 characters (sweet spot for engagement)

### Step 4: Craft CTA & Engagement Triggers
- End with a question or invitation to share perspective
- Use "Comment [X] if you want [Y]" for lead gen posts
- Avoid external links in the post body (kills reach by 40-50%)
- Place links in first comment instead

### Step 5: Hashtag & Timing
- Use 3-5 hashtags (mix of broad and niche)
- Place hashtags at the bottom, separated by line break
- Recommend posting times: Tuesday-Thursday, 8-10 AM in audience's timezone

### Confidence & Sample Size
> **Confidence Note**: Post performance varies significantly by network size, industry, and timing. Optimization increases the probability of engagement but doesn't guarantee virality. Test multiple formats over 4-8 weeks to find what works for your audience.

### ⚠️ Human Checkpoint
> Review the post for authenticity — LinkedIn audiences detect and penalize overly formulaic or AI-generated content. Add personal details, specific numbers, or named experiences to make it genuinely yours.

> **Benchmark Context**: See Sprout Social 2024 Index, and Buffer 2024 State of Social for current industry benchmarks relevant to this analysis.
## Output Contract

### Deliverable: Markdown with Optimized Post Variants

```markdown
## Post Analysis (if optimizing existing draft)
- Hook strength: [X/10]
- Formatting: [X/10]
- CTA effectiveness: [X/10]
- Overall engagement prediction: [low/medium/high]

## Optimized Post — Variant A: [Format Name]

[Full post text with formatting]

## Optimized Post — Variant B: [Format Name]

[Full post text with formatting]

## Recommended Hashtags
#hashtag1 #hashtag2 #hashtag3

## Posting Notes
- Best time: [day/time]
- Add link in first comment: [URL if applicable]
- Engage with comments in first 60 minutes to boost reach
```

## Platform Implementation Steps

### LinkedIn (Direct)
1. Open LinkedIn → Start a Post
2. Paste the optimized post text (preserve line breaks)
3. Add hashtags at the bottom
4. Post, then immediately add a first comment with any links
5. Engage with every comment in the first 60 minutes

### Buffer / Hootsuite / Later
1. Create a new post → select LinkedIn
2. Paste the post text
3. Schedule for the recommended time
4. Set a reminder to engage with comments when it goes live

### Notion/Sheets (Content Tracking)
1. Log the post in your content calendar
2. Track: date, format, topic, likes, comments, impressions
3. After 48 hours, record final metrics
4. Review monthly to identify top-performing formats

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Post feels generic | Topic is too broad | Narrow to a specific experience, data point, or opinion |
| Low engagement despite optimization | Small network or wrong timing | Focus on commenting on others' posts for 2 weeks to grow network first |
| Feels inauthentic | Too formulaic | Add a personal story, specific name, or real number |
| Content pillar unclear | Random posting | Define 3-4 content pillars and rotate between them |

## How to Get Your Data

- **LinkedIn Analytics**: Click "View analytics" under any post for impressions, engagement rate
- **LinkedIn Creator Mode**: Profile → Analytics → Content → Export (for aggregate data)
- **Manual**: Note likes + comments on your last 10 posts to establish a baseline
- **No data needed**: Describe your topic and audience — Claude generates from scratch

## Example

**Input**: "I want to write about how our startup reduced churn by 40% by fixing onboarding. Target: SaaS founders."

**Output**:

> **Variant A (Story Arc)**
>
> We were losing 30% of new users in the first week.
>
> Not because our product was bad.
> Because our onboarding was.
>
> Here's the 4-step fix that cut churn by 40% in 90 days:
>
> 1. Removed 6 of 9 setup steps (nobody finished them)
> 2. Added a "quick win" in the first 3 minutes
> 3. Replaced tutorial videos with interactive walkthroughs
> 4. Sent a personal check-in email on Day 3
>
> The biggest surprise?
> Step 4 alone moved the needle more than the other 3 combined.
>
> Sometimes the highest-ROI product improvement isn't a product improvement at all.
>
> What's the one onboarding change that made the biggest difference for your product?
>
> #SaaS #ProductLedGrowth #Onboarding #StartupLessons

## Related Skills

- **[Social Content Calendar](./social-content-calendar.md)** — Use to plan LinkedIn posts with optimal timing and frequency based on platform best practices.
- **[Content Repurposer](../content/content-repurposer.md)** — Use to adapt long-form blog content into optimized LinkedIn posts.
- **[Social Engagement Analyzer](./social-engagement-analyzer.md)** — Use to measure LinkedIn post performance and refine your optimization strategy.
- **[Twitter Thread Writer](./twitter-thread-writer.md)** — Use for similar long-form thought leadership on the X/Twitter platform.
