---
name: blog-section-expander
description: >
  Expand a single blog section or heading into polished, SEO-aware copy. Use this skill whenever
  the user mentions expanding a section, writing a blog section, fleshing out an outline point,
  turning bullet points into paragraphs, writing 300-500 words for a heading, expanding a
  subheading into full copy, drafting a blog section, "write this part of my blog post",
  "expand this heading into content", or needs to turn a blog outline into actual written content
  section by section. This skill chains with blog-outline-generator — use after getting an outline.
  Also trigger when the user pastes an outline section and asks "write this" or "flesh this out".
---

# Blog Section Expander

Expand a single blog section heading (H2 or H3) into 300-500 words of polished, SEO-optimized prose. Designed to be called iteratively — once per section — to build a complete blog post from an outline.

## Granularity Check

> Can this be completed in a single Claude session? **Yes — expect ~5 min data prep → ~10 min Claude session → ~30-60 min implementing in your CMS.** If implementing output in a platform, add 10-20 min for setup. Input is one section heading + context. Output is 300-500 words of ready-to-publish copy. This is intentionally scoped to a single section — call multiple times for a full post.

## User Intent Mapping

Trigger when the user says:

- "Write this section of my blog post" (direct request)
- "Expand this heading into 400 words" (specific length)
- "Flesh out this outline point" (outline → copy)
- "Turn these bullet points into paragraphs" (format conversion)
- "I have an outline, now write section 3" (sequential creation)
- "Write the introduction for my blog post" (specific section)
- "Expand 'Benefits of Agile Project Management' into full copy" (heading expansion)
- "Continue writing the next section" (continuation)
- "Draft the conclusion" (specific section)
- "Help me write the comparison section" (section type)

## Input Contract

### Required Input

| Field | Type | Description |
|---|---|---|
| `section_heading` | string | The H2 or H3 heading to expand |
| `target_keyword` | string | Primary keyword for SEO |

### If You Don't Have This Data

- **No content strategy?** Describe your product and your top 3 customer pain points. That's enough to generate an outline.
- **No keyword research?** List 5 questions your customers frequently ask. These become your topics.
- **No brand voice guide?** Provide 2-3 examples of content you like the tone of. Claude can infer the voice from examples.
- **No performance data?** Start fresh. After publishing, track views, time-on-page, and conversions for 30 days.

### Optional Input (Improves Quality)

| Field | Type | Description | Default |
|---|---|---|---|
| `key_points` | list | Bullet points to cover | Inferred from heading |
| `word_count` | integer | Target word count | 400 |
| `tone` | string | Writing style | Professional yet accessible |
| `blog_title` | string | Overall post title | Not used |
| `preceding_section` | text | Previous section content | Not used |
| `target_audience` | string | Reader profile | General B2B professional |
| `section_type` | string | Intro / Body / Comparison / How-to / Conclusion | Body |
| `internal_links` | list | URLs to naturally weave in | None |
| `secondary_keywords` | list | Additional keywords to include | None |

### Sample Input

```
Section heading: "Why Traditional Project Management Fails Remote Teams"
Target keyword: remote project management
Key points:
- Synchronous communication dependency
- Status meetings that could be async updates
- Lack of visibility into individual progress
- Tool sprawl across time zones
Tone: Conversational but data-backed
Word count: 450
```

### Input Validation Rules

1. Section heading is required — if missing, ask for it
2. Target keyword should be relevant to the section (warn if mismatch seems likely)
3. Key points help guide content — if not provided, Claude will infer from heading
4. Word count should be 200-800 (warn if outside range; default to 400)
5. If preceding section is provided, ensure natural transition

## Process

1. **Understand context** — Parse heading, keyword, key points, and section type. Determine the section's role in the larger post.

2. **Plan section structure:**
   - **Opening line** — Hook that connects to heading topic (avoid generic starts)
   - **Body** — 2-4 paragraphs covering key points with evidence/examples
   - **Transition** — Final sentence that bridges to the next likely section

3. **Write the section** following these rules:
   - Natural keyword inclusion (1-2 mentions of primary keyword)
   - Include secondary keywords where they fit naturally
   - Use specific examples, data, or analogies — no generic filler
   - Vary sentence length (mix short punchy sentences with longer explanatory ones)
   - Include one concrete example, statistic, or case reference per section
   - If internal links provided, weave them in with descriptive anchor text
   - No heading repetition in the opening sentence

4. **Section-type specific rules:**
   - **Introduction:** Start with hook (stat, question, or scenario). State the problem. Preview the solution. Include primary keyword in first 100 words. 200-300 words.
   - **Body:** Lead with the strongest point. Support with evidence. Include transitions.
   - **Comparison:** Use parallel structure. Be fair but guide toward a recommendation.
   - **How-to:** Number the steps. Include expected outcomes for each step.
   - **Conclusion:** Summarize key takeaways (don't just repeat). Include CTA. 150-250 words.

5. **Quality check:**
   - Readability: aim for Grade 8-10 reading level (Flesch-Kincaid)
   - No passive voice in >20% of sentences
   - No paragraph longer than 4 sentences
   - No clichéd openings ("In today's world...", "As we all know...")

6. **Present output** — Deliver the expanded section. Offer: "Want me to expand the next section?"


> **Benchmark Context**: See Content Marketing Institute 2024 B2B Research, Semrush 2024 State of Content Marketing, and research + writing + editing. (Semrush 2024 State of Content Marketing for current industry benchmarks relevant to this analysis.


### Confidence & Sample Size.
> **Confidence Note**: Results are only as reliable as your input data. Small datasets (<50 records or <30 days of data) produce directional insights, not statistically significant conclusions. Always note your sample size when sharing results with stakeholders. Recommendations should be validated with A/B testing or additional data before making major strategic changes.

## Output Contract

### Output Format

| Output | Format | Contents |
|---|---|---|
| Expanded section | Markdown | 300-500 words of polished copy |

### Output Structure

```markdown
## [Section Heading]

[Opening hook — 1-2 sentences that grab attention]

[Body paragraph 1 — main argument with evidence]

[Body paragraph 2 — supporting point or example]

[Body paragraph 3 (if needed) — additional depth or counterpoint]

[Transition sentence bridging to next section]
```

### Quality Standards

- Target keyword appears 1-2 times naturally
- At least 1 specific data point, example, or reference
- No paragraph exceeds 4 sentences
- Opening avoids clichés
- Transition to next section is smooth

## Platform Implementation Steps

### WordPress
1. Log in to wp-admin → Posts → Add New
2. Paste the content outline into the editor
3. Use the Heading blocks (H2, H3) for structure
4. Add Featured Image and set Category/Tags before publishing

### Google Docs (Collaboration)
1. Create a new Google Doc
2. Paste the output and use Suggesting Mode for team review
3. Use Insert → Table of Contents for navigation
4. Share with stakeholders for feedback

### CMS-Agnostic
1. Copy Markdown output as-is into any CMS that supports Markdown
2. For HTML-based CMS platforms, convert Markdown to HTML using any converter
3. Adapt headings and formatting to match your site's style guide

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Heading too vague | "Overview" or "Background" | Ask: "What specific aspect should this section cover?" |
| Conflicting keyword + heading | Keyword doesn't match section topic | Use keyword as context, not forced inclusion; note mismatch |
| No key points provided | User only gave heading | Infer 3-4 logical points from the heading; confirm before writing |
| Requested word count too long (>800) | User wants a mini-article | Suggest splitting into 2 sections; warn about reader fatigue |
| Preceding section has different tone | Inconsistent writing | Match the preceding section's tone for consistency |

## How to Get Your Data

### From Blog Outline Generator (Best Path)

1. Run blog-outline-generator to get a structured outline
2. Take one section heading + its bullet points
3. Feed into blog-section-expander
4. Repeat for each section until the full post is complete

### From an Existing Outline

1. Paste your outline (headings + bullet points)
2. Tell Claude which section to expand first
3. Iterate through remaining sections

### From Scratch

1. Tell Claude: "Write 400 words for a blog section titled '[heading]' targeting '[keyword]'"
2. Optionally provide key points to cover
3. Claude expands and delivers

## Example

**User prompt:** "Expand this section: 'Why Traditional Project Management Fails Remote Teams' for a blog post targeting 'remote project management'. Cover synchronous communication dependency and tool sprawl."

**Claude responds:**

> ## Why Traditional Project Management Fails Remote Teams
>
> When a team of 12 engineers spread across four time zones tried to run their daily standup at 9am EST, only six could attend live. The other six watched the recording the next day — by which time the discussed blockers had already derailed their sprints. This is the fundamental fracture in traditional project management: it was built for hallways, whiteboards, and same-room conversations.
>
> Synchronous communication dependency is the most visible failure point. Traditional PM methodologies assume team members can tap each other on the shoulder, gather for impromptu discussions, and read the room during meetings. Remote teams can't do any of this. A 2025 Buffer survey found that 58% of remote workers cite "collaboration and communication" as their biggest struggle — not motivation, not loneliness, but the basic mechanics of working together across distance.
>
> The second fracture is tool sprawl. When teams go remote, they compensate by adding tools: Slack for chat, Zoom for calls, Jira for tickets, Confluence for docs, Google Drive for files, Loom for async updates. The average remote team now uses 6.3 collaboration tools. Each tool holds a fragment of project context, and no single person has the complete picture. Status meetings become archaeology expeditions — digging through five platforms to reconstruct what happened yesterday.
>
> What makes this particularly damaging is the compound effect. Tool sprawl creates communication gaps, which trigger more status meetings, which eat into deep work time, which slows progress, which creates more gaps. Traditional PM frameworks don't have a circuit-breaker for this cycle because they were never designed to handle it.
>
> The solution isn't fewer tools or more meetings — it's a fundamentally different approach to how teams coordinate work across distance.

**Word count:** 278 (Claude would note: "This came in at 278 words. Want me to expand any paragraph, or does this feel right for the flow?")

## Related Skills

- **[Blog Outline Generator](./blog-outline-generator.md)** — Use before section expansion to create the outline you'll be expanding section-by-section.
- **[Content Brief Writer](./content-brief-writer.md)** — Use to provide the brief that guides section writing, tone, and SEO optimization.
- **[Content Repurposer](./content-repurposer.md)** — Use after expansion to turn the full blog post into social posts, email snippets, and other formats.
- **[Content Performance Scorecard](./content-performance-scorecard.md)** — Use after publication to measure section-level engagement and optimize future content.
