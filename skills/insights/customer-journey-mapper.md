---
name: customer-journey-mapper
description: >
  Map and analyze customer journeys across touchpoints to identify friction, drop-offs, and optimization opportunities.
  Use this skill when the user says "customer journey mapping", "buyer journey analysis", "touchpoint mapping",
  "customer experience mapping", "journey optimization", "path to purchase analysis", "customer journey audit",
  "omnichannel journey design", "journey stage analysis", "customer lifecycle mapping", or "journey friction
  identification". Also trigger for cross-channel journey analysis, moments of truth mapping, or journey
  orchestration strategy.
---

# Customer Journey Mapper

Maps customer journeys across touchpoints, identifies friction points and drop-offs, and designs optimized experiences for higher conversion and retention.

## Granularity Check

> **Session time**: ~10 min context gathering + ~15 min Claude session. If implementing, add 1-2 weeks for data collection and validation. Input is customer data, touchpoint inventory, and conversion metrics. Output is Markdown journey map with optimization plan.

## User Intent Mapping

- "Map our customer journey" (mapping)
- "Where do customers drop off?" (friction)
- "Customer touchpoint analysis" (touchpoints)
- "Path to purchase — what's happening?" (purchase path)
- "Customer experience gaps" (gaps)
- "Journey from awareness to purchase" (full funnel)
- "Omnichannel customer experience" (omnichannel)
- "Customer lifecycle stages" (lifecycle)
- "Moments of truth in our journey" (critical moments)
- "Journey orchestration strategy" (orchestration)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Business Model | Text | B2B/B2C/DTC, product type, sales cycle |
| Key Touchpoints | Text | Where customers interact with your brand |
| Conversion Goals | Text | What success looks like at each stage |

### If You Don't Have This Data

- **No journey data?** Claude builds a journey hypothesis based on your business model and industry patterns, then recommends data collection to validate.
- **Don't know all touchpoints?** Claude maps the typical touchpoints for your business type and helps you identify gaps in your tracking.
- **No cross-channel data?** Claude designs each channel's journey independently and identifies likely cross-channel patterns to investigate.
- **No customer research?** Claude creates a journey based on behavioral data and recommends customer interviews to validate assumptions.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Analytics Data | CSV | Traffic sources, page flows, conversion funnels |
| Customer Interviews | Text | Qualitative journey feedback |
| Support Data | Text | Common complaints, support ticket themes |
| NPS/CSAT Scores | Text | Satisfaction at different journey stages |
| Competitor Journeys | Text | How competitors handle key touchpoints |

## Process

### Step 1: Journey Stage Framework
| Stage | Customer Goal | Brand Goal | Key Metric |
|---|---|---|---|
| Awareness | "I have a problem" | Get noticed | Reach, impressions |
| Consideration | "What are my options?" | Educate and differentiate | Engagement, time on site |
| Evaluation | "Is this right for me?" | Build confidence | Demo requests, trial signups |
| Purchase | "I'm ready to buy" | Remove friction | Conversion rate |
| Onboarding | "Help me get started" | Deliver quick value | Time to first value |
| Adoption | "Make this part of my routine" | Drive usage | Feature adoption, DAU/MAU |
| Advocacy | "I love this — tell others" | Activate champions | Referrals, reviews, NPS |

### Step 2: Touchpoint Inventory
Per stage, map:
- **Channels**: Web, email, social, ads, sales, support, in-app
- **Content**: What content exists at this touchpoint
- **Action**: What the customer does here
- **Emotion**: How the customer feels (frustrated, confident, excited, confused)
- **Metric**: How you measure success at this point
- **Gap**: What's missing or broken

### Step 3: Friction Identification
| Friction Type | Signals | Impact |
|---|---|---|
| Information gap | High bounce on key pages, support tickets asking basic questions | Customers can't find what they need to decide |
| Trust gap | Low conversion despite high traffic, checkout abandonment | Customers don't feel confident enough to commit |
| Effort gap | Multi-step processes with high drop-off | Process requires too much customer effort |
| Expectation gap | High refund/churn, low NPS after purchase | Product doesn't match what was promised |
| Channel gap | Customers switching channels to complete tasks | Journey breaks when crossing channels |

### Step 4: Moments of Truth
Critical interactions that disproportionately influence the overall journey:
- **First impression**: Initial website visit or ad interaction
- **Evaluation moment**: Comparing your solution to alternatives
- **Purchase decision**: The final conversion moment
- **First use**: Initial product or service experience
- **Problem resolution**: How you handle issues
- **Renewal/repurchase**: Decision to continue the relationship

### Step 5: Journey Optimization
Per friction point:
- **Quick win**: What can be fixed in 1-2 weeks (copy changes, CTA moves, email additions)
- **Medium effort**: What requires 2-8 weeks (page redesign, new content, flow changes)
- **Strategic investment**: What requires 2-6 months (new channels, platform changes, personalization)

### Step 6: Journey Orchestration
- Define triggers that move customers between stages
- Design automated nudges for stalled journeys
- Create re-engagement paths for dropped-off customers
- Build cross-channel handoff protocols (email → web, social → sales)
- Set up journey analytics dashboard for ongoing monitoring

### Confidence & Sample Size

> **Confidence Note**: Journey maps based solely on internal assumptions are wrong 60-70% of the time. Validate with actual customer behavior data (analytics) and customer research (interviews). The most valuable journey insights come from analyzing where customers deviate from the designed journey. Journey optimization is iterative — don't try to fix everything at once. Focus on the highest-drop-off stages first. B2B journeys are rarely linear and involve multiple stakeholders — map the buying committee, not just one persona.

### ⚠️ Human Checkpoint
> Validate journey maps with real customers through interviews or surveys. Internal stakeholders often have blind spots about customer experience. Test journey changes with a subset of customers before rolling out broadly.

> **Benchmark Context**: Companies with documented customer journey maps are 2.4x more likely to exceed revenue goals. 89% of customers switch brands after a poor experience. Reducing customer effort by one point on a 7-point scale increases repurchase likelihood by 94%. Companies that optimize for moments of truth see 20-30% improvement in customer satisfaction. Cross-channel customers have 30% higher lifetime value than single-channel customers.

## Output Contract

### Deliverable: Markdown Journey Map

```markdown
# Customer Journey Map: [Persona/Segment]

## Journey Overview
- Persona: [who]
- Journey type: [acquisition/retention/expansion]
- Stages: [number of stages]
- Key metric: [north star]

## Journey Map
### Stage: [Name]
- **Customer goal**: [what they want]
- **Touchpoints**: [channels and interactions]
- **Content**: [what they see/receive]
- **Emotion**: [how they feel]
- **Friction**: [what's broken]
- **Metric**: [how you measure]
- **Drop-off rate**: [% who leave at this stage]

[Repeat for each stage]

## Friction Points
| Stage | Friction | Severity | Evidence | Fix |
|---|---|---|---|---|

## Moments of Truth
| Moment | Current Experience | Ideal Experience | Gap | Priority |
|---|---|---|---|---|

## Optimization Plan
| Fix | Stage | Effort | Expected Impact | Timeline |
|---|---|---|---|---|

## Journey Orchestration
| Trigger | Action | Channel | Timing |
|---|---|---|---|
```

## Platform Implementation Steps

### Analytics Setup
1. Map conversion funnel in GA4 matching journey stages
2. Set up cross-device tracking (User-ID feature in GA4)
3. Create audience segments by journey stage
4. Track micro-conversions at each stage (not just final conversion)
5. Build journey dashboard showing stage-to-stage conversion rates

### Marketing Automation
1. Map email/nurture sequences to journey stages
2. Set up behavioral triggers for stage transitions
3. Create re-engagement flows for stalled journeys
4. Design cross-channel handoff automation
5. Build dynamic content rules based on journey stage

### Customer Research
1. Conduct 10-15 customer interviews covering full journey
2. Survey customers at key moments of truth (post-purchase, post-onboarding)
3. Analyze support tickets for journey friction themes
4. Review session recordings of key journey touchpoints
5. Run quarterly journey validation with new customer data

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Journey map doesn't match reality | Based on assumptions, not data | Validate with analytics + customer interviews |
| Too complex to act on | Mapped every possible path | Focus on primary journey for primary persona |
| Stakeholders disagree on journey | Different teams see different touchpoints | Use data to resolve disputes; run cross-functional workshop |
| Optimization doesn't improve metrics | Fixed low-impact friction points | Prioritize by drop-off rate × traffic volume |

## How to Get Your Data

- **Funnel data**: GA4 → Explore → Funnel exploration → define stages
- **Path analysis**: GA4 → Explore → Path exploration → starting/ending pages
- **Support themes**: Support tool → export tickets → categorize by journey stage
- **Customer voice**: Interview 10-15 customers about their experience from discovery to current
- **No data**: Describe your business and typical customer — Claude creates a journey hypothesis

## Example

**Input**: "Map the customer journey for our B2B SaaS. Sales cycle: 30-60 days. Touchpoints: website, blog, demo request form, sales calls, free trial, email nurture. Problems: 60% of demo requests don't show up, 40% of free trial users never log in after day 1. 2,000 monthly website visitors, 3% demo request rate."

**Output**: Journey map reveals 2 critical gaps: (1) Demo no-show (60%): gap between request and demo. Currently: form → confirmation email → demo 3-5 days later. Fix: add instant calendar booking (reduce to same-day or next-day), send 3-email confirmation sequence (immediate confirmation with prep materials, 24-hour reminder with social proof, 1-hour reminder with meeting link), add SMS reminder option. Expected: reduce no-shows from 60% to 25-30%. (2) Trial abandonment (40% never return after day 1): no onboarding guidance. Fix: add in-app onboarding checklist, send Day 1 email with "3 things to try first," trigger live chat at 5-minute mark for stuck users, send Day 3 email highlighting key feature based on user role. Expected: reduce day-1 abandonment from 40% to 15-20%. Additional findings: blog → demo path is strongest conversion path (5.2% vs. 1.8% from homepage), but blog has no CTA on 60% of posts. Quick win: add contextual CTAs to all blog posts. Journey orchestration: set up behavioral triggers — if trial user completes setup → congratulations email; if trial user stalls → help email at 24 hours; if trial user succeeds → sales outreach at day 7.
