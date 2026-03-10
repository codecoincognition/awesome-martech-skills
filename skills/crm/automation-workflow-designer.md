---
name: automation-workflow-designer
description: >
  Design CRM automation workflows for lead nurturing, task management, notifications, and data operations.
  Use this skill when the user says "CRM automation workflow", "marketing automation design", "workflow
  builder strategy", "automated lead nurturing", "CRM workflow optimization", "automation rules design",
  "trigger-based automation", "if-then workflow logic", "HubSpot workflow design", "Salesforce flow design",
  or "CRM automation audit". Also trigger for drip campaign automation, task automation, or notification
  workflow design.
---

# Automation Workflow Designer

Designs CRM automation workflows including triggers, conditions, actions, and branching logic for lead nurturing, internal operations, and customer lifecycle management.

## Granularity Check

> **Session time**: ~5 min context gathering + ~10 min Claude session. If implementing, add 2-8 hours per workflow in CRM. Input is business process description and CRM platform. Output is Markdown workflow design with trigger/action specifications and implementation guide.

## User Intent Mapping

- "Design a lead nurture workflow" (nurture)
- "Automate our CRM processes" (general)
- "What workflows should we build?" (strategy)
- "Workflow for new lead follow-up" (lead)
- "Automate internal notifications" (notifications)
- "Customer onboarding automation" (onboarding)
- "Re-engagement workflow for cold leads" (re-engagement)
- "Workflow audit — what's broken?" (audit)
- "Too many manual tasks in our CRM" (efficiency)
- "HubSpot/Salesforce workflow design" (platform-specific)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| CRM Platform | Text | HubSpot, Salesforce, ActiveCampaign, etc. |
| Process to Automate | Text | What manual process to replace or optimize |
| Goals | Text | What the automation should achieve |

### If You Don't Have This Data

- **Not sure what to automate?** Claude audits common CRM processes and identifies the highest-ROI automation opportunities for your business.
- **No workflows exist yet?** Claude designs a starter automation stack (5-7 essential workflows) for your business type.
- **Current workflows are broken?** Claude reviews your workflow descriptions and identifies logic errors, gaps, and optimization opportunities.
- **Don't know CRM capabilities?** Claude designs workflows within your platform's automation capabilities and flags where you might need third-party tools.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Current Workflows | Text | Existing automations and their logic |
| Team Structure | Text | Who handles what in the process |
| Lead Volume | Text | Monthly leads or contacts processed |
| Pain Points | Text | Where manual processes cause problems |
| Integration Stack | Text | Tools connected to CRM |

## Process

### Step 1: Automation Opportunity Assessment
| Category | Example Workflows | ROI Potential |
|---|---|---|
| Lead management | New lead assignment, scoring updates, stage transitions | High |
| Nurturing | Email sequences, content delivery, re-engagement | High |
| Internal ops | Task creation, notifications, data updates | Medium-High |
| Customer lifecycle | Onboarding, health monitoring, renewal reminders | High |
| Data hygiene | Duplicate detection, field standardization, decay management | Medium |

### Step 2: Workflow Design Framework
Per workflow:
- **Name**: Clear, descriptive name
- **Trigger**: What starts the workflow (form submission, property change, date, list membership)
- **Enrollment criteria**: Who qualifies (include + exclude conditions)
- **Re-enrollment**: Can contacts go through this workflow again?
- **Actions**: Step-by-step sequence with timing
- **Branching**: If/then conditions for different paths
- **Exit criteria**: When/why a contact leaves the workflow
- **Goal**: How you measure success

### Step 3: Essential Workflow Stack
| Workflow | Trigger | Key Actions | Priority |
|---|---|---|---|
| New lead welcome | Form submission | Welcome email → assign owner → create task | P0 |
| MQL notification | Lead score threshold | Notify sales → create task → update stage | P0 |
| Lead nurture | MQL not contacted in 48h | Email sequence (3-5 emails over 2 weeks) | P0 |
| Re-engagement | No activity 60 days | Re-engagement email → if no response → cold segment | P1 |
| Customer onboarding | Deal closed-won | Welcome email → onboarding tasks → check-in sequence | P0 |
| Renewal reminder | 90 days before renewal | Notify CSM → email customer → create renewal task | P1 |
| Deal stale alert | No activity on deal 14 days | Notify AE → manager escalation at 21 days | P1 |
| Data cleanup | Duplicate detected | Merge notification → assign cleanup task | P2 |

### Step 4: Branching Logic Design
```
IF [condition]
  THEN [action A]
  ELSE
    IF [condition B]
      THEN [action B]
    ELSE
      [default action]
```

Common branching patterns:
- Engagement branch: if opened email → send next content; if not → send reminder
- Qualification branch: if meets MQL criteria → notify sales; if not → continue nurture
- Segment branch: if enterprise → route to AE team; if SMB → route to self-serve
- Response branch: if replied → stop automation, alert owner; if no reply → next step

### Step 5: Timing & Delays
| Workflow Type | Recommended Timing |
|---|---|
| Welcome/transactional | Immediate (no delay) |
| Nurture sequence | 2-3 days between emails |
| Re-engagement | 7 days between attempts |
| Internal notifications | Immediate or within 1 hour |
| Escalations | 24-48 hours after initial alert |
| Follow-up reminders | 3-5 days after task creation |

### Step 6: Testing & Monitoring
- Test every workflow with a test contact before activation
- Monitor enrollment rates (too high = criteria too broad, too low = criteria too narrow)
- Check email deliverability within workflow sequences
- Review branching paths — ensure all branches have actions
- Monitor exit criteria — contacts shouldn't get stuck
- Set up workflow performance dashboard

### Confidence & Sample Size

> **Confidence Note**: Start with 5-7 essential workflows before building complex automation. Each workflow should solve one clear problem. Over-automation creates maintenance burden — every workflow needs monitoring and updating. Workflows with 10+ steps have higher failure rates — keep them focused. Test workflows with 50-100 contacts before full activation. The most common workflow failure is incorrect branching logic — map every possible path before building.

### ⚠️ Human Checkpoint
> Test all workflows with internal contacts before activating for real leads/customers. Review email content in workflow sequences for accuracy and brand consistency. Verify timing and delays work as expected across time zones. Check that workflows don't conflict with each other (e.g., contact enrolled in two competing sequences).

> **Benchmark Context**: Marketing automation increases sales productivity by 14.5% and reduces overhead by 12.2%. Companies using lead nurture workflows generate 50% more sales-ready leads at 33% lower cost. Automated email workflows have 70.5% higher open rates than one-off emails. 80% of automation users see increased leads, 77% see increased conversions. The average company automates only 25% of automatable marketing processes.

## Output Contract

### Deliverable: Markdown Workflow Design

```markdown
# CRM Automation Workflows: [Company]

## Workflow Architecture
| Workflow | Category | Trigger | Priority | Status |
|---|---|---|---|---|

## Workflow 1: [Name]
### Overview
- Purpose: [what it does]
- Trigger: [what starts it]
- Enrollment: [who qualifies]
- Re-enrollment: [yes/no, conditions]
- Goal: [success metric]

### Flow
1. [Trigger event]
2. [Delay: X hours/days]
3. [Action: send email / create task / update property]
4. [Branch: IF condition THEN action A, ELSE action B]
5. [Continue...]

### Exit Criteria
- [When contacts leave this workflow]

### Performance Metrics
| Metric | Target |
|---|---|

[Repeat for each workflow]

## Workflow Dependencies
| Workflow A | Depends On | Conflict With |
|---|---|---|

## Implementation Timeline
| Phase | Workflows | Build Time | Test Time |
|---|---|---|---|
```

## Platform Implementation Steps

### HubSpot
1. Navigate to Automation → Workflows → Create workflow
2. Select trigger type (contact-based, company-based, deal-based)
3. Set enrollment triggers and re-enrollment settings
4. Add actions using drag-and-drop builder
5. Set up branching with if/then logic
6. Add delays between actions
7. Set goal criteria for workflow completion tracking
8. Test with test contact → review → activate

### Salesforce
1. Navigate to Setup → Process Automation → Flows
2. Select flow type (Record-Triggered, Screen, Scheduled)
3. Define trigger criteria and entry conditions
4. Add actions (send email, create task, update record)
5. Use Decision elements for branching logic
6. Add Wait elements for time-based delays
7. Test in sandbox before deploying to production

### General
1. Document workflow logic in plain language before building
2. Identify all data fields needed (create if missing)
3. Create email templates before building workflows
4. Build and test one workflow at a time
5. Monitor performance for first 2 weeks after activation

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Contacts stuck in workflow | Missing exit criteria or broken branch | Add exit criteria; review all branches for dead ends |
| Duplicate emails sent | Contact enrolled in multiple overlapping workflows | Add suppression logic; check workflow conflicts |
| Wrong contacts enrolled | Enrollment criteria too broad | Tighten criteria; add exclusion filters |
| Workflow not triggering | Trigger condition not met or workflow inactive | Verify trigger logic; check workflow status |

## How to Get Your Data

- **Current processes**: Interview sales and marketing teams about manual repetitive tasks
- **CRM audit**: Review existing automations/workflows for gaps and conflicts
- **Lead flow**: CRM → leads per month, current handling process
- **No workflows yet**: Describe your business model and team structure — Claude designs your starter automation stack

## Example

**Input**: "Design CRM automation workflows for our B2B SaaS. HubSpot CRM. Currently manual: lead follow-up (SDR checks CRM daily), customer onboarding (CSM sends emails manually), and no re-engagement for cold leads. 300 new leads/month, 50 new customers/month."

**Output**: 5 priority workflows: (1) New Lead Alert — Trigger: form submission. Actions: immediate email notification to assigned SDR with lead details, create follow-up task (due in 1 hour), if no contact in 4 hours → escalation to SDR manager. (2) Lead Nurture — Trigger: MQL score reached but no demo booked in 48 hours. Actions: 5-email sequence over 14 days (value content → case study → comparison guide → demo invite → last chance). Branch: if demo booked at any point → exit workflow. (3) Customer Onboarding — Trigger: deal stage = closed-won. Actions: Day 0 → welcome email with setup guide + assign CSM task. Day 3 → check-in email + onboarding call task. Day 7 → tips email. Day 14 → feedback survey. Day 30 → first success review task for CSM. (4) Re-engagement — Trigger: no email open AND no website visit in 60 days. Actions: "We miss you" email → wait 7 days → if engaged → move to active. If not → "Is this still relevant?" email → wait 7 days → if still no engagement → move to cold segment. (5) Deal Stale Alert — Trigger: deal no activity for 14 days. Actions: Slack notification to AE → if no update in 7 more days → Slack to sales manager. Implementation: build workflows 1 and 3 first (highest impact), then 2 and 5, then 4. Total build time: ~3 days.
