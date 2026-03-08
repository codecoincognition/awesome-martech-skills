---
name: sla-document-generator
description: >
  Generate a marketing-sales SLA document defining lead definitions, handoff criteria, response
  times, and accountability metrics. Use this skill when the user says "create a marketing-sales
  SLA", "define lead handoff process", "sales and marketing alignment document", "SLA between
  marketing and sales", "lead response time agreement", "define MQL and SQL criteria",
  "marketing-sales handoff rules", "service level agreement for leads", "sales follow-up SLA",
  or "align sales and marketing on lead definitions". Also trigger when teams are arguing about
  lead quality or follow-up speed.
---

# SLA Document Generator

Generates a formal Marketing-Sales SLA document that defines lead stages, qualification criteria, handoff processes, response time commitments, and mutual accountability metrics.

## Granularity Check

> Can this be completed in a single 10-minute Claude session? **Yes.** Input is business context and team preferences. Output is a Markdown SLA document. No system access needed.

## User Intent Mapping

This skill should trigger when the user says things like:

- "Create an SLA between marketing and sales" (direct request)
- "Define what an MQL vs SQL means for our team" (definition work)
- "Sales complains about lead quality — help us fix this" (problem statement)
- "How fast should sales follow up on leads?" (process question)
- "Document our lead handoff process" (documentation)
- "Marketing and sales aren't aligned — we need an SLA" (alignment need)
- "What should our lead response time commitment be?" (benchmark question)
- "Create lead scoring criteria for handoff" (scoring framework)
- "Define lead stages from subscriber to customer" (lifecycle mapping)
- "Build accountability metrics for both teams" (mutual accountability)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Business Type | Text | B2B/B2C, industry, sales model (self-serve, inside sales, field sales) |
| Current Lead Volume | Text | Approximate monthly leads and conversion rates if known |

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Current Pain Points | Text | What's broken (e.g., "sales ignores leads", "marketing sends junk") |
| Sales Cycle Length | Text | Average days from lead to close |
| CRM Platform | Text | HubSpot, Salesforce, etc. (for implementation notes) |
| Existing Definitions | Text | Any current MQL/SQL definitions to refine |
| Team Size | Text | Marketing and sales headcount (affects response time feasibility) |

## Process

### Step 1: Define Lead Lifecycle Stages
Define each stage with clear entry/exit criteria:
- **Subscriber**: Opted in but no engagement signal
- **Lead**: Known contact with basic demographic fit
- **MQL (Marketing Qualified Lead)**: Meets marketing's behavioral + demographic thresholds
- **SAL (Sales Accepted Lead)**: Sales has reviewed and accepted the MQL
- **SQL (Sales Qualified Lead)**: Sales has qualified via discovery conversation
- **Opportunity**: Active deal in pipeline
- **Customer**: Closed-won

### Step 2: Qualification Criteria
For MQL → SAL handoff, define:
- Demographic fit criteria (title, company size, industry)
- Behavioral signals (pages visited, content downloaded, email engagement)
- Minimum lead score threshold
- Disqualification criteria (competitor, student, wrong geography)

### Step 3: Response Time Commitments

| Lead Type | Response SLA | Escalation |
|---|---|---|
| Inbound Demo Request | ≤ 5 minutes (business hours) | Auto-reassign after 15 min |
| MQL (High Score) | ≤ 1 hour | Escalate to manager after 2 hours |
| MQL (Standard) | ≤ 4 hours | Escalate after 8 hours |
| Recycled Lead | ≤ 24 hours | Weekly review |

### Step 4: Mutual Commitments
**Marketing commits to:**
- Lead volume targets (monthly MQL goal)
- Lead quality standards (minimum qualification criteria)
- Lead data completeness (required fields populated)
- SLA compliance reporting

**Sales commits to:**
- Response time adherence
- Follow-up attempt minimums (e.g., 6 touches in 14 days)
- Disposition/feedback on every MQL (accepted, rejected + reason, recycled)
- CRM data hygiene (update stages, log activities)

### Step 5: Accountability & Reporting
Define review cadence and metrics:
- Weekly: MQL volume, response time compliance, acceptance rate
- Monthly: MQL-to-SQL conversion, pipeline contribution, SLA violations
- Quarterly: Full SLA review, target adjustments

### ⚠️ Human Checkpoint
> Both marketing and sales leadership must review and agree to the SLA. A one-sided SLA will fail. Schedule a joint review meeting before finalizing.

## Output Contract

### Deliverable: Markdown SLA Document

```markdown
# Marketing-Sales Service Level Agreement

## Effective Date: [date]
## Review Cadence: Quarterly

## 1. Purpose
[1-2 paragraphs on why this SLA exists]

## 2. Lead Lifecycle Definitions
[Table: Stage | Definition | Entry Criteria | Exit Criteria | Owner]

## 3. MQL Qualification Criteria
### Demographic Fit
[Criteria list]
### Behavioral Signals
[Criteria list]
### Disqualification Criteria
[Criteria list]

## 4. Handoff Process
[Step-by-step handoff workflow]

## 5. Response Time Commitments
[Table: Lead Type | SLA | Escalation Path]

## 6. Marketing Commitments
[Numbered list with measurable targets]

## 7. Sales Commitments
[Numbered list with measurable targets]

## 8. Reporting & Accountability
[Cadence, metrics, review process]

## 9. Dispute Resolution
[Process for disagreements]

## 10. Signatures
[Placeholder for marketing + sales leadership sign-off]
```

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| No current data | User doesn't know conversion rates | Use industry benchmarks, build measurement-first |
| One-sided request | Only marketing or sales is asking | Note that both teams must agree, draft for joint review |
| Overly ambitious SLAs | 5-minute response with 2-person sales team | Reality-check against headcount and capacity |
| No CRM | Team uses spreadsheets | Include manual tracking process, recommend CRM adoption |

## How to Get Your Data

No data export needed. Bring:
- Your current lead definitions (even informal ones)
- Monthly lead volume estimates
- Known pain points between marketing and sales
- Sales team size and current response time estimates
- CRM platform name (for implementation notes)

## Example

**Input**: B2B SaaS, inside sales model, ~200 MQLs/month, 45-day sales cycle, HubSpot CRM. Pain point: "Sales says 60% of MQLs are junk. Marketing says sales doesn't follow up fast enough."

**Output**: Full SLA document with tightened MQL criteria (added minimum company size and removed single-page-visit leads), 1-hour response time for high-score MQLs, mandatory disposition logging within 48 hours, weekly alignment meeting, shared dashboard with MQL acceptance rate and response time metrics. Marketing commits to 200 MQLs/month at 50%+ acceptance rate. Sales commits to 95% response time compliance and 6-touch follow-up sequence.
