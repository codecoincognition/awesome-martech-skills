---
name: email-list-segmentation
description: >
  Build email list segmentation strategies for targeted campaigns and improved engagement.
  Use this skill when the user says "email list segmentation", "email audience segmentation",
  "segment my email list", "targeted email campaigns", "email personalization strategy",
  "behavioral email segmentation", "RFM segmentation for email", "email list strategy",
  "dynamic email segments", "email segmentation best practices", or "segment subscribers
  by engagement". Also trigger for lifecycle email segmentation, re-engagement segmentation,
  or purchase-based email targeting.
---

# Email List Segmentation

Builds email list segmentation strategies using behavioral, demographic, engagement, and purchase data to create targeted campaigns that improve open rates, conversions, and subscriber lifetime value.

## Granularity Check

> **Time**: ~5 min data prep → ~10 min Claude session → ~30-45 min setup in Mailchimp / Klaviyo / HubSpot. If implementing, add 1-3 hours for ESP segment setup. Input is subscriber data and business context. Output is Markdown segmentation framework with implementation plan.

## User Intent Mapping

- "How should we segment our email list?" (strategy)
- "Our emails get low engagement — we're sending the same thing to everyone" (problem)
- "Build segments for our e-commerce email" (e-commerce)
- "RFM segmentation for our subscriber list" (RFM)
- "Segment by engagement level" (engagement)
- "Behavioral email segmentation strategy" (behavioral)
- "Dynamic segments vs. static lists" (technical)
- "Re-engagement segments for inactive subscribers" (re-engagement)
- "Lifecycle email segments" (lifecycle)
- "Email personalization based on segments" (personalization)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Business Type | Text | E-commerce, SaaS, B2B, publisher, nonprofit, etc. |
| List Size | Number | Total subscribers |
| Available Data | Text | What data you have on subscribers (demographics, purchase history, behavior, etc.) |

### If You Don't Have This Data

- **Minimal subscriber data?** Start with engagement-based segmentation (opens, clicks, recency) — every ESP tracks this automatically.
- **No purchase data?** Claude designs segments using engagement and demographic data. Add purchase tracking as a priority.
- **No behavioral data?** Begin with signup source segmentation and engagement tiers. Layer in behavioral data as you collect it.
- **Small list (<1,000)?** Segment into 2-3 groups maximum. Over-segmentation on small lists reduces statistical significance.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Subscriber Export | CSV | Full subscriber data with available fields |
| Engagement Data | CSV | Opens, clicks, last activity per subscriber |
| Purchase Data | CSV | Order history, AOV, frequency |
| Signup Sources | Text | Where subscribers come from |
| Current Segments | Text | Any segmentation already in place |

## Process

### Step 1: Data Inventory
Map available data fields to segmentation potential:
- **Demographic**: location, company size, job title, industry
- **Behavioral**: pages visited, content downloaded, features used
- **Engagement**: email opens, clicks, last activity date
- **Transactional**: purchases, AOV, frequency, recency
- **Source**: how they subscribed, lead magnet, channel

### Step 2: Engagement Tiers
Create universal engagement segments:
| Tier | Criteria | Strategy |
|---|---|---|
| VIP | Opened 5+ of last 10 emails, clicked 3+ | Exclusive content, early access, loyalty rewards |
| Active | Opened 2-4 of last 10, clicked 1+ | Standard campaigns, upsell, cross-sell |
| Passive | Opened 1 of last 10, no clicks | Re-engagement content, simpler emails, frequency reduction |
| At-Risk | No opens in 60-90 days | Re-engagement campaign (3-email sequence) |
| Inactive | No opens in 90+ days | Sunset series (final 2 emails), then suppress or remove |

### Step 3: Business-Specific Segments
**E-commerce**: Buyer vs. non-buyer, one-time vs. repeat, product category preference, cart abandoners, high-AOV vs. discount buyers
**SaaS**: Trial vs. paid, plan tier, feature usage, expansion candidates, churn risk
**B2B**: Industry, company size, decision stage, role, content interest
**Publisher**: Content preferences, reading frequency, premium vs. free

### Step 4: RFM Segmentation (if transactional data available)
- **Recency**: When did they last purchase? (score 1-5)
- **Frequency**: How often do they purchase? (score 1-5)
- **Monetary**: How much do they spend? (score 1-5)
- Create segments: Champions (5-5-5), Loyal (4-4-3+), At Risk (2-3-3+), Lost (1-1-any)

### Step 5: Dynamic vs. Static Segments
- **Dynamic segments**: Auto-update based on criteria (engagement tier, purchase recency) — use for ongoing campaigns
- **Static lists**: Fixed point-in-time snapshots — use for one-time campaigns, event attendees
- Most segments should be dynamic for automated targeting

### Step 6: Personalization Framework
Map segments to content variations:
- Subject line personalization
- Content block variations
- Offer differentiation
- Send time optimization per segment
- CTA customization

### Confidence & Sample Size
> **Confidence Note**: Segments need minimum 500 subscribers each to measure performance reliably. Over-segmentation (10+ micro-segments) often underperforms due to small sample sizes. Start with 3-5 segments and expand as your list grows. Test segment-specific campaigns against unsegmented sends to measure lift.

### ⚠️ Human Checkpoint
> Review segment definitions with your team to ensure alignment with business goals. Verify that segment criteria are technically achievable in your ESP. Check compliance with data privacy regulations (GDPR, CAN-SPAM) for data usage in segmentation.

> **Benchmark Context**: Average email open rate is 42.35% and click-through rate is 2.09% (MailerLite 2025 Email Marketing Benchmarks). Average email ROI is $36 per $1 spent (Forbes Advisor, 2025). Automated emails achieve 42.1% open rates and 5.4% click rates, generating 320% more revenue than manual campaigns (Genesys Growth, 2025).
## Output Contract

### Deliverable: Markdown Segmentation Strategy

```markdown
# Email Segmentation Strategy: [Brand]

## Data Fields Available
| Field | Source | Segmentation Use |
|---|---|---|

## Segment Definitions
### Segment 1: [Name]
- Criteria: [rules]
- Size estimate: [% of list]
- Content strategy: [approach]
- Send frequency: [cadence]

## Engagement Tiers
| Tier | Criteria | Size | Strategy |
|---|---|---|---|

## Campaign Matrix
| Campaign | Segments | Content | Frequency |
|---|---|---|---|

## Personalization Plan
| Element | Segment-Specific Variation |
|---|---|

## Implementation Checklist
- [ ] [ESP setup step]

## Measurement Plan
| Segment | KPI | Target |
|---|---|---|
```

## Platform Implementation Steps

### Mailchimp
1. Audience → Segments → Create Segment using conditions
2. Use Tags for manual categorization and Groups for subscriber preferences
3. Set up automated segments based on purchase activity and engagement
4. Use merge tags for personalization in email content

### HubSpot
1. Contacts → Lists → Create Active List (dynamic) or Static List
2. Use contact properties, engagement data, and lifecycle stage for criteria
3. Build smart content blocks that change based on list membership
4. Use workflows to automatically tag contacts for segmentation

### Klaviyo
1. Lists & Segments → Create Segment with conditions
2. Use predictive analytics for CLV and churn risk segments
3. Build flows triggered by segment entry/exit
4. Use catalog data for product-specific segmentation

### General ESP
1. Export subscriber data → analyze in spreadsheet for segment sizing
2. Create segments using your ESP's native segmentation builder
3. Tag subscribers based on engagement tier criteria
4. Set up automated segment updates (daily or real-time)

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Segments too small | Over-segmentation for list size | Consolidate into 3-5 broader segments |
| No performance lift | Segments not meaningfully different | Redefine segments based on behavioral differences, not demographics |
| Segment overlap confuses sends | Subscriber in multiple segments gets duplicate emails | Create priority rules; use exclusion logic |
| Data quality issues | Incomplete or outdated subscriber data | Run data enrichment; progressive profiling in emails |

## How to Get Your Data

- **ESP export**: Export full subscriber list with all available fields
- **Engagement data**: Most ESPs provide open/click history — export or use native segmentation
- **Purchase data**: E-commerce platform → export customer order history; match by email
- **No data beyond email**: Start with engagement tiers (opens/clicks) — available in every ESP

## Example

**Input**: "Email segmentation strategy for a DTC skincare brand. 25K subscribers. Mailchimp. Have purchase data, browse behavior (Shopify), and email engagement. Currently sending same email to everyone."

**Output**: 6 segments recommended: (1) VIP Buyers — purchased 3+ times, opened recent emails (8% of list, 2K) → early access, exclusive bundles, loyalty rewards; (2) One-Time Buyers — purchased once, active on email (15%, 3.75K) → cross-sell, replenishment reminders, education; (3) Browse Abandoners — viewed products, no purchase (12%, 3K) → product-specific triggers, social proof, first-purchase incentive; (4) Engaged Non-Buyers — active on email, never purchased (20%, 5K) → content nurture, samples, introductory offers; (5) Passive — occasional opens, no clicks (30%, 7.5K) → reduced frequency, re-engagement series, best-of content; (6) Inactive — no opens 90+ days (15%, 3.75K) → sunset series, then suppress. Quick wins: (1) Suppress 3.75K inactive subscribers immediately — instant deliverability boost, (2) Create replenishment email for one-time buyers at estimated reorder time (e.g., 45 days for moisturizer), (3) Set up browse abandonment trigger (expected 5-8% conversion rate). Expected impact: 40-60% revenue increase from email within 90 days.

## Related Skills

- **[Email Automation Workflow](./email-automation-workflow.md)** — Use to define the audience segments that trigger different automation paths and branching logic.
- **[Email Sequence Builder](./email-sequence-builder.md)** — Use to create targeted sequences for each segment identified in your segmentation strategy.
- **[Segmentation Rule Builder](../crm/segmentation-rule-builder.md)** — Use to define and implement segmentation rules in your CRM or email platform.
- **[Customer Persona Builder](../insights/customer-persona-builder.md)** — Use to understand the distinct personas you'll segment your list by.
