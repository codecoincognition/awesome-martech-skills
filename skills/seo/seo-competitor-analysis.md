---
name: seo-competitor-analysis
description: >
  Analyze competitor SEO strategies — keyword overlap, content gaps, backlink comparison, and ranking opportunities.
  Use this skill when the user says "SEO competitor analysis", "competitor keyword analysis",
  "SEO competitive landscape", "who's outranking us", "competitor content analysis", "SEO market
  share analysis", "share of voice SEO", "competitor ranking comparison", "SEO battlecard",
  "keyword overlap analysis", or "competitive SEO audit". Also trigger for organic traffic
  comparison, competitor SERP strategy, or SEO market positioning.
---

# SEO Competitor Analysis

Comprehensive competitor SEO analysis — keyword overlap, content gaps, backlink comparison, SERP positioning, and actionable strategies to outrank competitors.

## Granularity Check

> **Session time**: ~5 min data prep + ~10 min Claude session. If implementing strategy, add 4-10 hours for content and link building. Input is SEO tool exports for you and competitors. Output is Markdown competitive analysis with attack plan.

## User Intent Mapping

- "Who's outranking us and why?" (diagnosis)
- "SEO competitor analysis for our market" (landscape)
- "Which keywords do competitors rank for that we don't?" (gaps)
- "Compare our SEO to competitor X" (head-to-head)
- "SEO share of voice analysis" (market share)
- "Competitor content strategy analysis" (content)
- "Why does competitor X rank higher?" (specific diagnosis)
- "SEO opportunities competitors are missing" (opportunities)
- "Competitor backlink comparison" (links)
- "SEO market positioning" (strategy)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Your Domain | Text | Your website domain |
| Competitor Domains | Text list | 3-5 competitor domains |
| Target Keywords | Text list | Core keywords for your business |

### If You Don't Have This Data

- **Don't know your competitors?** Tell Claude your industry and product. Google your top 5 keywords — the sites that consistently appear are your SEO competitors (not always your business competitors).
- **No SEO tool?** Use free versions: Ubersuggest (3 free searches/day), Google Search Console (your data), or Ahrefs Webmaster Tools (your backlinks). Claude can work with manual SERP observations.
- **No keyword data?** Claude identifies competitor keywords from their content and site structure analysis.
- **No backlink data?** Claude focuses on content and keyword strategy. Add backlink analysis when you get tool access.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Keyword Rankings | CSV | Your rankings vs. competitor rankings |
| Organic Traffic Estimates | Text | Ahrefs/Semrush traffic estimates per competitor |
| Competitor Content | Text | Notable content pieces or strategies |
| Backlink Data | CSV | Referring domains comparison |
| Business Context | Text | How you differentiate from competitors |

## Process

### Step 1: Competitive Landscape Mapping
- Identify true SEO competitors (may differ from business competitors)
- Organic traffic comparison (estimated monthly organic visits)
- Domain authority / domain rating comparison
- Total keyword portfolio size per competitor
- Organic traffic trend (growing, stable, declining)

### Step 2: Keyword Gap Analysis
- Keywords competitors rank for that you don't (opportunity gap)
- Keywords where competitors outrank you (competitive gap)
- Shared keywords with different rankings (improvement gap)
- Long-tail keywords competitors haven't targeted (white space)

### Step 3: Content Strategy Analysis
- Content types that rank (blog, product pages, tools, guides)
- Content depth and format comparison
- Publishing frequency and content freshness
- Top-performing content by traffic and backlinks
- Content cluster / topic authority assessment

### Step 4: Backlink Comparison
- Referring domains count and quality comparison
- Link acquisition velocity per competitor
- Common linking domains (who links to everyone)
- Unique linking domains (competitive advantages)
- Link building tactics competitors use

### Step 5: SERP Positioning Analysis
- SERP feature ownership per competitor (snippets, PAA, rich results)
- Brand SERP comparison
- Local vs. national ranking differences
- Mobile vs. desktop ranking variations

### Step 6: Attack Strategy
- Quick wins: keywords where small improvements yield big results
- Content opportunities: topics competitors haven't covered well
- Link targets: sites linking to competitors but not you
- Technical advantages: speed, UX, schema opportunities
- Differentiation: content angles competitors can't replicate

### Confidence & Sample Size
> **Confidence Note**: Third-party traffic estimates (Ahrefs, Semrush) can be 30-50% off from actual traffic — use for relative comparison, not absolute numbers. Keyword difficulty scores vary between tools. Competitor strategies should inform, not dictate, your approach — copying competitors leads to parity, not advantage.

### ⚠️ Human Checkpoint
> Verify competitor identification with the business team — SEO competitors may not be business competitors. Review attack strategy for feasibility given your resources (team size, content budget, link building capacity).

> **Benchmark Context**: The top 3 organic results get 68% of all clicks. A 10-position improvement (e.g., #15 to #5) can increase traffic 10x. Sites with more content covering a topic cluster rank higher for all related terms. Competitor analysis should be repeated quarterly as the landscape shifts.

## Output Contract

### Deliverable: Markdown Competitive Analysis

```markdown
# SEO Competitor Analysis: [Your Domain]

## Competitive Landscape
| Competitor | Est. Traffic | DR/DA | Total Keywords | Trend |
|---|---|---|---|---|

## Keyword Gap Analysis
| Keyword | Volume | Your Rank | Best Competitor Rank | Opportunity |
|---|---|---|---|---|

## Content Strategy Comparison
| Competitor | Content Types | Publishing Freq | Top Content Topics |
|---|---|---|---|

## Backlink Comparison
| Metric | You | Comp 1 | Comp 2 | Comp 3 |
|---|---|---|---|---|

## Attack Strategy
### Quick Wins (< 2 weeks)
1. [Action] — [expected result]

### Medium-Term (1-3 months)
1. [Action] — [expected result]

### Long-Term (3-6 months)
1. [Action] — [expected result]

## Content Hit List
| Topic | Competitor Gaps | Format | Priority |
|---|---|---|---|
```

## Platform Implementation Steps

### Semrush
1. Domain Overview → enter each competitor → compare organic metrics
2. Keyword Gap → enter your domain + competitors → find missing keywords
3. Organic Research → Competitors tab → discover new SEO competitors
4. Backlink Gap → compare referring domain profiles

### Ahrefs
1. Site Explorer → Competing Domains → identify keyword overlap
2. Content Gap → find keywords competitors rank for that you don't
3. Top Pages → see which competitor pages drive the most traffic
4. Link Intersect → find sites linking to competitors but not you

### Google Search Console
1. Performance → compare your rankings to manual competitor checks
2. Coverage → ensure your pages are indexed and competitive
3. Identify keywords where you're position 4-10 (easy improvement targets)

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Chasing wrong competitors | SEO competitors ≠ business competitors | Re-identify based on actual SERP overlap |
| Copying competitor content | Leads to parity, not advantage | Differentiate with unique data, angles, or format |
| Overwhelmed by gap size | Too many keyword gaps to address | Prioritize by volume × achievability; focus on clusters |
| Analysis paralysis | Too much data, no action | Pick top 10 keywords, execute for 90 days, then reassess |

## How to Get Your Data

- **Semrush**: Keyword Gap tool + Organic Research for each competitor
- **Ahrefs**: Content Gap + Competing Domains + Top Pages
- **Free**: Search your keywords manually and note who ranks; use Google Search Console for your own data
- **No tools**: List your domain and competitors — Claude analyzes based on available data

## Example

**Input**: "SEO competitor analysis: we're an HR software company (domain: hrflow.io). Competitors: bamboohr.com, gusto.com, rippling.com. We rank for 200 keywords, competitors rank for 5,000+. Struggling to compete."

**Output**: Landscape: BambooHR (DR 78, 850K organic/month, 45K keywords), Gusto (DR 82, 1.2M organic/month, 58K keywords), Rippling (DR 75, 420K organic/month, 22K keywords). Your position: DR 35, 8K organic/month, 200 keywords — significant gap but winnable with focused strategy. Keyword gap: 1,200 keywords where all 3 competitors rank but you don't — filtered to 85 achievable targets (KD <40, volume >200). Top opportunities: "employee onboarding checklist" (8,100/mo, no strong content from competitors), "PTO policy template" (4,400/mo, competitors have thin content), "HR compliance checklist" (3,200/mo, template-based content gap). Content strategy: competitors dominate with template/checklist content (40% of their traffic) — create 20 best-in-class templates in 90 days. Link strategy: 45 domains link to 2+ competitors but not you — 15 are high-quality industry publications achievable via expert commentary. Attack plan: Month 1 — publish 8 template pages targeting highest-volume gaps; Month 2 — begin outreach to gap link targets; Month 3 — launch "State of HR" data report for link-worthy content. Quick win: optimize existing 200 keyword pages (title tags, content depth) — expected 30% traffic lift from position improvements.
