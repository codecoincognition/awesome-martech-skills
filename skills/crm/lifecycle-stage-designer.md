---
name: lifecycle-stage-designer
description: >
  Design and optimize CRM lifecycle stages, lead statuses, and pipeline definitions for marketing and sales alignment.
  Use this skill when the user says "lifecycle stage design", "CRM pipeline setup", "lead status definitions",
  "MQL to SQL criteria", "lead lifecycle mapping", "CRM stage optimization", "pipeline stage definitions",
  "marketing to sales handoff criteria", "lead qualification framework", "funnel stage design",
  or "CRM workflow architecture". Also trigger for lead routing rules, stage transition automation,
  or sales-marketing SLA design.
---

# Lifecycle Stage Designer

Designs CRM lifecycle stages, lead qualification criteria, pipeline definitions, and marketing-to-sales handoff rules for aligned revenue operations.

## Granularity Check

> **Session time**: ~10 min context gathering + ~15 min Claude session. If implementing, add 1-2 weeks for CRM configuration. Input is current CRM setup and business process. Output is Markdown lifecycle architecture with stage definitions, criteria, and automation rules.

## User Intent Mapping

- "Design our CRM lifecycle stages" (architecture)
- "MQL to SQL — what's the criteria?" (qualification)
- "Marketing-to-sales handoff process" (handoff)
- "Our pipeline stages don't match our process" (optimization)
- "Lead status definitions" (definitions)
- "When should marketing pass leads to sales?" (timing)
- "CRM workflow automation rules" (automation)
- "Sales and marketing alignment" (alignment)
- "Lead routing rules" (routing)
- "Our CRM is a mess — help us define stages" (cleanup)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Business Model | Text | B2B/B2C, sales-led vs. product-led, deal complexity |
| Current CRM | Text | Platform (HubSpot, Salesforce, Pipedrive, etc.) |
| Sales Process | Text | How leads currently become customers |

### If You Don't Have This Data

- **No defined stages?** Claude designs lifecycle stages based on your business model, then helps you configure them in your CRM.
- **Not sure what MQL/SQL means?** Claude defines qualification criteria specific to your business — no jargon required.
- **No sales-marketing alignment?** Claude creates an SLA framework both teams can agree on.
- **CRM is too complex?** Claude simplifies — most businesses need 5-7 lifecycle stages, not 15.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Current Stages | Text | Existing lifecycle/pipeline definitions |
| Conversion Data | Text | Stage-to-stage conversion rates |
| Team Structure | Text | Marketing, SDR, AE roles |
| Lead Volume | Text | Monthly lead flow |
| Deal Size | Text | Average contract value |

## Process

### Step 1: Lifecycle Stage Framework
| Stage | Definition | Owner | Exit Criteria |
|---|---|---|---|
| Subscriber | Opted in for content | Marketing | Downloads gated content OR visits pricing page |
| Lead | Known contact, unknown intent | Marketing | Meets demographic + 1 engagement criteria |
| MQL | Meets marketing qualification criteria | Marketing | Scores above threshold OR requests demo |
| SQL | Sales-accepted, qualified opportunity | Sales (SDR) | Budget, authority, need, timeline confirmed |
| Opportunity | Active deal in pipeline | Sales (AE) | Proposal sent or evaluation started |
| Customer | Closed-won | Customer Success | Purchase completed |
| Evangelist | Active promoter | CS/Marketing | NPS 9-10, referral, case study |

### Step 2: Qualification Criteria
**MQL Criteria** (Marketing Qualified Lead):
- Demographic fit: matches ICP (role, company size, industry)
- Behavioral signals: 3+ content downloads, pricing page visit, demo page visit, OR high engagement score
- NOT: single content download, newsletter subscriber only, competitor/student

**SQL Criteria** (Sales Qualified Lead):
- BANT confirmed: Budget available, Authority to decide, Need identified, Timeline defined
- OR: explicit request (demo, pricing, "talk to sales")
- SDR-qualified via discovery call or email exchange

### Step 3: Lead Scoring Integration
| Signal | Points | Stage Implication |
|---|---|---|
| Job title matches ICP | +20 | Demographic fit |
| Company size matches | +15 | Demographic fit |
| Downloaded 3+ assets | +15 | Engagement threshold |
| Visited pricing page | +20 | Intent signal |
| Requested demo | +30 | SQL trigger |
| Email unsubscribed | -50 | Disqualify |
| No activity 30 days | -20 | Re-engagement needed |

MQL threshold: 50+ points. SQL threshold: 80+ points OR explicit request.

### Step 4: Pipeline Stage Definitions
| Stage | Probability | Exit Criteria | Max Time |
|---|---|---|---|
| Discovery | 10% | Qualified need identified | 14 days |
| Evaluation | 25% | Product demo completed, stakeholders identified | 21 days |
| Proposal | 50% | Proposal delivered, pricing discussed | 14 days |
| Negotiation | 75% | Terms agreed, contract in review | 21 days |
| Closed Won | 100% | Signed contract | — |
| Closed Lost | 0% | Documented reason | — |

### Step 5: Automation Rules
| Trigger | Action | Owner |
|---|---|---|
| Lead score reaches MQL threshold | Notify SDR, add to sequence | Automated |
| MQL not contacted within 1 hour | Escalation alert to SDR manager | Automated |
| SQL created | Create opportunity in pipeline | SDR |
| Opportunity stale >14 days | Alert AE with re-engagement suggestions | Automated |
| Closed Won | Trigger onboarding sequence | Automated |
| Closed Lost | Add to nurture sequence (re-engage in 90 days) | Automated |

### Step 6: SLA Framework
| Metric | Marketing SLA | Sales SLA |
|---|---|---|
| Lead response time | Deliver MQL within 5 min of qualification | Contact MQL within 1 hour |
| Follow-up | Nurture non-MQL leads | Minimum 5 touch attempts per MQL |
| Feedback | Report on MQL quality monthly | Report on MQL disposition within 48 hours |
| Volume | Deliver [X] MQLs per month | Accept or reject with documented reason |

### Confidence & Sample Size

> **Confidence Note**: Lifecycle stages should reflect your actual sales process, not a textbook framework. If you close deals in 1 conversation, you don't need 6 pipeline stages. Start simple (5-7 stages) and add complexity only when you have data showing where the process breaks. MQL definitions should be revisited quarterly — what qualifies a lead changes as your product and market evolve. The biggest lifecycle mistake is over-engineering: 15 stages with complex branching logic that no one follows.

### ⚠️ Human Checkpoint
> Get buy-in from both marketing and sales leadership before implementing lifecycle changes. CRM stage changes affect reporting, automation, and team workflows. Test new stages with a subset of leads before full rollout.

> **Benchmark Context**: Companies with defined lifecycle stages convert MQLs to SQLs at 2-3x the rate of those without. Average MQL-to-SQL conversion: 13% (varies by industry). Average SQL-to-close: 20-30% for B2B SaaS. Leads contacted within 5 minutes are 9x more likely to convert. Companies with sales-marketing SLAs see 36% higher customer retention.

## Output Contract

### Deliverable: Markdown Lifecycle Architecture

```markdown
# CRM Lifecycle Architecture: [Company]

## Lifecycle Stages
| Stage | Definition | Owner | Entry Criteria | Exit Criteria |
|---|---|---|---|---|

## MQL Definition
- Demographic criteria: [requirements]
- Behavioral criteria: [requirements]
- Disqualification: [criteria]

## SQL Definition
- Qualification framework: [BANT/MEDDIC/custom]
- Required fields: [what SDR must complete]

## Pipeline Stages
| Stage | Probability | Exit Criteria | Max Duration |
|---|---|---|---|

## Lead Scoring Model
| Signal | Points | Category |
|---|---|---|

## Automation Rules
| Trigger | Action | System |
|---|---|---|

## SLA Framework
| Metric | Marketing | Sales |
|---|---|---|

## Implementation Plan
| Step | System Change | Owner | Timeline |
|---|---|---|---|
```

## Platform Implementation Steps

### HubSpot
1. Configure lifecycle stages in Settings → Properties → Lifecycle Stage
2. Set up lead scoring in Marketing → Lead Scoring
3. Create workflows for stage transitions (Automation → Workflows)
4. Build pipeline stages in Sales → Deals → Pipeline settings
5. Set up SLA reporting dashboard

### Salesforce
1. Configure Lead Status picklist values
2. Set up Lead Assignment Rules for routing
3. Configure Opportunity Stages with probabilities
4. Create Process Builder flows for stage transitions
5. Build Einstein Lead Scoring or custom scoring

### General CRM
1. Map lifecycle stages to CRM fields
2. Create automation rules for stage transitions
3. Set up notifications for time-based SLAs
4. Build reporting on stage-to-stage conversion
5. Schedule monthly stage health review

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Sales ignores MQLs | MQL criteria too loose, low quality | Tighten MQL criteria; review with sales monthly |
| Leads stuck in stages | No exit criteria or time limits | Add maximum time per stage with escalation |
| Pipeline not predictable | Stages don't reflect actual process | Shadow 5-10 deals; redesign stages to match reality |
| Over-engineered stages | Too many stages, complex branching | Simplify to 5-7 stages; remove unused stages |

## How to Get Your Data

- **Current stages**: CRM → Settings → lifecycle/pipeline configuration
- **Conversion rates**: CRM reports → stage-to-stage conversion funnel
- **Lead velocity**: CRM → leads created per month, time in each stage
- **No CRM data**: Describe your sales process step by step — Claude designs stages from scratch

## Example

**Input**: "Design lifecycle stages for our B2B SaaS. HubSpot CRM. Team: 2 marketers, 2 SDRs, 3 AEs. Monthly leads: ~500 from website. Average deal: $12K/year. Sales cycle: 30-45 days. Currently no defined MQL criteria — marketing sends everything to sales."

**Output**: Problem: 500 unqualified leads per month overwhelm 2 SDRs (250 each). Solution: implement MQL filter to send only qualified leads. Lifecycle: Subscriber → Lead → MQL → SQL → Opportunity → Customer → Evangelist. MQL criteria: (1) Demographic: director+ title at 50-500 employee company in target industries. (2) Behavioral: visited pricing page OR downloaded 2+ resources OR attended webinar. Expected MQL volume: 75-100/month (15-20% of 500 leads). SDR workload: 37-50 MQLs each — manageable for quality follow-up. MQL-to-SQL target: 25% (19-25 SQLs/month). SQL-to-Close target: 30% (6-8 new customers/month). Pipeline: Discovery (10%) → Demo (25%) → Proposal (50%) → Negotiation (75%) → Closed. SLA: marketing delivers MQLs in real-time, SDRs contact within 1 hour, SDRs disposition within 48 hours. Automation: HubSpot workflow triggers SDR notification when lead reaches MQL score threshold (50 points), creates deal automatically when SDR marks as SQL.
