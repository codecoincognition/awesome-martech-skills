---
name: win-loss-interview-analyzer
description: >
  Analyze win/loss interview transcripts or notes to extract patterns in why deals were won or lost.
  Use this skill when the user says "analyze win loss interviews", "why are we losing deals",
  "win loss analysis", "deal loss patterns", "why did we win this deal", "competitive loss reasons",
  "sales win patterns", "interview transcript analysis for sales", "extract themes from win loss",
  "deal post-mortem analysis", "why do customers choose us", or "churn reason analysis from
  interviews". Also trigger when the user pastes interview notes and wants to find patterns
  across multiple conversations.
---

> **How this skill works:** You export or paste win-loss interview transcripts, notes, or structured feedback data, and Claude analyzes patterns. Claude cannot conduct interviews or pull data from repositories directly — you bring the interview data, Claude brings the analysis.

# Win/Loss Interview Analyzer

Analyzes win/loss interview transcripts or structured notes to extract recurring themes, competitive insights, product gaps, and actionable recommendations. Turns qualitative interview data into quantitative patterns.

## Granularity Check

> Can this be completed in a single Claude session? **Yes — expect ~5 min data prep + ~10 min Claude session.** If implementing output in a platform, add 10-20 min for setup. Input is pasted interview notes or a CSV of structured responses. Output is a Markdown analysis report. No CRM or call recording access needed.

## User Intent Mapping

This skill should trigger when the user says things like:

- "Analyze these 10 win/loss interview transcripts" (batch analysis)
- "Why are we losing to [competitor]?" (competitive pattern)
- "What do customers say about our pricing?" (theme extraction)
- "Find common themes in our deal post-mortems" (pattern recognition)
- "Summarize what buyers care about most" (priority mapping)
- "Why did we win these 5 deals?" (win pattern analysis)
- "What's the #1 reason we're losing enterprise deals?" (segment-specific)
- "Compare win reasons vs. loss reasons" (comparative analysis)
- "Extract product feedback from sales interviews" (product insights)
- "Build a win/loss report for leadership" (executive summary)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Interview Data | Text or CSV | Interview transcripts, structured notes, or CSV with columns like: deal_name, outcome (win/loss), interview_notes, competitor, deal_size, segment |

### If You Don't Have This Data

- **No customer interviews?** Use support tickets, sales call notes, or online reviews as proxy customer voice data.
- **No survey data?** Send a 5-question NPS-style survey to your customer base. 30+ responses is enough for initial patterns.
- **No competitor content?** Search your primary keywords and screenshot the top 10 results. That's your competitive landscape.
- **No win/loss data?** Ask your sales team to recall their last 5 won and 5 lost deals. Verbal notes work fine as input.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Deal Metadata | CSV columns | Deal size, segment, sales cycle length, rep name, product line |
| Competitor Focus | Text | Specific competitor(s) to analyze losses against |
| Time Period | Text | Date range to filter interviews |
| Analysis Focus | Text | Specific themes to prioritize (pricing, product, sales process, support) |

### Sample Input CSV

```csv
deal_name,outcome,deal_size,segment,competitor,interview_date,key_themes,verbatim_quote,decision_factors
Acme Corp,win,85000,mid-market,CompetitorX,2025-06-15,"ease of use;integration;support","Your onboarding was the smoothest we've seen",product;support;price
BigTech Inc,loss,220000,enterprise,CompetitorY,2025-07-01,"missing features;price;slow sales cycle","We needed real-time dashboards and you didn't have them",product;price
StartupCo,win,15000,smb,none,2025-07-10,"fast setup;price;modern UI","We were up and running in 2 days",product;price;speed
MegaCorp,loss,500000,enterprise,CompetitorX,2025-08-01,"security concerns;missing compliance;slow RFP response","Your security documentation was incomplete",process;product;trust
```

## Process

### Step 1: Data Structuring
If raw transcripts are provided, extract structured data:
- **Outcome**: Win or loss
- **Decision factors**: What drove the decision (product, price, support, competition, timing)
- **Key themes**: Recurring topics mentioned (categorize into standard taxonomy)
- **Verbatim quotes**: Notable direct quotes that illustrate themes
- **Competitor mentions**: Which competitors were involved and how they were positioned
- **Sentiment indicators**: Positive, negative, neutral toward your product/team

### Step 2: Theme Extraction & Coding
Apply a consistent coding framework across all interviews:

| Theme Category | Sub-Themes |
|---|---|
| Product | Features, UX/UI, reliability, integration, roadmap, customization |
| Price | Cost, value perception, packaging, discounts, ROI clarity |
| Sales Process | Responsiveness, expertise, demo quality, proposal quality, follow-up |
| Support | Onboarding, training, ongoing support, documentation, CSM quality |
| Company | Brand trust, stability, references, case studies, market position |
| Competition | Competitive features, competitive pricing, incumbent advantage, switching costs |

Count frequency of each theme across wins and losses separately.

### Step 3: Pattern Analysis
Identify statistically meaningful patterns:
- **Win drivers**: Top 5 themes that correlate with wins (ranked by frequency)
- **Loss drivers**: Top 5 themes that correlate with losses (ranked by frequency)
- **Swing factors**: Themes that appear in both wins and losses (context-dependent)
- **Segment differences**: Do win/loss reasons differ by deal size, segment, or competitor?
- **Trend analysis**: Are loss reasons changing over time? (if date data available)

### Step 4: Competitive Intelligence
For each competitor mentioned:
- Win rate against them (from available data)
- Their perceived strengths (from buyer perspective)
- Their perceived weaknesses
- Common objections when competing against them
- Recommended counter-positioning

### Step 5: Actionable Recommendations
Translate patterns into specific actions:
- **Product team**: Feature gaps causing losses, ranked by deal value impact
- **Sales team**: Process improvements, talk track adjustments, objection handling
- **Marketing team**: Messaging gaps, competitive positioning, case study needs
- **Leadership**: Strategic themes, market positioning, investment priorities


### Confidence & Sample Size
> **Confidence Note**: Results are only as reliable as your input data. Small datasets (<50 records or <30 days of data) produce directional insights, not statistically significant conclusions. Always note your sample size when sharing results with stakeholders. Recommendations should be validated with A/B testing or additional data before making major strategic changes.

### ⚠️ Human Checkpoint
> Small sample sizes can produce misleading patterns. Flag confidence levels based on sample size. Recommendations from fewer than 10 interviews should be labeled as directional, not definitive.


> **Benchmark Context**: Win/loss analysis requires minimum 20 interviews per segment for reliable patterns. Survey response rates average 10-15% for email surveys, 30-50% for in-app. Qualitative research saturation typically occurs at 12-15 interviews.

## Output Contract

### Deliverable: Markdown Win/Loss Analysis Report

```markdown
# Win/Loss Analysis Report

## Executive Summary
- **Period**: [date range]
- **Interviews Analyzed**: [count] ([wins] wins, [losses] losses)
- **Win Rate**: [percentage] (from this sample)
- **Top Win Driver**: [theme]
- **Top Loss Driver**: [theme]
- **Most Dangerous Competitor**: [name] — [win rate against them]

## Win Drivers (Ranked)
| Rank | Theme | Frequency | % of Wins | Representative Quote |
|---|---|---|---|---|
| 1 | [theme] | [count] | [%] | "[quote]" |

## Loss Drivers (Ranked)
| Rank | Theme | Frequency | % of Losses | Representative Quote |
|---|---|---|---|---|
| 1 | [theme] | [count] | [%] | "[quote]" |

## Segment Analysis
### By Deal Size
| Segment | Win Rate | Top Win Reason | Top Loss Reason |
|---|---|---|---|

### By Competitor
| Competitor | Deals | Win Rate | Their Strength | Their Weakness | Our Counter |
|---|---|---|---|---|---|

## Theme Heatmap
| Theme | Wins (freq) | Losses (freq) | Net Sentiment | Trend |
|---|---|---|---|---|
| Product - Features | [n] | [n] | [+/-] | [↑↓→] |

## Product Feedback Summary
| Feature/Gap | Mentions | Deal Value at Risk | Priority |
|---|---|---|---|

## Recommendations
### For Product
1. [action] — [evidence] — [expected impact]

### For Sales
1. [action] — [evidence] — [expected impact]

### For Marketing
1. [action] — [evidence] — [expected impact]

## Confidence Note
Based on [n] interviews. [Directional/Moderate/High] confidence.
Minimum recommended sample: 20+ interviews for reliable patterns.

## Appendix: All Coded Interviews
| Deal | Outcome | Size | Themes | Key Quote |
|---|---|---|---|---|
```

## Platform Implementation Steps

### Google Sheets / Excel
1. Create a new spreadsheet
2. Paste output tables directly (Markdown tables → Sheets)
3. Add conditional formatting for scores/ratings
4. Create charts for visual summaries
5. Share with stakeholders

### Notion
1. Create a new page
2. Paste the Markdown output directly
3. Convert tables to Notion databases for filtering/sorting
4. Add to your team's research hub

### Presentation (for Stakeholders)
1. Copy key findings into a slide deck
2. Use the output scores/rankings as data slides
3. Include the recommended actions as a closing slide
4. Present to marketing/product leadership

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Tiny sample size (<5 interviews) | Not enough data for patterns | Analyze what's available, heavily caveat findings, recommend more interviews |
| All wins, no losses (or vice versa) | Biased sample | Analyze available data, note inability to compare, recommend balanced sampling |
| Unstructured notes | Raw paragraphs, no clear themes | Apply NLP-style theme extraction, ask user to validate coding |
| No competitor data | Interviews don't mention competitors | Skip competitive section, focus on product/process themes |
| Contradictory feedback | One buyer loves what another hates | Segment by deal size/persona to find context-dependent patterns |

## How to Get Your Data

- **Gong/Chorus**: Export call transcripts or summaries for closed deals
- **CRM notes**: Export opportunity close notes from Salesforce/HubSpot
- **Survey tools**: Export win/loss survey responses from SurveyMonkey, Typeform
- **Interview notes**: Copy-paste from Google Docs, Notion, or email
- **Clozd/DoubleCheck**: Export win/loss analysis data
- **Manual notes**: Structure as CSV with columns: deal_name, outcome, themes, quotes

## Example

**Input**: 15 win/loss interviews (9 wins, 6 losses) from Q3. Enterprise SaaS product competing against CompetitorX and CompetitorY.

**Output**: Top win driver: "Ease of integration" (mentioned in 7/9 wins, representative quote: "We were live in 2 weeks vs. 3 months with CompetitorX"). Top loss driver: "Missing real-time analytics" (mentioned in 5/6 losses, $1.2M total deal value at risk). CompetitorX: 60% win rate against them (strength: brand recognition; weakness: slow implementation). CompetitorY: 33% win rate (strength: enterprise features; weakness: pricing complexity). Key recommendation for Product: prioritize real-time dashboard feature — directly caused 5 losses worth $1.2M. Key recommendation for Sales: lead demos with integration speed, our strongest differentiator. Confidence: Moderate (15 interviews — directional patterns reliable, but recommend 25+ for high confidence).
