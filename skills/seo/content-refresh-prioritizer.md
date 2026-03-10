---
name: content-refresh-prioritizer
description: >
  Prioritize which existing content to update first for maximum SEO impact. Use this skill whenever
  the user mentions content refresh, content update priority, declining traffic, ranking decay,
  content decay analysis, stale content, outdated blog posts, "which pages should I update first",
  content maintenance, re-optimization, evergreen content refresh, content audit for updates,
  or says things like "my traffic is declining on old posts" or "I need to update my blog" or
  "which content should I refresh". Also trigger on "content pruning", "thin content audit",
  or "consolidate old posts".
---

# Content Refresh Prioritizer

Analyze existing content performance data to identify which pages to update, consolidate, or retire — ranked by potential traffic recovery and effort.

## Granularity Check

> Can this be completed in a single Claude session? **Yes — expect ~5 min data prep + ~10 min Claude session.** If implementing output in a platform, add 10-20 min for setup. Input is a CSV of pages with performance metrics. Output is a prioritized XLSX action list. No crawling required.

## User Intent Mapping

Trigger when the user says:

- "Which blog posts should I update first?" (prioritization)
- "My organic traffic has been declining on old content" (problem statement)
- "I have 200 blog posts and don't know which to refresh" (overwhelmed)
- "Help me prioritize a content refresh sprint" (project planning)
- "Which pages are losing rankings?" (diagnostic)
- "Should I update, merge, or delete these old posts?" (decision-making)
- "I exported my Google Search Console data, help me find decaying pages" (tool-specific)
- "Do a content decay analysis" (specific technique)
- "Find my best candidates for content refreshes" (opportunity finding)
- "I need a content maintenance plan for Q2" (strategic planning)

## Input Contract

### Required Input

| Column | Type | Description | Example |
|---|---|---|---|
| `url` or `page` | string | Page URL or title | `/blog/project-management-tips` |

### Recommended Input (significantly improves analysis)

| Column | Type | Description | Example |
|---|---|---|---|
| `clicks` or `sessions` | integer | Recent period traffic | `450` |
| `clicks_previous` or `sessions_previous` | integer | Prior period traffic | `890` |
| `impressions` | integer | Search impressions | `12000` |
| `avg_position` | float | Average SERP position | `8.4` |
| `ctr` | float | Click-through rate | `0.038` |
| `publish_date` or `last_modified` | date | When published/updated | `2024-03-15` |
| `word_count` | integer | Content length | `1200` |
| `target_keyword` | string | Primary keyword | `project management tips` |

### Sample Input

```csv
url,clicks,clicks_previous,impressions,avg_position,publish_date,word_count,target_keyword
/blog/pm-software-guide,890,1450,24000,6.2,2023-06-01,2800,project management software
/blog/agile-methodology,340,320,8500,12.1,2024-01-15,1500,agile methodology
/blog/gantt-charts-101,120,580,6200,15.8,2022-09-10,900,gantt chart
/blog/remote-team-tips,650,640,14000,4.3,2024-09-01,2200,remote team management
/blog/waterfall-vs-agile,45,290,3800,22.4,2021-11-20,700,waterfall vs agile
```

### Input Validation Rules

1. URL or page identifier is required
2. At least one traffic metric (clicks, sessions, or impressions) recommended
3. Two periods of data enables trend analysis — warn if only one period
4. Dates help calculate content age — estimate if missing
5. Flag pages with zero traffic in both periods (candidates for removal)

### If You Don't Have This Data

- **No Search Console access?** Ask your web developer to grant you Viewer access, or use free tools like Ubersuggest for basic keyword data.
- **No keyword research?** Type your topic into Google and note the autocomplete suggestions + "People Also Ask" questions. That's free keyword research.
- **No competitor URLs?** Search your target keyword — the top 5 organic results are your SEO competitors.
- **No content inventory?** Export your sitemap (yoursite.com/sitemap.xml) or use Screaming Frog's free tier (500 URLs).

## Process

1. **Validate and normalize input** — Identify available columns, handle missing data. Report: "Analyzing X pages. Traffic trend data: [available/unavailable]. Date data: [available/unavailable]."

2. **Calculate decay signals** — For each page:
   - **Traffic change %** = (current - previous) / previous × 100
   - **Position trend** = current position vs expected (page 1 = good, declining = bad)
   - **Content age** = months since publish/last update
   - **CTR gap** = actual CTR vs expected CTR for position (position 1 ≈ 28%, position 5 ≈ 6%)
   - **Impressions-to-clicks ratio** = high impressions + low clicks = CTR opportunity

3. **Classify each page** — Assign one action:
   - **🔄 Refresh** — Declining traffic but still has search impressions. Update content, refresh stats, add new sections. (Most common.)
   - **📈 Expand** — Ranking on page 2 (positions 8-20) with decent impressions. Add depth to push to page 1.
   - **🔀 Consolidate** — Thin content (<500 words) or duplicate topics. Merge with a stronger page via 301 redirect.
   - **🗑️ Retire** — Zero traffic, zero impressions, no backlinks, outdated topic. 301 to relevant page or noindex.
   - **✅ Maintain** — Performing well. No action needed. Monitor.
   - **⚡ Quick win** — High impressions, low CTR. Just needs a better title/meta description.

4. **Score refresh priority** — Priority score formula:
   ```
   priority = (traffic_decline_severity × 0.3) + (search_volume_potential × 0.3) + (ease_of_update × 0.2) + (content_age_penalty × 0.2)
   ```

5. **Human checkpoint** — Show top 10 refresh candidates. Ask: "Do these priorities make sense? Any pages you want to keep as-is or definitely remove?"

6. **Generate output** — XLSX with prioritized action list + Markdown summary.


> **Benchmark Context**: Average time to rank on page 1 for a new page is 3-6 months. Long-tail keywords (3+ words) have 3-5% CTR vs. 1-2% for head terms. The #1 organic result gets ~27.6% of clicks. Content updates on existing pages show ranking improvements within 2-4 weeks.


### Confidence & Sample Size
> **Confidence Note**: Results are only as reliable as your input data. Small datasets (<50 records or <30 days of data) produce directional insights, not statistically significant conclusions. Always note your sample size when sharing results with stakeholders. Recommendations should be validated with A/B testing or additional data before making major strategic changes.

## Output Contract

### Output Format

| Output | Format | Contents |
|---|---|---|
| Refresh plan | XLSX | Two sheets: priority list + detail |
| Executive summary | Markdown | Top 10 actions with rationale |

### Sheet 1: Priority Action List

| Column | Type | Description |
|---|---|---|
| `priority_rank` | integer | 1 = highest priority |
| `url` | string | Page URL |
| `action` | string | Refresh / Expand / Consolidate / Retire / Quick win |
| `priority_score` | float | Weighted priority (0-100) |
| `traffic_change_pct` | float | Period-over-period change |
| `current_traffic` | integer | Current period clicks/sessions |
| `potential_traffic` | integer | Estimated traffic if improved |
| `effort_level` | string | Low / Medium / High |
| `specific_tasks` | string | What to do (comma-separated) |

### Sheet 2: Full Detail

All input columns plus calculated metrics (decay rate, CTR gap, content age, action classification).

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
| No trend data | Only one period of metrics | Prioritize by content age + current position instead |
| All pages declining | Sitewide issue | Flag potential algorithm update or technical SEO problem |
| Very few pages (<10) | Small site | Proceed but note small sample; every page matters more |
| No traffic data at all | Only have page list | Estimate based on content age and word count; recommend getting GSC data |
| Mixed metrics (some pages have data, others don't) | Incomplete export | Analyze what's available; flag pages with missing data separately |

## How to Get Your Data

### From Google Search Console

1. Go to Search Console → Performance → Pages
2. Set date comparison: Last 3 months vs Previous 3 months
3. Click "Export" → CSV (or Google Sheets → download as CSV)
4. Upload to Claude

### From Google Analytics 4

1. Go to GA4 → Reports → Engagement → Pages and screens
2. Set comparison period (e.g., Jan-Mar 2026 vs Oct-Dec 2025)
3. Export → CSV
4. Upload to Claude

### From Ahrefs Site Audit

1. Go to Site Explorer → your domain → Top Pages
2. Set "Compare" to previous period
3. Export → CSV with traffic change data
4. Upload to Claude

### Manual Method

1. List all your published content URLs
2. For each, note: publish date, approximate traffic (from GA), target keyword
3. Provide list to Claude — analysis will focus on age and content quality signals

## Example

**User prompt:** "I exported 50 blog posts from Google Search Console. Traffic is down overall. Help me figure out which posts to refresh first."

**Claude responds:**

> Analyzed 50 pages. Here's the breakdown:
>
> | Action | Pages | Combined Traffic Impact |
> |---|---|---|
> | 🔄 Refresh (content updates needed) | 18 | Recover ~4,200 clicks/month |
> | 📈 Expand (push to page 1) | 8 | Gain ~2,100 clicks/month |
> | ⚡ Quick win (title/meta only) | 6 | Gain ~900 clicks/month |
> | 🔀 Consolidate (merge thin posts) | 9 | Redirect equity to stronger pages |
> | 🗑️ Retire (no value) | 4 | Clean up index bloat |
> | ✅ Maintain (performing well) | 5 | No action needed |
>
> **Top 5 refresh priorities:**
> 1. `/blog/pm-software-guide` — Down 39%, still 890 clicks. Refresh stats, add 2024 tools. Est. recovery: +560 clicks/mo.
> 2. `/blog/gantt-charts-101` — Down 79%, thin (900 words). Expand to 2,000+ words. Est. recovery: +460 clicks/mo.
> 3. `/blog/waterfall-vs-agile` — Down 84%, position 22. Major rewrite needed. Est. recovery: +245 clicks/mo.
>
> Want me to generate the full XLSX with all 50 pages prioritized?
