---
name: data-enrichment-prioritizer
description: >
  Score and rank CRM records by enrichment priority — which contacts and accounts to enrich
  first based on value signals, data gaps, and business impact. Use this skill when the user
  says "which leads should I enrich first", "prioritize enrichment", "enrichment budget allocation",
  "rank contacts for data enrichment", "who should we enrich", "data enrichment ROI",
  "enrichment strategy", "maximize enrichment spend", "which accounts need more data",
  or "smart enrichment prioritization". Also trigger when the user has limited enrichment
  credits (Clearbit, ZoomInfo, Apollo) and needs to decide where to spend them.
---

# Data Enrichment Prioritizer

Scores and ranks CRM records by enrichment priority to maximize ROI on enrichment credits. Combines data gap analysis with value signals to ensure enrichment spend goes to the contacts and accounts most likely to convert.

## Granularity Check

> Can this be completed in a single Claude session? **Yes — expect ~5 min data prep + ~10 min Claude session.** If implementing output in a platform, add 10-20 min for setup. Input is a CRM export CSV. Output is an XLSX with scored records. No enrichment API calls needed — this is the prioritization step before enrichment.

## User Intent Mapping

This skill should trigger when the user says things like:

- "We have 500 ZoomInfo credits — who should we enrich?" (budget constraint)
- "Prioritize our contact list for Clearbit enrichment" (tool-specific)
- "Which accounts are worth enriching?" (strategic question)
- "Rank our leads by enrichment ROI potential" (ROI focus)
- "We imported 2000 leads — which ones need enrichment first?" (post-import)
- "Our enrichment budget is limited, help me allocate it" (resource planning)
- "Find high-value leads with missing data" (gap + value intersection)
- "Enrichment strategy for our MQL-to-SQL pipeline" (funnel-specific)
- "Which fields should we prioritize enriching?" (field-level strategy)
- "Score contacts for Apollo enrichment" (tool-specific)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| CRM Export | CSV | Contacts/leads with available fields: email, name, company, lifecycle_stage, lead_score, created_date, last_activity |

### If You Don't Have This Data

- **No CRM export?** Create a simple spreadsheet with columns: Name, Email, Company, Stage, Last Contact Date. Even 50 records work.
- **No lead scores?** Use lifecycle stage as a proxy: Customer > Opportunity > SQL > MQL > Lead > Subscriber.
- **No enrichment budget?** This skill helps you prioritize so you can make the case for budget. Start with the output.
- **No ICP definition?** Look at your best 5 customers — what industry, size, and title do they share? That's your starting ICP.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Enrichment Budget | Number | Available credits or dollar budget |
| Cost Per Enrichment | Number | Price per record enrichment (default: $0.25) |
| Priority Fields | Text list | Which missing fields matter most (e.g., "phone, company_size, industry") |
| ICP Criteria | Text | Ideal customer profile for relevance scoring |
| Revenue Data | CSV column | Deal value or account revenue for value weighting |

## Process

### Step 1: Data Gap Scoring
For each record, calculate a gap score (0-100) based on:
- Number of empty fields vs. total available fields
- Weighted by field importance (email = critical, phone = high, industry = medium, etc.)
- Flag records with zero enrichable data (email-only) vs. partial data

### Step 2: Value Signal Scoring
Score each record's business potential (0-100):
- Lifecycle stage weight (SQL > MQL > Lead > Subscriber)
- Lead score (if available)
- Recency of engagement (active > dormant)
- Deal value or account revenue (if available)
- ICP fit signals (company domain, title keywords)

### Step 3: Enrichment Priority Score
Combine scores: `Priority = (Value Score × 0.6) + (Gap Score × 0.4)`

Logic: High-value records with data gaps get enriched first. Low-value records with gaps get deprioritized regardless of incompleteness.

### Step 4: Budget Allocation
- Rank all records by priority score
- Apply budget constraint (top N records based on credits/budget)
- Group into tiers: Tier 1 (enrich immediately), Tier 2 (next budget cycle), Tier 3 (skip/archive)
- Calculate expected ROI per tier

### Step 5: Field Prioritization
Across the dataset, recommend which fields to enrich first:
- Rank fields by: (missing rate) × (impact on sales workflow)
- Example: "Phone number is missing on 65% of SQLs — enriching this field alone would enable outbound calling for 340 records"


### Confidence & Sample Size
> **Confidence Note**: Results are only as reliable as your input data. Small datasets (<50 records or <30 days of data) produce directional insights, not statistically significant conclusions. Always note your sample size when sharing results with stakeholders. Recommendations should be validated with A/B testing or additional data before making major strategic changes.

### ⚠️ Human Checkpoint
> Review Tier 1 list before spending enrichment credits. Confirm ICP criteria are correct — bad ICP definition wastes budget on wrong-fit leads.


> **Benchmark Context**: Average CRM data decay rate is 30% per year. Enriched leads convert at 2-3x the rate of non-enriched leads. Data enrichment typically costs $0.10-$0.50 per record depending on provider and depth.

## Output Contract

### Deliverable: XLSX (3 sheets)

**Sheet 1: Prioritized Records**
Columns: `email | name | company | lifecycle_stage | value_score | gap_score | priority_score | tier | fields_to_enrich | estimated_cost`

**Sheet 2: Budget Summary**

| Metric | Value |
|---|---|
| Total Records | count |
| Tier 1 (Enrich Now) | count |
| Tier 2 (Next Cycle) | count |
| Tier 3 (Skip) | count |
| Estimated Cost (Tier 1) | $ |
| Expected Enriched Conversion Rate Lift | % |

**Sheet 3: Field Priority**
Columns: `field_name | missing_rate | impact_score | priority_rank | records_affected | estimated_value_unlocked`

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
| No value signals | CSV has no lead score, lifecycle, or revenue data | Use recency and completeness only, note limited prioritization |
| All records equally incomplete | Uniform data gaps | Prioritize by value signals alone |
| No ICP defined | User can't articulate ideal customer | Use lifecycle stage and engagement as proxy for value |
| Tiny dataset (<50 records) | Not enough to justify prioritization | Recommend enriching all — cost is minimal |

## How to Get Your Data

- **HubSpot**: Contacts → Export → Select all properties
- **Salesforce**: Reports → Leads/Contacts → Export
- **Apollo**: Saved lists → Export
- **Clearbit/ZoomInfo**: Check your current credit balance in account settings
- **Any CRM**: Export contacts as CSV with all available fields

## Example

**Input**: 2,400 contacts from HubSpot. 500 ZoomInfo credits available at $0.30/record. ICP: B2B SaaS, 50-500 employees, North America.

**Output**: Tier 1: 500 records (enrich now, $150 budget). These are 280 MQLs + 220 SQLs missing phone and company size. Tier 2: 800 records (next cycle, $240). Tier 3: 1,100 records (skip — subscribers with low engagement, stale leads). Top field to enrich: direct phone (missing on 72% of Tier 1, enables SDR outreach). Expected lift: enriching Tier 1 phone numbers could increase SQL-to-meeting rate by 15-25% based on typical outbound benchmarks.
