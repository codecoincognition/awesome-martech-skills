---
name: event-roi-calculator
description: >
  Calculate and optimize ROI for marketing events, conferences, trade shows, and sponsored experiences.
  Use this skill when the user says "event ROI calculation", "trade show ROI", "conference ROI analysis",
  "event marketing ROI", "was our event worth it", "event cost-benefit analysis", "sponsorship ROI",
  "event pipeline attribution", "event marketing budget justification", "calculate event return", or
  "event performance metrics". Also trigger for event budget planning, post-event performance review,
  or event marketing effectiveness measurement.
---

# Event ROI Calculator

Calculates and optimizes ROI for marketing events by tracking costs, attributing pipeline and revenue, and providing frameworks for pre-event budgeting and post-event analysis.

## Granularity Check

> **Time**: ~10 min data prep → ~10 min Claude session → ~120-240 min coordinating across vendors. If building a full event measurement program, add 2-4 weeks for tracking setup. Input is event costs and results data. Output is Markdown ROI analysis with attribution framework, benchmarks, and optimization recommendations.

## User Intent Mapping

- "Was our trade show booth worth it?" (post-event)
- "How to calculate event ROI" (methodology)
- "Should we sponsor this conference?" (pre-event)
- "Event budget justification for leadership" (justification)
- "Track pipeline from events" (attribution)
- "Compare event ROI across our events" (comparison)
- "Event marketing budget planning" (budgeting)
- "Post-event analysis framework" (analysis)
- "Event cost per lead" (efficiency)
- "Sponsorship tier evaluation" (sponsorship)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Event Costs | Text/CSV | All costs (booth, travel, sponsorship, swag, staff time) |
| Event Results | Text | Leads, meetings, pipeline, or revenue generated |
| Event Type | Text | Conference, trade show, hosted event, webinar, sponsorship |

### If You Don't Have This Data

- **No post-event data?** Claude provides an event tracking checklist and attribution framework to capture data at your next event.
- **Can't attribute revenue to events?** Claude designs a multi-touch attribution approach that gives events fair credit alongside other channels.
- **No benchmark data?** Claude provides industry benchmarks for event CPL, pipeline generation, and ROI by event type.
- **First event?** Claude helps you set realistic targets based on event size, your industry, and typical conversion rates.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Staff Time | Text | Hours spent by team on event prep, attendance, follow-up |
| Opportunity Data | CSV | Deals influenced or sourced by event |
| Historical Events | Text | Past event performance for comparison |
| Sales Cycle Data | Text | Average time from event to closed deal |
| Brand Impact | Text | Qualitative benefits (awareness, relationships, partnerships) |

## Process

### Step 1: Full Cost Accounting

| Cost Category | Line Items | Often Missed |
|---|---|---|
| Sponsorship/Booth | Sponsorship fee, booth rental, space upgrade | Electricity, Wi-Fi, lead scanner rental |
| Travel | Flights, hotels, ground transport, meals | Per diem, tips, visa fees |
| Materials | Booth design, signage, banners, displays | Shipping to/from venue, storage |
| Swag/Collateral | Giveaways, brochures, business cards | Design cost, minimum order quantities |
| Staff | Salaries for time spent (prep + event + follow-up) | Opportunity cost, overtime |
| Technology | Lead capture app, demo equipment, screens | Rental equipment, internet upgrades |
| Entertainment | Client dinners, hosted happy hours, VIP events | Venue rental, catering minimums |
| Marketing | Pre-event promotion, social media, email campaigns | Content creation, paid promotion |

### Step 2: Revenue Attribution

| Attribution Model | Description | Best For |
|---|---|---|
| First touch | Event gets full credit if it was first interaction | Events that drive net-new pipeline |
| Last touch | Event gets full credit if it was last touch before close | Events focused on deal acceleration |
| Multi-touch equal | Event gets equal share of credit with other touches | Balanced view across marketing |
| Multi-touch weighted | Event gets weighted credit based on influence | Most accurate but complex |
| Self-reported | Sales or customer says event influenced the deal | Supplementary data point |
| Time-decay | Recent touches (including events) get more credit | Deals with long sales cycles |

### Step 3: ROI Calculation

| Metric | Formula | Example |
|---|---|---|
| Event ROI | (Revenue - Cost) / Cost × 100 | ($150K - $50K) / $50K = 200% |
| Cost per lead (CPL) | Total Cost / Total Leads | $50K / 200 leads = $250 CPL |
| Cost per meeting | Total Cost / Meetings Booked | $50K / 40 meetings = $1,250 |
| Cost per opportunity | Total Cost / Opportunities Created | $50K / 15 opps = $3,333 |
| Pipeline generated | Total pipeline value from event | $500K pipeline from $50K spend |
| Pipeline-to-spend ratio | Pipeline / Cost | $500K / $50K = 10:1 |
| Revenue-to-spend ratio | Closed revenue / Cost | $150K / $50K = 3:1 |

### Step 4: Event Type Benchmarks

| Event Type | Avg CPL | Pipeline Ratio | ROI Timeline | Typical ROI |
|---|---|---|---|---|
| Industry conference (booth) | $150-400 | 8-15:1 | 3-9 months | 200-500% |
| Trade show | $100-300 | 5-12:1 | 3-6 months | 150-400% |
| Hosted dinner/roundtable | $200-500 | 10-20:1 | 2-6 months | 300-800% |
| Webinar | $30-75 | 5-10:1 | 1-3 months | 400-1000% |
| Sponsored conference | $250-600 | 5-10:1 | 3-12 months | 100-300% |
| User conference (own event) | $300-800 | 15-30:1 | 1-6 months | 200-600% |
| Field event (workshop) | $100-250 | 8-15:1 | 1-4 months | 300-700% |

### Step 5: Beyond-ROI Value Assessment

| Value Category | How to Measure | Impact |
|---|---|---|
| Brand awareness | Social mentions, booth traffic, press coverage | Long-term pipeline growth |
| Relationship building | Executive meetings, partner conversations | Deal acceleration, referrals |
| Competitive intelligence | Competitor booth observations, attendee conversations | Strategic advantage |
| Recruitment | Candidates met, employer brand impressions | Hiring pipeline |
| Product feedback | Feature requests, user conversations | Product roadmap input |
| Content generation | Speaking sessions, customer quotes, video | Marketing asset creation |

### Step 6: Optimization Recommendations

| Current Situation | Optimization | Expected Impact |
|---|---|---|
| High CPL, low conversion | Better pre-event targeting and outreach | 30-50% CPL reduction |
| Good leads but low pipeline | Faster, more structured follow-up | 2-3x pipeline conversion |
| Expensive booth, low traffic | Invest in pre-event promotion, not booth size | Same traffic at 40% lower cost |
| Staff time dominates cost | Reduce team size, extend via virtual participation | 20-30% cost reduction |
| Good pipeline, long close cycle | Add event-specific offers or incentives | 20-30% faster close |

### Confidence & Sample Size

> **Confidence Note**: Event ROI typically takes 3-12 months to fully materialize due to sales cycle length — measuring ROI at 30 days post-event significantly underestimates true return. Pipeline-to-spend ratio is more useful than immediate revenue ROI for long-cycle B2B events. Self-reported attribution ("how did you hear about us?") is 30-40% less accurate than tracked attribution but captures influence that tracking misses. Compare event CPL to other channel CPLs for context — a $300 event CPL may be efficient if your average CAC is $5,000.

### ⚠️ Human Checkpoint
> Validate event attribution with sales team — CRM data alone may miss event influence on existing deals. Ensure costs include ALL categories (staff time is commonly 30-40% of true event cost and often excluded). Compare event ROI to the same investment in other channels before making budget decisions.

> **Benchmark Context**: B2B events generate 24% of total marketing pipeline on average (Bizzabo 2024 Event Marketing Report). The average B2B event ROI is 3-5:1 (revenue to spend) when measured over 12 months (Bizzabo 2024 Event Marketing Report). 68% of event leads require 3+ follow-up touches to convert (Bizzabo 2024 Event Marketing Report). Companies that follow up within 24 hours of an event convert leads at 2-3x the rate of those who wait a week (Bizzabo 2024 Event Marketing Report). The cost of NOT attending a key industry event is hard to quantify but real — competitors meeting your prospects is a hidden cost. (Bizzabo 2024 Event Marketing Report).
## Output Contract

### Deliverable: Markdown Event ROI Report

```markdown
# Event ROI Analysis: [Event Name]

## Event Summary
- Type: [conference/trade show/hosted/webinar]
- Date: [when]
- Location: [where]
- Our presence: [booth/sponsor/speaker/attendee]

## Cost Breakdown
| Category | Cost | % of Total |
|---|---|---|

## Results
| Metric | Count | Cost Per | Benchmark | vs. Benchmark |
|---|---|---|---|---|

## Pipeline Attribution
| Deal | Stage | Value | Attribution Model | Event Credit |
|---|---|---|---|---|

## ROI Summary
| Metric | Value |
|---|---|
| Total investment | $X |
| Pipeline generated | $X |
| Revenue attributed (to date) | $X |
| Pipeline-to-spend ratio | X:1 |
| Current ROI | X% |
| Projected 12-month ROI | X% |

## Beyond-ROI Value
| Category | Value | Evidence |
|---|---|---|

## Recommendations
| Action | Rationale | Impact |
|---|---|---|

## Year-over-Year Comparison (if applicable)
| Metric | This Year | Last Year | Change |
|---|---|---|---|
```

## Platform Implementation Steps

### Pre-Event Tracking Setup
1. Create event-specific campaign in CRM (HubSpot, Salesforce)
2. Set up lead capture tool with event source tagging
3. Create UTM parameters for all event-related links
4. Prepare pre-event outreach tracking (emails sent, meetings booked)
5. Brief sales team on lead capture and CRM logging requirements

### During-Event Data Collection
1. Capture all leads with consistent data format
2. Log meetings held and key conversations
3. Track booth traffic and engagement metrics
4. Document competitive intelligence and market insights
5. Capture social media mentions and engagement

### Post-Event Analysis
1. Import all leads into CRM with event campaign attribution
2. Track pipeline creation from event leads (30, 60, 90 days)
3. Calculate full cost including staff time and opportunity cost
4. Compare results to pre-event targets and benchmarks
5. Produce ROI report for leadership within 2 weeks of event

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Can't calculate ROI | No tracking setup before event | Implement tracking checklist for next event; estimate based on available data |
| ROI looks terrible | Measured too early (before deals close) | Re-measure at 6 and 12 months; use pipeline ratio instead of revenue |
| Staff time not included | Only counting out-of-pocket expenses | Add loaded labor cost (salary × hours / working hours per year) |
| Over-attributing to events | Multi-touch deals credited entirely to event | Use weighted multi-touch attribution |

## How to Get Your Data

- **Costs**: Finance/procurement → invoices, POs, expense reports for event
- **Leads**: Lead capture tool or CRM → filter by event campaign
- **Pipeline**: CRM → opportunities tagged to event campaign → pipeline value
- **Revenue**: CRM → closed-won deals with event campaign touch
- **No CRM tagging**: Manually list deals where event attendees are contacts; ask sales team

## Example

**Input**: "Event ROI for our booth at SaaS Connect 2026. Costs: booth $12K, travel (4 people) $8K, materials/swag $3K, booth design $5K, staff time (80 hours × $75/hr) $6K. Total: $34K. Results: 185 badge scans, 42 qualified leads, 18 meetings booked, 8 opportunities created ($680K pipeline), 2 closed deals ($85K revenue so far). Event was 6 weeks ago."

**Output**: ROI analysis: (1) Current metrics: CPL = $34K / 42 qualified leads = $810. Cost per meeting = $34K / 18 = $1,889. Cost per opportunity = $34K / 8 = $4,250. Pipeline-to-spend ratio = $680K / $34K = 20:1 (excellent — benchmark is 8-15:1). Current revenue ROI = ($85K - $34K) / $34K = 150%. (2) Projected ROI: 6 of 8 opportunities still open ($595K pipeline remaining). At your typical 30% close rate, expect $178K additional revenue. Projected total revenue: $263K. Projected ROI: ($263K - $34K) / $34K = 673%. (3) Assessment: this was a strong event. Pipeline ratio of 20:1 is above benchmark. CPL of $810 is moderate for B2B SaaS conferences but reasonable given deal sizes ($85K+ average). (4) Optimization for next year: reduce badge scanning focus (185 scans but only 42 qualified — 23% qualification rate). Invest in pre-event outreach to book more meetings before the event (target 25+ vs. 18). Consider reducing team to 3 people (saves $2K travel + $1.5K staff time). Expected improvement: same pipeline at $30K cost, improving ROI to 775%.

## Related Skills

- **[Marketing ROI Calculator](../analytics/marketing-roi-calculator.md)** — Calculate overall marketing ROI with event contribution included.
- **[Event Logistics Coordinator](./event-logistics-coordinator.md)** — Review logistics efficiency as a cost component of ROI calculation.
- **[Attribution Model Builder](../analytics/attribution-model-builder.md)** — Build attribution model that properly credits events for pipeline influenced.
- **[Campaign Performance Benchmarker](../analytics/campaign-performance-benchmarker.md)** — Compare event ROI to other marketing campaign ROI for budget allocation decisions.
