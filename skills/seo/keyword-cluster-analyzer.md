---
name: keyword-cluster-analyzer
description: >
  Cluster a list of keywords into topical groups based on search intent and semantic similarity.
  Use this skill whenever the user mentions keyword research, keyword grouping, content planning
  around keywords, topic clusters, SEO content strategy, keyword mapping, pillar-cluster models,
  keyword categorization, or organizing keywords by intent. Also trigger when the user has a
  keyword export from Ahrefs, SEMrush, Google Keyword Planner, or Moz and wants to make sense of it.
  Even if they just say "I have a bunch of keywords" or "help me organize these keywords", use this skill.
---

# Keyword Cluster Analyzer

Transforms a flat list of keywords into organized topical clusters, each with a primary keyword, search intent classification, and content recommendations. This is the entry point for any content-led SEO strategy.

## Granularity Check

> Can this be completed in a single Claude session? **Yes — expect ~5 min data prep → ~10 min Claude session → ~30-60 min implementation in Google Search Console / CMS.** If implementing output in a platform, add 10-20 min for setup. Input is a CSV, output is an XLSX with clusters. No external API calls needed — clustering is done via semantic similarity analysis.

## User Intent Mapping

This skill should trigger when the user says things like:

- "Group these keywords into topics" (direct command)
- "I exported keywords from Ahrefs, now what?" (tool-specific)
- "I have 200 keywords and don't know where to start" (problem statement)
- "Help me build topic clusters for my blog" (goal-oriented)
- "Which keywords should I target together?" (strategy question)
- "Organize my keyword list by search intent" (specific technique)
- "Create a pillar-cluster keyword map" (SEO framework)
- "I need to plan content around these keywords" (content planning)
- "Sort these keywords into informational vs commercial" (intent classification)
- "Which keywords are competing with each other?" (cannibalization concern)

## Input Contract

### Required Input

| Column | Type | Description | Example |
|---|---|---|---|
| `keyword` | string | The search term | `"best project management software"` |

### If You Don't Have This Data

- **No Search Console access?** Ask your web developer to grant you Viewer access, or use free tools like Ubersuggest for basic keyword data.
- **No keyword research?** Type your topic into Google and note the autocomplete suggestions + "People Also Ask" questions. That's free keyword research.
- **No competitor URLs?** Search your target keyword — the top 5 organic results are your SEO competitors.
- **No content inventory?** Export your sitemap (yoursite.com/sitemap.xml) or use Screaming Frog's free tier (500 URLs).

### Optional Input

| Column | Type | Default | Description |
|---|---|---|---|
| `search_volume` | integer | `0` | Monthly search volume |
| `difficulty` | float (0-100) | `null` | Keyword difficulty score |
| `cpc` | float | `null` | Cost per click in USD |
| `current_position` | integer | `null` | Current SERP ranking |

### Sample Input

```csv
keyword,search_volume,difficulty,cpc,current_position
best project management software,12100,45,3.20,
project management tools for small teams,2400,32,2.10,15
free project management app,6600,38,1.80,
agile project management software,1900,41,3.50,8
how to manage projects effectively,1600,22,0.90,
project management methodology comparison,880,28,1.20,
```

### Input Validation Rules

1. CSV must have a `keyword` column (case-insensitive)
2. Minimum 10 keywords for meaningful clustering (warn if fewer, proceed anyway)
3. Maximum 1,000 keywords per batch (recommend splitting if more)
4. Duplicate keywords are flagged and deduplicated
5. Empty keyword values are skipped with a warning

**If validation fails:** Tell the user exactly which rows/columns are invalid and provide a corrected sample row.

## Process

1. **Validate input** — Check CSV structure, deduplicate, flag issues. Report: "Found X keywords, Y duplicates removed, Z missing volumes."

2. **Classify search intent** — Categorize each keyword as one of:
   - **Informational** — "how to", "what is", "guide", "tutorial"
   - **Commercial Investigation** — "best", "top", "review", "comparison", "vs"
   - **Transactional** — "buy", "pricing", "discount", "free trial", "download"
   - **Navigational** — brand names, specific product names

3. **Cluster by semantic similarity** — Group keywords that target the same topic. Two keywords belong in the same cluster if a single piece of content could reasonably rank for both. Rules:
   - Cluster size: 3-15 keywords (split large clusters, flag tiny ones)
   - Each cluster gets a descriptive name based on the shared topic
   - Select the highest-volume keyword as the "primary keyword" per cluster

4. **Rank clusters** — Score each cluster by total search volume, average difficulty, and content opportunity (high volume + low difficulty = high opportunity).

5. **Human checkpoint** — Present the clusters in a summary table. Ask: "Do these groupings make sense? Should I merge or split any clusters before generating the full output?"

6. **Generate output** — Create XLSX with two sheets: Cluster Summary and Keyword Details.

7. **Add content recommendations** — For each cluster, suggest content type (blog post, landing page, comparison page, guide), target word count, and priority level.


> **Benchmark Context**: Average time to rank on page 1 for a new page is 3-6 months (Semrush 2024 State of Search). Long-tail keywords (3+ words) have 3-5% CTR vs (Ahrefs 2024 Search Traffic Study). 1-2% for head terms. The #1 organic result gets ~27.6% of clicks. Content updates on existing pages show ranking improvements within 2-4 weeks (Semrush 2024 State of Search). (Ahrefs 2024 Search Traffic Study)


### Confidence & Sample Size.
> **Confidence Note**: Results are only as reliable as your input data. Small datasets (<50 records or <30 days of data) produce directional insights, not statistically significant conclusions. Always note your sample size when sharing results with stakeholders. Recommendations should be validated with A/B testing or additional data before making major strategic changes.

## Output Contract

### Output Format

| Output | Format | Contents |
|---|---|---|
| Cluster analysis | Markdown tables | Two tables: summary + detail |
| Quick summary | Markdown | Top 5 clusters with recommendations |

### Table 1: Cluster Summary

| Column | Type | Description |
|---|---|---|
| `cluster_name` | string | Descriptive cluster topic |
| `primary_keyword` | string | Highest-volume keyword in cluster |
| `keyword_count` | integer | Number of keywords in cluster |
| `total_volume` | integer | Combined monthly search volume |
| `avg_difficulty` | float | Average difficulty score |
| `dominant_intent` | string | Most common intent in cluster |
| `content_type` | string | Recommended content format |
| `priority` | string | High / Medium / Low |

### Table 2: Keyword Details

| Column | Type | Description |
|---|---|---|
| `keyword` | string | Original keyword |
| `cluster_name` | string | Assigned cluster |
| `search_volume` | integer | Monthly volume |
| `difficulty` | float | Difficulty score |
| `intent` | string | Search intent classification |
| `is_primary` | boolean | Whether this is the cluster's primary keyword |

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
| Too few keywords (<10) | Small export | Warn but proceed; suggest user add more keywords |
| No volume data | Export didn't include volumes | Cluster by semantics only; note volume data would improve results |
| All keywords are identical intent | Very narrow niche | Note the pattern; suggest broadening keyword research |
| Unclear cluster boundaries | Ambiguous topics | Present options to the user and ask for guidance |
| CSV encoding issues | Non-UTF8 export | Attempt to detect encoding; ask user to re-export as UTF-8 |
| Extremely broad keywords mixed with long-tail | Diverse list | Create a "broad terms" cluster and flag for manual review |

## How to Get Your Data

### From Google Keyword Planner

1. Go to Google Ads → Tools → Keyword Planner
2. Click "Discover new keywords" or "Get search volume and forecasts"
3. Enter your seed keywords or URL
4. Click "Download keyword ideas" → CSV
5. Upload the CSV when prompted

### From Ahrefs

1. Go to Keywords Explorer → enter seed keyword
2. Click "Matching terms" or "Related terms"
3. Apply any filters (volume, difficulty)
4. Click "Export" → CSV
5. Upload the CSV when prompted

### From SEMrush

1. Go to Keyword Magic Tool → enter seed keyword
2. Apply filters as needed
3. Click "Export" → CSV
4. Upload the CSV when prompted

## Example

**User prompt:** "I exported 30 keywords from Ahrefs for project management software. Can you group them into topic clusters?"

**Claude processes the CSV and responds with:**

> Found 30 keywords, 0 duplicates. Here are 6 clusters I identified:
>
> | Cluster | Primary Keyword | Keywords | Total Volume | Priority |
> |---|---|---|---|---|
> | PM Software Reviews | best project management software | 8 | 24,500 | High |
> | Small Team Solutions | project management tools for small teams | 5 | 6,200 | High |
> | Free PM Tools | free project management app | 4 | 9,100 | Medium |
> | Agile PM | agile project management software | 5 | 5,800 | Medium |
> | PM Methodology | project management methodology comparison | 4 | 3,200 | Low |
> | PM Best Practices | how to manage projects effectively | 4 | 2,900 | Low |
>
> Do these groupings look right? I'd recommend starting with "PM Software Reviews" (highest volume, commercial intent) as a pillar page, with the others as supporting content.

**Then generates XLSX with both sheets for download.**

## Related Skills

- **[SEO Content Strategy](./seo-content-strategy.md)** — Use after clustering keywords to build your content strategy around the clusters you've identified.
- **[Content Brief Generator](../content/content-brief-writer.md)** — Use to create SEO-optimized briefs for each cluster's primary keyword and content type.
- **[Content Pillar Strategy](../content/content-pillar-strategy.md)** — Use to structure your clusters into a pillar-cluster content architecture.
- **[SEO Competitor Analysis](./seo-competitor-analysis.md)** — Use alongside clustering to identify competitor keywords and gaps in your cluster strategy.
