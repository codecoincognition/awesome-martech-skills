---
name: customer-onboarding-optimizer
description: >
  Design and optimize customer onboarding sequences for faster time-to-value and reduced early churn.
  Use this skill when the user says "customer onboarding optimization", "onboarding sequence design",
  "time to first value", "onboarding email sequence", "customer activation strategy", "reduce onboarding
  drop-off", "onboarding checklist design", "product adoption strategy", "new customer welcome sequence",
  "onboarding funnel optimization", or "first 90 days customer experience". Also trigger for user activation
  metrics, onboarding milestone design, or customer success onboarding playbook.
---

# Customer Onboarding Optimizer

Designs and optimizes customer onboarding sequences to accelerate time-to-value, improve activation rates, and reduce early-stage churn.

## Granularity Check

> **Session time**: ~10 min context gathering + ~10 min Claude session. If implementing, add 1-2 weeks for email/in-app setup. Input is current onboarding process and activation data. Output is Markdown onboarding plan with milestone definitions, email sequences, and measurement framework.

## User Intent Mapping

- "Optimize our customer onboarding" (optimization)
- "Customers aren't activating after signup" (activation)
- "Design onboarding email sequence" (email)
- "Reduce time to first value" (TTFV)
- "Onboarding checklist for new customers" (checklist)
- "First 30/60/90 day customer plan" (plan)
- "Too many customers churn in month 1" (early churn)
- "Product adoption is low after purchase" (adoption)
- "B2B customer onboarding playbook" (B2B)
- "Self-serve onboarding flow" (self-serve)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Product/Service | Text | What customers are onboarding to |
| Current Process | Text | How onboarding works today |
| Activation Definition | Text | What "success" looks like for a new customer |

### If You Don't Have This Data

- **No activation definition?** Claude helps define your "aha moment" — the key action that predicts long-term retention.
- **No onboarding data?** Claude designs an onboarding sequence based on best practices for your product type, with tracking recommendations.
- **Not sure where customers get stuck?** Claude maps typical onboarding friction points and recommends diagnostic data to collect.
- **No current onboarding?** Claude designs the full onboarding flow from scratch — emails, milestones, and success criteria.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Activation Data | CSV | % of customers completing key milestones |
| Drop-off Points | Text | Where customers get stuck or abandon |
| Time to Value | Text | How long until customers see results |
| Support Tickets | Text | Common onboarding issues from support |
| Churn Data | Text | Early churn rate and reasons |

## Process

### Step 1: Activation Milestone Definition
| Milestone | Definition | Target Timeline | Success Rate |
|---|---|---|---|
| Account setup | Profile completed, settings configured | Day 1 | >90% |
| First action | Completed primary use case once | Day 3 | >70% |
| Aha moment | Experienced core value proposition | Day 7 | >50% |
| Habit formed | Used product 3+ times in first 14 days | Day 14 | >40% |
| Integrated | Connected to existing workflow/tools | Day 30 | >30% |
| Expanded | Used secondary features or invited team | Day 60 | >25% |

### Step 2: Onboarding Email Sequence
| Day | Email | Goal | CTA |
|---|---|---|---|
| 0 | Welcome + quick start | Get them to first action | "Start here" |
| 1 | Setup completion | Complete account setup | "Finish setup" |
| 3 | First use case guide | Show how to solve their problem | "Try it now" |
| 5 | Success story | Show what's possible (social proof) | "See results" |
| 7 | Feature spotlight | Introduce key feature they haven't tried | "Explore" |
| 10 | Check-in | Ask how it's going, offer help | "Need help?" |
| 14 | Tips and tricks | Deepen usage with power-user tips | "Level up" |
| 21 | Progress report | Show what they've accomplished | "See your progress" |
| 30 | Review + expand | Encourage team adoption or plan upgrade | "Invite team" |

### Step 3: Onboarding Friction Audit
| Friction Point | Signal | Fix |
|---|---|---|
| Complex setup | High drop-off at setup, support tickets | Simplify setup, add wizard, pre-fill defaults |
| Unclear value | Users explore but don't complete key action | Add guided tutorial, show value before effort |
| Feature overwhelm | Low depth of feature usage, quick abandon | Progressive disclosure, show 1-2 features first |
| Integration hurdles | Low integration adoption, manual workarounds | Pre-built integrations, setup assistance |
| No quick win | Long time to first valuable output | Create instant-gratification moment (template, sample data) |

### Step 4: Onboarding Channels
| Channel | Best For | Timing |
|---|---|---|
| Email | Milestone nudges, educational content | Days 0-30, scheduled |
| In-app messages | Contextual guidance, feature discovery | Triggered by behavior |
| Video/tutorials | Complex feature explanation | Linked from emails and in-app |
| Live session | High-touch onboarding, complex products | Week 1 for enterprise |
| Chatbot | Quick answers during setup | Always available |
| Community | Peer learning, tips sharing | After basic activation |

### Step 5: Segmented Onboarding
| Segment | Onboarding Approach | Key Difference |
|---|---|---|
| Self-serve (individual) | Automated email + in-app guidance | Speed-focused, minimal friction |
| Team/SMB | Automated + 1 live kickoff call | Balance automation and human touch |
| Enterprise | Dedicated CSM + custom success plan | High-touch, project-managed |
| Product-led trial | Value-first, upgrade later | Show ROI before asking for payment |

### Step 6: Measurement Framework
| Metric | Formula | Target | Review |
|---|---|---|---|
| Activation rate | Users reaching aha moment / total signups | >50% in 7 days | Weekly |
| Time to first value | Median days from signup to first action | <3 days | Weekly |
| Onboarding completion | Users completing all milestones / total signups | >40% in 30 days | Monthly |
| Early churn (Day 30) | Users inactive after 30 days / total signups | <20% | Monthly |
| Support ticket rate | Onboarding tickets / total new users | <15% | Weekly |

### Confidence & Sample Size

> **Confidence Note**: Onboarding changes should be measured over at least 200 new users before drawing conclusions — cohort effects and seasonal variation can mislead with small samples. The "aha moment" is the single most important metric to define and optimize for. Companies that reduce time-to-value by 50% typically see 20-30% improvement in 90-day retention. Don't try to teach everything at once — progressive onboarding (introduce features over time) outperforms "boot camp" onboarding (teach everything day 1).

### ⚠️ Human Checkpoint
> Test onboarding sequences with new users and collect qualitative feedback. Automated emails should be reviewed for relevance as product changes. In-app messages should be tested for mobile compatibility. Enterprise onboarding plans should be customizable by CSM.

> **Benchmark Context**: 40-60% of free trial users log in once and never return. Users who activate in the first 3 days retain at 3x the rate of those who take 7+ days. Onboarding emails have 4x higher open rates than marketing emails. Companies with structured onboarding see 50% greater new-hire productivity (same principle applies to customers). 86% of customers say they'd be more loyal if they received better onboarding content.

## Output Contract

### Deliverable: Markdown Onboarding Plan

```markdown
# Customer Onboarding Plan: [Product]

## Activation Definition
- Aha moment: [key action]
- Target timeline: [days]
- Current activation rate: [%]
- Target activation rate: [%]

## Onboarding Milestones
| Milestone | Action | Day | Success Criteria | Current Rate |
|---|---|---|---|---|

## Email Sequence
| Day | Subject | Goal | CTA | Trigger |
|---|---|---|---|---|

## In-App Guidance
| Trigger | Message | Action | Exit Condition |
|---|---|---|---|

## Segmented Approaches
| Segment | Channel Mix | Key Differences |
|---|---|---|

## Friction Fixes
| Problem | Evidence | Fix | Priority | Expected Impact |
|---|---|---|---|---|

## Measurement Dashboard
| Metric | Current | Target | Tracking |
|---|---|---|---|
```

## Platform Implementation Steps

### Email (HubSpot/ActiveCampaign/Customer.io)
1. Create onboarding email workflow triggered by account creation
2. Set enrollment criteria (new customers only, exclude existing)
3. Build 7-10 emails with appropriate delays
4. Add behavioral triggers (skip emails for actions already completed)
5. Set up goal completion (mark as activated when aha moment reached)

### In-App (Pendo/Appcues/Intercom)
1. Create guided product tour for first-time users
2. Set up milestone-based tooltips and checklists
3. Configure behavioral triggers for contextual messages
4. Build completion tracking for onboarding milestones
5. A/B test tour variations for activation impact

### Customer Success
1. Create onboarding playbook for CSM team
2. Define handoff point from automated to human-led onboarding
3. Set up health score tracking from Day 1
4. Schedule automated check-ins at key milestones
5. Build escalation paths for stalled onboarding

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Low email engagement | Emails not relevant or too frequent | Reduce frequency; make emails behavioral (triggered by actions, not just time) |
| Users skip onboarding | Too many steps or unclear value | Simplify to 3-step quick start; show value before asking for effort |
| Activation rate flat | Wrong aha moment definition | Re-analyze which action correlates with retention; redefine activation |
| Enterprise onboarding takes too long | No structure, CSM ad-hoc approach | Standardize onboarding project plan with milestones and timelines |

## How to Get Your Data

- **Activation data**: Product analytics → user actions → filter by first 30 days
- **Email performance**: ESP → onboarding workflow → open/click/conversion rates
- **Drop-off points**: Product analytics → funnel analysis → onboarding steps
- **Support tickets**: Support tool → filter by "new customer" or "getting started" tags
- **No data**: Describe your product and current onboarding — Claude designs a measured onboarding plan

## Example

**Input**: "Optimize onboarding for our project management SaaS. Current: welcome email → nothing. 60% of trial users never create a project. 45% churn within 30 days. Average activation (created project + added task) takes 5 days. Need to improve trial-to-paid conversion."

**Output**: Problem: no onboarding guidance after welcome email → users don't know what to do → abandon. Aha moment redefined: "created first project AND added 3+ tasks AND invited 1 team member" (this predicts conversion 4x better than project creation alone). Onboarding redesign: Day 0 — welcome email with 2-minute video showing "create your first project in 3 clicks" + pre-made project template ready to use. Day 1 — if no project created → "Start with a template" email with 1-click template import. Day 2 — if project created but no tasks → "Add your first 3 tasks" email with examples. Day 3 — if tasks added but no team → "Invite your first teammate" email (collaborative tools need team adoption). Day 5 — progress email: "Here's what you've accomplished" (reinforce value). Day 7 — if activated → case study of similar company. If not → "Need help? 15-min setup call" offer. Day 14 — trial ending reminder + ROI summary. In-app: onboarding checklist (4 items) pinned to sidebar. First login: guided tour (30 seconds) showing create project → add task → invite team. Expected results: activation rate from 40% to 65% (guided setup + templates), Day 30 churn from 45% to 25%, trial-to-paid conversion increase 30-40%.
