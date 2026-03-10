---
name: pricing-page-optimizer
description: >
  Optimize pricing page design, plan structure, and conversion elements.
  Use this skill when the user says "pricing page optimization", "pricing page review", "pricing
  page design", "pricing tier strategy", "optimize our pricing page", "pricing page conversion",
  "pricing page best practices", "feature comparison table", "pricing page A/B test", "plan
  naming strategy", or "freemium vs paid strategy". Also trigger for pricing page copy review,
  FAQ optimization, or pricing psychology application.
---

# Pricing Page Optimizer

Audits and optimizes pricing page design with plan structure, feature presentation, conversion elements, psychological pricing tactics, and A/B testing recommendations.

## Granularity Check

> **Time**: ~5 min data prep → ~10 min Claude session → ~60-120 min implementing in your product / tools. If implementing output, add 2-4 hours for page redesign. Input is current pricing page or plan details. Output is Markdown audit with redesigned pricing page recommendations.

## User Intent Mapping

- "Review our pricing page for conversions" (audit)
- "How should we structure our pricing tiers?" (structure)
- "Our pricing page has low conversion" (optimization)
- "Pricing page best practices" (best practices)
- "Which plan should we highlight?" (anchoring)
- "Feature comparison table design" (table design)
- "Should we show prices or use 'Contact Sales'?" (display strategy)
- "Pricing page FAQ — what questions to answer" (FAQ)
- "Freemium vs. free trial vs. paid only" (model)
- "Pricing psychology tips" (psychology)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Pricing Plans | Text | Plan names, prices, and included features |
| Product Type | Text | SaaS, e-commerce, service, marketplace |
| Target Buyers | Text | Who's buying and their decision-making process |

### If You Don't Have This Data

- **No pricing page yet?** Describe your plans and features. Claude designs the page structure and copy.
- **No conversion data?** Claude audits against best practices. Set up pricing page analytics (clicks per plan, signup starts per plan) as a priority.
- **No competitor pricing?** Search competitor pricing pages and note their plan names, prices, and featured plans. Claude uses this for positioning.
- **No A/B testing tool?** Make changes sequentially and compare 2-week performance periods in analytics.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Current Conversion Rate | Number | Pricing page to signup/purchase rate |
| Plan Distribution | Text | % of customers on each plan |
| Competitor Pricing | Text | Competitor plans and pricing |
| Common Objections | Text | What prospects ask before buying |
| Annual vs. Monthly | Text | Current billing split |

## Process

### Step 1: Plan Structure Audit
Evaluate:
- Number of plans (3-4 is optimal; 5+ causes decision paralysis)
- Plan naming (avoid generic: Basic/Pro/Enterprise → use value-based names)
- Price anchoring (most expensive plan should make middle plan look reasonable)
- Feature differentiation (clear value steps between plans)
- Free tier/trial strategy (freemium vs. free trial vs. demo)

### Step 2: Pricing Psychology
Apply proven tactics:
- **Anchoring**: Show highest plan first (or highlight middle plan)
- **Charm pricing**: $29 vs. $30 (9-ending prices increase conversions 8-12%)
- **Annual discount**: Show monthly price with annual savings
- **Decoy effect**: Add a plan that makes the target plan look like the best value
- **Loss aversion**: "Save $X/year" vs. "Pay $X/month"
- **Social proof**: "Most popular" badge, customer count per plan

### Step 3: Feature Table Optimization
- Lead with benefits, not feature names
- Group features by category
- Use checkmarks for included, dashes for excluded (never X marks — too negative)
- Highlight differentiating features between plans
- Limit to 10-15 features visible (expandable for full list)

### Step 4: Conversion Elements
Must-have elements:
- Clear CTA buttons (contrasting color, action-oriented text)
- Trust signals (security badges, money-back guarantee, customer logos)
- Social proof (customer count, testimonials, case studies)
- FAQ section (addressing top 5-7 objections)
- Annual/monthly toggle with savings highlighted
- Risk reducers (free trial, no credit card required, cancel anytime)

### Step 5: Pricing Page Copy
- Headline: Value proposition, not just "Pricing"
- Subheadline: Who it's for and key benefit
- Plan descriptions: 1-2 sentence positioning for each plan
- CTA text: Specific ("Start Free Trial") not generic ("Sign Up")
- FAQ answers: Concise, objection-handling

### Confidence & Sample Size
> **Confidence Note**: Pricing page optimization requires minimum 1,000 visitors and 50+ conversions to measure changes reliably. Pricing changes affect conversion AND revenue simultaneously — track both. Annual plan promotion may increase conversion rate but reduce immediate revenue (payback analysis needed). Seasonal effects and traffic source shifts can confound results.

### ⚠️ Human Checkpoint
> Verify pricing accuracy with finance team before publishing. Review feature comparisons with product team for accuracy. Ensure compliance with any contractual pricing agreements. Test the complete purchase flow after changes.

> **Benchmark Context**: Average SaaS pricing page conversion rate is 2-5% (ProfitWell 2024 SaaS Benchmarks). Highlighting a "recommended" plan increases its selection by 20-30%. Showing annual savings increases annual plan adoption by 15-25%. FAQ sections reduce support inquiries by 20-30%. Mobile pricing page conversion is typically 30-50% lower than desktop — optimize for mobile. 3 plans convert better than 2 or 4+ plans. (ProfitWell 2024 SaaS Benchmarks).
## Output Contract

### Deliverable: Markdown Pricing Page Audit

```markdown
# Pricing Page Optimization: [Product]

## Current Assessment
| Element | Score (1-10) | Issue | Fix |
|---|---|---|---|

## Plan Structure Recommendations
| Plan | Name | Price | Positioning | Target Buyer |
|---|---|---|---|---|

## Feature Table
| Feature | [Plan 1] | [Plan 2] | [Plan 3] |
|---|---|---|---|

## Copy Recommendations
- Headline: [text]
- Subheadline: [text]
- Plan 1 description: [text]
- CTA text: [per plan]

## Pricing Psychology Applied
1. [Tactic]: [implementation]

## FAQ Section
1. Q: [question]
   A: [answer]

## A/B Test Recommendations
| Test | Hypothesis | Primary Metric |
|---|---|---|

## Quick Wins
1. [Change] — Expected impact: [metric]
```

## Platform Implementation Steps

### Website/CMS
1. Create or update pricing page with recommended structure
2. Add plan highlighting (CSS border/badge for recommended plan)
3. Build annual/monthly toggle with JavaScript
4. Add FAQ accordion section
5. Implement conversion tracking on CTA clicks and plan selections

### A/B Testing (VWO/Optimizely/Google Optimize)
1. Create pricing page variant with recommended changes
2. Set conversion goal: pricing page → signup/purchase
3. Traffic split: 50/50
4. Run for minimum 2 weeks or until 95% significance

### Analytics
1. Track events: plan_selected, annual_toggled, faq_expanded, cta_clicked
2. Create funnel: pricing_page_view → plan_click → signup_start → signup_complete
3. Segment by traffic source (paid vs. organic visitors convert differently on pricing pages)

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Conversion dropped after changes | Changed too many things at once | Revert and test one change at a time |
| Everyone picks cheapest plan | Insufficient value differentiation in higher plans | Add exclusive features to higher plans; adjust anchoring |
| High bounce rate | Prices too high for traffic source or audience mismatch | Segment analysis by source; test price anchoring |
| FAQ doesn't reduce support | Wrong questions addressed | Analyze actual support tickets to identify top objections |

## How to Get Your Data

- **Current pricing page**: Share the URL or screenshot for Claude to audit
- **Analytics**: Google Analytics → behavior flow for pricing page → track CTA clicks
- **No data**: Describe your plans and prices — Claude designs from best practices

## Example

**Input**: "Audit our pricing page: 3 plans — Starter ($19/mo), Professional ($49/mo), Business ($99/mo). Starter gets 50% of signups, Professional 35%, Business 15%. We want more Professional plan signups. Current page has no highlighted plan, generic CTAs ('Get Started'), and a 25-feature comparison table."

**Output**: Issues: (1) No visual anchoring — add "Most Popular" badge to Professional; (2) Generic CTAs — change to "Start Free Trial" (Starter), "Start Free Trial — Most Popular" (Professional), "Contact Sales" (Business); (3) 25-feature table causes analysis paralysis — reduce to top 10 differentiating features, add "See all features" expandable; (4) No annual pricing shown — add toggle with "Save 20%" badge; (5) No social proof — add customer count and 2 testimonials. Pricing psychology: add annual pricing ($15/$39/$79 annually) to make monthly feel expensive by comparison. Reposition plans: Starter → "For individuals", Professional → "For growing teams" (most value), Business → "For organizations." Quick wins: highlight Professional plan (CSS change, 30 min), add annual toggle (2-hour dev), shorten feature table (1 hour). A/B test: current page vs. highlighted Professional plan — expected shift: Professional from 35% to 45-50% of signups.

## Related Skills

- **[customer-persona-builder](./customer-persona-builder.md)** — Tailor pricing messaging to different buyer personas.
- **[ab-test-designer](../cro/ab-test-designer.md)** — A/B test pricing page elements for conversion optimization.
- **[gtm-launch-planner](./gtm-launch-planner.md)** — Align pricing page with product launch strategy.
- **[marketing-roi-calculator](../analytics/marketing-roi-calculator.md)** — Analyze ROI impact of pricing changes.
