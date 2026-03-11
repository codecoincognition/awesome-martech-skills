---
name: lead-scoring-model-builder
description: >
  Build a lead scoring model from CRM data.
  Use this skill whenever the user mentions lead scoring, lead qualification, MQL/SQL
  scoring, lead prioritization, or says things like "help me score my leads" or "which
  leads should sales focus on" or "build a scoring model for my CRM." Also trigger for
  lead ranking, prospect scoring, fit scoring, engagement scoring, or any request to
  prioritize leads based on demographic and behavioral data. Use even for "help me
  figure out which leads are worth pursuing."
---

# Lead Scoring Model Builder

Builds a points-based lead scoring model from CRM data. Analyzes which demographic and behavioral attributes correlate with conversions, assigns point values, sets MQL/SQL thresholds, and provides implementation guides for HubSpot, Salesforce, and Pipedrive.

## Granularity Check

> **Time**: ~5 min data prep → ~10 min Claude session → ~30-60 min configuring in Salesforce / HubSpot. If implementing output in a platform, add 10-20 minutes for setup. Input is a CSV of leads with attributes + conversion outcome. Output is an XLSX scoring model.

## User Intent Mapping

- "Build a lead scoring model from my CRM data" (direct command)
- "Which leads should my sales team call first?" (prioritization)
- "Help me set up lead scoring in HubSpot" (tool-specific)
- "My sales team wastes time on bad leads" (problem statement)
- "How do I know which leads are ready to buy?" (qualification)
- "Create MQL and SQL definitions for our business" (threshold setting)
- "Score leads based on their engagement and fit" (two-factor scoring)
- "Build a lead prioritization system" (system design)
- "Analyze which lead attributes predict conversion" (analytical)
- "Help me define our ideal customer profile for scoring" (ICP-based)

## Input Contract

### Required Input

| Column | Type | Description | Example |
|---|---|---|---|
| `lead_id` | string | Unique lead identifier | `"L-001"` |
| `converted` | boolean/integer | Whether lead became a customer (1/0, true/false, yes/no) | `1` |

### Required: At Least 3 of These Attribute Columns

| Column | Type | Description | Example |
|---|---|---|---|
| `company_size` | string/integer | Employee count or range | `"51-200"` |
| `industry` | string | Industry vertical | `"Technology"` |
| `job_title` | string | Contact's role | `"VP of Marketing"` |
| `source` | string | Lead source | `"organic"`, `"paid"`, `"referral"` |
| `page_views` | integer | Total pages viewed | `23` |
| `email_opens` | integer | Emails opened | `8` |
| `content_downloads` | integer | Resources downloaded | `3` |
| `demo_requested` | boolean | Whether demo was requested | `1` |
| `days_since_first_touch` | integer | Days in pipeline | `45` |

### If You Don't Have This Data

- **No CRM export?** Create a simple spreadsheet with columns: Name, Email, Company, Stage, Last Contact Date. Even 50 records work.
- **No lead scores?** Use lifecycle stage as a proxy: Customer > Opportunity > SQL > MQL > Lead > Subscriber.
- **No enrichment budget?** This skill helps you prioritize so you can make the case for budget. Start with the output.
- **No ICP definition?** Look at your best 5 customers — what industry, size, and title do they share? That's your starting ICP.

### Optional Input

| Column | Type | Default | Description |
|---|---|---|---|
| `deal_value` | float | `null` | Revenue from converted leads (for weighting) |
| `sales_cycle_days` | integer | `null` | Days to close (for velocity scoring) |

### Input Validation Rules

1. Must have `lead_id` and `converted` columns
2. Need at least 50 leads (20+ converted) for meaningful analysis
3. At least 3 attribute columns beyond id and converted
4. Conversion column must have both 0s and 1s

**If validation fails:** Tell the user exactly what's missing. If too few leads, explain minimum data requirements and suggest they export a larger date range.

### Sample Input

```csv
lead_id,company_size,industry,job_title,source,page_views,email_opens,content_downloads,demo_requested,converted
L-001,51-200,Technology,VP Marketing,organic,23,8,3,1,1
L-002,1-50,Healthcare,Marketing Manager,paid,5,2,0,0,0
L-003,201-1000,Technology,CMO,referral,45,15,5,1,1
L-004,51-200,Finance,Director Marketing,organic,12,4,1,0,0
L-005,1-50,Retail,Marketing Coordinator,paid,3,1,0,0,0
```

## Process

1. **Validate data** — Check columns, data types, conversion distribution. Report: "Found X leads, Y converted (Z% conversion rate), W attribute columns."

2. **Calculate conversion rates by attribute** — For each attribute value, compute conversion rate:
   - "Technology" industry: 35% conversion vs. 12% overall
   - "VP+" title: 28% vs. 12% overall
   - "51-200 employees": 22% vs. 12% overall

3. **Assign point values** — Weight each attribute based on how much it lifts conversion rate above baseline:
   - Points = round((attribute_conv_rate / baseline_conv_rate) × 10)
   - Behavioral attributes (actions) typically get higher weights than demographic (fit)

4. **Set thresholds** — Define score ranges:
   - **Cold:** 0-30 points (nurture only)
   - **MQL:** 31-60 points (marketing qualified, enter nurture sequence)
   - **SQL:** 61+ points (sales qualified, route to sales)
   - Validate thresholds against historical data: "X% of converted leads would have scored as SQL"

5. **Human checkpoint** — Present the scoring model and thresholds. Ask: "Do these point values match your intuition? Should any attributes be weighted differently? Are the MQL/SQL thresholds realistic for your sales team?"

6. **Generate implementation guide** — CRM-specific setup instructions.

7. **Validate model** — Check: What % of actual conversions score above SQL threshold? What % of non-conversions score below MQL? Report precision and recall.


> **Benchmark Context**: Consult current industry reports for up-to-date benchmarks relevant to this analysis.


### Confidence & Sample Size
> **Confidence Note**: Results are only as reliable as your input data. Small datasets (<50 records or <30 days of data) produce directional insights, not statistically significant conclusions. Always note your sample size when sharing results with stakeholders. Recommendations should be validated with A/B testing or additional data before making major strategic changes.

## Output Contract

### Output Format

| Output | Format | Contents |
|---|---|---|
| Scoring model | Markdown tables + CSV-ready data | Point values + thresholds (paste into Google Sheets or Excel) |
| Implementation guide | Markdown | CRM setup instructions |

### Scoring Card Table

| Column | Type | Description |
|---|---|---|
| `attribute` | string | Scoring factor |
| `value` | string | Specific attribute value |
| `points` | integer | Points awarded |
| `conversion_rate` | float | Conversion rate for this value |
| `category` | string | Demographic / Behavioral |

### Threshold Definitions Table

| Column | Type | Description |
|---|---|---|
| `tier` | string | Cold / MQL / SQL |
| `min_score` | integer | Minimum score for this tier |
| `max_score` | integer | Maximum score |
| `action` | string | What to do with leads in this tier |
| `historical_conversion` | float | Conversion rate of leads in this tier historically |

### Model Validation Table

| Column | Type | Description |
|---|---|---|
| `metric` | string | Accuracy, precision, recall |
| `value` | float | Score |
| `interpretation` | string | What this means |

## Platform Implementation Steps

### HubSpot
1. Navigate to Contacts → Import → Start an Import
2. Upload the output CSV, mapping columns to HubSpot properties
3. Use Workflows → Create Workflow to automate actions on scored records
4. Create Active Lists based on output tiers for segmentation

### Salesforce
1. Go to Setup → Data Import Wizard or Data Loader
2. Map CSV columns to Salesforce fields
3. Create Reports filtered by output scores/tiers
4. Build Process Builder flows for automated follow-up

### Spreadsheet (Manual CRM)
1. Import output CSV into Google Sheets
2. Use conditional formatting to color-code tiers
3. Create filter views per team member
4. Set up weekly review cadence

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Too few leads (<50) | Small dataset | Warn about statistical reliability; build model but flag uncertainty |
| No behavioral data | Only demographic columns | Build fit-only model; recommend adding engagement tracking |
| Extreme class imbalance | <5% or >50% conversion rate | Adjust methodology; note limitations |
| All attributes equally predictive | No clear differentiators | Suggest collecting different data; recommend qualitative scoring |
| Missing data in columns | Lots of nulls | Report missing data %; exclude columns with >50% missing |

## How to Get Your Data

### From HubSpot

1. Go to Contacts → All Contacts
2. Add columns: company size, industry, job title, lifecycle stage, source
3. Filter for contacts created in last 12 months
4. Click Actions → Export → CSV
5. Add a "converted" column (1 for Customers, 0 for others)

### From Salesforce

1. Go to Reports → New Report → Leads
2. Add fields: company, industry, title, lead source, status
3. Set date range (last 12 months)
4. Run report → Export → CSV
5. Mark converted leads (Closed Won = 1, others = 0)

### From Pipedrive

1. Go to Contacts → Filter by date range
2. Export to CSV
3. Add conversion column based on deal status

## Example

**User prompt:** "Build a lead scoring model from our HubSpot export. We have 200 leads from Q1-Q2 with 28 conversions."

**Claude output:**

> Analyzed 200 leads (14% conversion rate). Here's the scoring model:
>
> ## Scoring Card (Top Factors)
>
> | Attribute | Value | Points | Conv. Rate | vs Baseline |
> |---|---|---|---|---|
> | Demo Requested | Yes | +25 | 52% | 3.7x |
> | Content Downloads | 3+ | +15 | 38% | 2.7x |
> | Job Title | VP/C-level | +12 | 29% | 2.1x |
> | Company Size | 51-200 | +10 | 22% | 1.6x |
> | Industry | Technology | +8 | 21% | 1.5x |
> | Email Opens | 5+ | +8 | 20% | 1.4x |
> | Source | Referral | +7 | 19% | 1.4x |
> | Page Views | 15+ | +5 | 18% | 1.3x |
>
> ## Thresholds
>
> | Tier | Score Range | Action | Historical Conv. |
> |---|---|---|---|
> | SQL | 40+ | Route to sales immediately | 42% |
> | MQL | 20-39 | Enter nurture sequence | 15% |
> | Cold | 0-19 | General marketing only | 3% |
>
> ## Validation
> - 89% of actual conversions scored as MQL or SQL
> - 78% of non-conversions scored as Cold
>
> Do these thresholds work for your sales team's capacity?

## Related Skills

- **[Lifecycle Stage Designer](./lifecycle-stage-designer.md)** — Map lead scores to pipeline stages for consistent MQL/SQL definitions.
- **[Predictive Lead Scoring](../ai-marketing/predictive-lead-scoring.md)** — Layer predictive modeling on top of rule-based scoring for more accurate prioritization.
- **[Automation Workflow Designer](./automation-workflow-designer.md)** — Use scoring thresholds as triggers for automated lead routing and nurture workflows.
- **[Data Enrichment Prioritizer](./data-enrichment-prioritizer.md)** — Prioritize data enrichment on high-scoring leads to improve conversion probability.
