---
name: vendor-performance-scorecard
description: >
  Score and evaluate marketing vendor or agency performance across delivery, cost, quality,
  communication, and strategic value. Use this skill when the user says "score my vendor",
  "agency performance review", "vendor scorecard", "rate our agency", "evaluate vendor
  performance", "should we renew this vendor", "vendor QBR prep", "agency report card",
  "compare vendor performance", "vendor renewal decision", or "how is our agency doing".
  Also trigger when preparing for a vendor quarterly business review or renewal decision.
---

# Vendor Performance Scorecard

Scores marketing vendor or agency performance across 5 weighted dimensions, producing a quantified scorecard with trend analysis and a data-backed renewal recommendation.

## Granularity Check

> Can this be completed in a single Claude session? **Yes — expect ~5 min data prep → ~10 min Claude session → ~30-60 min implementing in your MarTech stack.** If implementing output in a platform, add 10-20 min for setup. Input is vendor performance data (text or CSV). Output is an XLSX scorecard. No external system access needed.

## User Intent Mapping

This skill should trigger when the user says things like:

- "Create a scorecard for our SEO agency" (direct request)
- "How is our marketing vendor performing?" (assessment question)
- "Prepare for our agency QBR" (meeting prep)
- "Should we renew this vendor contract?" (decision support)
- "Compare our two content agencies" (comparison)
- "Rate our media buying agency this quarter" (periodic review)
- "Our agency isn't delivering — help me document it" (accountability)
- "Build a vendor evaluation framework" (framework creation)
- "Score our MarTech vendors for the annual review" (batch evaluation)
- "Vendor report card for Q4" (periodic deliverable)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Vendor Name | Text | Name of the vendor or agency |
| Review Period | Text | Time period being evaluated (e.g., "Q4 2025", "H2 2025") |
| Performance Data | Text or CSV | Deliverables completed, SLA compliance, budget adherence, satisfaction notes |

### If You Don't Have This Data

- **No brand guidelines?** Document your current logo, colors (use a color picker on your website), and 3 tone-of-voice adjectives. That's a starting brand guide.
- **No asset inventory?** Search your Google Drive/Dropbox for common marketing file types (.pdf, .pptx, .png). The list IS your inventory.
- **No compliance checklist?** Start with industry basics: GDPR consent, CAN-SPAM footer, accessibility alt text. This skill helps you build the full checklist.
- **No vendor data?** List every tool your marketing team pays for. Include name, monthly cost, and primary user. That's your vendor inventory.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Contract Value | Number | Total contract value for the period |
| SLA Targets | Text | Agreed-upon service levels (response time, deliverable cadence, uptime) |
| Previous Scores | Text/CSV | Prior period scores for trend analysis |
| Custom Weights | Text | Override default dimension weights |
| Comparison Vendor | Text + data | Second vendor to compare side-by-side |

## Process

### Step 1: Organize Performance Data
Map provided data to 5 scoring dimensions:

| Dimension | Weight | Metrics |
|---|---|---|
| Delivery | 25% | On-time delivery rate, milestone completion, scope adherence |
| Cost | 20% | Budget variance, cost per deliverable, change order frequency |
| Quality | 25% | Error/revision rate, output quality assessment, stakeholder satisfaction |
| Communication | 15% | Response time, proactive updates, meeting preparedness, escalation handling |
| Strategic Value | 15% | Proactive recommendations, industry insights, innovation, knowledge transfer |

### Step 2: Score Each Dimension (1-5 scale)
For each dimension, assign a score based on available data:
- **5 (Exceptional)**: Consistently exceeds expectations, best-in-class
- **4 (Strong)**: Meets all expectations, occasional overdelivery
- **3 (Adequate)**: Meets most expectations, some gaps
- **2 (Below Standard)**: Frequently misses expectations, requires oversight
- **1 (Unacceptable)**: Consistently fails to deliver, active risk

### Step 3: Calculate Overall Score
- Weighted score = Σ (dimension score × weight) × 20
- Scale: 0-100 points
- Performance bands: Exceptional (85-100), Strong (70-84), Adequate (55-69), At Risk (40-54), Unacceptable (0-39)

### Step 4: Trend Analysis
If prior scores available:
- Calculate score delta per dimension
- Identify improving vs. declining areas
- Determine trajectory (improving, stable, declining)

### Step 5: Renewal Recommendation
Based on overall score and trend:
- **85+**: RENEW — strong partner, explore expansion
- **70-84**: RENEW WITH CONDITIONS — specify improvement areas and timeline
- **55-69**: PROBATION — 90-day improvement plan with measurable targets
- **40-54**: TRANSITION — begin vendor search, plan migration
- **Below 40**: TERMINATE — immediate transition planning


### Confidence & Sample Size
> **Confidence Note**: Results are only as reliable as your input data. Small datasets (<50 records or <30 days of data) produce directional insights, not statistically significant conclusions. Always note your sample size when sharing results with stakeholders. Recommendations should be validated with A/B testing or additional data before making major strategic changes.

### ⚠️ Human Checkpoint
> Review scores before sharing with the vendor. Ensure ratings are fair, documented with examples, and defensible. One bad quarter may not warrant termination if the trend is improving.


> **Benchmark Context**: See Gartner 2024 Marketing Technology Survey for current industry benchmarks relevant to this analysis.
## Output Contract

### Deliverable: Structured Analysis Tables in Markdown

Claude generates four detailed analysis tables in Markdown format that you can copy directly into Google Sheets, Excel, or any spreadsheet tool

**Table 1: Executive Summary**
| Field | Value |
|---|---|
| Vendor | [name] |
| Period | [period] |
| Overall Score | [X/100] |
| Band | [Exceptional/Strong/Adequate/At Risk/Unacceptable] |
| Trend | [↑ Improving / → Stable / ↓ Declining] |
| Recommendation | [RENEW / RENEW WITH CONDITIONS / PROBATION / TRANSITION / TERMINATE] |
| Top Strength | [dimension] |
| Top Weakness | [dimension] |

**Table 2: Detailed Scorecard**
Columns: `dimension | weight | score_1to5 | weighted_score | evidence | notes`

**Table 3: Trend Analysis**
Columns: `dimension | current_score | prior_score | delta | trajectory | commentary`

**Table 4: Action Plan**
Columns: `priority | area | current_state | target_state | deadline | success_metric`

## Platform Implementation Steps

### Notion / Confluence (Documentation)
1. Create a new page for the audit/report
2. Paste Markdown output directly
3. Add status properties for tracking remediation
4. Assign team members to action items

### Google Sheets (Tracking)
1. Import CSV output into a new spreadsheet
2. Add a "Status" column for tracking fixes
3. Use conditional formatting for severity levels
4. Create a dashboard tab with summary charts

### Project Management (Asana/Jira/Linear)
1. Create tasks from each action item in the output
2. Set priority based on severity ratings
3. Assign to responsible team members
4. Set due dates based on priority tiers

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Vague performance data | User provides feelings, not metrics | Ask for specific examples — deliverables count, timeline adherence, budget numbers |
| Single data point | Only one quarter of data | Score what's available, note no trend analysis possible, recommend tracking framework |
| Emotional bias | User frustrated with vendor | Focus on measurable data points, separate feelings from facts |
| No SLA baseline | No agreed-upon targets | Use industry benchmarks, note they're proxy targets |

## How to Get Your Data

- **Project management tools**: Export task completion data from Asana, Monday, Jira
- **Finance**: Pull invoices and PO amounts from your accounting system
- **Email**: Search for delivery confirmations, feedback threads, escalation emails
- **Meeting notes**: Review QBR notes, status meeting summaries
- **Satisfaction**: Run a quick internal survey (1-5 rating per dimension) among stakeholders who interact with the vendor

## Example

**Input**: "ContentPros Agency", Q4 2025. Delivered 11 of 12 blog posts on time, 2 required major revisions, budget was $15K against $12K plan (25% over), response time averaged 6 hours (SLA: 4 hours), proactively suggested a content pillar strategy that increased organic traffic 15%.

**Output**: Overall score 68/100 (Adequate). Delivery 4/5 (92% on-time), Cost 2/5 (25% over budget), Quality 3/5 (17% revision rate), Communication 3/5 (response time 50% above SLA), Strategic Value 5/5 (proactive strategy with measurable results). Recommendation: RENEW WITH CONDITIONS — require scope/budget alignment process and response time improvement to 4-hour SLA within 60 days.

## Related Skills

- **[Contract Clause Extractor](./contract-clause-extractor.md)** — Extract contract terms that inform vendor SLA and performance expectations.
- **[SLA Document Generator](./sla-document-generator.md)** — Create vendor SLAs that form the basis of performance measurement.
- **[Approval Bottleneck Analyzer](./approval-bottleneck-analyzer.md)** — Score vendors partially on their impact to approval cycle times.
- **[Content Performance Scorecard](../content/content-performance-scorecard.md)** — Compare agency-produced content performance to evaluate vendor quality.
