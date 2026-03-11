---
name: seo-content-strategy
description: >
  Build an SEO content strategy — topic clusters, content calendars, and keyword-to-content mapping.
  Use this skill when the user says "SEO content strategy", "topic cluster strategy", "pillar page
  planning", "content hub design", "keyword-to-content mapping", "editorial SEO calendar", "topical
  authority strategy", "SEO blog strategy", "content cluster architecture", "hub and spoke content",
  or "semantic SEO strategy". Also trigger for content prioritization by SEO potential, search intent
  content mapping, or content-led SEO growth planning.
---

# SEO Content Strategy

Builds a comprehensive SEO content strategy with topic clusters, pillar pages, keyword-to-content mapping, search intent alignment, and a prioritized editorial calendar for organic growth.

## Granularity Check

> **Time**: ~5 min data prep → ~10 min Claude session → ~45-90 min writing in your CMS. If implementing, add 2-4 hours/week for content production. Input is keyword data and business goals. Output is Markdown content strategy with editorial calendar.

## User Intent Mapping

- "Build an SEO content strategy for our blog" (full strategy)
- "How do we structure topic clusters?" (architecture)
- "Create a pillar page plan" (pillar pages)
- "Map our keywords to content" (mapping)
- "SEO editorial calendar for Q2" (calendar)
- "Which content should we write first for maximum SEO impact?" (prioritization)
- "Build topical authority in our niche" (authority)
- "Our blog traffic plateaued" (growth diagnosis)
- "Search intent mapping for our keywords" (intent)
- "Content hub design for [topic]" (hub design)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Business/Niche | Text | What you do, your expertise area |
| Target Keywords | Text/CSV | Seed keywords or keyword research export |
| Goal | Text | Traffic growth, lead generation, brand authority, or specific ranking targets |

### If You Don't Have This Data

- **No keyword research?** Tell Claude your business and target audience. Claude generates seed keyword lists and suggests topic clusters from industry patterns.
- **No content inventory?** Claude designs the strategy from scratch. If you have existing content, export blog post titles and URLs for gap analysis.
- **No competitor data?** Claude identifies content opportunities from keyword research alone. For competitive edge, note what topics top competitors cover heavily.
- **No traffic data?** Start publishing and track with Google Search Console. Claude prioritizes content by keyword difficulty and business value instead.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Existing Content | CSV | Current blog posts, pages, and their topics |
| Keyword Research | CSV | Full keyword research with volume and difficulty |
| Competitor Content | Text | What competitors publish and their top posts |
| Content Resources | Text | Writers, publishing frequency capacity |
| Buyer Journey | Text | How your audience moves from awareness to purchase |

## Process

### Step 1: Topic Cluster Identification
- Group keywords into thematic clusters (semantic relationships)
- Identify 3-5 pillar topics (broad, high-volume, competitive)
- Map 10-20 cluster topics per pillar (specific, lower competition)
- Ensure clusters align with business value and expertise
- Validate cluster structure against competitor coverage

### Step 2: Search Intent Mapping
Map every keyword to search intent:
| Intent | Signal Words | Content Type | Conversion Proximity |
|---|---|---|---|
| Informational | how, what, why, guide | Blog post, guide | Low (top of funnel) |
| Navigational | brand name, product name | Landing page | Medium |
| Commercial | best, review, comparison, vs | Comparison post, review | High |
| Transactional | buy, pricing, signup, demo | Product/pricing page | Highest |

### Step 3: Pillar Page Design
- Comprehensive guide (2,000-5,000 words) covering the broad topic
- Table of contents with jump links
- Internal links to all cluster content pieces
- Regular updates to maintain freshness
- Multiple content formats (text, images, video, downloadable resources)

### Step 4: Content Prioritization
Score each content piece on:
- **Business value** (1-5): how closely it relates to your product/service
- **Search volume** (1-5): monthly search demand
- **Keyword difficulty** (1-5, inverted): lower difficulty = higher score
- **Content gap** (1-5): how underserved the topic is by competitors
- Priority score = Business Value × 2 + Volume + (6 - Difficulty) + Gap

### Step 5: Editorial Calendar
- Publishing frequency recommendation based on resources
- Content mix: 60% cluster content, 20% pillar content, 20% trending/news
- Internal linking plan: every new post links to pillar + 2-3 related clusters
- Content update schedule for existing posts (quarterly review)

### Step 6: Content Production Guidelines
- Word count targets by content type and competition
- On-page SEO checklist per post
- Internal linking requirements
- Image and multimedia requirements
- Content brief template for writers

### Confidence & Sample Size
> **Confidence Note**: SEO content strategy requires 6-12 months to see full results. Publish at least 20 pieces in a cluster before evaluating topical authority impact. Keyword difficulty scores are estimates — easier-than-expected wins and harder-than-expected battles are normal. Revisit and adjust the strategy quarterly based on actual performance data.

### ⚠️ Human Checkpoint
> Review topic clusters for brand relevance — not every high-volume keyword is worth targeting. Verify content accuracy with subject matter experts. Ensure content meets E-E-A-T standards (Experience, Expertise, Authoritativeness, Trustworthiness) for your industry.

> **Benchmark Context**: See BrightEdge 2024 Organic Search Report, and Ahrefs 2024 Search Traffic Study for current industry benchmarks relevant to this analysis.
## Output Contract

### Deliverable: Markdown Content Strategy

```markdown
# SEO Content Strategy: [Brand]

## Topic Cluster Architecture
### Pillar 1: [Topic]
- Pillar page: [title and target keyword]
- Cluster content:
  1. [Title] — [keyword, volume, KD]

## Search Intent Map
| Keyword | Intent | Content Type | Funnel Stage |
|---|---|---|---|

## Content Prioritization
| Title | Keyword | Priority Score | Business Value | Effort |
|---|---|---|---|---|

## Editorial Calendar
| Week | Title | Cluster | Keyword | Writer | Status |
|---|---|---|---|---|---|

## Content Brief Template
- Target keyword: [keyword]
- Search intent: [type]
- Word count: [range]
- Outline: [H2s]
- Internal links: [targets]

## Measurement Plan
| Metric | Target | Review Cadence |
|---|---|---|
```

## Platform Implementation Steps

### Content Management
1. Create a content calendar in your CMS or project management tool
2. Build content brief templates for writers (keyword, intent, outline, links)
3. Set up editorial workflow: brief → draft → review → optimize → publish
4. Schedule content updates for existing posts (quarterly review queue)

### SEO Tools
1. Use Semrush/Ahrefs Topic Research for cluster ideation
2. Track keyword rankings per content piece weekly
3. Monitor GSC for content performance (impressions, clicks, CTR)
4. Use Clearscope or SurferSEO for content optimization scoring

### Internal Linking
1. Build a cluster-to-pillar link map (spreadsheet or tool)
2. Add internal links to every new post at publication time
3. Retroactively add links from old posts to new cluster content
4. Audit internal links quarterly for broken links and new opportunities

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Content not ranking after 6 months | Targeting keywords too competitive for current authority | Pivot to lower-difficulty keywords; build more cluster content |
| High traffic, low conversions | Too much informational content, not enough commercial | Rebalance mix toward commercial intent; add CTAs to informational posts |
| Writer output doesn't match SEO needs | Briefs not detailed enough | Create structured briefs with exact H2s, keywords, and competitor analysis |
| Pillar page underperforms | Too broad or not comprehensive enough | Expand depth; add more internal links from cluster content |

## How to Get Your Data

- **Keyword research**: Semrush/Ahrefs → Keyword Explorer → export keyword list
- **Content inventory**: CMS export of all published URLs and titles
- **Competitor content**: Ahrefs → Site Explorer → Top Pages (by organic traffic)
- **No tools**: Describe your niche — Claude generates a seed keyword list and cluster structure

## Example

**Input**: "SEO content strategy for a cybersecurity SaaS company. Target: IT managers and CISOs. Current blog has 30 posts with ~5K organic visits/month. Goal: 25K organic visits/month within 12 months."

**Output**: 4 topic clusters identified: (1) Endpoint Security (pillar: "Complete Guide to Endpoint Security" — 12 cluster posts), (2) Cloud Security (pillar: "Cloud Security Best Practices" — 10 cluster posts), (3) Compliance (pillar: "Cybersecurity Compliance Guide" — 8 cluster posts), (4) Threat Intelligence (pillar: "Threat Intelligence for Business" — 6 cluster posts). Prioritization: Compliance cluster first (highest commercial intent, lowest competition — KD 25-35). Content mix: 3 posts/week — 2 cluster posts + 1 trending security news analysis. Editorial calendar: Q1 — Compliance pillar + 8 cluster posts; Q2 — Endpoint Security pillar + 6 clusters; Q3-Q4 — Cloud Security + Threat Intelligence. Quick wins: update 10 existing posts with current year data and internal links to new cluster content (expected 40% traffic lift on updated posts). Projected growth: 5K → 12K by month 6, 25K by month 12 at 3 posts/week cadence.

## Related Skills

- **[Keyword Cluster Analyzer](./keyword-cluster-analyzer.md)** — Use first to organize keywords into topic clusters that form the foundation of your content strategy.
- **[Content Pillar Strategy](../content/content-pillar-strategy.md)** — Use to design the pillar-cluster architecture that your SEO content strategy will follow.
- **[Editorial Calendar Builder](../content/editorial-calendar-builder.md)** — Use to translate your SEO content strategy into a month-by-month publishing calendar.
- **[SEO Competitor Analysis](./seo-competitor-analysis.md)** — Use to inform your strategy with competitive insights before finalizing your content roadmap.
