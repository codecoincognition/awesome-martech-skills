---
name: digital-asset-audit-report
description: >
  Audit a digital asset library for naming inconsistencies, missing metadata, duplicates, and
  organization gaps. Use this skill when the user says "audit my asset library", "clean up my
  DAM", "organize my marketing assets", "find duplicate assets", "asset inventory audit",
  "check asset naming conventions", "review asset metadata", "digital asset management cleanup",
  "asset library health check", or "how messy is my asset library". Also trigger when the user
  has a CSV export from a DAM (Bynder, Brandfolder, Canto, Google Drive) and wants to assess quality.
---

> **How this skill works:** You export your digital asset inventory (from DAM systems, shared drives, or other platforms) as a CSV or provide a list, and Claude audits it. Claude cannot connect to live asset management systems or pull data directly — you bring the data, Claude brings the analysis.

# Digital Asset Audit Report

Audits an exported digital asset inventory for naming convention violations, missing metadata, potential duplicates, orphaned files, and organizational gaps. Produces a prioritized cleanup action plan.

## Granularity Check

> Can this be completed in a single Claude session? **Yes — expect ~5 min data prep + ~10 min Claude session.** If implementing output in a platform, add 10-20 min for setup. Input is a CSV of asset metadata. Output is an XLSX audit report. No system access needed — works entirely from exported data.

## User Intent Mapping

This skill should trigger when the user says things like:

- "Audit my marketing asset library" (direct command)
- "I exported my DAM inventory, help me clean it up" (tool-specific)
- "Find duplicate and orphaned assets" (specific task)
- "Are our assets properly tagged and named?" (quality check)
- "We're migrating DAMs — what needs cleanup first?" (migration prep)
- "How many assets are missing metadata?" (quantitative question)
- "Our naming conventions are a mess" (problem statement)
- "Asset library health check before rebrand" (pre-project audit)
- "Which assets should we archive or delete?" (lifecycle management)
- "Review our Google Drive marketing folder structure" (organization)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Asset Inventory | CSV | Exported asset list with columns: filename, file_type, folder_path, created_date, modified_date |

### If You Don't Have This Data

- **No brand guidelines?** Document your current logo, colors (use a color picker on your website), and 3 tone-of-voice adjectives. That's a starting brand guide.
- **No asset inventory?** Search your Google Drive/Dropbox for common marketing file types (.pdf, .pptx, .png). The list IS your inventory.
- **No compliance checklist?** Start with industry basics: GDPR consent, CAN-SPAM footer, accessibility alt text. This skill helps you build the full checklist.
- **No vendor data?** List every tool your marketing team pays for. Include name, monthly cost, and primary user. That's your vendor inventory.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Naming Convention | Text | Expected pattern (e.g., "YYYY-MM_campaign-name_asset-type_version") |
| Required Metadata | Text | Fields every asset should have (e.g., campaign, channel, expiry date) |
| Active Campaigns | Text | List of current campaigns to identify orphaned assets |
| Tags/Categories | CSV column | Existing taxonomy to audit completeness |

### Sample Input CSV

```csv
filename,file_type,folder_path,created_date,modified_date,tags,campaign
hero-banner-v3-FINAL.png,image,/marketing/campaigns/q1-launch,2025-09-15,2025-09-20,banner;launch,Q1 Launch
logo_new_blue (1).svg,image,/marketing/brand,2024-03-01,2024-03-01,,
Q4-email-header.jpg,image,/marketing/email,2025-11-01,2025-11-15,email,
FB_ad_creative_DRAFT_old.psd,image,/marketing/social/facebook,2024-06-10,2024-06-10,social;facebook,Summer Sale
hero-banner-v3-FINAL-v2.png,image,/marketing/campaigns/q1-launch,2025-09-22,2025-09-22,banner;launch,Q1 Launch
```

## Process

### Step 1: Naming Convention Analysis
- Parse all filenames and detect patterns
- Identify violations: spaces, special characters, inconsistent casing, version confusion ("FINAL-v2"), duplicate suffixes ("(1)")
- Calculate naming compliance percentage
- Suggest a standardized naming convention if none provided

### Step 2: Metadata Completeness
- Check each required metadata field for population
- Calculate fill rates per field
- Identify assets with zero metadata (high-risk)
- Flag inconsistent taxonomy (e.g., "social" vs "Social" vs "social-media")

### Step 3: Duplicate Detection
- Flag exact filename matches in different folders
- Identify near-duplicates (same base name + version suffix variations)
- Group suspected duplicates for human review
- Estimate storage waste from duplicates

### Step 4: Lifecycle Analysis
- Flag assets not modified in 12+ months as stale
- Identify assets with no campaign association (orphaned)
- Check for draft/temp files that were never finalized
- Calculate age distribution of asset library

### Step 5: Organization Assessment
- Analyze folder structure depth and consistency
- Identify folders with 50+ files (needs subfolder structure)
- Flag empty folders
- Check for logical grouping (by campaign vs. by asset type vs. by channel)


### Confidence & Sample Size
> **Confidence Note**: Results are only as reliable as your input data. Small datasets (<50 records or <30 days of data) produce directional insights, not statistically significant conclusions. Always note your sample size when sharing results with stakeholders. Recommendations should be validated with A/B testing or additional data before making major strategic changes.

### ⚠️ Human Checkpoint
> Review duplicate groups before bulk action — some "duplicates" may be intentional variants (e.g., localized versions, A/B test variants).


> **Benchmark Context**: Average enterprise has 91 marketing tools in its stack. Brand compliance violations occur in 60% of co-branded partner materials. UTM tracking is implemented on only 40-50% of marketing URLs on average.

## Output Contract

### Deliverable: Structured Analysis Tables in Markdown

Claude generates three detailed analysis tables in Markdown format that you can copy directly into Google Sheets, Excel, or any spreadsheet tool

**Table 1: Audit Summary**

| Metric | Value | Status |
|---|---|---|
| Total Assets | count | — |
| Naming Compliance | percentage | ✅/❌ |
| Metadata Completeness | percentage | ✅/❌ |
| Suspected Duplicates | count (groups) | ⚠️ |
| Stale Assets (12+ months) | count | ⚠️ |
| Orphaned Assets | count | ⚠️ |

**Table 2: Issue Details**
Columns: `filename | issue_type | severity | description | recommended_action | new_filename`

**Table 3: Action Plan**
Columns: `priority | action | asset_count | effort_estimate | impact`

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
| Sparse CSV | Export has only filename + path, no metadata | Audit what's available, note which analyses couldn't run |
| No naming convention provided | User doesn't have standards documented | Infer patterns from existing names, propose a convention |
| Massive inventory (10k+ rows) | CSV too large for single session | Sample first 2000 rows, extrapolate findings, note limitation |
| Non-standard folder structure | Flat dump with no hierarchy | Propose a folder taxonomy based on detected patterns |

## How to Get Your Data

- **Bynder**: Admin → Reports → Asset Export
- **Brandfolder**: Collection → Export Metadata as CSV
- **Google Drive**: Use Google Takeout or a Drive inventory script
- **SharePoint**: Site Contents → Export to Excel
- **Manual**: Run `find /marketing -type f > asset_list.txt` on your file server

## Example

**Input**: 847-row CSV export from Google Drive marketing folder. No naming convention defined.

**Output**: XLSX showing 73% naming compliance (detected pattern: lowercase-kebab-case), 45% metadata completeness (tags missing on 466 files), 23 duplicate groups (estimated 340MB recoverable), 189 stale assets (not touched since 2024), 67 orphaned files with no campaign tag. Action plan: (1) De-duplicate — 23 groups, save 340MB. (2) Archive 189 stale assets. (3) Backfill tags on 466 files. (4) Adopt naming convention: `YYYY-MM_campaign_type_variant.ext`.
