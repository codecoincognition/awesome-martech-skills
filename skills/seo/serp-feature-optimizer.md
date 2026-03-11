---
name: serp-feature-optimizer
description: >
  Optimize for SERP features — featured snippets, People Also Ask, knowledge panels, and rich results.
  Use this skill when the user says "featured snippet optimization", "SERP feature strategy",
  "People Also Ask optimization", "rich results optimization", "knowledge panel strategy",
  "position zero targeting", "answer box optimization", "SERP feature analysis", "FAQ schema
  for SERP", "video carousel optimization", or "image pack SEO". Also trigger for SERP
  landscape analysis, zero-click search strategy, or Google SGE preparation.
---

# SERP Feature Optimizer

Analyzes SERP feature opportunities and optimizes content to win featured snippets, People Also Ask boxes, rich results, and other SERP features for maximum visibility.

## Granularity Check

> **Time**: ~5 min data prep → ~10 min Claude session → ~30-60 min implementation in Google Search Console / CMS. If implementing, add 2-4 hours for content restructuring and schema markup. Input is target keywords and current SERP analysis. Output is Markdown optimization plan per SERP feature type.

## User Intent Mapping

- "How do we get featured snippets?" (snippet strategy)
- "Analyze SERP features for our keywords" (landscape analysis)
- "Optimize for People Also Ask" (PAA)
- "Rich results strategy for our site" (schema/rich results)
- "We rank #3 but get no clicks — zero-click issue" (visibility)
- "Google SGE — how do we prepare?" (AI overview)
- "Knowledge panel for our brand" (brand SERP)
- "Video carousel optimization" (video SEO)
- "Image pack ranking" (image SEO)
- "FAQ schema implementation" (structured data)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Target Keywords | Text list | Keywords you want SERP features for |
| Current Rankings | Text/CSV | Where you currently rank for these keywords |
| Content Type | Text | Blog, product page, service page, FAQ, etc. |

### If You Don't Have This Data

- **No SERP analysis tool?** Search your target keywords incognito and note which SERP features appear (snippets, PAA, images, videos). Claude works from manual observations.
- **No ranking data?** Use free Google Search Console or search manually. Claude identifies the most winnable SERP features regardless.
- **No schema markup experience?** Claude provides copy-paste JSON-LD code for each recommended schema type.
- **No content optimization tools?** Claude provides the content restructuring recommendations directly — no tool needed.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| SERP Screenshots | Image/Text | Current SERP layout for target keywords |
| Competitor Snippets | Text | Who currently owns featured snippets |
| Schema Markup | Text | Current structured data on your pages |
| Content Inventory | CSV | Pages, topics, word count, format |
| Search Console Data | CSV | Queries, impressions, clicks, CTR, position |

## Process

### Step 1: SERP Landscape Analysis
Map SERP features present for each target keyword:
- Featured snippet (paragraph, list, table, video)
- People Also Ask boxes
- Knowledge panel
- Image pack
- Video carousel
- FAQ rich results
- How-to rich results
- Local pack
- Shopping results
- AI Overview / SGE

### Step 2: Featured Snippet Optimization
- Identify snippet type needed (paragraph, list, table)
- Structure content to match snippet format:
  - Paragraph snippets: 40-60 word direct answer below the question as H2
  - List snippets: H2 question + ordered/unordered list items
  - Table snippets: HTML table with clear headers
- Place snippet-optimized content above the fold
- Use the exact query as an H2 heading
- Provide a concise answer immediately after the heading

### Step 3: People Also Ask (PAA) Strategy
- Research PAA questions for target keywords
- Create FAQ sections answering each PAA question
- Structure: question as H3, 2-3 sentence answer, then expanded detail
- Implement FAQ schema markup for PAA visibility
- Target PAA clusters (groups of related questions)

### Step 4: Rich Results Implementation
- FAQ schema for question-answer pages
- HowTo schema for tutorial content
- Product schema for product pages (price, availability, reviews)
- Article schema for blog posts
- Video schema for pages with embedded video
- Breadcrumb schema for navigation
- Review/Rating schema where applicable

### Step 5: Zero-Click Strategy
- Brand SERP optimization (own your brand's search results)
- Knowledge panel claiming and optimization
- Sitelinks optimization via clear site architecture
- Social profile linking for brand panel
- Maximize impression value even without clicks

### Confidence & Sample Size
> **Confidence Note**: Featured snippets change frequently — Google rotates snippet holders and may remove snippets entirely. Winning a snippet typically requires ranking in the top 5 already. SERP features vary by device, location, and personalization. AI Overviews (SGE) are still evolving and may change SERP feature dynamics significantly. Monitor weekly, not daily.

### ⚠️ Human Checkpoint
> Verify all schema markup with Google's Rich Results Test before deploying. Incorrect schema can result in manual actions. Review content accuracy before targeting featured snippets — Google prioritizes authoritative answers.

> **Benchmark Context**: See Ahrefs 2024 Search Traffic Study, and Semrush 2024 State of Search for current industry benchmarks relevant to this analysis.
## Output Contract

### Deliverable: Markdown SERP Feature Plan

```markdown
# SERP Feature Optimization: [Site]

## SERP Landscape
| Keyword | Current Rank | SERP Features Present | Opportunity |
|---|---|---|---|

## Featured Snippet Targets
| Keyword | Snippet Type | Current Holder | Content Changes Needed |
|---|---|---|---|

## PAA Optimization
| PAA Question | Target Page | Answer Draft | Schema Needed |
|---|---|---|---|

## Schema Implementation
| Page | Schema Type | JSON-LD Code | Rich Result Type |
|---|---|---|---|

## Content Restructuring Plan
| Page | Current Format | Optimized Format | Changes |
|---|---|---|---|

## Quick Wins
1. [Action] — Expected impact: [metric]
```

## Platform Implementation Steps

### Content Optimization
1. Restructure target pages with question-based H2 headings
2. Add concise 40-60 word answers immediately below each H2
3. Format list-type content with proper HTML lists (not just line breaks)
4. Add HTML tables where table snippets are appropriate
5. Create FAQ sections at the bottom of relevant pages

### Schema Markup
1. Generate JSON-LD for each page using schema.org vocabulary
2. Add to page `<head>` section or via CMS plugin (Yoast, Rank Math)
3. Test with Google Rich Results Test (search.google.com/test/rich-results)
4. Monitor rich results in GSC → Enhancements reports

### Monitoring
1. Track SERP features in Semrush, Ahrefs, or SERPstat
2. Set up rank tracking with SERP feature detection enabled
3. Monitor CTR changes in GSC after snippet wins
4. Weekly SERP screenshot comparison for target keywords

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Lost featured snippet | Competitor optimized better or Google rotated | Re-optimize content; add more comprehensive answer |
| Schema markup errors | Invalid JSON-LD or unsupported properties | Validate with Rich Results Test; fix syntax errors |
| CTR dropped despite snippet win | Snippet answers query fully (no click needed) | Add a teaser that encourages click-through; expand on-page value |
| Rich results disappeared | Schema policy violation or algorithm update | Check GSC manual actions; review schema against current guidelines |

## How to Get Your Data

- **Semrush/Ahrefs**: Enter keywords → check SERP Features column in ranking reports
- **Manual**: Search keywords incognito → note all SERP features visible
- **Google Search Console**: Performance → filter by query → check CTR vs. position
- **No tools**: List your target keywords — Claude identifies likely SERP feature opportunities

## Example

**Input**: "SERP feature optimization for a cooking blog. Keywords: 'how to make sourdough bread', 'best pasta recipes', 'meal prep ideas for beginners'. Currently ranking positions 3-8. No schema markup on the site."

**Output**: SERP landscape: "how to make sourdough bread" has list snippet + video carousel + PAA (6 questions); "best pasta recipes" has image pack + carousel; "meal prep ideas" has list snippet + PAA (8 questions). Featured snippet targets: restructure sourdough post with H2 "How to Make Sourdough Bread" followed by numbered steps (list snippet format), add recipe time/yield table. PAA strategy: answer all 14 PAA questions across target keywords — create FAQ section per post with FAQ schema. Schema: add Recipe schema to all recipe posts (cook time, ingredients, nutrition, rating), HowTo schema for tutorial posts, Article schema site-wide. Content changes: (1) sourdough post — add numbered step list at top, currently buried in narrative text, (2) pasta recipes — add image alt text with keyword variations for image pack, (3) meal prep — restructure as H2 "Meal Prep Ideas for Beginners" + bulleted list of ideas. Quick wins: add Recipe schema (30 min with plugin), restructure sourdough steps (1 hour).

## Related Skills

- **[On Page SEO Auditor](./on-page-seo-auditor.md)** — Use to optimize page elements specifically for SERP feature eligibility (formatting, headings, structured data).
- **[Content Brief Generator](../content/content-brief-writer.md)** — Use to create briefs that explicitly include SERP feature requirements (featured snippets, how-to schema, etc.).
- **[Technical SEO Auditor](./technical-seo-auditor.md)** — Use to ensure proper structured data implementation required for knowledge panels, rich results, and other SERP features.
- **[Keyword Cluster Analyzer](./keyword-cluster-analyzer.md)** — Use to identify keywords with high SERP feature potential before optimizing for them.
