---
name: funnel-drop-off-analyzer
description: >
  Diagnose and fix conversion funnel drop-offs across marketing and sales funnels.
  Use this skill when the user says "funnel analysis", "funnel drop-off diagnosis", "conversion funnel
  optimization", "where are we losing leads", "funnel leak identification", "stage-to-stage conversion",
  "pipeline velocity analysis", "funnel bottleneck detection", "lead-to-customer conversion analysis",
  "signup funnel optimization", or "checkout funnel analysis". Also trigger for funnel visualization,
  conversion path analysis, or multi-step funnel diagnosis.
---

# Funnel Drop-Off Analyzer

Diagnoses conversion funnel drop-offs, identifies bottleneck stages, and provides prioritized fixes to improve stage-to-stage conversion rates across marketing, sales, and product funnels.

## Granularity Check

> **Time**: ~5 min data prep → ~10 min Claude session → ~30-60 min building in Google Sheets / Looker / GA4. If implementing fixes, add 1-4 weeks depending on the stage. Input is funnel stage volumes and conversion rates. Output is Markdown funnel diagnosis with stage-by-stage analysis, root causes, and prioritized fixes.

## User Intent Mapping

- "Where are we losing leads in our funnel?" (diagnosis)
- "Our signup flow has high drop-off" (signup)
- "Funnel conversion rates are declining" (trend)
- "Marketing to sales handoff is broken" (handoff)
- "Checkout abandonment analysis" (checkout)
- "Stage-by-stage conversion optimization" (optimization)
- "Funnel comparison: this month vs. last" (comparison)
- "Which funnel stage needs the most work?" (prioritization)
- "Pipeline velocity is too slow" (velocity)
- "Free trial to paid conversion" (trial)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Funnel Stages | Text | Defined stages with names and order |
| Stage Volumes | Text/CSV | Number of users/leads at each stage |
| Time Period | Text | When this data is from |

### If You Don't Have This Data

- **No funnel defined?** Claude helps you define a standard funnel for your business model (SaaS, e-commerce, B2B, services) and recommends tracking for each stage.
- **Missing stage data?** Claude works with available stages and estimates missing transitions using industry benchmarks — then recommends tracking to fill gaps.
- **Only top and bottom of funnel?** Claude reverse-engineers likely middle-funnel metrics based on industry patterns and helps you set up mid-funnel tracking.
- **No historical comparison?** Claude uses industry benchmarks to identify underperforming stages and recommends baseline measurement for future analysis.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Historical Data | CSV | Previous period funnel data for comparison |
| Segment Breakdown | Text | Funnel by channel, device, or audience |
| Time-in-Stage | Text | How long users spend at each stage |
| Drop-off Reasons | Text | Known reasons users leave (surveys, support tickets) |
| Industry Benchmarks | Text | Expected conversion rates for your industry |

## Process

### Step 1: Funnel Mapping

| Business Model | Typical Funnel Stages |
|---|---|
| SaaS | Visit → Sign-up → Activation → Trial → Paid → Expansion |
| E-commerce | Visit → Product View → Add to Cart → Checkout → Purchase |
| B2B Sales | MQL → SQL → Opportunity → Proposal → Close |
| Content/Media | Visit → Read/View → Subscribe → Engage → Convert |
| Marketplace | Visit → Search → View Listing → Contact → Transaction |

### Step 2: Drop-Off Calculation

| Stage | Volume | Stage Conversion | Cumulative Conversion | Drop-Off |
|---|---|---|---|---|
| Stage 1 (top) | 10,000 | — | 100% | — |
| Stage 2 | 3,000 | 30% | 30% | 7,000 (70%) |
| Stage 3 | 900 | 30% | 9% | 2,100 (70%) |
| Stage 4 | 360 | 40% | 3.6% | 540 (60%) |
| Stage 5 (bottom) | 180 | 50% | 1.8% | 180 (50%) |

Key calculations:
- **Stage conversion**: % moving from one stage to next
- **Cumulative conversion**: % of original top-of-funnel reaching this stage
- **Biggest drop-off**: Stage with lowest conversion rate or highest absolute loss
- **Biggest opportunity**: Fixing which stage would yield the most bottom-of-funnel gain

### Step 3: Root Cause Analysis by Stage

| Stage Drop-Off | Common Causes | Diagnostic Questions |
|---|---|---|
| Visit → Sign-up | Wrong traffic, weak value prop, too much friction | Where does traffic come from? What does the page promise? How many form fields? |
| Sign-up → Activation | Unclear next steps, complex setup, no quick win | What's the first action after sign-up? How long to first value? |
| Trial → Paid | Feature gaps, price shock, no urgency | What features are gated? Is pricing clear before trial? |
| MQL → SQL | Misqualified leads, slow follow-up, bad handoff | What qualifies an MQL? How fast does sales respond? |
| SQL → Close | Long sales cycle, decision-maker missing, competitor | Is the right person involved? What's the average sales cycle? |
| Cart → Purchase | Shipping costs, payment friction, trust concerns | When do users see shipping? How many checkout steps? |

### Step 4: Impact Prioritization

| Stage Fix | Current Rate | Improved Rate | Additional Conversions | Revenue Impact |
|---|---|---|---|---|
| Fix Stage 2 (30% → 40%) | 30% | 40% | +1,000 at Stage 2 → +X at bottom | $XXX |
| Fix Stage 3 (30% → 40%) | 30% | 40% | +300 at Stage 3 → +X at bottom | $XXX |
| Fix Stage 4 (40% → 50%) | 40% | 50% | +90 at Stage 4 → +X at bottom | $XXX |

Priority rule: **Fix the highest-volume drop-off that's below benchmark first.** A 5% improvement at a high-volume stage beats a 20% improvement at a low-volume stage.

### Step 5: Stage-Specific Fixes

| Stage Type | Quick Wins | Medium Effort | Strategic |
|---|---|---|---|
| Landing → Signup | Reduce form fields, improve CTA, add social proof | Redesign page, add live chat | Personalize by traffic source |
| Signup → Activation | Welcome email, onboarding checklist, progress bar | Interactive tutorial, setup wizard | AI-powered onboarding |
| Trial → Paid | Usage reminders, feature highlights, urgency emails | In-app upgrade prompts, limited-time offers | Personalized pricing |
| MQL → SQL | Faster follow-up (<5 min), better qualification | Lead scoring refinement, nurture sequences | Intent data integration |
| Cart → Purchase | Guest checkout, express pay, free shipping threshold | One-page checkout, trust badges | Personalized retargeting |

### Step 6: Velocity Analysis

| Stage | Avg Time in Stage | Benchmark | Issue |
|---|---|---|---|
| MQL → SQL | 5 days | 1-2 days | Sales follow-up too slow |
| SQL → Opportunity | 14 days | 7-10 days | Too many qualification meetings |
| Opportunity → Proposal | 21 days | 10-14 days | Proposal creation bottleneck |
| Proposal → Close | 30 days | 14-21 days | Decision process too long |

Velocity fixes:
- Reduce time-in-stage by removing unnecessary steps
- Automate handoffs between stages
- Set SLA targets for each stage transition
- Alert when deals exceed stage time limits

### Confidence & Sample Size

> **Confidence Note**: Funnel analysis needs at least 100 entries at each stage for directionally reliable conversion rates. Below 100, individual behaviors create too much noise. Week-to-week fluctuations are normal — compare month-over-month or use 4-week rolling averages. Funnel data from different sources (analytics vs. CRM) may not match perfectly due to tracking gaps — reconcile definitions before analyzing. Fixing the wrong stage (lowest absolute drop-off vs. lowest conversion rate vs. highest-impact improvement) is the most common mistake.

### ⚠️ Human Checkpoint
> Validate funnel definitions with all stakeholders (marketing, sales, product) — misaligned stage definitions will produce misleading analysis. Test proposed fixes with A/B tests before making permanent changes. Ensure tracking is consistent across stages — gaps in tracking look like drop-offs.

> **Benchmark Context**: Consult current industry reports for up-to-date benchmarks relevant to this analysis.

## Output Contract

### Deliverable: Markdown Funnel Analysis

```markdown
# Funnel Analysis: [Business/Product]

## Funnel Overview
| Stage | Volume | Conversion | Benchmark | Gap | Priority |
|---|---|---|---|---|---|

## Biggest Drop-Off Points
| Stage | Drop-Off Rate | Root Cause | Evidence |
|---|---|---|---|

## Impact Analysis
| Fix | Stage | Improvement | Additional Revenue | Effort |
|---|---|---|---|---|

## Recommended Fixes (Prioritized)
| Priority | Stage | Fix | Expected Lift | Timeline |
|---|---|---|---|---|

## Velocity Analysis
| Stage | Current Time | Target Time | Fix |
|---|---|---|---|

## Segmented Analysis
| Segment | Best Funnel Rate | Worst Funnel Rate | Key Difference |
|---|---|---|---|

## Measurement Plan
| Metric | Baseline | Target | Review Cadence |
|---|---|---|---|
```

## Platform Implementation Steps

### Analytics Setup (GA4)
1. Define funnel steps as events in GA4
2. Create funnel exploration: Explore → Funnel exploration
3. Add steps matching your funnel stages
4. Apply segments (device, channel, geography) for comparison
5. Set up weekly funnel report export

### CRM Setup (HubSpot / Salesforce)
1. Define lifecycle stages and pipeline stages
2. Create funnel report: Reports → Funnels → define stages
3. Add time-in-stage tracking to each pipeline stage
4. Set up conversion rate dashboards by stage
5. Configure alerts for SLA violations (time in stage exceeds target)

### Spreadsheet Analysis
1. Export stage volumes from analytics and CRM
2. Calculate stage conversion rates and cumulative conversion
3. Compare against benchmarks and previous periods
4. Identify largest gap between actual and benchmark
5. Model impact of fixing each stage (sensitivity analysis)

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Fix wrong stage | Focused on lowest conversion rate, not highest-impact stage | Model revenue impact of improving each stage by 5-10% |
| Funnel looks fine but revenue declining | Top-of-funnel volume dropping, not conversion rates | Monitor absolute volumes alongside conversion rates |
| Fixes don't improve conversion | Root cause was misdiagnosed | Gather qualitative data (surveys, interviews, session recordings) |
| Tracking discrepancies | Different tools count differently | Reconcile definitions and data sources before analysis |

## How to Get Your Data

- **Website funnel**: GA4 → Explore → Funnel exploration → define steps
- **Sales funnel**: CRM → pipeline report → stage-to-stage conversion
- **E-commerce**: Shopify/WooCommerce → conversion funnel report
- **Product funnel**: Mixpanel/Amplitude → funnel analysis → define steps
- **No tracking**: Describe your business model — Claude defines funnel stages and recommends tracking setup

## Example

**Input**: "Funnel analysis for our SaaS signup flow. Monthly data: Landing page visitors: 25,000. Started signup: 3,750 (15%). Completed signup: 2,250 (60% of started). Activated (first project created): 675 (30% of signup). Converted to paid: 135 (20% of activated). Overall: 0.54% visitor-to-paid."

**Output**: Funnel diagnosis: your 0.54% visitor-to-paid rate is below SaaS benchmark (2-5%). The biggest opportunity is the activation stage. Stage analysis: (1) Visit → Start signup (15%): Slightly below benchmark (20-25%). Quick wins: stronger CTA, add social proof, reduce perceived commitment. Expected lift: 15% → 20% = +1,250 signups started. (2) Start → Complete signup (60%): This is actually decent for multi-step signups, but below best-in-class (75-85%). Fix: reduce form fields to email + password only, add progress indicator, enable social signup (Google/SSO). Expected lift: 60% → 75% = +375 completed signups. (3) Signup → Activated (30%): This is your biggest bottleneck — benchmark is 40-60%. Users sign up but don't create their first project. P0 fix: implement a guided setup wizard that walks users to their first project within 5 minutes. Add "create your first project" as the immediate post-signup screen (not a dashboard). Send activation email at 24 hours if no project created. Expected lift: 30% → 45% = +337 activated users. (4) Activated → Paid (20%): Below benchmark (25-40%) but acceptable as secondary priority. Fix: in-app upgrade prompts when users hit free tier limits, 14-day trial countdown, comparison of free vs. paid features during usage. Priority order: activation (P0), signup completion (P1), visit-to-signup (P1), activation-to-paid (P2). Fixing activation alone from 30% to 45% would increase paid conversions from 135 to ~202 per month (+50%).

## Related Skills

- **[ab-test-designer](../cro/ab-test-designer.md)** — Test fixes identified in funnel analysis to validate improvements.
- **[dashboard-requirement-gatherer](./dashboard-requirement-gatherer.md)** — Include funnel metrics in dashboard requirements.
- **[marketing-roi-calculator](./marketing-roi-calculator.md)** — Calculate impact of funnel optimizations on ROI.
- **[cohort-analysis-builder](./cohort-analysis-builder.md)** — Analyze funnel performance by user cohort to identify segment-specific issues.
