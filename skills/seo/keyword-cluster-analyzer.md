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

> Can this be completed in a single 10-minute Claude session? **Yes.** Input is a CSV, output is an XLSX with clusters. No external API calls needed — clustering is done via semantic similarity analysis.

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

## Output Contract

### Output Format

| Output | Format | Contents |
|---|---|---|
| Cluster analysis | XLSX | Two sheets: summary + detail |
| Quick summary | Markdown | Top 5 clusters with recommendations |

### Sheet 1: Cluster Summary

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

### Sheet 2: Keyword Details

| Column | Type | Description |
|---|---|---|
| `keyword` | string | Original keyword |
| `cluster_name` | string | Assigned cluster |
| `search_volume` | integer | Monthly volume |
| `difficulty` | float | Difficulty score |
| `intent` | string | Search intent classification |
| `is_primary` | boolean | Whether this is the cluster's primary keyword |

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
