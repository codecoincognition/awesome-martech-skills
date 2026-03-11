---
name: sales-content-usage-analyzer
description: >
  Analyze which sales content gets used, shared, and correlates with closed deals. Use this
  skill when the user says "which sales content works", "content usage analysis", "what content
  do reps actually use", "sales content ROI", "content effectiveness report", "most used
  sales assets", "content engagement analytics", "sales enablement report", "which collateral
  closes deals", or "content performance by deal stage". Also trigger when the user has
  content engagement data from Highspot, Seismic, Showpad, or Google Drive analytics.
---

> **How this skill works:** You export sales engagement data (email opens, document views, call activity, etc.) from your CRM or sales tools as a CSV, and Claude analyzes it. Claude cannot connect to live CRM platforms or pull data directly — you bring the data, Claude brings the analysis.

# Sales Content Usage Analyzer

Analyzes sales content usage data to identify which assets reps actually use, which correlate with won deals, and which are gathering dust. Produces a content effectiveness report with recommendations for what to create, retire, or promote.

## Granularity Check

> Can this be completed in a single Claude session? **Yes — expect ~5 min data prep → ~10 min Claude session → ~30-60 min customizing for your prospect.** If implementing output in a platform, add 10-20 min for setup. Input is content usage CSV. Output is an XLSX analysis report. No system access needed.

## User Intent Mapping

This skill should trigger when the user says things like:

- "Which sales content actually gets used?" (usage question)
- "What content correlates with closed deals?" (effectiveness)
- "Our content library is huge — what should we retire?" (lifecycle)
- "Sales reps say they can't find the right content" (problem statement)
- "Content ROI analysis for the sales team" (ROI)
- "Which case studies perform best?" (asset-type specific)
- "Content engagement report from Highspot" (tool-specific)
- "What content gaps do our reps have by deal stage?" (gap analysis)
- "Help us prioritize what content to create next" (planning)
- "Sales enablement content audit" (comprehensive review)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Content Usage Data | CSV | Columns: asset_name, asset_type, views, shares, downloads, deal_stage, deal_outcome |

### If You Don't Have This Data

- **No CRM data?** Export your email contacts, LinkedIn connections, or even a list of companies you've spoken to in a spreadsheet.
- **No deal outcome data?** Start with win/loss status on your last 20 deals. Even rough data is better than none.
- **No content library?** List every PDF, deck, and one-pager your sales team uses — even a 10-item list is a valid starting point.
- **No engagement metrics?** Track which content sales reps send in emails for the next 2 weeks. Manual tracking beats no tracking.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Content Library | CSV | Full asset list (to identify unused content) |
| Deal Data | CSV | Deal ID, outcome (won/lost), value, sales cycle length |
| Time Period | Text | Analysis window (e.g., "Q4 2025") |
| Rep Data | CSV column | Which reps use which content (for adoption analysis) |

### Sample Input CSV

```csv
asset_name,asset_type,views,shares,deal_stage,deal_outcome,rep_name
Product Overview Deck,presentation,145,38,discovery,won,Sarah K
ROI Calculator,spreadsheet,89,52,proposal,won,Mike T
Enterprise Case Study,pdf,67,41,evaluation,won,Sarah K
Feature Comparison,one-pager,23,5,evaluation,lost,James R
2024 Product Brochure,pdf,4,0,discovery,lost,Various
Security Whitepaper,pdf,56,28,evaluation,won,Mike T
```

## Process

### Step 1: Usage Metrics
Calculate per asset:
- Total views, shares, and downloads
- Unique rep usage (adoption breadth)
- Share-to-view ratio (is it worth sharing?)
- Trend over time (growing or declining usage)

### Step 2: Win Correlation
For each asset, calculate:
- Win rate when used vs. overall win rate
- Correlation with deal velocity (faster close?)
- Stage-specific usage (when in the funnel is it used?)
- Deal size correlation (does it help with larger deals?)

### Step 3: Content Effectiveness Scoring
Score each asset (0-100) combining:
- Usage volume (40% weight)
- Win correlation (40% weight)
- Recency of use (20% weight)

Classify into quadrants:
- **Stars** ⭐: High usage + high win correlation → promote widely
- **Hidden Gems** 💎: Low usage + high win correlation → increase visibility
- **Crowd Pleasers** 📢: High usage + low win correlation → investigate why
- **Dead Weight** 💀: Low usage + low win correlation → retire or update

### Step 4: Gap Analysis
Identify content gaps by:
- Deal stages with no associated content
- Industries/verticals with no case studies
- Objections without supporting content
- Competitor comparisons missing

### Step 5: Recommendations
Prioritized action plan:
- Content to promote (hidden gems reps don't know about)
- Content to retire (saves maintenance effort)
- Content to create (fills gaps)
- Content to update (popular but outdated)


### Confidence & Sample Size
> **Confidence Note**: Results are only as reliable as your input data. Small datasets (<50 records or <30 days of data) produce directional insights, not statistically significant conclusions. Always note your sample size when sharing results with stakeholders. Recommendations should be validated with A/B testing or additional data before making major strategic changes.

### ⚠️ Human Checkpoint
> Correlation ≠ causation. High-performing content may simply be used by top reps. Cross-reference with rep performance data before drawing conclusions.


> **Benchmark Context**: See Gartner 2024 B2B Buying Journey Report for current industry benchmarks relevant to this analysis.
## Output Contract

### Deliverable: Markdown Tables + CSV-Ready Data (3 sections)

**Section 1: Content Scorecard**
Markdown table: `asset_name | asset_type | usage_score | win_correlation | effectiveness_score | quadrant | recommendation`

Can be pasted into Google Sheets, Excel, or any spreadsheet tool.

**Section 2: Gap Analysis**
Markdown table: `gap_type | description | deal_stage | priority | recommended_content`

**Section 3: Action Plan**
Markdown table: `priority | action | assets | expected_impact | effort`

## Platform Implementation Steps

### Salesforce
1. Navigate to Reports → New Report → select relevant object
2. Add columns matching the output schema
3. Use filters to scope the data
4. Export as CSV for input, or build dashboard from output

### HubSpot
1. Go to Contacts/Companies → Import → select CSV
2. Map columns to HubSpot properties
3. Use Lists → Create List to filter by output criteria
4. Dashboards → Create Dashboard for ongoing tracking

### Google Sheets (No CRM)
If no CRM is available:
1. Create a new Google Sheet
2. Structure columns per the output schema
3. Use Data → Filter Views for dynamic sorting
4. Share with team via link for collaboration

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| No deal outcome data | Usage data only, no win/loss | Score on usage alone, note effectiveness can't be measured |
| Small dataset | <30 deals with content usage | Note small sample, provide directional insights |
| Inconsistent naming | Same content tracked under different names | Normalize names, ask user to confirm groupings |
| No attribution | Can't tie content to specific deals | Analyze aggregate usage patterns only |

## How to Get Your Data

- **Highspot**: Analytics → Content Performance → Export
- **Seismic**: Reports → Content Usage → Download
- **Showpad**: Analytics → Content → Export
- **Google Drive**: Activity dashboard → export access logs
- **CRM**: If content is shared via CRM, pull activity reports
- **Manual**: Track content shares in a spreadsheet for 30 days

## Example

**Input**: 6 months of content usage data, 47 assets, 156 closed deals (89 won, 67 lost).

**Output**: 5 Stars (ROI Calculator has 73% win rate vs. 57% average — strongest asset), 3 Hidden Gems (Security Whitepaper used by only 2 reps but 85% win rate when used — needs broader distribution), 8 Dead Weight assets (2024 Product Brochure viewed 4 times in 6 months — retire). Top gap: no case study for financial services (25% of pipeline). Action plan: (1) Add Security Whitepaper to rep onboarding. (2) Create FinServ case study. (3) Archive 8 dead weight assets. (4) Investigate why Feature Comparison has high usage but low win correlation.

## Related Skills

- **[Sales Deck Assembler](./sales-deck-assembler.md)** — Use insights on what content works best to prioritize which assets to assemble in customized decks.
- **[Content Performance Scorecard](../content/content-performance-scorecard.md)** — Complement sales content analysis with marketing content performance metrics.
- **[Approval Bottleneck Analyzer](../martech-ops/approval-bottleneck-analyzer.md)** — Analyze why high-performing content takes longer to approve, to reduce lag on future winners.
- **[Lead Scoring Model Builder](../crm/lead-scoring-model-builder.md)** — Use content engagement data as a behavioral signal in your lead scoring model.
