---
name: onboarding-flow-optimizer
description: >
  Optimize user onboarding flows to increase activation and reduce time-to-value.
  Use this skill when the user says "optimize onboarding", "onboarding flow design", "user
  activation strategy", "reduce time to value", "onboarding checklist", "new user experience",
  "activation rate improvement", "onboarding email sequence", "product tour design", "first-run
  experience", or "onboarding drop-off analysis". Also trigger for aha moment identification,
  onboarding personalization, or activation funnel optimization.
---

# Onboarding Flow Optimizer

Analyzes and optimizes user onboarding flows to reduce time-to-value, increase activation rates, and improve the new user experience through personalized onboarding paths and progressive disclosure.

## Granularity Check

> **Time**: ~5 min data prep → ~10 min Claude session → ~60-120 min implementing in your product / tools. If implementing output, add 1-4 weeks for development. Input is current onboarding flow and activation data. Output is Markdown optimization plan with redesigned flow.

## User Intent Mapping

- "Our users sign up but don't activate" (activation problem)
- "Design an onboarding flow for our app" (new design)
- "Reduce our onboarding drop-off" (optimization)
- "What's our aha moment?" (activation analysis)
- "Onboarding checklist for new users" (checklist design)
- "Personalized onboarding by user type" (segmentation)
- "Onboarding email sequence" (email design)
- "Product tour best practices" (tour design)
- "Time to value is too long" (speed optimization)
- "Compare self-serve vs. guided onboarding" (strategy)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Product | Text | What your product does |
| Current Onboarding | Text | Steps new users go through today |
| Activation Metric | Text | What counts as an "activated" user |

### If You Don't Have This Data

- **No activation metric?** Describe the moment users get value. Claude helps define your activation event (e.g., "created first project", "sent first email", "connected first integration").
- **No onboarding data?** Walk through your signup as a new user and list every step. Count the steps — that's your starting point.
- **No drop-off data?** Set up funnel tracking in your analytics tool. After 2 weeks, you'll see where users drop off.
- **No user feedback?** Interview 5-10 churned users. Ask: "What was confusing when you first signed up?" The patterns will be clear.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Funnel Data | CSV | Step, users_entered, users_completed, completion_rate |
| User Segments | Text | Different user types with different needs |
| Time to Activation | Number | Average days from signup to activation |
| Churned User Feedback | Text | Why users didn't activate |
| Competitor Onboarding | Text | How competitors onboard users |

## Process

### Step 1: Aha Moment Identification
Find the action that correlates most with retention:
- What do retained users do in their first session that churned users don't?
- How quickly do retained users reach this action?
- Can this action be reached in under 5 minutes?

### Step 2: Current Flow Audit
Evaluate each step:
- Is it necessary for reaching the aha moment?
- Can it be deferred to after activation?
- Does it cause drop-off? (>20% drop at any step is a red flag)
- Does it add value or just collect information?

### Step 3: Flow Redesign
Principles:
- **Reduce steps**: Cut anything between signup and aha moment
- **Progressive disclosure**: Show features as users need them, not all at once
- **Quick win first**: Let users experience value before asking for investment (data, settings, payment)
- **Personalize**: Ask one question to route users to relevant onboarding path
- **Celebrate progress**: Mark milestones to motivate completion

### Step 4: Multi-Channel Onboarding
| Channel | Purpose | Timing |
|---|---|---|
| In-app | Core onboarding flow, tooltips, checklists | Immediate |
| Email | Nudges, tips, re-engagement | Day 0, 1, 3, 7, 14 |
| In-app messages | Feature discovery, milestone celebration | Triggered by behavior |
| Video/Tour | Complex feature explanation | First-time feature use |
| Human touch | High-value accounts, complex products | Day 1-3 (sales-assisted) |

### Step 5: Onboarding Metrics Dashboard
| Metric | Definition | Target |
|---|---|---|
| Signup-to-Activation Rate | % who reach aha moment | 40-60% |
| Time to Activation | Days from signup to activation | <24 hours |
| Onboarding Completion Rate | % who complete all steps | 70%+ |
| Day 1 / Day 7 Retention | % returning after 1/7 days | 40%+ / 25%+ |

### Confidence & Sample Size
> **Confidence Note**: Onboarding changes need minimum 500 new users per variant to measure activation rate changes reliably. Small products should test sequentially (before/after) rather than A/B testing. Day 7 and Day 30 retention are lagging metrics — use activation rate as a leading indicator. Interview qualitative feedback alongside quantitative data for a complete picture.

### ⚠️ Human Checkpoint
> Review redesigned flow with actual users (5 user tests minimum) before full rollout. Verify that removed steps don't break downstream features. Ensure onboarding emails comply with CAN-SPAM/GDPR. Test on mobile if applicable.

> **Benchmark Context**: Average SaaS activation rate is 20-40% (ProfitWell 2024 SaaS Benchmarks) Top products achieve 60%+. . Reducing onboarding from 8 steps to 3 increases completion by 50-100% (OpenView 2024 Product Benchmarks) Personalized onboarding flows convert 2x better than generic (OpenView 2024 Product Benchmarks) Onboarding emails have 4x the engagement rate of regular marketing emails (OpenView 2024 Product Benchmarks) 86% of users say they'd be more likely to stay loyal to a product that invests in onboarding (OpenView 2024 Product Benchmarks) (ProfitWell 2024 SaaS Benchmarks).
## Output Contract

### Deliverable: Markdown Optimization Plan

```markdown
# Onboarding Optimization: [Product]

## Aha Moment
- Action: [what activated users do]
- Target time: [minutes/hours to reach it]

## Current vs. Optimized Flow
### Current Flow (X steps, ~Y minutes)
1. [Step]: [completion rate]
...
### Optimized Flow (X steps, ~Y minutes)
1. [Step]: [expected improvement]
...

## Personalization Paths
| User Type | Aha Moment | Custom Flow |
|---|---|---|

## Email Sequence
| Day | Subject | Goal | Trigger |
|---|---|---|---|

## Onboarding Checklist (In-App)
- [ ] [Step 1]: [why it matters]
...

## Metrics & Targets
| Metric | Current | Target | Timeline |
|---|---|---|---|
```

## Platform Implementation Steps

### Product Analytics (Mixpanel/Amplitude/PostHog)
1. Define activation event
2. Build onboarding funnel: signup → each step → activation
3. Segment by user type to find different aha moments
4. Set up retention curves comparing activated vs. non-activated users

### In-App Onboarding (Appcues/Userflow/Chameleon)
1. Build product tour following the optimized flow
2. Create onboarding checklist widget
3. Set up triggered tooltips for feature discovery
4. Configure completion tracking and analytics

### Email (Customer.io/Intercom/HubSpot)
1. Build triggered email sequence based on user behavior
2. Suppress emails when in-app actions are completed
3. Create re-engagement triggers for users who stall
4. A/B test subject lines and send times

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Activation didn't improve | Wrong aha moment identified | Re-analyze retained vs. churned user behaviors |
| Users skip onboarding | Too many steps or perceived low value | Make first step deliver immediate value |
| Personalization overwhelmed users | Too many paths or questions upfront | Simplify to 1-2 segmentation questions |
| Emails ignored | Wrong timing or generic content | Test behavioral triggers vs. time-based; personalize content |

## How to Get Your Data

- **Product analytics**: Mixpanel/Amplitude → Funnels → Onboarding steps
- **User interviews**: Talk to 5 churned and 5 retained users about their first experience
- **No data**: Walk through your own signup flow, count steps, time each one — that's your audit

## Example

**Input**: "Optimize onboarding for a CRM tool. Current flow: signup → verify email → company info form (12 fields) → invite team → import contacts → set up pipeline → create first deal. Activation: 'Create first deal.' Current activation rate: 18%. Time to activation: 4.2 days."

**Output**: Problem: 7 steps before value, 12-field form is a wall. Aha moment confirmed: users who create a deal in day 1 retain 4x better. Optimized flow: (1) Signup (email only) → (2) "What do you sell?" (1 question, auto-generates sample pipeline) → (3) Create first deal (guided, with sample data pre-filled) → aha moment reached in <3 minutes. Deferred: email verification (to day 2), company info (progressive, collect over first week), team invite (prompt after 3rd deal), contact import (prompt after pipeline is set up). Email sequence: Day 0 — welcome + quick win tip; Day 1 — "Import your contacts in 60 seconds"; Day 3 — "Invite your team"; Day 7 — success story from similar company. Expected impact: activation rate from 18% to 35-45%, time to activation from 4.2 days to <1 hour.

## Related Skills

- **[customer-persona-builder](./customer-persona-builder.md)** — Create persona-specific onboarding flows to improve activation rates.
- **[retention-analysis-framework](./retention-analysis-framework.md)** — Track how onboarding improvements affect retention and churn.
- **[growth-experiment-designer](./growth-experiment-designer.md)** — Design A/B tests to validate onboarding optimizations.
- **[ga4-event-setup-guide](../analytics/ga4-event-setup-guide.md)** — Set up activation events to measure onboarding success.
