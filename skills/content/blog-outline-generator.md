---
name: blog-outline-generator
description: >
  Create a structured blog post outline from a content brief or topic.
  Use this skill whenever the user wants to outline a blog post, plan article structure,
  create a writing skeleton, needs H2/H3 headings for a post, or says "help me outline
  this article". Also trigger when chaining from content-brief-generator output. Use for
  any blog planning that needs to go from topic to detailed section-by-section outline
  with word count targets and key points. Even "I need to write about X, where do I start?"
  should trigger this skill.
---

# Blog Outline Generator

Creates a detailed blog post outline with H2/H3 hierarchy, key points per section, word count allocations, CTA placement, and writing notes. Takes a content brief or a simple topic and produces a ready-to-write skeleton.

## Granularity Check

> Completable in one 10-minute session. Input is a brief or topic. Output is a structured Markdown outline. No external tools needed.

## User Intent Mapping

- "Outline a blog post about [topic]" (direct command)
- "I have a content brief, now help me plan the structure" (chaining)
- "What sections should my article on [topic] have?" (planning)
- "Create H2/H3 headings for this blog post" (specific structure)
- "Help me structure this article before I write it" (pre-writing)
- "I need to write a 2,000-word post about [topic]" (word count driven)
- "Break this topic into sections" (structural request)
- "Plan the outline for my next blog post" (general planning)
- "Turn this brief into something I can start writing" (action-oriented)
- "What should each section of this article cover?" (detail-oriented)

## Input Contract

### Required Input

| Field | Type | Description | Example |
|---|---|---|---|
| `topic` | string | Blog topic or target keyword | `"project management for remote teams"` |

### Optional Input

| Field | Type | Default | Description |
|---|---|---|---|
| `content_brief` | Markdown | `null` | Full brief from content-brief-generator |
| `target_word_count` | integer | `1,500` | Total word count target |
| `audience` | string | `"general"` | Target reader |
| `content_type` | string | `"how-to guide"` | Blog type: how-to, listicle, comparison, tutorial, opinion |
| `cta_goal` | string | `"newsletter signup"` | What the CTA should drive |
| `tone` | string | `"professional but approachable"` | Writing tone |

### Input Validation Rules

1. `topic` must not be empty (or `content_brief` must be provided)
2. `target_word_count` should be 500-10,000 (warn outside this range)
3. If `content_brief` is provided, extract topic, keywords, and structure from it

**If validation fails:** Ask the user for at minimum a topic or keyword to build around.

## Process

1. **Parse input** — Extract topic, constraints, and any brief data. If a content_brief is provided, use its structure as the starting framework.

2. **Determine content type** — Based on the topic and keywords, recommend the best format:
   - How-to guide: procedural, step-by-step
   - Listicle: numbered items, skimmable
   - Comparison: side-by-side analysis
   - Deep-dive: comprehensive coverage of one topic
   - Opinion/thought leadership: perspective-driven

3. **Generate H2 structure** — Create 4-8 H2 sections that cover the topic comprehensively:
   - Each H2 gets a descriptive heading (not generic like "Introduction")
   - Sections flow logically (problem → solution → implementation → results)
   - Allocate word count per section (proportional to importance)

4. **Add H3 subsections** — For sections over 400 words, add 2-4 H3 subsections with specific talking points.

5. **Place CTAs and internal links** — Identify where to place:
   - Primary CTA (typically after value-heavy section, before conclusion)
   - Secondary CTAs (in-content mentions, sidebar suggestions)
   - Internal link opportunities (reference existing content)

6. **Human checkpoint** — Present the outline. Ask: "Does this structure work? Should I add, remove, or reorganize any sections?"

7. **Add writing notes** — For each section, add 2-3 bullet points of key things to cover, data points to include, or angles to take.

## Output Contract

### Output Format

| Output | Format | Contents |
|---|---|---|
| Blog outline | Markdown | Complete section-by-section outline |

### Outline Structure

```markdown
# [Blog Post Title]

**Target word count:** X,XXX words
**Content type:** [type]
**Target keyword:** [keyword]
**Audience:** [audience]
**Tone:** [tone]

---

## H2: [Section Title] (~XXX words)

**Purpose:** Why this section exists
**Key points:**
- Point 1 to cover
- Point 2 to cover
- Point 3 to cover

**Keywords to include:** [keyword1], [keyword2]

### H3: [Subsection] (~XXX words)
- Specific talking point
- Data or example to include

### H3: [Subsection] (~XXX words)
- Specific talking point

---

[Repeat for each H2]

## CTA Placement
- **Primary CTA:** [Location + action]
- **Secondary CTA:** [Location + action]

## Internal Links
- [Anchor text] → [target page/topic]

## Writing Notes
- Tone reminders
- Things to avoid
- Key differentiators to emphasize
```

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Topic too broad | "marketing" with no angle | Ask user to narrow: audience, specific aspect, or goal |
| Topic too narrow | Very specific micro-topic | Suggest expanding to fill word count, or recommend shorter format |
| Word count mismatch | 500 words requested for complex topic | Recommend minimum word count or suggest splitting into series |
| No clear angle | Generic topic with no unique perspective | Suggest 3 angles and ask user to pick one |
| Content brief conflicts | Brief says one thing, user says another | Prioritize user's direct input; flag the discrepancy |

## How to Get Your Data

### From content-brief-generator

Run the content brief generator first with your target keyword. Pass its Markdown output directly as `content_brief` input to this skill.

### From scratch

Just provide a topic and optional constraints. No data export needed — this skill works from a topic description alone.

## Example

**User prompt:** "Outline a 2,000-word blog post about project management for remote teams. We sell a PM tool called TaskFlow. Target audience is startup CTOs."

**Claude output:**

> # How to Manage Projects Across Time Zones (Without Losing Your Mind)
>
> **Target word count:** 2,000 words | **Type:** How-to guide | **Audience:** Startup CTOs
>
> ---
>
> ## H2: Why Remote Project Management Is Different (~300 words)
> **Purpose:** Establish the problem — remote ≠ office with webcams
> **Key points:**
> - Async communication changes everything about status updates
> - Time zone overlap creates natural bottlenecks
> - "Just hop on a call" doesn't scale past 3 time zones
>
> ## H2: The 5 Principles That Actually Work (~500 words)
> **Purpose:** Framework that structures the rest of the post
>
> ### H3: Principle 1 — Default to Async (~100 words)
> - Why synchronous communication is the enemy of remote productivity
>
> ### H3: Principle 2 — Single Source of Truth (~100 words)
> - Every project needs one canonical place for status
>
> ### H3: Principle 3 — Overlap Windows, Not Overlap Days (~100 words)
> - How to design 2-hour daily overlap windows
>
> ### H3: Principle 4 — Decision Logs Over Decision Meetings (~100 words)
> - Written decisions are searchable, meetings are not
>
> ### H3: Principle 5 — Automate the Status Update (~100 words)
> - Let the tool do the reporting (natural TaskFlow mention)
>
> ## H2: Setting Up Your Remote PM Stack (~400 words)
> **Purpose:** Practical implementation guide
> - Tool categories needed: PM, communication, documentation
> - How TaskFlow fits each category
> - Integration checklist
>
> **[Primary CTA here: "Try TaskFlow free for 14 days"]**
>
> ## H2: Common Mistakes Remote Teams Make (~400 words)
> - Over-meeting, under-documenting
> - Treating remote as temporary
> - Not investing in async tooling
>
> ## H2: Measuring Success in Remote PM (~300 words)
> - KPIs that matter: cycle time, async response time, decision velocity
> - What to track weekly vs. monthly
>
> ## CTA Placement
> - **Primary:** After "Setting Up Your Remote PM Stack" section
> - **Secondary:** In-text mention of TaskFlow in Principle 5
>
> ## Internal Links
> - "async communication" → [guide to async work]
> - "project management tools" → [PM software comparison]
