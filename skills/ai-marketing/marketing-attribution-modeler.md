---
name: marketing-attribution-modeler
description: >
  Design and implement marketing attribution models — multi-touch, data-driven, and channel contribution analysis.
  Use this skill when the user says "marketing attribution model", "multi-touch attribution",
  "attribution analysis", "channel attribution", "marketing ROI attribution", "data-driven
  attribution", "first touch vs last touch", "attribution modeling setup", "marketing mix modeling",
  "campaign attribution report", or "which channels drive conversions". Also trigger for
  attribution window optimization, cross-channel attribution, or incrementality testing.
---

# Marketing Attribution Modeler

Designs and implements marketing attribution models to accurately measure channel contribution, optimize budget allocation, and prove marketing ROI across the customer journey.

## Granularity Check

> **Time**: ~10 min data prep → ~15 min Claude session → ~30-60 min configuring in your marketing platform. If implementing, add 1-4 weeks depending on model complexity. Input is conversion data, channel mix, and current tracking. Output is Markdown attribution model with implementation plan.

## User Intent Mapping

- "Which marketing channels actually drive revenue?" (channel contribution)
- "Set up multi-touch attribution" (MTA setup)
- "First-touch vs. last-touch — what should we use?" (model selection)
- "Attribution model for our marketing" (new model)
- "Our attribution data is a mess" (data quality)
- "Data-driven attribution setup" (advanced)
- "Marketing mix modeling" (MMM)
- "How to prove marketing ROI" (ROI proof)
- "Attribution across online and offline" (cross-channel)
- "Attribution for B2B long sales cycles" (B2B)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Marketing Channels | Text | All channels used (paid, organic, email, etc.) |
| Conversion Events | Text | What counts as a conversion (lead, trial, purchase) |
| Sales Cycle | Text | Average time from first touch to conversion |

### If You Don't Have This Data

- **No tracking setup?** Claude designs a tracking plan from scratch — UTM structure, conversion events, and tool configuration.
- **Limited data?** Claude recommends starting with last-touch attribution and building toward multi-touch as data accumulates.
- **No analytics tools?** Claude works with GA4 (free) attribution models and recommends additional tools by budget.
- **B2B long cycle?** Claude designs attribution for long cycles with touchpoint weighting appropriate for 3-12 month sales processes.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Conversion Data | CSV | Touchpoint sequences per conversion |
| Channel Spend | CSV | Monthly spend per channel |
| CRM Data | CSV | Lead-to-close touchpoints |
| Current Model | Text | What attribution you currently use |
| Tech Stack | Text | Analytics, CRM, marketing tools |

## Process

### Step 1: Attribution Model Selection
| Model | Best For | Pros | Cons |
|---|---|---|---|
| Last-touch | Simple, short cycles | Easy to implement | Ignores upper funnel |
| First-touch | Awareness campaigns | Shows what generates demand | Ignores nurture |
| Linear | Equal credit desired | Fair to all channels | Oversimplifies |
| Time-decay | Long sales cycles | Weights recent touches more | Complex setup |
| Position-based | B2B with clear funnel | Credits intro and close | Arbitrary weights |
| Data-driven | 500+ monthly conversions | Based on actual data | Needs volume, complexity |
| Marketing mix modeling | Includes offline | Statistical, privacy-safe | Requires spend data, expertise |

### Step 2: Touchpoint Mapping
- Identify all trackable touchpoints (ad click, organic visit, email open, event attendance)
- Define touchpoint categories (paid, organic, owned, earned)
- Map touchpoint sequence for typical conversion path
- Identify offline touchpoints (events, calls, direct mail) and how to track them
- Set attribution window (7 days, 30 days, 90 days based on sales cycle)

### Step 3: Data Infrastructure
- UTM parameter structure and governance
- Cross-device and cross-channel identity resolution
- CRM integration for lead-to-revenue tracking
- Cookie consent and privacy-compliant tracking
- Data warehouse setup for attribution data

### Step 4: Model Implementation
- Configure chosen model in analytics platform
- Set up conversion tracking for all defined conversion events
- Create channel groupings that match your marketing taxonomy
- Build attribution reports per channel, campaign, and content piece
- Compare model outputs to validate reasonableness

### Step 5: Incrementality Validation
- Geo-based holdout tests (pause channel in one region, measure impact)
- Matched market tests for offline channels
- Lift studies (Meta, Google) for digital channels
- Before/after analysis for new channel launches
- Compare attribution model output vs. incrementality results

### Step 6: Budget Optimization
- Map attributed revenue per dollar spent per channel
- Calculate marginal ROI (diminishing returns per channel at current spend)
- Identify channels with highest CAC and lowest ROAS
- Model budget reallocation scenarios
- Set channel-level ROAS targets based on attribution data

### Confidence & Sample Size

> **Confidence Note**: No attribution model is perfect — every model has biases. Last-touch overcredits bottom-funnel; first-touch overcredits top-funnel. Data-driven models need 500+ monthly conversions to be reliable. Cookie deprecation and privacy regulations are making digital attribution harder — consider marketing mix modeling as a complement. Use attribution as a directional guide, not absolute truth. Validate with incrementality testing.

### ⚠️ Human Checkpoint
> Review model assumptions with stakeholders before implementation. Validate attribution data against finance-reported revenue. Run incrementality tests before making major budget shifts based on attribution alone.

> **Benchmark Context**: Consult current industry reports for up-to-date benchmarks relevant to this analysis.

## Output Contract

### Deliverable: Markdown Attribution Model

```markdown
# Marketing Attribution Model: [Company]

## Model Selection
- Chosen model: [model]
- Rationale: [why]
- Attribution window: [days]

## Touchpoint Map
| Touchpoint | Channel | Category | Weight |
|---|---|---|---|

## Data Infrastructure
| Component | Current | Required | Gap |
|---|---|---|---|

## Channel Attribution
| Channel | Spend | Attributed Revenue | ROAS | CPA |
|---|---|---|---|---|

## Model Comparison
| Channel | Last-Touch | First-Touch | [Chosen Model] | Delta |
|---|---|---|---|---|

## Budget Recommendations
| Channel | Current Spend | Recommended | Change | Expected Impact |
|---|---|---|---|---|

## Validation Plan
| Test | Channel | Method | Timeline |
|---|---|---|---|

## Implementation Roadmap
| Phase | Action | Timeline |
|---|---|---|
```

## Platform Implementation Steps

### GA4
1. Admin → Attribution Settings → select model and lookback window
2. Configure conversion events in GA4
3. Set up cross-domain tracking if applicable
4. Build Exploration reports for attribution analysis
5. Enable Google Ads data import for cost data

### HubSpot
1. Reports → Attribution Reports → select model
2. Ensure all marketing channels are tracked via UTM parameters
3. Configure contact create attribution and revenue attribution
4. Build custom attribution reports per channel and campaign

### CRM-Based (Salesforce)
1. Enable Campaign Influence tracking
2. Configure multi-touch attribution model (first-touch, even, custom)
3. Map marketing touches to opportunities via Campaign Members
4. Build attribution dashboards in Salesforce or BI tool

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Attribution data doesn't match revenue | Tracking gaps, attribution window mismatch | Audit tracking; extend attribution window; reconcile with finance data |
| Model credits wrong channels | Model bias (last-touch overcredits branded search) | Compare multiple models; validate with incrementality tests |
| Stakeholders don't trust model | Results contradict intuition or prior beliefs | Explain model logic; show comparison across models; run validation tests |
| Privacy regulations block tracking | Cookie consent reduces tracked conversions | Implement server-side tracking; adopt marketing mix modeling; use modeled conversions |

## How to Get Your Data

- **Channel performance**: GA4 → Advertising → Attribution paths; or CRM → campaign influence reports
- **Spend data**: Finance or ad platforms → monthly spend per channel
- **Conversion data**: CRM → all touchpoints per converted lead/opportunity
- **No attribution data**: Describe your channels and sales process — Claude designs a tracking and attribution plan from scratch

## Example

**Input**: "Marketing attribution model. B2B SaaS, $20K ACV, 90-day average sales cycle. Channels: Google Ads, LinkedIn Ads, organic search, content marketing, webinars, email nurture. Using GA4 and HubSpot. $50K/month marketing budget. Currently using last-touch — organic search gets all the credit."

**Output**: Problem: last-touch overcredits organic search because it's often the final click before demo booking, but other channels drive initial awareness. Recommended model: position-based (40% first-touch, 40% last-touch, 20% middle touches) — appropriate for B2B with clear awareness → consideration → decision funnel. Attribution window: 90 days (matching sales cycle). Reattribution analysis: moving from last-touch to position-based will likely shift 25-35% of credit from organic search to LinkedIn Ads (awareness) and webinars (middle touch). Implementation: (1) HubSpot — enable multi-touch revenue attribution; configure for position-based model. (2) GA4 — switch to data-driven attribution (Google's default). (3) UTM governance — standardize UTM naming across all channels. (4) CRM — track all offline touchpoints (webinars, sales calls) as HubSpot campaigns. Validation: run geo-based holdout test on LinkedIn Ads (pause in one region for 60 days, compare pipeline). Expected outcome: discover LinkedIn Ads drives 20-25% of pipeline when properly attributed, justifying current spend. Organic search contribution drops from 60% (last-touch) to 30-35% (position-based) — still valuable but not the only driver.

## Related Skills

- **[Marketing ROI Calculator](../analytics/marketing-roi-calculator.md)** — Use attribution insights to calculate true ROI by channel after mapping touchpoints accurately.
- **[Marketing Mix Modeler](../analytics/marketing-mix-modeler.md)** — Complement attribution with econometric modeling to test optimal budget allocation.
- **[Campaign Performance Benchmarker](../analytics/campaign-performance-benchmarker.md)** — Compare attributed performance across campaigns to identify top-performing channel combinations.
- **[UTM Tracking Manager](../martech-ops/utm-tracking-manager.md)** — Ensure consistent UTM tagging across channels to enable accurate attribution modeling.
