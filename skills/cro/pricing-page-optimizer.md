---
name: pricing-page-optimizer
description: >
  Optimize pricing page design, layout, and psychology for higher conversion and plan selection.
  Use this skill when the user says "pricing page optimization", "pricing page design",
  "pricing page conversion", "pricing tier optimization", "pricing page A/B test", "pricing
  page best practices", "plan comparison page", "pricing page layout", "pricing psychology",
  "how to design a pricing page", or "pricing page isn't converting". Also trigger for
  free trial vs. freemium page design, enterprise pricing page, or pricing page UX.
---

# Pricing Page Optimizer

Optimizes pricing page design, layout, psychological triggers, and plan presentation for higher conversion rates, optimal plan selection, and reduced decision friction.

## Granularity Check

> **Session time**: ~5 min context gathering + ~10 min Claude session. If implementing, add 2-5 days for design and development. Input is current pricing page and conversion data. Output is Markdown optimization plan with specific design recommendations.

## User Intent Mapping

- "Our pricing page isn't converting" (optimization)
- "Pricing page design best practices" (design)
- "How to present 3 pricing tiers" (tier design)
- "Pricing page A/B test ideas" (testing)
- "Should we show pricing or hide it?" (strategy)
- "Pricing page for enterprise" (enterprise)
- "Free trial vs. freemium decision" (model)
- "Pricing psychology techniques" (psychology)
- "Pricing page layout" (layout)
- "Plan comparison table design" (comparison)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Pricing Plans | Text | Plan names, features, and prices |
| Target Customer | Text | Who your pricing page serves |
| Current Conversion | Text | Pricing page visitor-to-signup rate |

### If You Don't Have This Data

- **No conversion data?** Claude uses industry benchmarks and designs tracking recommendations from day one.
- **Haven't finalized pricing?** Claude focuses on page layout and psychology principles that work regardless of specific prices.
- **No A/B testing capability?** Claude prioritizes the single highest-impact change to implement first.
- **Competitor confusion?** Claude analyzes competitor pricing pages and recommends differentiation strategies.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Current Page | URL/Screenshot | Existing pricing page for review |
| Plan Distribution | Text | % of signups per plan |
| Competitor Pricing | Text | How competitors price and present |
| Objections | Text | Common sales objections about pricing |
| Trial Data | Text | Trial-to-paid conversion rates |

## Process

### Step 1: Pricing Page Audit
- Clear plan differentiation (can users quickly identify the right plan?)
- Visual hierarchy (is the recommended plan highlighted?)
- Feature comparison (easy to scan, not overwhelming?)
- CTA clarity (clear action for each plan)
- Social proof (customer logos, testimonials, user counts)
- FAQ section (addressing common objections)
- Mobile responsiveness (pricing tables are notoriously bad on mobile)

### Step 2: Layout Psychology
- **Anchoring**: show highest-priced plan first (left-to-right) or use it as anchor
- **Decoy effect**: middle tier should be obviously best value
- **Default selection**: pre-select recommended plan
- **Annual discount**: show monthly price with annual savings highlighted
- **Price framing**: per-user per-month, total cost, or "less than a coffee per day"
- **Loss aversion**: emphasize what lower plans don't include

### Step 3: Plan Presentation
| Element | Best Practice |
|---|---|
| Plan count | 3-4 plans (3 ideal — too many causes decision paralysis) |
| Recommended plan | Visually highlighted ("Most Popular" or "Best Value" badge) |
| Feature comparison | Show 5-7 key differentiating features, not exhaustive list |
| CTA buttons | Different emphasis for recommended plan (filled vs. outlined) |
| Annual toggle | Default to annual; show savings amount or percentage |
| Enterprise | "Contact Sales" with brief qualifying info |

### Step 4: Trust & Conversion Elements
- Customer logos (especially recognizable brands)
- Testimonials specific to value/ROI (not generic praise)
- Money-back guarantee or free trial details
- Security badges (SOC 2, GDPR, payment security)
- "No credit card required" (if applicable)
- FAQ addressing top objections (contract length, cancellation, support)

### Step 5: Mobile Optimization
- Stackable plan cards (vertical scroll, not horizontal)
- Collapsible feature comparison (accordion style)
- Sticky CTA button at bottom of screen
- Simplified plan names and feature highlights
- Toggle between plans (tab interface)

### Step 6: A/B Test Priorities
| Test | Expected Impact | Effort |
|---|---|---|
| Annual vs. monthly default toggle | 10-20% revenue lift | Low |
| Recommended plan highlight | 5-15% conversion lift | Low |
| Feature list reduction (15 → 7) | 5-10% conversion lift | Low |
| Add social proof near CTA | 5-15% conversion lift | Low |
| Price anchoring (reorder plans) | 5-10% plan mix shift | Low |
| Full page redesign | 20-40% conversion lift | High |

### Confidence & Sample Size

> **Confidence Note**: Pricing page changes need 200+ conversions per variant for A/B testing. Small copy changes on pricing pages often have outsized impact (changing "Buy" to "Start Free Trial" can lift 30%+). Annual billing default significantly impacts revenue per user. Pricing page performance is highly sensitive to traffic source — segment by channel when analyzing. Don't over-optimize for signup rate at the expense of qualified signups.

### ⚠️ Human Checkpoint
> Verify pricing accuracy before publishing any changes. Review with sales team for enterprise pricing messaging. Test all CTAs lead to correct signup flows. Ensure mobile experience is fully tested.

> **Benchmark Context**: Best-in-class SaaS pricing pages convert at 3-5% of visitors. 80% of SaaS companies use 3 pricing tiers. Showing annual pricing default increases ARPU by 15-25%. "Most Popular" badges increase selection of that plan by 20-30%. Adding a money-back guarantee increases conversion by 15-20%. Pricing pages with customer testimonials convert 34% higher.

## Output Contract

### Deliverable: Markdown Pricing Page Optimization

```markdown
# Pricing Page Optimization: [Brand]

## Current State
- Plans: [number and names]
- Page conversion: [%]
- Plan distribution: [%]

## Page Audit
| Element | Current | Issue | Recommendation |
|---|---|---|---|

## Recommended Layout
- [Plan structure and visual hierarchy]

## Plan Presentation
| Plan | Price | Highlight | CTA | Target Audience |
|---|---|---|---|---|

## Psychology Tactics
| Tactic | Implementation | Expected Impact |
|---|---|---|

## Trust Elements
- [Specific recommendations]

## A/B Test Roadmap
| Test | Hypothesis | Metric | Priority |
|---|---|---|---|

## Expected Results
- Conversion: [current] → [target]
- Plan mix: [current] → [target]
- Revenue impact: [estimate]
```

## Platform Implementation Steps

### Design
1. Create wireframe with recommended layout and hierarchy
2. Design plan cards with clear visual differentiation
3. Build feature comparison table (responsive for mobile)
4. Add toggle for annual/monthly with savings callout
5. Include social proof section near CTAs

### Development
1. Build responsive pricing table (CSS Grid or Flexbox)
2. Implement billing toggle (annual/monthly) with price animation
3. Add plan recommendation badge and visual emphasis
4. Create FAQ accordion section
5. Set up analytics tracking (plan views, CTA clicks, toggles)

### Analytics
1. Track pricing page visits, time on page, scroll depth
2. Track CTA clicks per plan
3. Track annual vs. monthly toggle usage
4. Set up funnel from pricing page to signup completion
5. Segment conversion by traffic source

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Conversion drops after redesign | Removed trust elements or changed too many things | A/B test incremental changes; keep key trust signals |
| Wrong plan selection bias | Highlight or anchoring pushing users to wrong plan | Verify recommended plan is actually best for majority; adjust highlight |
| Enterprise leads decrease | CTA or messaging not compelling for enterprise | Add specific enterprise value props; simplify "Contact Sales" path |
| Mobile conversion still low | Pricing table doesn't work on small screens | Redesign for mobile-first; use card stack instead of side-by-side |

## How to Get Your Data

- **Conversion**: GA4 → pricing page → track CTA clicks as events → measure signups
- **Plan distribution**: Billing system → signups by plan per month
- **Page behavior**: Hotjar → heatmap and scroll map on pricing page
- **No data**: Share your current pricing structure — Claude designs an optimized page based on best practices

## Example

**Input**: "Pricing page optimization. B2B SaaS, 3 plans: Starter ($29/mo), Pro ($79/mo), Enterprise (custom). Pro is our ideal plan but 60% choose Starter. Pricing page gets 2,000 monthly visitors, 2.8% conversion. No annual option. Feature comparison shows 20 features."

**Output**: Issues: (1) No annual billing — missing 15-25% ARPU lift. (2) Pro not visually distinguished — users default to cheapest. (3) 20 features causes decision paralysis. (4) No social proof on pricing page. Fixes: (1) Add annual billing toggle (20% discount, default to annual). (2) Highlight Pro with "Most Popular" badge, larger card, filled CTA button (vs. outlined for Starter). (3) Reduce to 7 differentiating features + "See all features" expandable link. (4) Add 3 customer testimonials mentioning ROI + 6 customer logos. (5) Reframe Starter as limited ("For individuals getting started") and Pro as standard ("For growing teams — everything you need"). (6) Add FAQ: "Can I switch plans?", "Is there a free trial?", "What happens when I hit limits?" Expected results: Pro selection 60% Starter → 50% Pro (plan mix shift). Conversion 2.8% → 3.5-4.2%. Annual billing adoption: 40-50% of new signups. Revenue impact: +$24K ARR from plan mix shift + $18K from annual billing = $42K additional ARR.
