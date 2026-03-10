---
name: marketing-mix-modeler
description: >
  Analyze marketing channel contributions and optimize budget allocation using marketing mix modeling principles.
  Use this skill when the user says "marketing mix modeling", "media mix analysis", "channel contribution
  analysis", "budget allocation optimization", "marketing spend efficiency", "incremental revenue by channel",
  "diminishing returns analysis", "channel saturation analysis", "marketing effectiveness measurement",
  "optimal budget split", or "how to allocate marketing budget". Also trigger for media planning optimization,
  channel ROI comparison, or cross-channel budget allocation.
---

# Marketing Mix Modeler

Analyzes marketing channel contributions to business outcomes and optimizes budget allocation across channels using marketing mix modeling principles and diminishing returns analysis.

## Granularity Check

> **Session time**: ~10 min data prep + ~15 min Claude session. For full econometric MMM, add 4-8 weeks with a data science team. Input is marketing spend and results data by channel over time. Output is Markdown channel analysis with contribution estimates, optimization recommendations, and budget allocation plan.

## User Intent Mapping

- "How should we allocate our marketing budget?" (allocation)
- "Which marketing channels are most effective?" (effectiveness)
- "Are we overspending on any channel?" (efficiency)
- "Marketing mix optimization" (optimization)
- "Diminishing returns on paid ads" (saturation)
- "Cross-channel budget allocation" (cross-channel)
- "Incremental revenue by channel" (incrementality)
- "Media planning for next quarter" (planning)
- "Channel ROI comparison" (ROI)
- "Marketing spend vs. revenue correlation" (correlation)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Channel Spend | CSV/Text | Monthly spend per marketing channel (6+ months) |
| Business Results | CSV/Text | Monthly revenue, leads, or conversions |
| Channel List | Text | All active marketing channels |

### If You Don't Have This Data

- **No historical data?** Claude creates a test-and-learn budget allocation plan based on industry benchmarks, and designs measurement to build your data foundation over 3-6 months.
- **Only a few months of data?** Claude works with as little as 3 months but flags lower confidence — 12+ months is ideal for reliable channel contribution estimates.
- **Can't isolate channel spend?** Claude helps you categorize spend into analyzable buckets and recommends tracking improvements for future analysis.
- **No revenue attribution?** Claude uses proxy metrics (leads, traffic, sign-ups) and explains the limitations of each approach.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Conversion Data | CSV | Leads, sign-ups, or conversions by channel |
| Seasonality Pattern | Text | Known seasonal trends in your business |
| External Factors | Text | Market events, competitor actions, pricing changes |
| Historical Budgets | CSV | Past budget allocations and results |
| Business Constraints | Text | Minimum spend requirements, channel commitments |

## Process

### Step 1: Channel Contribution Assessment

| Channel | Spend | Revenue Attributed | ROI | Contribution % | Confidence |
|---|---|---|---|---|---|
| Paid Search | $X | $Y | Y/X | % of total | High (last-click) |
| Paid Social | $X | $Y | Y/X | % of total | Medium (assisted) |
| SEO/Content | $X | $Y | Y/X | % of total | Medium (estimated) |
| Email | $X | $Y | Y/X | % of total | High (tracked) |
| Display/Programmatic | $X | $Y | Y/X | % of total | Low (awareness) |
| Events | $X | $Y | Y/X | % of total | Low (indirect) |

### Step 2: Diminishing Returns Analysis

| Channel | Current Spend | Marginal ROI | Saturation Level | Recommendation |
|---|---|---|---|---|
| Channel A | $50K/mo | 4.2x | 60% | Room to increase |
| Channel B | $80K/mo | 1.8x | 85% | Near saturation |
| Channel C | $30K/mo | 6.1x | 40% | Significant room to increase |
| Channel D | $40K/mo | 0.9x | 95% | Over-saturated, reduce spend |

Saturation indicators:
- **Below 50%**: High growth potential — increase spend aggressively
- **50-75%**: Moderate growth — increase spend incrementally
- **75-90%**: Diminishing returns — maintain or test reductions
- **Above 90%**: Saturated — reallocate to higher-potential channels

### Step 3: Budget Optimization Framework

| Scenario | Total Budget | Channel A | Channel B | Channel C | Projected Revenue |
|---|---|---|---|---|---|
| Current allocation | $200K | $50K (25%) | $80K (40%) | $70K (35%) | $800K |
| Optimized allocation | $200K | $70K (35%) | $60K (30%) | $70K (35%) | $920K (+15%) |
| Growth scenario (+20%) | $240K | $85K (35%) | $70K (29%) | $85K (35%) | $1.1M |
| Efficiency scenario (-10%) | $180K | $65K (36%) | $50K (28%) | $65K (36%) | $780K (-2.5%) |

### Step 4: Cross-Channel Interaction Effects

| Channel Pair | Interaction | Effect | Implication |
|---|---|---|---|
| Paid Search + SEO | Complementary | Combined lift 15-25% | Invest in both; don't cut SEO when scaling SEM |
| Display + Paid Search | Sequential | Display drives 10-20% of search volume | Cutting display may reduce search performance |
| Social + Email | Reinforcing | Social awareness lifts email open rates 5-10% | Align social and email messaging/timing |
| Content + Paid | Amplifying | Content improves ad quality scores and landing pages | Fund content even when optimizing for paid ROI |

### Step 5: Seasonal Budget Adjustments

| Season | Demand Level | Budget Strategy | Channel Focus |
|---|---|---|---|
| Peak season | High demand | Increase total spend 20-40% | Performance channels (search, email) |
| Shoulder season | Moderate demand | Maintain baseline | Balanced across channels |
| Low season | Low demand | Reduce performance, increase brand | Content, brand, community building |
| Launch periods | Variable | Front-load awareness, back-load conversion | Full funnel: awareness → retargeting → conversion |

### Step 6: Measurement & Iteration

| Method | What It Measures | When to Use | Accuracy |
|---|---|---|---|
| Last-click attribution | Direct response channel credit | Always (as baseline) | Low (biased toward bottom funnel) |
| Multi-touch attribution | Assisted conversions across channels | When you have multi-touch data | Medium |
| Incrementality testing | True causal impact of a channel | Quarterly for key channels | High (but resource-intensive) |
| Geo-lift testing | Channel impact by market | For expensive or hard-to-attribute channels | High |
| Time-series correlation | Spend-to-outcome relationship over time | With 12+ months of data | Medium |

### Confidence & Sample Size

> **Confidence Note**: True marketing mix modeling requires 2-3 years of weekly data and econometric expertise — the approach here is a practical framework that gives directionally useful insights with less data. Channel ROI comparisons are most reliable when comparing performance channels (search, email) and least reliable for awareness channels (display, brand). Budget optimization models assume past performance predicts future results — major market changes can invalidate projections. Always hold back 5-10% of budget for experimentation with new channels or tactics.

### ⚠️ Human Checkpoint
> Validate channel contribution estimates with channel managers — the data may not capture offline or relationship-driven conversions. Before making large budget shifts (>20%), run a 4-6 week test in one market or segment to verify the model's predictions hold.

> **Benchmark Context**: The average enterprise allocates marketing budget as: 25-35% paid media, 15-25% content/SEO, 10-15% events, 10-15% email/CRM, 5-10% social, 10-15% tools/technology. Companies that reallocate budget quarterly outperform those with annual fixed budgets by 15-20%. The typical marketing budget is 5-15% of revenue (B2B: 5-10%, B2C: 10-15%). Over-allocating to a single channel (>50% of budget) increases risk without proportional return.

## Output Contract

### Deliverable: Markdown Budget Allocation Plan

```markdown
# Marketing Mix Analysis: [Company]

## Channel Performance Summary
| Channel | Monthly Spend | Revenue | ROI | Saturation | Trend |
|---|---|---|---|---|---|

## Current vs. Optimized Allocation
| Channel | Current $ | Current % | Optimized $ | Optimized % | Change |
|---|---|---|---|---|---|

## Diminishing Returns Analysis
| Channel | Marginal ROI at Current Spend | Room to Scale | Recommendation |
|---|---|---|---|

## Cross-Channel Effects
| Interaction | Impact | Budget Implication |
|---|---|---|

## Recommended Budget (Next Quarter)
| Channel | Budget | % of Total | Key Metric | Target |
|---|---|---|---|---|

## Test Plan
| Test | Channel | Budget | Duration | Success Metric |
|---|---|---|---|---|

## Expected Impact
- Revenue change: [estimate]
- ROI improvement: [estimate]
- Risk factors: [key assumptions]
```

## Platform Implementation Steps

### Data Collection
1. Export monthly spend from each ad platform and marketing tool
2. Pull monthly revenue/conversion data from CRM or analytics
3. Align time periods and remove outlier months (launches, incidents)
4. Create unified spreadsheet: rows = months, columns = spend + results per channel
5. Add external variables: seasonality indicators, market events, pricing changes

### Analysis Setup
1. Calculate basic ROI per channel (revenue / spend)
2. Plot spend vs. revenue for each channel to visualize diminishing returns
3. Run correlation analysis between spend changes and revenue changes
4. Identify interaction effects (does increasing Channel A affect Channel B results?)
5. Build scenario models: current, optimized, growth, efficiency

### Ongoing Optimization
1. Review channel performance monthly against targets
2. Shift 5-10% of budget per quarter based on performance
3. Run incrementality tests on top 2-3 channels quarterly
4. Update models with new data every 6 months
5. Hold quarterly marketing mix review with leadership

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Model says cut a channel that's actually working | Attribution doesn't capture full impact (especially brand/awareness) | Run incrementality test before cutting; look for assisted conversions |
| Optimized allocation doesn't improve results | External factors changed (competition, market, product) | Re-calibrate model; account for market changes |
| Over-rotation to one channel | Model finds one channel "optimal" and over-invests | Cap any single channel at 40% of budget; diversify for resilience |
| Stakeholder disagreement | Different teams advocate for their channels | Use objective criteria and test-based evidence; not opinion |

## How to Get Your Data

- **Ad platforms**: Google Ads, Meta Ads, LinkedIn Ads → campaign reports → monthly spend and conversions
- **Revenue data**: CRM → closed revenue by month, attributed to marketing source
- **Email**: Email platform → campaign revenue attribution by month
- **SEO**: GA4 → organic traffic and conversions by month
- **No attribution**: Monthly total spend + monthly total revenue — Claude identifies correlations and recommends tracking improvements

## Example

**Input**: "Marketing mix analysis. Monthly budget: $150K. Channels: Google Ads ($55K, 3.2x ROI), LinkedIn Ads ($35K, 2.1x ROI), Content/SEO ($25K, 4.5x ROI), Email ($15K, 8.2x ROI), Events ($20K, 1.5x ROI). Total monthly revenue: $650K. Want to optimize for revenue growth without increasing total budget."

**Output**: Current analysis: email has highest ROI (8.2x) but lowest spend ($15K — only 10% of budget). Content/SEO has strong ROI (4.5x) at only 17% of budget. Google Ads is solid (3.2x) but consumes 37% of budget. Events have lowest ROI (1.5x) at 13% of budget. Optimization: (1) Increase email from $15K to $25K (+67%). At 8.2x ROI, additional $10K should generate ~$82K revenue. Email is likely under-saturated — invest in list growth, segmentation, and automation. (2) Increase Content/SEO from $25K to $35K (+40%). At 4.5x ROI, additional $10K should generate ~$45K. Focus on high-converting content topics. (3) Reduce Events from $20K to $10K (-50%). Events ROI of 1.5x is well below other channels. Shift to virtual events or co-sponsored events to maintain presence at lower cost. (4) Reduce Google Ads from $55K to $50K (-9%). Test small reduction — if ROI holds or improves, the channel may be approaching saturation at $55K. (5) Maintain LinkedIn at $35K — 2.1x ROI is acceptable for B2B awareness and pipeline. Projected impact: revenue from $650K to $720-$750K (+11-15%) at same $150K budget. Run the shift over 2 months, measuring weekly. If email or content don't scale as expected, reallocate back to Google Ads.
