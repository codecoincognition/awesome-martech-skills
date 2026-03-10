---
name: channel-mix-optimizer
description: >
  Optimize marketing channel mix based on performance data, budget, and growth stage.
  Use this skill when the user says "channel mix optimization", "marketing channel strategy",
  "where should we invest our marketing budget", "channel performance comparison", "best
  marketing channels for us", "channel diversification strategy", "reduce channel dependency",
  "customer acquisition channel analysis", "organic vs paid mix", "channel ROI comparison",
  or "marketing investment strategy". Also trigger for channel attribution analysis, new
  channel evaluation, or channel saturation detection.
---

# Channel Mix Optimizer

Analyzes marketing channel performance to recommend optimal budget allocation, identify channel saturation, and plan strategic diversification based on growth stage and business goals.

## Granularity Check

> **Time**: ~5 min data prep → ~10 min Claude session → ~60-120 min implementing in your product / tools. If implementing output, add 15-30 min for budget adjustments across channels. Input is multi-channel performance data. Output is Markdown channel strategy with allocation plan.

## User Intent Mapping

- "Which marketing channels should we focus on?" (strategy)
- "Optimize our channel mix for growth" (optimization)
- "We're too dependent on Google Ads — diversify" (diversification)
- "Channel performance comparison for Q1" (analysis)
- "Should we invest in TikTok/LinkedIn/podcasts?" (new channel evaluation)
- "Our organic traffic is declining — channel rebalance" (rebalancing)
- "Marketing budget allocation across channels" (budget planning)
- "Which channels are saturating?" (saturation detection)
- "Channel strategy for a startup with $10K/month" (stage-specific)
- "Compare CAC across all channels" (benchmarking)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Channel Performance | CSV or Text | Channel, spend, leads/conversions, revenue (if available) |
| Total Marketing Budget | Number | Monthly or quarterly budget |
| Business Goal | Text | Growth stage and primary objective |

### If You Don't Have This Data

- **No multi-channel data?** List your active channels and estimate monthly spend per channel. Even rough estimates are useful.
- **No revenue attribution?** Use leads or conversions as the optimization metric. Set up multi-touch attribution as a priority.
- **No historical trends?** Provide current-month data. Claude compares to industry benchmarks. Start tracking monthly for trend analysis.
- **First-time marketer?** Describe your product, audience, and total budget — Claude recommends a starting channel mix.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Historical Data | CSV | 3-12 months of channel data for trend analysis |
| Customer LTV | Number | Lifetime value for CAC payback analysis |
| Sales Cycle | Text | Average time from lead to close |
| Competitor Channels | Text | Where competitors are investing |
| Growth Stage | Text | Pre-product-market-fit, scaling, mature |

## Process

### Step 1: Channel Performance Analysis
Calculate per-channel metrics:
- CAC (Customer Acquisition Cost) = Channel spend ÷ customers acquired
- Channel ROAS = Revenue from channel ÷ channel spend
- Contribution margin = Revenue per customer - CAC
- CAC payback period = CAC ÷ monthly revenue per customer

### Step 2: Channel Efficiency Ranking
Score channels on a composite index:
- Volume (how many customers does it deliver?)
- Efficiency (what's the CAC relative to LTV?)
- Scalability (can we 2x spend and maintain efficiency?)
- Time to result (how fast does it deliver?)
- Sustainability (will it keep working without active investment?)

### Step 3: Growth Stage Framework
| Stage | Priority Channels | Budget Split |
|---|---|---|
| Pre-PMF (<$1M ARR) | Content, community, founder-led sales, referrals | 80% organic, 20% paid experiments |
| Early Growth ($1-5M) | SEO, paid search, content, email, 1-2 paid channels | 50% organic, 50% paid |
| Scaling ($5-20M) | Diversified paid, SEO, partnerships, events | 30% organic, 70% paid |
| Mature ($20M+) | Full channel mix, brand, offline, programmatic | 25% organic, 75% paid + brand |

### Step 4: Saturation Detection
For each channel, check:
- Is CAC increasing month-over-month despite consistent spend?
- Is impression share or reach plateauing?
- Are diminishing returns visible (doubling spend ≠ doubling results)?
- Is frequency cap being hit (same users seeing ads repeatedly)?

### Step 5: Reallocation Recommendations
- Shift from saturated to high-potential channels
- Maintain minimum viable investment in all proven channels
- Allocate 10-20% as a testing budget for new channels
- Plan 90-day transition (don't shift all at once)

### Confidence & Sample Size
> **Confidence Note**: Channel mix optimization is inherently imprecise because channels interact (search + display, social + email). Attribution models attribute differently — last-click favors bottom-of-funnel, multi-touch gives more credit to awareness channels. Always consider a 15-25% attribution overlap when summing channel contributions. Make changes gradually and measure for 30+ days before drawing conclusions.

### ⚠️ Human Checkpoint
> Review recommendations against strategic context — some channels serve brand/awareness goals not captured by CAC alone. Verify no contractual commitments (agency retainers, media buys) would be violated by reallocation. Consider team skills — shifting to a channel requires expertise to execute well.

> **Benchmark Context**: Best-in-class companies attribute revenue across 5-7 channels (ProfitWell 2024 SaaS Benchmarks). . Over-reliance on one channel (>50% of revenue) is high-risk (ProfitWell 2024 SaaS Benchmarks). . Organic channels (SEO, content, community) have 5-10x better LTV-to-CAC ratios than paid channels but take 6-12 months to build (OpenView 2024 Product Benchmarks) Testing a new channel requires minimum 3-month commitment and $5,000-10,000 investment to evaluate. . (OpenView 2024 Product Benchmarks).
## Output Contract

### Deliverable: Markdown Channel Strategy

```markdown
# Channel Mix Optimization: [Brand] — [Period]

## Current Channel Performance
| Channel | Spend | Customers | CAC | Revenue | ROAS | Trend |
|---|---|---|---|---|---|---|

## Channel Efficiency Ranking
1. [Channel]: CAC $X, ROAS X.X — [status]

## Saturation Analysis
| Channel | Saturation Level | Evidence |
|---|---|---|

## Recommended Channel Mix
| Channel | Current % | Recommended % | Budget | Rationale |
|---|---|---|---|---|

## New Channel Evaluation
| Channel | Opportunity | Investment | Expected CAC | Timeline |
|---|---|---|---|---|

## 90-Day Transition Plan
| Month | Action | Expected Impact |
|---|---|---|

## Key Risks
1. [Risk]: [Mitigation]
```

## Platform Implementation Steps

### Google Analytics (Attribution)
1. Set up GA4 → Attribution → Model Comparison
2. Compare last-click vs. data-driven attribution
3. Use the path analysis report to see channel interactions
4. Set conversion values for revenue-based optimization

### Budget Tracking (Spreadsheet)
1. Create a master channel tracker with monthly columns
2. Track: budget, actual spend, leads, customers, CAC, ROAS
3. Add MoM trend formulas for each metric
4. Monthly review meeting using this report

### Testing New Channels
1. Set aside 10-15% of budget for channel experiments
2. Run each new channel for minimum 90 days
3. Track dedicated landing pages or UTMs for clean attribution
4. Compare CAC to proven channels after the test period

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Killed a channel that was assisting others | Single-touch attribution miss | Re-invest partial budget; analyze multi-touch attribution |
| New channel underperformed | Insufficient time or budget for the test | Extend test to 90 days; ensure enough budget for learning |
| Over-diversified | Too many channels, not enough budget per channel | Consolidate to top 4-5 channels with minimum viable budgets |
| Team can't execute on recommended mix | Skill gaps in new channels | Hire or outsource; don't shift budget to channels you can't staff |

## How to Get Your Data

- **Multi-channel**: Combine platform exports into one spreadsheet with consistent columns (channel, spend, conversions, revenue)
- **Google Analytics**: Acquisition → Traffic Acquisition for organic channel data
- **CRM**: Export lead source data with deal values
- **No data**: Describe your budget, channels, and stage — Claude recommends from benchmarks

## Example

**Input**: "Channel mix for B2B SaaS, $15K/month marketing budget. Current: Google Ads $6K (42 leads, $143 CAC), LinkedIn Ads $4K (18 leads, $222 CAC), Content/SEO $3K (30 leads, $100 CAC), Events $2K (8 leads, $250 CAC). LTV: $3,000. Goal: reduce blended CAC while increasing lead volume."

**Output**: Efficiency ranking: Content/SEO ($100) > Google Ads ($143) > LinkedIn ($222) > Events ($250). Content/SEO has best CAC and is not saturated — increase investment from $3K to $5K (+66%). Google Ads showing early saturation (CAC up 15% MoM) — maintain at $6K but shift $1K from broad to exact match. LinkedIn high CAC but drives enterprise leads (higher LTV) — reduce to $2.5K, focus on retargeting only. Events: highest CAC, lowest volume — pause and redirect $2K to content and a new channel test. New channel recommendation: test email nurture ($1.5K for 3 months, expected CAC $80-120 based on content lead nurturing). 90-day plan: Month 1 — shift budgets, launch email nurture; Month 2 — evaluate new allocation, double down on SEO content production; Month 3 — review results, consider adding webinar channel.

## Related Skills

- **[marketing-roi-calculator](../analytics/marketing-roi-calculator.md)** — Calculate channel ROI to inform optimization decisions.
- **[marketing-mix-modeler](../analytics/marketing-mix-modeler.md)** — Use MMM analysis to validate and refine channel allocation.
- **[growth-experiment-designer](./growth-experiment-designer.md)** — Design A/B tests to validate channel optimization recommendations.
- **[gtm-launch-planner](./gtm-launch-planner.md)** — Apply channel mix strategy for product and feature launches.
