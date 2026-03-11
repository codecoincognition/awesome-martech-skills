---
name: crm-data-hygiene-auditor
description: >
  Audit CRM data for duplicates, missing fields, stale records, inconsistent formatting, and
  data decay — then produce a prioritized cleanup action plan. Use this skill when the user says
  "clean up my CRM", "audit CRM data quality", "find duplicate contacts", "CRM hygiene check",
  "deduplicate my leads", "data quality audit", "fix CRM data", "lead data cleanup",
  "how dirty is my CRM data", "CRM deduplication strategy", "enrich or clean my contact list",
  or "data decay report". Also trigger when the user has a HubSpot, Salesforce, or Pipedrive
  export and wants to assess or improve data quality.
---

> **How this skill works:** You export your CRM data (HubSpot, Salesforce, Pipedrive, etc.) as a CSV, paste or attach it, and Claude analyzes it. Claude cannot connect to live CRMs or pull data directly — you bring the data, Claude brings the analysis.

# CRM Data Hygiene Auditor

Audits a CRM contact/lead export for data quality issues — duplicates, missing required fields, stale records, formatting inconsistencies, and data decay patterns. Produces a scored health report with a prioritized remediation plan.

## Granularity Check

> Can this be completed in a single Claude session? **Yes — expect ~5 min data prep → ~10 min Claude session → ~30-60 min configuring in Salesforce / HubSpot.** If implementing output in a platform, add 10-20 min for setup. Input is a CSV export. Output is an XLSX audit report. No CRM API access needed.

## User Intent Mapping

This skill should trigger when the user says things like:

- "Audit my HubSpot contact data quality" (tool-specific)
- "How many duplicate contacts do we have?" (quantitative)
- "Clean up our Salesforce leads before the migration" (pre-migration)
- "Find and merge duplicate records" (dedup strategy)
- "What percentage of our contacts have valid emails?" (field completeness)
- "Our CRM data is a mess — where do we start?" (problem statement)
- "Data hygiene check before we launch the campaign" (pre-campaign QA)
- "Which contacts should we prioritize for enrichment?" (enrichment planning)
- "Identify stale leads we should archive" (lifecycle management)
- "Score our data quality across all fields" (health score)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| CRM Export | CSV | Contact/lead export with columns like: email, first_name, last_name, company, phone, created_date, last_activity_date, lifecycle_stage, owner |

### If You Don't Have This Data

- **No CRM export?** Create a simple spreadsheet with columns: Name, Email, Company, Stage, Last Contact Date. Even 50 records work.
- **No lead scores?** Use lifecycle stage as a proxy: Customer > Opportunity > SQL > MQL > Lead > Subscriber.
- **No enrichment budget?** This skill helps you prioritize so you can make the case for budget. Start with the output.
- **No ICP definition?** Look at your best 5 customers — what industry, size, and title do they share? That's your starting ICP.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Required Fields | Text list | Fields that must be populated for a record to be "complete" |
| Dedup Rules | Text | Match criteria (e.g., "email exact match" or "company + last name fuzzy") |
| Stale Threshold | Number | Days since last activity to flag as stale (default: 180) |
| Record Value Tier | CSV column | Lead score or deal value to prioritize high-value record cleanup |

### Sample Input CSV

```csv
email,first_name,last_name,company,phone,created_date,last_activity_date,lifecycle_stage,lead_source
john.doe@acme.com,John,Doe,Acme Inc,(555) 123-4567,2024-01-15,2025-08-20,customer,webinar
j.doe@acme.com,J,Doe,ACME,555.123.4567,2024-06-01,2024-06-01,lead,website
,Jane,,Smith Corp,,2023-03-10,2023-03-10,subscriber,import
sarah@,,Wilson,tech startup,n/a,2025-01-01,2025-09-15,mql,linkedin
MIKE@BIGCO.COM,mike,Johnson,BigCo Inc.,555-999-8888,2024-11-01,2025-09-01,sql,referral
```

## Process

### Step 1: Field Completeness Audit
For each column, calculate:
- Population rate (% non-empty)
- Validity rate (% properly formatted — email regex, phone format, date parsing)
- Unique value count
- Most common values (detect "test", "n/a", "unknown" as pseudo-blanks)

### Step 2: Duplicate Detection
Apply matching rules in priority order:
1. **Exact email match** (highest confidence)
2. **Email domain + last name match** (high confidence)
3. **Company name + first name fuzzy match** (medium confidence — flag for review)
4. **Phone number normalization match** (strip formatting, compare digits)

Group duplicates and identify the "master" record (most complete, most recent activity).

### Step 3: Formatting Consistency
- **Email**: lowercase normalization, domain validation
- **Phone**: detect mixed formats, propose standard (E.164 or national)
- **Company**: case inconsistencies ("Acme" vs "ACME" vs "acme inc")
- **Names**: capitalization, initials vs full names
- **Dates**: mixed formats (MM/DD vs DD/MM vs ISO)
- **Lifecycle stages**: inconsistent values ("MQL" vs "mql" vs "Marketing Qualified")

### Step 4: Data Decay Analysis
- Flag records with no activity in [stale_threshold] days
- Calculate decay rate (% of records going stale per quarter)
- Identify "zombie" records (created but never engaged)
- Segment staleness by lifecycle stage and lead source

### Step 5: Enrichment Prioritization
Score each incomplete record by enrichment priority:
- High: active lifecycle stage + missing key fields + high lead score
- Medium: recent creation + missing some fields
- Low: stale record + missing fields (archive, don't enrich)


### Confidence & Sample Size
> **Confidence Note**: Results are only as reliable as your input data. Small datasets (<50 records or <30 days of data) produce directional insights, not statistically significant conclusions. Always note your sample size when sharing results with stakeholders. Recommendations should be validated with A/B testing or additional data before making major strategic changes.

### ⚠️ Human Checkpoint
> Review duplicate groups before merging. Confirm merge rules (which record becomes master, which fields survive). Never auto-merge without human approval.


> **Benchmark Context**: Consult current industry reports for up-to-date benchmarks relevant to this analysis.

## Output Contract

### Deliverable: Markdown Tables + CSV-Ready Data (4 sections)

**Section 1: Health Score Dashboard**

| Metric | Value | Grade |
|---|---|---|
| Overall Health Score | X/100 | A/B/C/D/F |
| Field Completeness | percentage | |
| Duplicate Rate | percentage | |
| Stale Record Rate | percentage | |
| Format Consistency | percentage | |
| Estimated Addressable Records | count | |

**Section 2: Field-Level Analysis**
Markdown table: `field_name | population_rate | validity_rate | common_issues | fix_recommendation`

Can be pasted into Google Sheets or Excel.

**Section 3: Duplicate Groups**
Markdown table: `group_id | match_type | confidence | email | name | company | last_activity | recommended_master | action`

**Section 4: Remediation Plan**
Markdown table: `priority | action | record_count | estimated_effort | expected_impact | instructions`

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
| Minimal columns | Export has only email + name | Audit what's available, note limited scope |
| Huge export (50k+ rows) | Too many records for single session | Sample 5000 rows (stratified by lifecycle stage), extrapolate |
| No activity dates | CRM doesn't track engagement | Skip decay analysis, note limitation |
| Non-standard CRM | Custom fields with no obvious mapping | Ask user to identify key fields |

## How to Get Your Data

- **HubSpot**: Contacts → Actions → Export → All properties
- **Salesforce**: Reports → Contacts/Leads → Export Details
- **Pipedrive**: Contacts → Export to Spreadsheet
- **Zoho CRM**: Leads/Contacts → Actions → Export
- **ActiveCampaign**: Contacts → Export
- **CSV/Excel**: Any contact list with at minimum email + name columns

## Example

**Input**: 3,200-row HubSpot contact export with 15 columns.

**Output**: Health score 58/100 (Grade C). Field completeness 72% (phone missing on 43% of records, company missing on 18%). 127 duplicate groups detected (89 exact email, 38 fuzzy). 34% of records stale (no activity in 180+ days). Formatting issues: 5 phone formats detected, 3 company name case variants for top accounts. Remediation plan: (1) Merge 89 exact-match duplicate groups. (2) Archive 412 zombie records (created 12+ months ago, never engaged). (3) Standardize phone format to (XXX) XXX-XXXX. (4) Enrich 156 high-priority records (active MQLs missing company/phone).

## Related Skills

- **[Data Enrichment Prioritizer](./data-enrichment-prioritizer.md)** — After auditing data quality, use to prioritize which contacts to enrich for maximum ROI.
- **[Lead Scoring Model Builder](./lead-scoring-model-builder.md)** — Clean data quality issues before building scoring models to ensure accuracy.
- **[Segmentation Rule Builder](./segmentation-rule-builder.md)** — Fix data issues that prevent accurate segment creation and maintenance.
- **[Digital Asset Audit Report](../martech-ops/digital-asset-audit-report.md)** — Apply similar audit methodology to your marketing asset library.
