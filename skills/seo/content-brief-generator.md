---
name: content-brief-generator
description: >
  Generate a detailed SEO content brief from a target keyword or keyword cluster.
  Use this skill whenever the user wants to create a content brief, plan a blog post,
  prepare writing instructions, needs a brief for a freelance writer, wants to outline
  what a piece of content should cover, or says things like "what should I write about
  for this keyword". Also trigger when the user has output from keyword-cluster-analyzer
  and wants to turn a cluster into a writing plan. Use for any content planning that
  starts with a keyword or topic and needs to become a structured brief.
---

# Content Brief Generator

Creates a comprehensive content brief that gives a writer everything they need to produce a high-ranking piece of content. Includes title options, target structure, SERP analysis, internal linking suggestions, and competitive gap analysis.

## Granularity Check

> **Time**: ~5 min data prep → ~10 min Claude session → ~45-90 min writing in your CMS. If implementing output in a platform, add 10-20 minutes for setup. Input is a keyword + optional context. Output is a structured Markdown brief. Web search may be used for SERP analysis but is optional.

## User Intent Mapping

- "Create a content brief for [keyword]" (direct command)
- "I need to write about [topic], what should I cover?" (problem statement)
- "Brief my writer on this keyword" (delegation)
- "What should a blog post about [topic] include?" (planning)
- "Turn this keyword cluster into a content brief" (chaining with keyword-cluster-analyzer)
- "I want to rank for [keyword], what content do I need?" (goal-oriented)
- "Analyze the SERP for [keyword] and tell me what to write" (competitive)
- "Help me plan content around [keyword]" (general planning)
- "What are competitors covering for this keyword?" (gap analysis)
- "Generate a writing brief with SEO guidelines" (format-specific)

## Input Contract

### Required Input

| Field | Type | Description | Example |
|---|---|---|---|
| `target_keyword` | string | Primary keyword to target | `"best project management software for small teams"` |

### If You Don't Have This Data

- **No Search Console access?** Ask your web developer to grant you Viewer access, or use free tools like Ubersuggest for basic keyword data.
- **No keyword research?** Type your topic into Google and note the autocomplete suggestions + "People Also Ask" questions. That's free keyword research.
- **No competitor URLs?** Search your target keyword — the top 5 organic results are your SEO competitors.
- **No content inventory?** Export your sitemap (yoursite.com/sitemap.xml) or use Screaming Frog's free tier (500 URLs).

### Optional Input

| Field | Type | Default | Description |
|---|---|---|---|
| `secondary_keywords` | list of strings | `[]` | Related keywords to include (from cluster analyzer) |
| `competitor_urls` | list of URLs | `[]` | Competitor articles to analyze |
| `target_audience` | string | `"general"` | Who the content is for |
| `content_format` | string | `"blog post"` | Blog post, landing page, guide, comparison |
| `brand_context` | string | `""` | Company name, product, unique angle |
| `target_word_count` | integer | auto-calculated | Override automatic word count recommendation |

### Input Validation Rules

1. `target_keyword` must not be empty
2. `competitor_urls` must be valid URLs if provided
3. If `secondary_keywords` provided, should be 2-20 keywords

**If validation fails:** Ask the user for the missing target keyword. If they provide a topic instead of a keyword, help them identify a target keyword.

## Process

1. **Parse input** — Extract target keyword, optional context, and any cluster data from keyword-cluster-analyzer output.

2. **Analyze search intent** — Classify the keyword's primary intent (informational, commercial, transactional). This determines content format and structure.

3. **SERP analysis** (if web search available) — Search the target keyword and analyze the top 5 results:
   - Content format (list, guide, comparison, tutorial)
   - Average word count
   - Common H2 headings
   - Content gaps (topics not covered by competitors)
   - Featured snippet opportunity

4. **Generate title options** — Create 5 title variants using proven frameworks:
   - Number-based: "X Best [Topic] in 2026"
   - How-to: "How to [Achieve Goal] with [Topic]"
   - Question: "What Is the Best [Topic] for [Audience]?"
   - Benefit-driven: "[Benefit]: A Guide to [Topic]"
   - Curiosity: "Why [Surprising Fact] About [Topic]"

5. **Build content structure** — Create H2/H3 outline with:
   - Recommended word count per section
   - Key points to cover in each section
   - Where to place target keyword and secondary keywords
   - Internal linking opportunities

6. **Human checkpoint** — Present the brief summary. Ask: "Does this structure match what you need? Should I adjust the angle, depth, or format?"

7. **Finalize brief** — Add SEO guidelines, meta description template, and content checklist.


> **Benchmark Context**: Average time to rank on page 1 for a new page is 3-6 months (Semrush 2024 State of Search). Long-tail keywords (3+ words) have 3-5% CTR vs (Ahrefs 2024 Search Traffic Study). 1-2% for head terms. The #1 organic result gets ~27.6% of clicks. Content updates on existing pages show ranking improvements within 2-4 weeks (Semrush 2024 State of Search). (Ahrefs 2024 Search Traffic Study)


### Confidence & Sample Size.
> **Confidence Note**: Results are only as reliable as your input data. Small datasets (<50 records or <30 days of data) produce directional insights, not statistically significant conclusions. Always note your sample size when sharing results with stakeholders. Recommendations should be validated with A/B testing or additional data before making major strategic changes.

## Output Contract

### Output Format

| Output | Format | Contents |
|---|---|---|
| Content brief | Markdown | Complete writing brief |

### Content Brief Structure

```markdown
# Content Brief: [Target Keyword]

## Overview
- Target keyword: [keyword]
- Secondary keywords: [list]
- Search intent: [intent type]
- Recommended format: [format]
- Target word count: [count]
- Target audience: [audience]

## SERP Analysis
- Top competitor takeaways
- Content gaps identified
- Featured snippet opportunity: [yes/no + format]

## Title Options
1. [Title 1]
2. [Title 2]
3. [Title 3]
4. [Title 4]
5. [Title 5]

## Content Structure
### H2: [Section Title] (~X words)
- Key points to cover
- Keywords to include: [list]
- Internal link opportunity: [page]

[Repeat for each H2]

## SEO Guidelines
- Primary keyword placement: title, H1, first 100 words, meta description
- Secondary keyword targets per section
- Meta description template (150-160 chars)
- Image alt text guidance

## Content Checklist
- [ ] Unique angle identified
- [ ] All H2 sections covered
- [ ] Keywords placed naturally
- [ ] Internal links added
- [ ] Meta description written
- [ ] Featured snippet format used (if applicable)
```

## Platform Implementation Steps

### Google Search Console
1. Navigate to Performance → Search Results
2. Compare output keywords against actual impressions/clicks
3. Use the URL Inspection tool to verify indexing
4. Submit updated pages for re-crawling after changes

### WordPress + Yoast/RankMath
1. Edit the target page in WordPress
2. Paste optimized title tag and meta description in the SEO plugin fields
3. Add recommended headings and content structure
4. Check the SEO score indicator before publishing

### Google Sheets (Tracking)
1. Create a keyword tracking spreadsheet from the output
2. Add columns: current rank, target rank, monthly search volume
3. Update rankings weekly using Search Console data
4. Track progress over 3-6 month periods

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Keyword too broad | "marketing" with no qualifier | Ask user to narrow: "Marketing for what audience or product?" |
| No search volume data | Keyword is very niche | Proceed without volume; note content may target long-tail traffic |
| SERP analysis unavailable | No web search access | Skip SERP section; build brief from keyword semantics alone |
| Competitor URLs are 404 | Stale links | Skip broken URLs; note which ones failed |
| Topic outside user's expertise | No brand context provided | Ask for company/product context to tailor the brief |
| Keyword cannibalization risk | User already has content on this topic | Flag the risk and suggest differentiation angle |

## How to Get Your Data

### From keyword-cluster-analyzer

If you've already run the keyword cluster analyzer, use the primary keyword and secondary keywords from any cluster as input for this skill.

### From Google Search Console

1. Go to Search Console → Performance
2. Filter by page or query
3. Note which queries your page appears for but doesn't rank well
4. Use the highest-impression, lowest-CTR query as your target keyword

### From Ahrefs / SEMrush

1. Use Content Gap or Keyword Gap tool
2. Enter your domain and 2-3 competitors
3. Export keywords your competitors rank for but you don't
4. Pick a high-opportunity keyword as your target

## Example

**User prompt:** "Create a content brief for 'best project management software for small teams'. We're a PM tool called TaskFlow targeting startups."

**Claude output:**

> # Content Brief: best project management software for small teams
>
> ## Overview
> - **Target keyword:** best project management software for small teams
> - **Secondary keywords:** project management tools startups, small team PM apps, affordable project management
> - **Search intent:** Commercial investigation
> - **Format:** Comparison/listicle with detailed reviews
> - **Target word count:** 2,500-3,000 words
> - **Audience:** Startup founders and small team leads (2-25 people)
>
> ## Title Options
> 1. 10 Best Project Management Software for Small Teams in 2026
> 2. Best Project Management Tools for Small Teams (Hands-On Review)
> 3. Small Team? Here Are the Project Management Tools That Actually Work
> 4. Project Management Software for Small Teams: The Complete Comparison
> 5. Which Project Management Tool Is Best for Your Small Team?
>
> ## Content Structure
> ### H2: What Small Teams Actually Need in PM Software (~300 words)
> - Pain points unique to small teams (budget, simplicity, fast onboarding)
> - Feature prioritization: collaboration > complexity
> - Keywords: project management for startups, small team needs
>
> ### H2: The 10 Best Options, Ranked (~1,500 words)
> - 150 words per tool: overview, best for, pricing, key limitation
> - Include TaskFlow naturally in position 1-3 with honest pros/cons
> - Keywords: best PM software, top project management tools
>
> [... additional H2s for comparison table, selection criteria, FAQ ...]

## Related Skills

- **[Keyword Cluster Analyzer](./keyword-cluster-analyzer.md)** — Use before creating a content brief to organize keywords into topic clusters that define what to write about.
- **[Content Pillar Strategy](../content/content-pillar-strategy.md)** — Use to position this brief within your broader topic cluster and pillar-cluster content architecture.
- **[SEO Content Strategy](./seo-content-strategy.md)** — Use to align this individual brief with your overall SEO strategy and content roadmap.
- **[Blog Outline Generator](../content/blog-outline-generator.md)** — Use immediately after the brief to structure the actual outline writers will follow.
