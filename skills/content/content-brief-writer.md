---
name: content-brief-writer
description: >
  Create detailed content briefs for writers — SEO requirements, structure, sources, and quality guidelines.
  Use this skill when the user says "content brief", "writing brief", "create a brief for writers",
  "content brief template", "SEO content brief", "brief for blog post", "content brief generator",
  "writer brief with SEO requirements", "content production brief", "freelance writer brief",
  or "content brief with outline". Also trigger for article brief, content specification,
  or writing assignment creation.
---

# Content Brief Writer

Creates detailed, actionable content briefs for writers that include SEO requirements, content structure, competitive analysis, source recommendations, and quality guidelines.

## Granularity Check

> **Session time**: ~5 min context gathering + ~10 min Claude session. Output is a ready-to-assign brief. Input is topic, keyword data, and content goals. Output is Markdown content brief.

## User Intent Mapping

- "Create a content brief for this blog post" (single brief)
- "Content brief template for our writers" (template)
- "SEO content brief with keyword requirements" (SEO-focused)
- "Brief for a freelance writer" (freelancer)
- "Content brief for our product comparison page" (specific type)
- "How to write better content briefs" (best practices)
- "Content brief with competitive analysis" (competitive)
- "Outline and brief for a pillar page" (pillar content)
- "Content production brief for our team" (team process)
- "Brief for a thought leadership article" (thought leadership)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Topic/Title | Text | What the content should be about |
| Target Keyword | Text | Primary keyword to target (if SEO-driven) |
| Content Goal | Text | What this content should achieve |

### If You Don't Have This Data

- **No keyword research?** Claude researches the topic and recommends primary + secondary keywords based on the topic.
- **No competitor analysis?** Claude identifies what currently ranks and provides differentiation recommendations.
- **No style guide?** Claude includes general quality guidelines that you can customize for your brand.
- **First brief?** Claude provides a comprehensive template you can reuse for future content.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Brand Voice | Text | Tone and style guidelines |
| Target Audience | Text | Specific persona or segment |
| Competitor URLs | Text | Competing content to analyze |
| Word Count | Text | Target length |
| Internal Links | Text | Pages to link to from this content |
| CTA | Text | Desired call-to-action |

## Process

### Step 1: Brief Foundation
- Title recommendations (3-5 options with SEO and click appeal)
- Primary keyword and search intent analysis
- Target word count (based on SERP analysis)
- Content format (listicle, guide, how-to, comparison, etc.)
- Target audience and their knowledge level

### Step 2: SEO Requirements
- Primary keyword (with placement guidance: title, H1, intro, URL)
- Secondary keywords (5-10 related terms to include naturally)
- Search intent alignment (informational, commercial, transactional)
- Meta title and description recommendations
- URL slug recommendation
- Internal linking requirements (specific pages to link to)

### Step 3: Content Structure
- Detailed outline with H2 and H3 headings
- Key points to cover under each section
- Questions to answer (from People Also Ask, forums, customer questions)
- Data points or statistics to include
- Examples or case studies to reference
- Visuals needed (screenshots, charts, infographics)

### Step 4: Competitive Differentiation
- Top 3-5 ranking pages analyzed
- Content gaps in competing articles
- Unique angles to pursue
- Information to include that competitors miss
- How to make this piece definitively better

### Step 5: Quality Guidelines
- Tone and voice requirements
- Formatting preferences (headers, bullets, paragraphs)
- Source requirements (cite data, link to studies)
- What to avoid (jargon, fluff, unsupported claims)
- CTA placement and wording
- Review and approval process

### Confidence & Sample Size

> **Confidence Note**: Content briefs are starting points — great writers will add their expertise and perspective. Over-prescriptive briefs can produce formulaic content. Balance structure (SEO requirements, key points) with creative freedom (voice, examples, unique insights). The best briefs constrain the topic, not the creativity.

### ⚠️ Human Checkpoint
> Review brief for accuracy of SEO data and competitive analysis. Verify internal linking targets are correct and relevant. Ensure brief reflects current brand voice and content strategy.

> **Benchmark Context**: Content produced from detailed briefs ranks 50% faster than unbriefed content. Briefs with competitive analysis produce content that ranks in the top 10 for 3x more keywords. Writers who receive structured briefs produce 30% fewer revision rounds. Content that answers People Also Ask questions earns featured snippets 2x more often.

## Output Contract

### Deliverable: Markdown Content Brief

```markdown
# Content Brief: [Title]

## Overview
- **Topic**: [topic]
- **Primary Keyword**: [keyword] ([volume], [difficulty])
- **Search Intent**: [informational/commercial/transactional]
- **Target Word Count**: [range]
- **Target Audience**: [persona]
- **Content Goal**: [goal]
- **Due Date**: [date]

## SEO Requirements
- **Primary Keyword**: [keyword] — use in title, H1, intro, 2-3x in body
- **Secondary Keywords**: [list with natural placement guidance]
- **Meta Title**: [recommendation, ≤60 chars]
- **Meta Description**: [recommendation, ≤155 chars]
- **URL Slug**: [recommendation]

## Content Outline
### [H2: Section 1]
- Key points: [bullets]
- Questions to answer: [list]

### [H2: Section 2]
- Key points: [bullets]
- Data to include: [specific stats]

[Continue for all sections]

## Competitive Analysis
| Competitor | URL | Strengths | Gaps |
|---|---|---|---|

## Internal Links
| Anchor Text | Target URL | Placement |
|---|---|---|

## Quality Checklist
- [ ] [Requirement]

## CTA
- Primary CTA: [text and placement]
```

## Platform Implementation Steps

### Content Operations
1. Create brief template in your project management tool (Notion, Asana, Monday)
2. Establish brief review and approval workflow before assigning to writers
3. Include SEO checklist as part of the editorial review process
4. Track brief-to-publish time to optimize content production

### SEO Integration
1. Pull keyword data from Ahrefs/SEMrush for each brief
2. Analyze top 5 SERP results for target keyword
3. Extract People Also Ask questions for the topic
4. Verify internal linking targets exist and are relevant

### Writer Workflow
1. Share brief with writer via project management tool
2. Writer submits draft against brief requirements
3. Editor reviews against SEO checklist and quality guidelines
4. Final review for brand voice and accuracy

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Writer produces off-topic content | Brief too vague or topic too broad | Add specific questions to answer and points to cover |
| Content doesn't rank | Wrong keyword or unrealistic difficulty target | Verify keyword difficulty; target keywords your domain authority can compete for |
| Too many revision rounds | Brief didn't specify quality expectations | Add examples, tone guidance, and explicit formatting requirements |
| Writer overwhelmed | Brief too long or over-prescriptive | Simplify to essential requirements; separate "must include" from "nice to have" |

## How to Get Your Data

- **Keywords**: Ahrefs/SEMrush → enter topic → filter by volume and difficulty
- **Competitor content**: Google the target keyword → analyze top 5 results
- **Questions**: Google → People Also Ask; AnswerThePublic; Reddit/Quora threads
- **No tools**: Share the topic and audience — Claude creates a brief with available information

## Example

**Input**: "Content brief for a blog post about 'email marketing automation for small businesses.' Target keyword: email marketing automation. We're a marketing SaaS. Audience: small business owners with 1-10 employees."

**Output**: Brief: "Email Marketing Automation for Small Businesses: The Complete 2025 Guide." Primary keyword: email marketing automation (vol: 8,100, KD: 45). Secondary: email automation tools, automated email campaigns, email drip campaigns, marketing automation for beginners. Word count: 2,500-3,500. Search intent: informational with commercial elements. Outline: (1) What is email marketing automation? (simple definition for non-technical readers), (2) Why small businesses need automation (time savings stats, ROI data), (3) 7 essential automated emails every small business should set up (welcome, abandoned cart, etc.), (4) How to choose an automation tool (comparison criteria, not specific product recommendations — we'll add ours naturally), (5) Getting started: your first automation in 30 minutes (step-by-step), (6) Common mistakes to avoid. Competitive gaps: top 3 results are enterprise-focused; none address the "1-person marketing team" angle. Differentiation: focus on simplicity, quick wins, realistic examples for tiny teams. Internal links: product page, pricing page, email templates library. CTA: "Start your free trial — set up your first automation in 15 minutes."
