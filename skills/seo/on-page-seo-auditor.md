---
name: on-page-seo-auditor
description: >
  Audit a webpage's on-page SEO elements and get a scored report with fixes. Use this skill whenever
  the user mentions on-page SEO, page SEO audit, SEO review of a page, title tag optimization,
  meta description check, heading structure review, keyword density analysis, image alt text audit,
  internal linking analysis, schema markup review, or wants to know "how is my page's SEO" or
  "why isn't this page ranking". Also trigger when the user pastes HTML source, shares a URL for
  SEO review, or says "check this page for SEO issues" or "optimize this page for [keyword]".
---

# On-Page SEO Auditor

Audit a single webpage's on-page SEO elements across 8 dimensions. Produces a scored report card with specific fixes and rewritten elements.

## Granularity Check

> Can this be completed in a single 10-minute Claude session? **Yes.** Input is page HTML or content. Output is a scored audit with rewrites. One page per session — for site-wide audits, run multiple times or use technical-seo-crawler-parser.

## User Intent Mapping

Trigger when the user says:

- "Audit this page for SEO" (direct request)
- "Why isn't this page ranking for [keyword]?" (diagnostic)
- "Check my title tags and meta descriptions" (specific element)
- "Is my heading structure correct for SEO?" (structure question)
- "Review my page's keyword usage" (optimization check)
- "What SEO improvements can I make to this page?" (improvement request)
- "I pasted the HTML, check it for SEO" (HTML input)
- "Optimize this page for [keyword]" (optimization task)
- "Score my page's on-page SEO" (scoring request)
- "Check if my images have proper alt text" (element-specific)

## Input Contract

### Required Input

Provide ONE of the following:

| Input Type | Description |
|---|---|
| HTML source | Full or partial HTML of the page |
| Page content | Copy-pasted text content with headings |
| URL + manual content | User describes page content (Claude cannot crawl) |

Plus:

| Field | Required | Description |
|---|---|---|
| `target_keyword` | Yes | Primary keyword the page should rank for |
| `secondary_keywords` | No | 2-5 related keywords |
| `page_type` | No | Blog post / Landing page / Product page / Homepage |

### Sample Input

```
Target keyword: project management software
Secondary keywords: best PM tools, project management app, team collaboration software
Page type: Landing page

[User pastes HTML or content of the page]
```

### Input Validation Rules

1. Target keyword is required — prompt if missing
2. Content must be substantial (>200 words) for meaningful analysis
3. If HTML is provided, parse it for structured elements; if plain text, work with what's available
4. Flag if page appears to be a duplicate of another provided page

## Process

1. **Parse page elements** — Extract: title tag, meta description, H1, H2-H6 hierarchy, body content, image alt tags, internal/external links, word count, URL structure.

2. **Audit 8 dimensions** — Score each 1-10:

   **a. Title Tag (weight: 15%)**
   - Contains target keyword? Position of keyword (front-loaded is better)?
   - Length: 50-60 characters optimal. Flag if too short/long.
   - Compelling for clicks? Unique value proposition?

   **b. Meta Description (weight: 10%)**
   - Contains target keyword? Length: 150-160 characters?
   - Includes call-to-action? Differentiating?

   **c. Heading Structure (weight: 15%)**
   - Single H1 containing target keyword?
   - Logical H2-H6 hierarchy (no skipped levels)?
   - Keywords naturally distributed across H2s?

   **d. Content Quality & Keyword Usage (weight: 20%)**
   - Word count adequate for topic? (compare to typical top-ranking content)
   - Keyword density: 1-2% for primary, 0.5-1% for secondary
   - Natural usage — no keyword stuffing
   - Semantic variations and related terms present?

   **e. Internal Linking (weight: 10%)**
   - Number of internal links (aim for 3-5 per 1,000 words)
   - Descriptive anchor text? Relevant destinations?
   - Links to/from pillar content?

   **f. Image Optimization (weight: 10%)**
   - All images have alt text? Alt text includes keywords where natural?
   - File names descriptive (not IMG_001.jpg)?

   **g. URL Structure (weight: 10%)**
   - Short, descriptive, contains keyword?
   - No unnecessary parameters or deep nesting?

   **h. Schema Markup (weight: 10%)**
   - Appropriate schema type for page? (Article, Product, FAQ, HowTo)
   - Required schema fields present?

3. **Calculate overall score** — Weighted average across 8 dimensions (1-100 scale).

4. **Generate fixes** — For each issue, provide:
   - What's wrong (current state)
   - Why it matters (SEO impact)
   - Rewritten/fixed version (ready to copy-paste)

5. **Human checkpoint** — Present score summary. Ask: "Want me to rewrite your title tag, meta description, and H1 with the fixes applied?"

6. **Generate output** — Markdown audit report with scores and fixes.

## Output Contract

### Output Format

| Output | Format | Contents |
|---|---|---|
| SEO audit report | Markdown | Scored audit with fixes per dimension |
| Quick fixes | Markdown | Top 5 copy-paste-ready fixes |

### Audit Report Structure

```markdown
# On-Page SEO Audit: [Page Title]
Target keyword: [keyword]
Overall Score: [X]/100 — [Rating: Poor/Fair/Good/Excellent]

## Score Card
| Dimension | Score | Status |
|---|---|---|
| Title Tag | 7/10 | ⚠️ Needs improvement |
| Meta Description | 4/10 | ❌ Critical |
| ... | ... | ... |

## Detailed Findings

### Title Tag — 7/10
**Current:** [current title]
**Issues:** Keyword not front-loaded. 72 characters (too long).
**Recommended:** [rewritten title, 58 chars]
**Impact:** Medium — better keyword position improves relevance signal.

[Repeat for each dimension]

## Priority Fix List
1. [Most impactful fix first]
2. ...
```

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| No HTML provided | User only described the page | Work with available info; note that HTML analysis would be more thorough |
| No target keyword | User forgot to specify | Ask: "What keyword should this page rank for?" |
| Very thin content (<200 words) | Thin page | Flag as critical issue; recommend minimum word count |
| Non-English content | Different language | Adjust character limits for title/meta; note analysis may be less precise |
| JavaScript-rendered content | SPA/React page | Note that search engines may see different content; recommend checking rendered HTML |
| Page is a PDF or non-HTML | Wrong format | Explain this skill works with HTML pages; suggest manual review |

## How to Get Your Data

### View Page Source (Any Browser)

1. Navigate to your page
2. Right-click → "View Page Source" (or Ctrl+U / Cmd+U)
3. Copy all HTML → paste into Claude

### Chrome DevTools

1. Open your page → F12 (DevTools)
2. Elements tab → right-click `<html>` → "Copy" → "Copy outerHTML"
3. Paste into Claude

### Content-Only Method (Easiest)

1. Open your page
2. Copy all visible content (Ctrl+A → Ctrl+C)
3. Paste into Claude with the URL and target keyword
4. Note: This misses meta tags and schema — Claude will note what couldn't be checked

## Example

**User prompt:** "Check the on-page SEO for my landing page targeting 'project management software'. Here's the HTML: [pastes HTML]"

**Claude responds:**

> ## On-Page SEO Audit: Best Project Management Software | Acme Tools
> **Target keyword:** project management software
> **Overall Score: 62/100 — Fair**
>
> | Dimension | Score | Status |
> |---|---|---|
> | Title Tag | 7/10 | ⚠️ Keyword not front-loaded |
> | Meta Description | 4/10 | ❌ Missing entirely |
> | Heading Structure | 8/10 | ✅ Good hierarchy |
> | Content & Keywords | 6/10 | ⚠️ Thin (480 words, aim for 1,500+) |
> | Internal Links | 3/10 | ❌ Only 1 internal link |
> | Images | 5/10 | ⚠️ 3 of 7 images missing alt text |
> | URL | 9/10 | ✅ Clean: /project-management-software |
> | Schema | 2/10 | ❌ No schema markup |
>
> **Top 3 fixes:**
> 1. **Add meta description:** "Compare the top project management software for 2026. Free trials, pricing, and features for teams of all sizes. Find your perfect PM tool →"
> 2. **Add 1,000+ words** of content covering features, pricing, and use cases
> 3. **Add SoftwareApplication schema** with ratings and pricing
>
> Want me to generate the rewritten elements?
