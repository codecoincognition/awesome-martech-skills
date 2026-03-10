---
name: approval-bottleneck-analyzer
description: >
  Analyze marketing approval cycle times to identify bottlenecks, slow approvers, and process
  inefficiencies. Use this skill when the user says "why do approvals take so long", "approval
  bottleneck analysis", "speed up our review process", "who is slowing down approvals",
  "content approval analytics", "review cycle analysis", "approval workflow optimization",
  "reduce time-to-publish", "approval SLA tracking", "campaign launch delays", or "how long
  does content approval take". Also trigger when the user has approval timestamps from
  project management tools and wants to optimize the review process.
---

# Approval Bottleneck Analyzer

Analyzes marketing content approval cycle times from exported workflow data to identify bottlenecks, slow stages, and process improvement opportunities. Produces a data-backed report with specific recommendations to reduce time-to-publish.

## Granularity Check

> Can this be completed in a single Claude session? **Yes — expect ~5 min data prep + ~10 min Claude session.** If implementing output in a platform, add 10-20 min for setup. Input is a CSV of approval requests with timestamps. Output is an XLSX analysis report. No system access needed.

## User Intent Mapping

This skill should trigger when the user says things like:

- "Why does it take 2 weeks to get content approved?" (problem statement)
- "Analyze our approval cycle times" (direct request)
- "Which approval stage takes the longest?" (specific question)
- "Who is the bottleneck in our review process?" (accountability)
- "Help us speed up content publishing" (goal-oriented)
- "Our campaigns always launch late because of approvals" (symptom)
- "Compare approval times across content types" (comparative analysis)
- "Track our approval SLA compliance" (measurement)
- "How can we streamline our review workflow?" (process improvement)
- "Export from Monday/Asana — show me approval bottlenecks" (tool-specific)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Approval Data | CSV | Requests with columns: request_id, content_type, submitted_date, stage_name, stage_entered, stage_completed, approver |

### If You Don't Have This Data

- **No brand guidelines?** Document your current logo, colors (use a color picker on your website), and 3 tone-of-voice adjectives. That's a starting brand guide.
- **No asset inventory?** Search your Google Drive/Dropbox for common marketing file types (.pdf, .pptx, .png). The list IS your inventory.
- **No compliance checklist?** Start with industry basics: GDPR consent, CAN-SPAM footer, accessibility alt text. This skill helps you build the full checklist.
- **No vendor data?** List every tool your marketing team pays for. Include name, monthly cost, and primary user. That's your vendor inventory.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| SLA Targets | Text | Expected turnaround per stage (e.g., "legal review: 2 business days") |
| Priority Levels | CSV column | Request priority (urgent, standard, low) |
| Content Categories | CSV column | Blog, email, social, ad, landing page, press release |

### Sample Input CSV

```csv
request_id,content_type,submitted_date,stage_name,stage_entered,stage_completed,approver
REQ-001,blog,2025-09-01,copy_review,2025-09-01,2025-09-02,Sarah M.
REQ-001,blog,2025-09-01,legal_review,2025-09-02,2025-09-08,Legal Team
REQ-001,blog,2025-09-01,final_approval,2025-09-08,2025-09-09,VP Marketing
REQ-002,email,2025-09-03,copy_review,2025-09-03,2025-09-03,Sarah M.
REQ-002,email,2025-09-03,legal_review,2025-09-03,2025-09-10,Legal Team
```

## Process

### Step 1: Cycle Time Calculation
For each request, calculate:
- Total cycle time (submitted → final approval)
- Time per stage
- Wait time between stages (gaps)
- Business days vs. calendar days

### Step 2: Bottleneck Identification
Aggregate across all requests:
- Average time per stage (identify the slowest)
- Median vs. P90 times (detect outliers vs. systemic issues)
- Stage with highest variance (unpredictable = process problem)
- Approver-level analysis (who consistently takes longest)

### Step 3: Pattern Analysis
- **By content type**: Do emails get approved faster than blog posts?
- **By day of week**: Do Friday submissions stall over weekends?
- **By priority**: Do "urgent" requests actually move faster?
- **By volume**: Does approval time increase when volume spikes?
- **Sequential bottleneck**: Which stage causes the most downstream delay?

### Step 4: SLA Compliance
If targets provided:
- Compliance rate per stage
- Most-violated SLAs
- Trend over time (improving or worsening)

### Step 5: Recommendations
Based on data, recommend:
- Stages to parallelize (don't need to be sequential)
- Auto-approval candidates (low-risk content types)
- SLA adjustments (current targets unrealistic?)
- Staffing changes (bottleneck approver needs backup)
- Process changes (pre-approved templates, tiered review)


### Confidence & Sample Size
> **Confidence Note**: Results are only as reliable as your input data. Small datasets (<50 records or <30 days of data) produce directional insights, not statistically significant conclusions. Always note your sample size when sharing results with stakeholders. Recommendations should be validated with A/B testing or additional data before making major strategic changes.

### ⚠️ Human Checkpoint
> Review approver-level findings sensitively. Slow approvals may reflect workload, not negligence. Present as process improvement, not blame assignment.


> **Benchmark Context**: Average enterprise has 91 marketing tools in its stack. Brand compliance violations occur in 60% of co-branded partner materials. UTM tracking is implemented on only 40-50% of marketing URLs on average.

## Output Contract

### Deliverable: XLSX Report (3 sheets)

**Sheet 1: Summary Dashboard**

| Metric | Value |
|---|---|
| Avg Cycle Time | X business days |
| Median Cycle Time | X business days |
| P90 Cycle Time | X business days |
| Slowest Stage | [stage name] (avg X days) |
| SLA Compliance | X% |
| #1 Bottleneck | [stage or approver] |

**Sheet 2: Stage Analysis**
Columns: `stage_name | avg_days | median_days | p90_days | request_count | sla_target | compliance_rate | bottleneck_rank`

**Sheet 3: Recommendations**
Columns: `priority | recommendation | expected_time_savings | effort | details`

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
| Incomplete timestamps | Some stages missing completion dates | Analyze what's available, note gaps, estimate from averages |
| Too few data points | Less than 20 requests | Note small sample size, provide directional insights only |
| Single-stage workflow | No multi-stage data | Calculate overall cycle time trends, skip stage analysis |
| Inconsistent stage names | "Legal" vs "legal_review" vs "Legal Review" | Normalize names, ask user to confirm groupings |

## How to Get Your Data

- **Asana**: Project → Export → CSV (include custom fields for stages/dates)
- **Monday.com**: Board → Export to Excel
- **Jira**: Filter → Export (include status change history)
- **Trello**: Use Butler or export via Power-Up
- **Wrike**: Reports → Export
- **Manual**: Create a simple spreadsheet tracking request_id, stage, entered_date, completed_date

## Example

**Input**: 87 content approval requests over Q3 2025, 3-stage workflow (copy review → legal review → final approval).

**Output**: Average cycle time 6.2 business days. Legal review is the #1 bottleneck (avg 4.1 days, 66% of total cycle time, only 31% SLA compliant at 2-day target). Copy review averages 0.8 days (efficient). Friday submissions take 2.3 days longer on average. Top recommendations: (1) Pre-approved legal templates for standard content types (estimated 60% volume reduction for legal). (2) Add backup legal reviewer (current single-person bottleneck). (3) Move to parallel review for copy + legal on low-risk content.
