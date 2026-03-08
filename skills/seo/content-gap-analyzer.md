---
name: content-gap-analyzer
description: >
  Find content gaps by comparing your site's content against competitors. Use this skill whenever
  someone mentions content gap analysis, competitor content comparison, topic gaps, keyword gaps,
  missing content opportunities, content audit vs competitors, "what are my competitors writing about
  that I'm not", content whitespace, competitive content analysis, or wants to find topics they
  should be covering but aren't. Also trigger when the user has a list of competitor URLs and wants
  to identify missing opportunities, or says "what content am I missing" or "where are my content gaps".
---

# Content Gap Analyzer

Compare your content coverage against 3-5 competitors to find topics, keywords, and content formats you're missing. Outputs a prioritized gap report with actionable recommendations.

## Granularity Check

> Can this be completed in a single 10-minute Claude session? **Yes.** Input is competitor URLs or keyword lists. Output is an XLSX gap analysis. No crawling needed — analysis is based on user-provided data or manual research summaries.

## User Intent Mapping

Trigger when the user says:

- "What content are my competitors publishing that I'm not?" (direct gap question)
- "Find content opportunities I'm missing" (opportunity discovery)
- "Compare my blog topics against [competitor]" (competitive comparison)
- "I exported keywords from Ahrefs content gap tool" (tool-specific)
- "Where should I focus my content strategy next quarter?" (strategic planning)
- "Which topics are my competitors ranking for that I'm not?" (keyword gap)
- "Do a content audit vs our competitors" (audit request)
- "I need fresh content ideas based on competitor research" (ideation)
- "Help me find low-competition topics in my niche" (opportunity finding)
- "What are the gaps in my content library?" (self-assessment)

## Input Contract

### Option A: Competitor Keyword Data (Preferred)

| Column | Type | Required | Description |
|---|---|---|---|
| `keyword` | string | Yes | The search term |
| `your_position` | integer | No | Your current ranking (blank = not ranking) |
| `competitor_1_position` | integer | No | Competitor 1 ranking |
| `competitor_2_position` | integer | No | Competitor 2 ranking |
| `search_volume` | integer | No | Monthly search volume |
| `difficulty` | float | No | Keyword difficulty (0-100) |

### Option B: Topic/URL Comparison

Provide:
- Your sitemap or list of published URLs/topics
- 3-5 competitor sitemaps or published URL lists
- Industry/niche context

### Sample Input (Option A)

```csv
keyword,your_position,competitor_1_position,competitor_2_position,search_volume,difficulty
project management software,5,2,3,12100,65
agile vs waterfall,,8,1,4400,35
kanban board best practices,,15,4,2900,28
remote team management tools,22,,6,3600,42
sprint planning template,,3,,1900,18
```

### Input Validation Rules

1. Minimum 20 keywords for meaningful gap analysis (warn if fewer)
2. At least 1 competitor column required
3. Keywords with no position data for anyone are flagged as "uncontested topics"
4. Duplicate keywords are deduplicated with a warning

**If validation fails:** Specify which columns are missing and provide a corrected sample row.

## Process

1. **Validate input** — Check structure, identify competitor columns, report: "Analyzing X keywords across Y competitors."

2. **Classify gaps** — Categorize each keyword into:
   - **Blind spot** — Competitors rank, you don't rank at all (highest priority)
   - **Losing** — You rank but competitors rank significantly higher (positions 1-3 vs your 10+)
   - **Weak** — You rank but below competitors (within striking distance)
   - **Winning** — You outrank all competitors (defend these)
   - **Uncontested** — Nobody ranks well (potential first-mover opportunity)

3. **Score opportunities** — For each gap, calculate:
   - Opportunity score = (search_volume × gap_severity) / difficulty
   - Where gap_severity: blind_spot=3, losing=2, weak=1

4. **Cluster gaps by topic** — Group related gaps into content themes (reuse clustering logic from keyword-cluster-analyzer if chaining).

5. **Human checkpoint** — Present top 10 gaps with scores. Ask: "Do these priorities align with your business goals? Any topics to exclude?"

6. **Generate output** — Create XLSX with three sheets: Gap Summary, Keyword Details, and Action Plan.

7. **Recommend content formats** — For each gap cluster, suggest format (blog, landing page, comparison, guide, tool) based on intent and competitor approach.

## Output Contract

### Output Format

| Output | Format | Contents |
|---|---|---|
| Gap analysis | XLSX | Three sheets: summary, details, action plan |
| Quick wins | Markdown | Top 5 immediate opportunities |

### Sheet 1: Gap Summary

| Column | Type | Description |
|---|---|---|
| `topic_cluster` | string | Grouped gap theme |
| `gap_type` | string | Blind spot / Losing / Weak / Uncontested |
| `keyword_count` | integer | Keywords in this gap |
| `total_volume` | integer | Combined search volume |
| `avg_difficulty` | float | Average difficulty |
| `opportunity_score` | float | Weighted priority score |
| `recommended_format` | string | Blog / Landing page / Guide / etc. |
| `effort_estimate` | string | Low / Medium / High |

### Sheet 2: Keyword Details

| Column | Type | Description |
|---|---|---|
| `keyword` | string | The search term |
| `gap_type` | string | Classification |
| `your_position` | integer | Current ranking |
| `best_competitor_position` | integer | Highest competitor ranking |
| `search_volume` | integer | Monthly volume |
| `opportunity_score` | float | Priority score |
| `topic_cluster` | string | Assigned gap cluster |

### Sheet 3: Action Plan

| Column | Type | Description |
|---|---|---|
| `priority` | integer | 1 = highest |
| `topic_cluster` | string | Gap theme |
| `recommended_action` | string | Create / Update / Expand |
| `content_format` | string | Suggested format |
| `target_keywords` | string | Primary + secondary keywords |
| `estimated_monthly_traffic` | integer | Potential traffic if ranking top 5 |
| `notes` | string | Strategic context |

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| No competitor data | User only provided their keywords | Ask for competitor URLs or suggest using Ahrefs/SEMrush content gap tool |
| All keywords are blind spots | Very new site | Prioritize by difficulty (easiest first); suggest building topical authority |
| Competitors rank for irrelevant terms | Different business model | Ask user to filter by relevance; add exclusion list |
| Too few keywords (<20) | Small export | Proceed but warn results may miss patterns |
| No search volume data | Export missing volumes | Rank by gap type only; note that volume data would improve prioritization |

## How to Get Your Data

### From Ahrefs Content Gap Tool

1. Go to Ahrefs → Site Explorer → Content Gap
2. Enter your domain in "But the following target doesn't rank for"
3. Enter 2-4 competitor domains in "Show keywords that the following rank for"
4. Apply filters (volume > 100 recommended)
5. Export → CSV → Upload to Claude

### From SEMrush Keyword Gap

1. Go to SEMrush → Keyword Gap
2. Enter your domain + up to 4 competitors
3. Select "Missing" or "Weak" tab
4. Export → CSV → Upload

### Manual Method (No Tools)

1. List your top 20 published pages/topics
2. List each competitor's top 20 pages/topics (check their blog sitemap)
3. Provide both lists to Claude with your industry context

## Example

**User prompt:** "I exported 50 keywords from Ahrefs content gap. My competitors are HubSpot and Monday.com, and they rank for keywords I don't. Help me find the best opportunities."

**Claude responds:**

> Analyzed 50 keywords across 2 competitors. Here's what I found:
>
> | Gap Type | Count | Total Volume |
> |---|---|---|
> | Blind spots (they rank, you don't) | 22 | 48,600 |
> | Losing (they outrank you significantly) | 12 | 31,200 |
> | Weak (close but behind) | 8 | 15,400 |
> | Uncontested (nobody ranks well) | 8 | 9,200 |
>
> **Top 3 quick wins:**
> 1. "sprint planning template" — Vol: 1,900, Diff: 18, both competitors rank top 5. Create a template + guide.
> 2. "kanban board best practices" — Vol: 2,900, Diff: 28. Format as a definitive guide.
> 3. "agile vs waterfall" — Vol: 4,400, Diff: 35. Comparison post with clear recommendation.
>
> Should I generate the full XLSX with all gaps and an action plan?

**Then generates XLSX with three sheets.**
