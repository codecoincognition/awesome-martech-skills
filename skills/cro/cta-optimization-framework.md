---
name: cta-optimization-framework
description: >
  Optimize calls-to-action across web, email, and ads for higher click-through and conversion rates.
  Use this skill when the user says "CTA optimization", "call to action best practices",
  "CTA button optimization", "improve CTA click rate", "CTA copy testing", "CTA placement
  strategy", "button design optimization", "CTA A/B testing", "CTA conversion improvement",
  "what makes a good CTA", or "CTA design best practices". Also trigger for CTA heat map
  analysis, micro-conversion optimization, or CTA personalization.
---

# CTA Optimization Framework

Optimizes calls-to-action across web, email, and ads through copy testing, design improvements, placement strategy, and personalization for higher click-through and conversion rates.

## Granularity Check

> **Session time**: ~5 min context gathering + ~10 min Claude session. If implementing, add 1-3 days for design and testing. Input is current CTAs and performance data. Output is Markdown optimization plan with CTA variants and testing strategy.

## User Intent Mapping

- "Our CTAs aren't getting clicks" (optimization)
- "CTA best practices for our website" (best practices)
- "What should our CTA button say?" (copy)
- "CTA A/B test ideas" (testing)
- "CTA placement — where should we put it?" (placement)
- "CTA design — button vs. text link" (design)
- "Personalized CTAs" (personalization)
- "CTA for different funnel stages" (funnel)
- "Email CTA optimization" (email)
- "Too many CTAs on our page" (simplification)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Current CTAs | Text | Button text, placement, and destination |
| Page/Channel | Text | Where the CTA appears |
| Conversion Goal | Text | What you want users to do |

### If You Don't Have This Data

- **No CTA performance data?** Claude recommends tracking setup and provides optimization based on CTA review.
- **No A/B testing tool?** Claude prioritizes single high-impact CTA changes and recommends free tools (Google Optimize successor, native platform testing).
- **Not sure what CTA to use?** Claude generates 5-10 CTA variants per placement with rationale.
- **Multiple CTAs competing?** Claude designs a CTA hierarchy with primary and secondary actions.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Click Data | CSV | CTR per CTA across pages |
| Heatmap Data | Screenshots | Where users click on pages |
| A/B Test History | Text | Past CTA tests and results |
| Audience Segments | Text | Different audiences seeing CTAs |
| Competitor CTAs | Text | What competitors use |

## Process

### Step 1: CTA Copy Formulas
| Formula | Example | Best For |
|---|---|---|
| Action + benefit | "Start Saving Time Today" | Clear value propositions |
| Action + specificity | "Download the 2025 Report" | Content offers |
| Action + urgency | "Claim Your Spot — 12 Left" | Limited availability |
| First-person | "Start My Free Trial" | Personal commitment |
| Question-based | "Ready to Grow?" | Engagement |
| Risk-reducer | "Try Free for 14 Days" | Risk-averse audiences |

### Step 2: CTA Design Rules
- **Size**: Large enough to be obvious, not so large it looks desperate (44px min height for mobile)
- **Color**: High contrast with background; doesn't need to be red/green — contrast matters most
- **Shape**: Rounded corners (3-5px radius) perform 5-10% better than sharp corners
- **White space**: Generous padding around CTA (1.5-2x button height as margin)
- **Hover state**: Visual feedback on hover (color shift, subtle animation)
- **Mobile**: Full-width buttons on mobile; 48px minimum tap target

### Step 3: Placement Strategy
| Page Type | Primary CTA Placement | Secondary CTA |
|---|---|---|
| Homepage | Above fold + after value proposition | Sticky header/footer |
| Blog post | After intro paragraph + end of post | Inline within content |
| Landing page | Above fold + after each benefit section | Exit intent popup |
| Email | Above fold + end of email | P.S. line |
| Product page | Near price/above fold | Sticky add-to-cart |

### Step 4: CTA Hierarchy
- **Primary CTA**: One per page — the main action you want (filled button, high contrast)
- **Secondary CTA**: Supporting action (outlined button, lower visual weight)
- **Tertiary CTA**: Soft action (text link)
- Rule: every page has one clear primary action; competing CTAs reduce all conversion

### Step 5: CTA Personalization
| Visitor Type | CTA | Rationale |
|---|---|---|
| First-time visitor | "Learn More" / "See How It Works" | Low commitment |
| Returning visitor | "Start Free Trial" / "Book a Demo" | Higher intent |
| Known lead | "Schedule Your Demo" / "Talk to Sales" | Ready to buy |
| Existing customer | "Upgrade" / "Explore Premium" | Expansion |

### Step 6: Testing Framework
- Test one element at a time (copy OR design OR placement, not all three)
- Run tests for full business cycles (minimum 2 weeks)
- Need 200+ clicks per variant for statistical significance
- Test copy first (highest impact, lowest effort)
- Then test placement, then design elements

### Confidence & Sample Size

> **Confidence Note**: CTA copy changes can lift conversion 10-40% — this is one of the highest-ROI optimizations available. First-person CTAs ("Start My Trial") outperform third-person ("Start Your Trial") by 25-30%. Personalized CTAs convert 202% better than default. But don't over-optimize CTAs in isolation — the value proposition above the CTA matters more than the button itself. A perfect CTA on a bad page still won't convert.

### ⚠️ Human Checkpoint
> Verify all CTA links work and go to correct destinations. Test CTAs on all devices and browsers. Ensure CTA text aligns with destination page content (don't promise what the landing page doesn't deliver).

> **Benchmark Context**: Personalized CTAs convert 202% better than default. First-person phrasing increases CTR by 25-30%. Single CTA emails increase clicks by 371%. CTAs above the fold get 80% of attention. Red and green buttons perform similarly — contrast with surroundings matters more than specific color. Anchor text CTAs in blog posts generate 47-93% of leads for inbound marketing.

## Output Contract

### Deliverable: Markdown CTA Optimization Plan

```markdown
# CTA Optimization: [Brand/Page]

## Current CTA Audit
| CTA | Location | Copy | CTR | Issue |
|---|---|---|---|---|

## Recommended CTAs
| Location | Primary CTA | Secondary CTA | Design Spec |
|---|---|---|---|

## CTA Copy Variants
### [Location/Page]
1. [Variant] — Formula: [type], Rationale: [why]
2. [Variant]
3. [Variant]

## Personalization Rules
| Audience | CTA Copy | CTA Design | Trigger |
|---|---|---|---|

## A/B Test Plan
| Test | Control | Variant | Metric | Duration |
|---|---|---|---|---|

## Expected Results
- CTR: [current] → [target]
- Conversion: [current] → [target]
```

## Platform Implementation Steps

### Website
1. Audit all CTAs across top 10 pages by traffic
2. Implement one primary CTA per page with consistent design
3. Set up CTA click tracking (GA4 events or Tag Manager)
4. Create CTA component library for consistency across pages

### Email
1. Standardize CTA button design across all email templates
2. Test button vs. text link CTAs
3. Implement dynamic CTAs based on subscriber segment
4. A/B test CTA copy on every send

### HubSpot Smart CTAs
1. Create CTA variants for different lifecycle stages
2. Configure smart rules (visitor, lead, customer)
3. Set up CTA A/B testing in HubSpot
4. Track CTA performance by placement and audience

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| CTR drops after change | New copy unclear or less compelling | Revert quickly; test smaller variations; keep what works |
| Multiple CTAs confuse users | No clear hierarchy; competing actions | Designate one primary CTA per page; reduce secondary CTAs |
| High CTR but low conversion | CTA promises more than destination delivers | Align CTA copy with landing page; manage expectations |
| Test inconclusive | Not enough traffic or too small a change | Extend test duration; make bolder changes; combine low-traffic pages |

## How to Get Your Data

- **CTA clicks**: GA4 → Events → click events on CTAs; or heatmap tool → click data
- **Conversion rate**: GA4 → Conversions → filter by CTA source page
- **Heatmaps**: Hotjar, FullStory, or Clarity → click and scroll maps on key pages
- **No data**: Share your current CTAs (text + placement) — Claude recommends improvements based on best practices

## Example

**Input**: "CTA optimization for SaaS homepage. Current CTA: 'Get Started' button above fold. CTR: 1.8%. Also have 'Learn More' and 'Watch Demo' competing. 10K monthly visitors. Target: increase trial signups."

**Output**: Problem: 3 competing CTAs diluting attention — "Get Started" is vague and doesn't communicate value. Solution: single primary CTA hierarchy. Primary (above fold): "Start Free — No Credit Card Needed" (action + risk-reducer). Why: adds specificity ("free") and removes objection ("no credit card"). Expected CTR: 3-4%. Secondary (after features section): "See [Product] in 2 Minutes" (links to demo video — lower commitment than trial). Tertiary (sticky header): "Start Free Trial" (persistent, lower visual weight). Remove: "Learn More" (vague, sends people to more reading instead of action). CTA design: primary button — filled, high-contrast color, 48px height, centered above fold with 40px top margin. A/B test plan: (1) "Get Started" vs. "Start Free — No Credit Card Needed" (copy test, 2 weeks). (2) Winner vs. "Try [Product] Free for 14 Days" (specificity test). (3) Test CTA position: above fold only vs. above fold + after each feature section. Expected results: homepage trial starts increase from 180/month to 300-400/month with optimized CTA hierarchy.
