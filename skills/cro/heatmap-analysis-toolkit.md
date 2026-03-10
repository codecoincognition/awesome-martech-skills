---
name: heatmap-analysis-toolkit
description: >
  Interpret heatmap, scroll map, and session recording data to identify UX issues and conversion opportunities.
  Use this skill when the user says "heatmap analysis", "click map interpretation", "scroll depth analysis",
  "session recording insights", "user behavior analysis", "where users click on our page", "rage click detection",
  "attention heatmap review", "mouse tracking analysis", "user interaction patterns", or "behavioral analytics
  interpretation". Also trigger for click pattern analysis, dead click identification, or attention mapping.
---

# Heatmap Analysis Toolkit

Interprets heatmap, scroll map, click map, and session recording data to identify UX friction, attention patterns, and conversion optimization opportunities.

## Granularity Check

> **Session time**: ~5 min data prep + ~10 min Claude session. If implementing fixes, add 2-8 hours for design changes. Input is heatmap screenshots or behavioral data exports. Output is Markdown analysis with prioritized UX fixes.

## User Intent Mapping

- "What does our heatmap tell us?" (interpretation)
- "Where are users clicking on our page?" (click analysis)
- "How far do users scroll?" (scroll depth)
- "Session recordings show users struggling" (friction)
- "Rage clicks on our checkout page" (frustration)
- "Users aren't seeing our CTA" (attention)
- "Heatmap shows clicks on non-clickable elements" (dead clicks)
- "Mobile vs. desktop behavior differences" (device comparison)
- "Where do users drop off on the page?" (abandonment)
- "Heatmap data for redesign planning" (redesign)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Heatmap Data | Screenshots/Text | Click maps, scroll maps, or attention maps |
| Page URL | Text | Which page the data is from |
| Page Goal | Text | What the page should accomplish |

### If You Don't Have This Data

- **No heatmap tool?** Claude recommends free tools (Microsoft Clarity, Hotjar free tier) and provides setup guidance — you can have data within 48 hours.
- **No screenshots available?** Describe your page layout and where users seem to struggle — Claude identifies likely problem areas based on UX patterns.
- **Low traffic pages?** Claude recommends minimum data thresholds (1,000+ sessions for click maps, 500+ for scroll maps) and suggests combining data across time periods.
- **No session recordings?** Claude works with click/scroll data alone and recommends recording setup for deeper insights.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Session Recordings | Text | Key observations from watching recordings |
| Conversion Data | Text | Conversion rate and funnel metrics for the page |
| A/B Test History | Text | Past changes and their impact |
| Device Breakdown | Text | Desktop vs. mobile vs. tablet split |
| Traffic Source | Text | Where visitors come from (affects behavior) |

## Process

### Step 1: Click Map Analysis
| Pattern | Meaning | Action |
|---|---|---|
| Clicks on non-clickable elements | Users expect interaction | Make element clickable or change design |
| No clicks on CTA | CTA not visible or compelling | Reposition, redesign, or rewrite CTA |
| Clicks concentrated on nav only | Page content not engaging | Improve above-fold content and value proposition |
| Rage clicks (rapid repeated clicks) | Frustration — element broken or slow | Fix broken interactions, improve load speed |
| Ghost clicks (clicks on blank space) | Confusing layout or misaligned elements | Realign layout, add visual cues |

### Step 2: Scroll Map Analysis
| Scroll Depth | Benchmark | Interpretation |
|---|---|---|
| 25% | ~80-90% of visitors | Above fold — must contain key message |
| 50% | ~50-60% of visitors | Mid-page — good for secondary CTAs |
| 75% | ~30-40% of visitors | Deep engagement — good for social proof |
| 100% | ~10-20% of visitors | Footer — only committed readers |

Key patterns:
- Sharp drop-off = content not compelling enough to continue
- False bottom = design element looks like page end (users stop scrolling)
- Content gap = long section with no engagement between scroll zones

### Step 3: Attention Map Analysis
- Hot zones (red/orange): high attention — place key messages and CTAs here
- Cold zones (blue/green): low attention — don't put critical content here
- Attention follows F-pattern on text-heavy pages, Z-pattern on visual pages
- Images with faces draw attention — use strategically near CTAs
- Users skip large blocks of text — break into scannable sections

### Step 4: Session Recording Insights
| Behavior | Signal | Priority |
|---|---|---|
| Hesitation before form | Uncertainty about fields or commitment | High |
| Back-and-forth scrolling | Looking for information they can't find | High |
| Tab switching | Comparing with competitors | Medium |
| Cursor hovering over text | Reading carefully (good) or confused (bad) | Medium |
| Quick page exit | Wrong landing, slow load, or mismatch | High |

### Step 5: Device-Specific Analysis
- Compare click patterns: desktop vs. mobile (tap targets, thumb zones)
- Check scroll depth differences (mobile users often scroll deeper)
- Identify mobile-specific issues: elements too small, horizontal scrolling, overlapping content
- Review mobile form interactions: keyboard covering fields, dropdown usability

### Step 6: Prioritized Recommendations
Priority framework:
- **P0 (Fix now)**: Broken interactions, rage clicks, false bottoms hiding CTAs
- **P1 (This sprint)**: Dead clicks on expected-interactive elements, CTA visibility issues
- **P2 (Next sprint)**: Scroll depth optimization, content reordering
- **P3 (Backlog)**: Minor attention pattern tweaks, micro-interaction improvements

### Confidence & Sample Size

> **Confidence Note**: Click maps need 1,000+ sessions for reliable patterns — below 500 you're seeing noise. Scroll maps stabilize faster (~500 sessions). Session recordings are qualitative — watch 20-30 recordings to identify patterns, not just one or two edge cases. Heatmaps show WHERE but not WHY — combine with session recordings and user feedback for full picture. Mobile and desktop heatmaps must be analyzed separately — combined views are misleading.

### ⚠️ Human Checkpoint
> Validate heatmap findings with actual user feedback before major redesigns. Heatmaps can be misinterpreted — a hot zone doesn't always mean satisfaction, and cold zones don't always mean failure. Test changes with A/B tests, don't just implement based on heatmap data alone.

> **Benchmark Context**: Users spend 80% of attention above the fold. F-pattern scanning means left side of page gets 2x more attention than right. Users spend 57% more time above the fold than below. Rage clicks affect 5-10% of sessions on poorly designed pages. Mobile users tap 30% less accurately than desktop users click — 48px minimum tap targets are essential.

## Output Contract

### Deliverable: Markdown Heatmap Analysis

```markdown
# Heatmap Analysis: [Page Name]

## Summary
- Data source: [tool, date range, sessions]
- Key finding: [most important insight]
- Biggest opportunity: [highest-impact fix]

## Click Map Findings
| Element | Clicks | Expected? | Issue | Priority |
|---|---|---|---|---|

## Scroll Map Findings
| Depth | % Reaching | Key Content at This Depth | Issue |
|---|---|---|---|

## Friction Points
| Location | Behavior | Severity | Fix |
|---|---|---|---|

## Recommendations
| Priority | Change | Expected Impact | Effort |
|---|---|---|---|

## A/B Test Plan
| Test | Hypothesis | Metric | Duration |
|---|---|---|---|
```

## Platform Implementation Steps

### Microsoft Clarity (Free)
1. Add Clarity tracking script to your website
2. Wait 48-72 hours for data collection
3. Review click maps under Heatmaps → Clicks
4. Review scroll maps under Heatmaps → Scroll
5. Watch session recordings filtered by "rage clicks" or "dead clicks"

### Hotjar
1. Install Hotjar tracking code
2. Create heatmap for target page (click, move, scroll)
3. Set up session recording with filters (visited page, rage click, u-turn)
4. Review heatmaps after 1,000+ sessions
5. Watch 20-30 recordings for behavioral patterns

### FullStory / LogRocket
1. Configure session recording with privacy settings
2. Create segments for key user behaviors (frustration signals, conversion paths)
3. Use frustration detection (rage clicks, error clicks, dead clicks)
4. Export click data for quantitative analysis
5. Build dashboards for ongoing monitoring

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Misleading hot spots | Clicks on navigation counted as engagement | Filter out nav clicks; focus on content-area interactions |
| Low-data heatmap | Not enough sessions for reliable patterns | Extend data collection period; combine date ranges |
| Desktop-mobile confusion | Combined heatmap mixing device types | Always analyze device types separately |
| Redesign doesn't improve | Changed based on heatmap alone without testing | Use heatmap for hypotheses, A/B test for validation |

## How to Get Your Data

- **Click maps**: Hotjar, Clarity, or FullStory → Heatmaps → select page → screenshot
- **Scroll maps**: Same tools → Scroll tab → screenshot or export scroll depth percentages
- **Session recordings**: Filter by page, frustration signals, or conversion outcome → watch 20-30
- **No tool yet**: Install Microsoft Clarity (free, 5-minute setup) — have data within 48 hours

## Example

**Input**: "Heatmap analysis for our pricing page. Hotjar click map shows heavy clicks on the feature comparison table but almost no clicks on the 'Start Free Trial' CTA button. Scroll map shows 70% of users reach the pricing cards but only 25% reach the CTA below the comparison table. 15K monthly sessions, 2.1% conversion rate."

**Output**: Problem: CTA placement below comparison table means 75% of users never see it. Heavy clicks on feature table suggest users are comparing plans but can't find the action step. Fix priority: (1) P0 — add CTA buttons directly within each pricing card (above comparison table, where 70% of users are). (2) P0 — make "Start Free Trial" sticky on scroll (visible at all scroll depths). (3) P1 — add individual plan CTAs at the top and bottom of the comparison table. (4) P2 — test making feature rows clickable (users clicking expecting interaction). Expected results: moving CTA to where 70% of users already engage should increase visibility 3x and conversion from 2.1% to 3.5-5%. A/B test: current page vs. pricing cards with embedded CTAs — run 2 weeks minimum at 15K sessions.
