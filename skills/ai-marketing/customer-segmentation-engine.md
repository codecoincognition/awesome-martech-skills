---
name: customer-segmentation-engine
description: >
  Build data-driven customer segments using behavioral, demographic, and transactional data for targeted marketing.
  Use this skill when the user says "customer segmentation", "audience segmentation strategy",
  "behavioral segmentation", "RFM segmentation", "customer clustering", "segmentation model",
  "data-driven segments", "customer persona building from data", "segmentation for personalization",
  "cohort analysis for marketing", or "which customer segments to target". Also trigger for
  lookalike audience building, segment-based marketing strategy, or customer tiering.
---

# Customer Segmentation Engine

Builds data-driven customer segments using behavioral, demographic, and transactional data to enable targeted marketing campaigns, personalized experiences, and strategic resource allocation.

## Granularity Check

> **Time**: ~10 min data prep → ~10 min Claude session → ~30-60 min configuring in your marketing platform. If implementing in CRM/CDP, add 1-2 weeks. Input is customer data exports. Output is Markdown segmentation model with targeting recommendations.

## User Intent Mapping

- "Segment our customer base" (full segmentation)
- "RFM analysis of our customers" (RFM)
- "Which customer segments are most valuable?" (value-based)
- "Behavioral segmentation for our marketing" (behavioral)
- "Build customer personas from data" (data-driven personas)
- "Customer tiering strategy" (tiering)
- "Cohort analysis for retention" (cohorts)
- "Segments for personalization" (personalization)
- "Lookalike audience building" (acquisition)
- "Our marketing treats everyone the same" (segmentation need)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Customer Data | CSV | Transactions, engagement, demographics |
| Business Model | Text | E-commerce, SaaS, services, marketplace |
| Marketing Goals | Text | Retention, upsell, acquisition, reactivation |

### If You Don't Have This Data

- **Limited customer data?** Claude builds segments from whatever data you have — even email engagement alone provides actionable segments.
- **No transactional data?** Claude uses engagement-based segmentation (active, passive, dormant) as a starting point.
- **No analytics tools?** Claude provides segment definitions you can implement in any email platform or CRM.
- **Small customer base?** Claude recommends fewer, broader segments — segmentation is most effective with 1,000+ customers.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Purchase History | CSV | Orders, revenue, products, frequency |
| Engagement Data | CSV | Email opens, logins, feature usage |
| Demographics | CSV | Age, location, company, role |
| Survey Responses | CSV | Satisfaction, preferences, NPS |
| Churn Data | CSV | Churned customers with attributes |

## Process

### Step 1: Segmentation Framework Selection
| Framework | Best For | Data Required |
|---|---|---|
| RFM (Recency, Frequency, Monetary) | E-commerce, transactional | Purchase history |
| Behavioral | SaaS, engagement-driven | Usage/engagement data |
| Lifecycle stage | All businesses | Customer timeline data |
| Value-based | Revenue optimization | Revenue data |
| Needs-based | Product development, positioning | Survey or preference data |
| Firmographic | B2B | Company attributes |

### Step 2: RFM Segmentation (E-commerce)
| Segment | Recency | Frequency | Monetary | Strategy |
|---|---|---|---|---|
| Champions | High | High | High | Reward, upsell, advocacy |
| Loyal | Medium | High | High | Upsell, cross-sell |
| Potential Loyalists | High | Medium | Medium | Increase frequency |
| New Customers | High | Low | Low | Onboard, second purchase |
| At Risk | Low | High | High | Win-back urgently |
| Hibernating | Very Low | Low | Low | Reactivation or sunset |

### Step 3: Behavioral Segmentation (SaaS)
| Segment | Engagement Level | Feature Usage | Strategy |
|---|---|---|---|
| Power Users | Daily active | All features | Advocacy, beta access |
| Regular Users | Weekly active | Core features | Feature education, upsell |
| Casual Users | Monthly active | Basic features | Re-engagement, value demos |
| At-Risk Users | Declining usage | Minimal | Intervention, success outreach |
| Dormant | Inactive 30+ days | None | Win-back campaign |

### Step 4: Segment Profiling
Per segment:
- Size (number and % of total)
- Value (revenue, LTV, engagement score)
- Growth trend (growing, stable, declining)
- Key characteristics (demographics, behavior patterns)
- Channel preferences (email, social, in-app)
- Content preferences (topic interests, format preferences)

### Step 5: Targeting Strategy
Per segment:
- Marketing message (what to say)
- Channel (where to reach them)
- Offer (what to offer)
- Frequency (how often to engage)
- Budget allocation (spend proportion)
- KPIs (success metrics per segment)

### Step 6: Segment Activation
- Create segments in CRM/CDP
- Build segment-specific email flows
- Configure ad audiences (upload segment lists)
- Design personalized website experiences per segment
- Set up segment-level reporting dashboards

### Confidence & Sample Size

> **Confidence Note**: Segments smaller than 100 customers are too small for reliable statistical analysis. RFM scores should be recalculated monthly for e-commerce, quarterly for SaaS. Segments are not permanent — customers move between segments over time. Over-segmentation (10+ segments) creates operational complexity without proportional value. Start with 4-6 segments and refine based on marketing performance per segment.

### ⚠️ Human Checkpoint
> Validate segment definitions with sales and customer success teams. Verify segment sizes are large enough for statistically significant campaigns. Review targeting strategies for fairness and compliance.

> **Benchmark Context**: See Salesforce 2024 State of Marketing, and McKinsey 2024 State of AI Report for current industry benchmarks relevant to this analysis.
## Output Contract

### Deliverable: Markdown Segmentation Model

```markdown
# Customer Segmentation: [Brand]

## Segmentation Overview
- Total customers: [number]
- Segments: [count]
- Framework: [type]

## Segment Profiles
### Segment 1: [Name]
- Size: [N] ([%] of total)
- Value: [revenue, LTV]
- Key characteristics: [description]
- Behavior: [patterns]
- Strategy: [approach]
- KPIs: [metrics]

## Segment Distribution
| Segment | Size | Revenue Share | LTV | Growth |
|---|---|---|---|---|

## Targeting Matrix
| Segment | Message | Channel | Offer | Frequency | Budget % |
|---|---|---|---|---|---|

## Migration Paths
| From Segment | To Segment | Trigger | Action |
|---|---|---|---|

## Implementation
| Step | Tool | Action | Timeline |
|---|---|---|---|
```

## Platform Implementation Steps

### CRM (HubSpot, Salesforce)
1. Create custom properties for segment assignment
2. Build workflow/flow to auto-assign segments based on criteria
3. Create smart lists or dynamic segments per segment
4. Build segment-level dashboards and reports

### Email (Klaviyo, Mailchimp)
1. Create segments based on RFM or behavioral criteria
2. Build segment-specific email flows (welcome, nurture, win-back)
3. Configure send frequency rules per segment
4. Set up A/B testing within segments

### CDP (Segment, mParticle)
1. Define segment rules in CDP using behavioral and transactional events
2. Sync segments to downstream tools (email, ads, analytics)
3. Set up real-time segment membership updates
4. Build unified customer profile for cross-channel segmentation

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Segments too similar | Criteria don't differentiate enough | Use more discriminating variables; combine behavioral + value data |
| Too many segments | Over-segmentation without operational capacity | Consolidate to 4-6 actionable segments; expand only when resourced |
| Segments don't drive action | Segments described but not activated in tools | Create specific campaign per segment; automate in CRM/ESP |
| Stale segments | Membership not updated | Recalculate segment scores monthly; automate reassignment |

## How to Get Your Data

- **Transaction data**: E-commerce platform → export orders with customer ID, date, revenue
- **Engagement data**: ESP → email engagement; product → feature usage logs
- **CRM data**: CRM → export contacts with attributes, lifecycle stage, revenue
- **No data**: Describe your customers and business model — Claude designs a segmentation framework you can populate

## Example

**Input**: "Customer segmentation for DTC skincare brand. 25K customers. Have Shopify data: orders, revenue, products purchased. Klaviyo email engagement data. Goal: improve retention and increase repeat purchases."

**Output**: RFM segmentation with 6 segments: (1) Champions (8% of base, 35% of revenue) — bought recently, frequently, high spenders. Strategy: VIP early access, loyalty rewards, referral program, exclusive launches. (2) Loyal Customers (15%, 25% revenue) — regular buyers, moderate-high spend. Strategy: cross-sell new product lines, subscription offers, loyalty tier upgrade. (3) Potential Loyalists (12%, 15% revenue) — recent buyers with 2-3 orders, growing frequency. Strategy: second product education, bundle offers, frequency incentives. (4) New Customers (20%, 10% revenue) — first purchase within 60 days. Strategy: post-purchase onboarding, replenishment reminders, second purchase discount. (5) At Risk (18%, 12% revenue) — haven't purchased in 60-120 days despite previous regular buying. Strategy: win-back email sequence, "we miss you" offer, product recommendation based on past purchases. (6) Dormant (27%, 3% revenue) — no purchase in 120+ days. Strategy: aggressive win-back offer, sunset after 180 days if no response. Implementation: Klaviyo segments with RFM scoring, automated flows per segment. Quick win: target At Risk segment (18% of base) with personalized win-back — recovering 10% would add $45K annual revenue.

## Related Skills

- **[Audience Persona Builder](../insights/audience-persona-builder.md)** — Validate segmentation with data-driven personas to ensure segments map to real customer archetypes.
- **[Segmentation Rule Builder](../crm/segmentation-rule-builder.md)** — Translate segmentation model into dynamic CRM lists for targeted campaigns.
- **[Predictive Lead Scoring](./predictive-lead-scoring.md)** — Layer predictive scoring on top of segments to prioritize high-value prospects within each segment.
- **[Personalization & Recommendation Engine](./personalization-recommendation-engine.md)** — Use segments to deliver tailored product or content recommendations per segment.
