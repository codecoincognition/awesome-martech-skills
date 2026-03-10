---
name: backlink-analysis-report
description: >
  Analyze backlink profiles for authority, toxicity, and link building opportunities.
  Use this skill when the user says "backlink analysis", "link building strategy",
  "backlink audit", "link profile review", "toxic backlink cleanup", "competitor backlink
  analysis", "link gap analysis", "domain authority improvement", "link building opportunities",
  "disavow file creation", or "anchor text analysis". Also trigger for link reclamation,
  broken link building, or digital PR link assessment.
---

# Backlink Analysis Report

Analyzes backlink profiles to assess authority, identify toxic links, discover competitor link gaps, and build an actionable link acquisition strategy.

## Granularity Check

> **Session time**: ~5 min data prep + ~10 min Claude session. If implementing outreach, add 5-20 hours for link building campaigns. Input is backlink export from Ahrefs, Moz, or Semrush. Output is Markdown analysis with link building action plan.

## User Intent Mapping

- "Analyze our backlink profile" (audit)
- "Find link building opportunities" (prospecting)
- "Which backlinks are hurting our SEO?" (toxic links)
- "Competitor backlink gap analysis" (competitive)
- "How do we increase domain authority?" (strategy)
- "Create a disavow file" (cleanup)
- "Anchor text distribution looks unnatural" (anchor audit)
- "Our link profile vs. competitor" (comparison)
- "Digital PR for link building" (PR-led links)
- "Reclaim lost backlinks" (reclamation)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Backlink Export | CSV | Ahrefs, Moz, or Semrush backlink export |
| Domain | Text | Your website domain |
| Goal | Text | Authority building, toxic cleanup, competitive gap, or specific ranking target |

### If You Don't Have This Data

- **No backlink tool?** Use free Ahrefs Webmaster Tools or Google Search Console Links report (limited but usable). Claude can work with GSC data.
- **No competitor data?** Tell Claude your top 3 competitors. Strategy will be based on best practices rather than gap analysis.
- **No link building experience?** Claude generates a beginner-friendly outreach plan with email templates and target criteria.
- **Small site with few backlinks?** That's a starting point, not a problem. Claude focuses on foundational link building tactics.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Competitor Backlinks | CSV | Top 3 competitor backlink exports |
| Target Keywords | Text list | Keywords you're trying to rank for |
| Current DA/DR | Number | Domain Authority or Domain Rating |
| Industry | Text | For industry-specific link opportunities |
| Past Outreach | Text | Previous link building efforts and results |

## Process

### Step 1: Profile Health Assessment
- Total referring domains and backlinks count
- Domain authority / domain rating trend
- Follow vs. nofollow ratio (healthy: 70-85% follow)
- Link velocity (new vs. lost links per month)
- Top linked pages analysis

### Step 2: Anchor Text Analysis
- Branded vs. exact-match vs. generic distribution
- Flag over-optimized anchor text (>5% exact match for competitive terms)
- Natural anchor text recommendations
- Identify potential manual penalty risks

### Step 3: Toxic Link Identification
- Spam score assessment per linking domain
- PBN (Private Blog Network) detection signals
- Link scheme patterns (paid links, excessive reciprocal linking)
- Foreign language spam links
- Disavow file generation for confirmed toxic links

### Step 4: Competitor Gap Analysis
- Identify domains linking to competitors but not to you
- Classify gap links by type (editorial, directory, resource, guest post)
- Prioritize by domain authority and relevance
- Estimate acquisition difficulty per opportunity

### Step 5: Link Building Strategy
- Content-led link building (linkable assets, data studies, tools)
- Digital PR opportunities (newsjacking, expert commentary, data stories)
- Resource page link building
- Broken link building opportunities
- Guest posting targets (quality over quantity)
- HARO / Connectively / journalist queries
- Unlinked brand mention reclamation

### Step 6: Outreach Plan
- Target list with contact information needs
- Email templates for each link type
- Follow-up cadence (3-touch sequence)
- Success metrics and tracking

### Confidence & Sample Size
> **Confidence Note**: Backlink data varies between tools — Ahrefs and Semrush discover different links. For complete analysis, cross-reference two tools. Toxic link scoring is probabilistic, not definitive — disavow only clearly spammy links. Domain authority is a third-party metric, not a Google ranking factor, but correlates with ranking ability.

### ⚠️ Human Checkpoint
> Review disavow file carefully before submitting to Google — incorrectly disavowing good links can hurt rankings. Verify outreach targets are legitimate sites before contacting. Never pay for links from link farms or PBNs.

> **Benchmark Context**: Top-ranking pages have 3.8x more backlinks than positions 2-10. Sites with 40+ referring domains rank for significantly more keywords. Average outreach response rate is 5-15%. Quality of linking domain matters more than quantity — one link from a DA 60+ site outweighs 100 links from DA 10 sites. Natural link profiles have 50-70% branded anchor text.

## Output Contract

### Deliverable: Markdown Backlink Analysis

```markdown
# Backlink Analysis: [Domain]

## Profile Summary
| Metric | Value | Benchmark | Status |
|---|---|---|---|

## Anchor Text Distribution
| Anchor Type | % | Healthy Range | Action |
|---|---|---|---|

## Toxic Links
| Domain | Spam Score | Link Type | Recommendation |
|---|---|---|---|

## Competitor Gap
| Domain | Links to Competitor | DA | Acquisition Approach |
|---|---|---|---|

## Link Building Strategy
| Tactic | Target Count | Effort | Expected Links/Month |
|---|---|---|---|

## Outreach Templates
### [Tactic 1]
Subject: [line]
Body: [template]

## 90-Day Action Plan
| Month | Focus | Target | KPI |
|---|---|---|---|
```

## Platform Implementation Steps

### Ahrefs
1. Site Explorer → enter domain → Backlinks report → Export
2. Competing Domains → identify top competitors
3. Link Intersect → find gap opportunities
4. Content Explorer → find linkable content ideas in your niche

### Google Search Console
1. Links report → Export top linking sites and top linked pages
2. Cross-reference with manual review for spam links
3. Submit disavow file via Disavow Links tool

### Outreach Tools
1. Use Hunter.io or Apollo for finding contact emails
2. Track outreach in a CRM or spreadsheet (Pitchbox, BuzzStream, or Google Sheets)
3. Set up email sequences with 3-touch follow-up cadence
4. Track link placements and anchor text monthly

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Disavow hurt rankings | Disavowed legitimate links | Remove entries from disavow file; resubmit |
| Outreach gets no responses | Generic templates or wrong targets | Personalize first line; verify contact accuracy; improve subject lines |
| Links don't improve rankings | Links from irrelevant or low-authority sites | Focus on topical relevance over raw DA; build links to specific pages |
| Penalized for link scheme | Paid links or PBN detected | Disavow offending links; file reconsideration request if manual action |

## How to Get Your Data

- **Ahrefs**: Site Explorer → [domain] → Backlinks → Export
- **Semrush**: Backlink Analytics → [domain] → Export
- **Moz**: Link Explorer → [domain] → Export
- **Free option**: Google Search Console → Links → Export External Links
- **No tools**: Provide your domain and competitors — Claude designs a strategy based on best practices

## Example

**Input**: "Backlink analysis for a B2B SaaS blog. DR 35, 450 referring domains. Competitors have DR 55-65. Losing rankings to competitors on key terms. Ahrefs export attached."

**Output**: Profile health: 450 RDs is below competitor average (1,200). Anchor text: 22% exact-match anchors (too high, risk of penalty — target <5%). Toxic links: 35 domains flagged (15 confirmed spam, 20 low-quality directories) — disavow file generated. Competitor gap: 280 domains link to 2+ competitors but not to you — top 50 prioritized by DA and relevance. Strategy: (1) Create 2 original data studies per quarter (most linkable asset type in B2B), (2) HARO responses — target 5 journalist queries/week, expect 2-3 links/month, (3) Guest posting on 10 industry blogs (pre-vetted list with DA 40+), (4) Reclaim 12 unlinked brand mentions found via Ahrefs Content Explorer. 90-day plan: Month 1 — disavow toxic links + launch first data study; Month 2 — begin outreach to gap domains + HARO cadence; Month 3 — guest post submissions + second data study. Target: 25-35 new quality referring domains in 90 days.
