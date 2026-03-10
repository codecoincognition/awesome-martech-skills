---
name: email-automation-workflow
description: >
  Design email automation workflows — triggers, sequences, branching logic, and lifecycle campaigns.
  Use this skill when the user says "email automation workflow", "email drip campaign", "automated
  email sequence", "email workflow builder", "trigger-based email", "lifecycle email automation",
  "cart abandonment email flow", "post-purchase email sequence", "lead nurture automation",
  "email flow design", or "marketing automation workflow". Also trigger for re-engagement
  automation, event-triggered emails, or multi-step email journeys.
---

# Email Automation Workflow

Designs email automation workflows with trigger logic, branching paths, timing optimization, and content recommendations for lifecycle marketing, lead nurturing, and revenue recovery.

## Granularity Check

> **Session time**: ~5 min data prep + ~10 min Claude session. If implementing, add 2-6 hours per workflow in your ESP. Input is customer journey and business goals. Output is Markdown workflow blueprint with email specifications.

## User Intent Mapping

- "Set up email automation for our business" (full automation)
- "Cart abandonment email flow" (recovery)
- "Lead nurturing drip campaign" (nurture)
- "Post-purchase email automation" (retention)
- "Onboarding email sequence" (onboarding)
- "Re-engagement automation for inactive subscribers" (win-back)
- "Customer lifecycle email strategy" (lifecycle)
- "Trigger-based email workflow" (triggers)
- "Our email automation isn't converting" (optimization)
- "Multi-step email journey with branching" (advanced)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Business Type | Text | E-commerce, SaaS, B2B services, etc. |
| Workflow Goal | Text | What you want the automation to achieve |
| Available Triggers | Text | Events you can use as triggers (signup, purchase, page view, etc.) |

### If You Don't Have This Data

- **No automation yet?** Claude designs your first 3 priority workflows from scratch. Start with the highest-impact flow for your business type.
- **Limited triggers?** Claude works with the triggers your ESP supports. Most support: signup, email engagement, time-based, and purchase events.
- **No customer journey map?** Describe your typical customer path. Claude maps the journey and identifies automation opportunities.
- **No content yet?** Claude provides email copy frameworks and subject lines for each workflow step.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| ESP | Text | Email platform and capabilities |
| Current Automations | Text | Any workflows already running |
| Customer Journey | Text | Key stages and touchpoints |
| Average Sales Cycle | Text | Time from lead to customer |
| Revenue Data | Text | AOV, LTV, repeat purchase rate |

## Process

### Step 1: Workflow Prioritization
| Workflow | Business Type | Revenue Impact | Complexity |
|---|---|---|---|
| Welcome Series | All | High (sets engagement baseline) | Low |
| Cart Abandonment | E-commerce | Very High (recovers 5-15% of carts) | Medium |
| Post-Purchase | E-commerce | High (drives repeat purchases) | Medium |
| Lead Nurture | B2B/SaaS | High (shortens sales cycle) | Medium |
| Onboarding | SaaS | Very High (reduces churn) | High |
| Re-engagement | All | Medium (recovers inactive users) | Low |
| Browse Abandonment | E-commerce | Medium (converts window shoppers) | Medium |
| Upsell/Cross-sell | All | High (increases LTV) | Medium |

### Step 2: Trigger & Flow Design
For each workflow, define:
- **Entry trigger**: What starts the workflow (event, behavior, time-based)
- **Entry conditions**: Qualifying criteria (segment membership, not in other flows)
- **Exit conditions**: What removes someone from the flow (purchase, unsubscribe, goal met)
- **Suppression rules**: Who should NOT enter (recent purchasers, VIPs, support tickets)

### Step 3: Email Sequence Design
Per workflow:
- Number of emails (typically 3-7)
- Timing between emails (hours, days, weeks based on urgency)
- Content progression (introduction → value → urgency → last chance)
- Subject line strategy per email
- CTA strategy per email (soft → direct as sequence progresses)

### Step 4: Branching Logic
- **Engagement branches**: different paths for openers vs. non-openers
- **Behavioral branches**: purchased → thank you flow; didn't purchase → more nurturing
- **Conditional content**: different content blocks based on subscriber data
- **Goal branches**: reached goal → exit; didn't reach → continue or escalate

### Step 5: Performance Monitoring
- Key metrics per workflow step (open, click, conversion, unsubscribe)
- Flow-level metrics (completion rate, conversion rate, revenue attributed)
- Drop-off analysis (where do people leave the flow?)
- A/B testing within flows (subject lines, timing, content)

### Confidence & Sample Size
> **Confidence Note**: Automation workflows need 500+ entries to evaluate performance reliably. New flows should run for 30 days before optimizing. Timing between emails is the most impactful variable — test different delays. Attribution for multi-touch flows is complex; use last-touch for simplicity or multi-touch if your ESP supports it.

### ⚠️ Human Checkpoint
> Review all automated email content for accuracy, brand voice, and compliance before activating. Test the complete flow with internal addresses first. Set up alerts for unusual unsubscribe rates in automated flows. Verify suppression rules prevent over-emailing.

> **Benchmark Context**: Cart abandonment emails recover 5-15% of abandoned carts. Welcome series generate 320% more revenue per email than promotional campaigns. Automated emails generate 29% of email marketing revenue with only 2% of sends. Post-purchase flows increase repeat purchase rate by 20-40%. Optimal cart abandonment timing: first email within 1 hour, second at 24 hours, third at 72 hours.

## Output Contract

### Deliverable: Markdown Workflow Blueprint

```markdown
# Email Automation Workflow: [Flow Name]

## Flow Overview
- Trigger: [event]
- Goal: [desired outcome]
- Expected conversion: [rate]
- Emails in flow: [count]

## Flow Diagram
[Trigger] → Email 1 (delay) → [Branch] → Email 2 (delay) → Email 3

## Email Specifications

### Email 1: [Name]
- Send: [trigger + delay]
- Subject: [line]
- Content: [brief description]
- CTA: [action]

### Email 2: [Name]
- Send: [delay from Email 1]
- Branch: [condition]
- Subject: [line]
- Content: [brief description]
- CTA: [action]

## Branching Logic
| Condition | Path | Next Email |
|---|---|---|

## Suppression Rules
1. [Rule]

## Metrics to Track
| Email | Target Open | Target Click | Target Conversion |
|---|---|---|---|
```

## Platform Implementation Steps

### Klaviyo
1. Flows → Create Flow → Select trigger (e.g., "Added to Cart")
2. Add emails with time delays between each
3. Configure conditional splits based on engagement or behavior
4. Set flow filters (suppression rules)
5. Activate flow and monitor in Flow Analytics

### HubSpot
1. Automation → Workflows → Create from scratch
2. Set enrollment trigger and criteria
3. Add email sends with delays and branches
4. Configure goal criteria (exits flow when goal met)
5. Monitor in Workflow Performance report

### Mailchimp
1. Automations → Create → Customer Journeys
2. Choose starting point (trigger event)
3. Add email steps with wait times
4. Add if/else branches based on conditions
5. Activate and monitor in Journey Reports

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Low flow conversion | Wrong timing or weak CTAs | Test different delays; strengthen offers in later emails |
| High unsubscribe rate | Too many emails too quickly | Increase delays between emails; add engagement check before continuing |
| Flow conflicts | Subscriber in multiple flows simultaneously | Set exclusion rules; prioritize flows by revenue impact |
| Stale content | Automation set-and-forget for months | Quarterly review of all active flows; refresh content and test |

## How to Get Your Data

- **Customer journey**: Map your typical customer path from awareness to purchase
- **ESP capabilities**: Check which triggers and automations your ESP supports
- **Revenue data**: E-commerce platform → average order value, repeat purchase rate
- **No data**: Describe your business type and goals — Claude designs the priority workflows

## Example

**Input**: "Email automation for a DTC coffee subscription. Shopify + Klaviyo. Flows needed: welcome series, cart abandonment, post-purchase. Subscription average is $24/month. 30% of first-time buyers never reorder."

**Output**: 3 workflows designed: (1) Welcome Series (5 emails over 14 days): Email 1 (immediate) — welcome + brand story + 10% first order; Email 2 (day 2) — coffee sourcing story; Email 3 (day 5) — brewing guide (educational); Email 4 (day 9) — customer reviews + social proof; Email 5 (day 14, non-buyers only) — expiring discount reminder. (2) Cart Abandonment (3 emails): Email 1 (1 hour) — "Your cart is waiting" with product image; Email 2 (24 hours, if didn't open #1) — "Still thinking it over?" with reviews; Email 3 (72 hours) — "Last chance" + free shipping offer. Expected recovery: 8-12%. (3) Post-Purchase (4 emails): Email 1 (day 1) — order confirmation + brewing tips for their blend; Email 2 (day 7) — "How's your coffee?" satisfaction check; Email 3 (day 21) — running low reminder + easy reorder link; Email 4 (day 28, non-reorderers) — subscription pitch with 15% discount. Expected: reduce 30% churn-after-first-purchase to 18-22%. Suppression: all flows exclude active support ticket holders and anyone who purchased in last 48 hours.
