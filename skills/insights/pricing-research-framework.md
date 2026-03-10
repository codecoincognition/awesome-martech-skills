---
name: pricing-research-framework
description: >
  Conduct pricing research to determine optimal price points, willingness-to-pay, and pricing strategy.
  Use this skill when the user says "pricing research", "willingness to pay analysis", "price sensitivity
  testing", "Van Westendorp analysis", "Gabor-Granger pricing", "conjoint analysis for pricing",
  "optimal price point", "pricing strategy research", "how to price our product", "price elasticity
  analysis", or "competitive pricing analysis". Also trigger for value-based pricing research,
  price testing methodology, or pricing tier optimization.
---

# Pricing Research Framework

Conducts pricing research using proven methodologies to determine optimal price points, willingness-to-pay ranges, and data-driven pricing strategies.

## Granularity Check

> **Time**: ~10 min data prep → ~15 min Claude session → ~30-60 min synthesizing into your strategy deck. If implementing research, add 2-4 weeks for survey design, data collection, and analysis. Input is product context, current pricing, and competitive data. Output is Markdown pricing research plan with methodology and analysis framework.

## User Intent Mapping

- "How should we price our product?" (strategy)
- "What are customers willing to pay?" (WTP)
- "Van Westendorp pricing analysis" (methodology)
- "Price sensitivity testing" (sensitivity)
- "Are we priced too high or too low?" (evaluation)
- "Pricing research methodology" (methodology)
- "Competitive pricing analysis" (competitive)
- "Pricing tier structure" (tiers)
- "How to test a price increase" (testing)
- "Value-based pricing research" (value)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Product/Service | Text | What you're pricing |
| Current Price | Text | Current pricing (or "not yet priced") |
| Target Market | Text | Who the buyer is |

### If You Don't Have This Data

- **No pricing data?** Claude designs a Van Westendorp or Gabor-Granger survey you can run in 1-2 weeks to get willingness-to-pay data.
- **No competitive prices?** Claude recommends research methods and provides a framework for competitive price mapping.
- **First time pricing?** Claude walks through value-based pricing methodology from scratch, including customer value quantification.
- **Small sample size?** Claude adapts research methodology for smaller audiences (50-100 responses) with appropriate confidence caveats.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Competitor Pricing | Text | Known competitor prices |
| Customer Segments | Text | Different buyer types with different WTP |
| Cost Structure | Text | Your costs (for margin analysis) |
| Survey Data | CSV | Existing pricing survey results |
| Usage Data | Text | How customers use your product (for usage-based pricing) |

## Process

### Step 1: Pricing Methodology Selection
| Method | Best For | Sample Needed | Complexity |
|---|---|---|---|
| Van Westendorp | Finding acceptable price range | 200+ responses | Low |
| Gabor-Granger | Testing specific price points | 300+ responses | Low-Medium |
| Conjoint Analysis | Multi-feature pricing decisions | 300+ responses | High |
| A/B Price Testing | Validating specific price changes | 1,000+ transactions | Medium |
| Competitive Benchmarking | Understanding market positioning | N/A (desk research) | Low |

### Step 2: Van Westendorp Price Sensitivity
Four questions:
1. "At what price would you consider this product too expensive?" (too expensive)
2. "At what price would you consider this product expensive but still worth considering?" (expensive)
3. "At what price would you consider this product a bargain?" (cheap)
4. "At what price would you consider this product too cheap, making you question its quality?" (too cheap)

Analysis outputs:
- **Point of marginal cheapness**: Where "too cheap" and "expensive" intersect
- **Point of marginal expensiveness**: Where "too expensive" and "cheap" intersect
- **Optimal price point**: Where "too cheap" and "too expensive" intersect
- **Acceptable price range**: Between marginal cheapness and marginal expensiveness

### Step 3: Value-Based Pricing Framework
1. **Identify value drivers**: What outcomes does your product deliver?
2. **Quantify value**: How much is each outcome worth in dollars?
3. **Calculate total value**: Sum of all quantified value drivers
4. **Set price as % of value**: Typically 10-30% of total value delivered
5. **Validate with WTP research**: Does market data support this price?

### Step 4: Competitive Price Mapping
| Competitor | Price | Features Included | Value Ratio | Positioning |
|---|---|---|---|---|
| Competitor A | $X | [features] | High/Med/Low | Premium/Value |

Map competitors on a price-value matrix:
- Premium (high price, high value): worth paying more
- Value (low price, high value): best deal
- Overpriced (high price, low value): vulnerable
- Economy (low price, low value): stripped-down option

### Step 5: Pricing Tier Design
| Tier | Target Segment | Features | Price Anchor |
|---|---|---|---|
| Free/Starter | Try before buy | Core features only | $0 (lead gen) |
| Growth/Pro | Core market | Key features + support | Primary revenue driver |
| Enterprise | High-value segment | Full platform + custom | Premium margin |

Tier design rules:
- 3 tiers is optimal (paradox of choice at 4+)
- Middle tier should be your target (anchored by high tier)
- Feature differences should be obvious and meaningful
- Clear upgrade path from each tier to the next

### Step 6: Price Testing Strategy
| Method | When to Use | Risk |
|---|---|---|
| Geographic testing | Different prices in different regions | Customer discovery risk |
| Cohort testing | New vs. existing customers see different prices | Fairness perception |
| Time-based testing | Different prices in different periods | Seasonality confounds |
| Feature bundling | Different packages at different prices | Not testing price directly |
| Anchor testing | Change price presentation (annual vs. monthly) | Low risk |

### Confidence & Sample Size

> **Confidence Note**: Van Westendorp requires 200+ responses for reliable results. Gabor-Granger needs 300+ (100+ per price point tested). Conjoint analysis requires 300+ with careful experimental design. Small samples (under 100) can indicate direction but shouldn't be used for final pricing decisions. Always segment by buyer type — aggregate WTP data can be misleading if you have distinct segments. Price elasticity is nonlinear — small price changes can have disproportionate effects near psychological thresholds ($9.99 vs. $10, $99 vs. $100).

### ⚠️ Human Checkpoint
> Pricing decisions affect revenue directly — validate research findings with actual market tests before full rollout. Survey-stated WTP is typically 15-20% higher than actual purchase behavior — adjust accordingly. Get finance team input on margin implications.

> **Benchmark Context**: Companies using data-driven pricing earn 2-7% more revenue than those using cost-plus or competitive pricing alone. 85% of pricing decisions are based on cost-plus despite research showing value-based pricing generates 20-30% more revenue. SaaS companies that optimize pricing annually grow 2x faster than those that set-and-forget. Annual billing with a discount (typically 15-20%) increases LTV by 30-40% vs. monthly-only.

## Output Contract

### Deliverable: Markdown Pricing Research Plan

```markdown
# Pricing Research: [Product/Service]

## Research Methodology
- Method: [Van Westendorp/Gabor-Granger/Conjoint]
- Sample size needed: [number]
- Target segments: [who to survey]
- Timeline: [data collection + analysis]

## Survey Design
[Complete survey questions with instructions]

## Competitive Price Map
| Competitor | Price | Key Features | Value Position |
|---|---|---|---|

## Analysis Framework
- Optimal price range: [low - high]
- Recommended price point: [price]
- Revenue sensitivity: [±% price = ±% revenue]

## Pricing Structure Recommendation
| Tier | Target | Price | Features | Revenue Share |
|---|---|---|---|---|

## Testing Plan
| Test | Method | Duration | Success Metric |
|---|---|---|---|

## Risk Assessment
| Risk | Mitigation |
|---|---|
```

## Platform Implementation Steps

### Survey Platforms
1. Build pricing survey in Typeform, SurveyMonkey, or Qualtrics
2. Include screener questions to qualify respondents
3. Randomize price point order to reduce bias
4. Add conjoint tasks if testing feature-price combinations
5. Include demographic questions for segmented analysis

### Data Analysis
1. Export survey responses to spreadsheet
2. For Van Westendorp: plot cumulative distribution curves for all four price questions
3. Find intersection points for optimal price range
4. Segment analysis by buyer type, company size, or use case
5. Create price sensitivity chart for stakeholder presentation

### Implementation
1. Start with small cohort test (10-20% of new customers)
2. Monitor conversion rate, average deal size, and churn closely
3. Run test for minimum 30 days (full billing cycle)
4. Compare test vs. control for revenue per visitor, not just conversion
5. Roll out gradually with monitoring at each stage

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Survey says high WTP but sales don't convert | Stated vs. revealed preference gap | Adjust down 15-20%; validate with real price test |
| Research delays pricing decision | Analysis paralysis | Set deadline; use directional data for initial price, iterate |
| Segment data conflicts | Different segments have very different WTP | Design tiered pricing to capture each segment |
| Price change causes churn | Existing customers perceive unfairness | Grandfather existing customers; increase price for new only |

## How to Get Your Data

- **Competitive pricing**: Visit competitor websites; check G2/Capterra for listed pricing
- **Customer WTP**: Run Van Westendorp survey (4 questions, 200+ respondents)
- **Transaction data**: Billing system → export average deal sizes, win/loss by price point
- **No data yet**: Describe your product and market — Claude designs the full pricing research plan

## Example

**Input**: "Pricing research for our project management SaaS. Currently priced at $15/user/month. Competitors range $10-30/user/month. We think we might be underpriced but nervous about losing customers. 800 paying customers, 5,000 free users. No pricing research done before."

**Output**: Recommended approach: Van Westendorp survey + cohort price test. Phase 1 (2 weeks): Run Van Westendorp survey targeting 3 segments — (1) current paying customers (200 respondents), (2) free users (200 respondents), (3) prospects from website (200 respondents). Survey questions: standard 4 Van Westendorp questions + "Which competitor do you also consider?" + "Company size" + "Primary use case." Phase 2 (2 weeks): Analyze by segment. Expected findings based on market: if competitors range $10-30 and you're at $15, your acceptable range is likely $12-25 with optimal point around $18-22. Phase 3 (4 weeks): Cohort price test — new signups randomly assigned to $15 (control), $19, or $22. Measure: conversion rate, 30-day retention, NPS. Expected outcome: 10-20% price increase with <5% conversion decrease = net revenue positive. Risk mitigation: grandfather all 800 existing customers at $15 for 12 months. Announce to existing customers as "legacy pricing" — they keep the best deal.

## Related Skills

- **[Pricing Page Optimizer](../cro/pricing-page-optimizer.md)** — Implement pricing research findings through A/B tested page optimization.
- **[Voice of Customer Miner](./voice-of-customer-miner.md)** — Complement quantitative pricing research with qualitative customer sentiment on pricing from Reddit.
- **[Product Launch Planner](../growth/gtm-launch-planner.md)** — Incorporate pricing research into go-to-market launch strategy.
- **[Survey Design Analyzer](./survey-design-analyzer.md)** — Design pricing surveys using best practices to gather reliable willingness-to-pay data.
