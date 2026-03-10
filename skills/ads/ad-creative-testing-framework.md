---
name: ad-creative-testing-framework
description: >
  Design structured ad creative testing plans with hypotheses, variants, and statistical rigor.
  Use this skill when the user says "ad creative testing", "A/B test my ads", "which ad creative
  wins", "creative testing framework", "ad variant testing", "multivariate ad test", "test ad
  headlines", "test ad images", "creative iteration plan", "ad testing roadmap", or "systematic
  creative testing". Also trigger for ad fatigue testing, creative refresh cadence, or hook
  testing strategies.
---

# Ad Creative Testing Framework

Designs structured creative testing plans with clear hypotheses, controlled variables, statistical rigor, and iteration workflows to systematically improve ad performance.

## Granularity Check

> **Time**: ~5 min data prep → ~10 min Claude session → ~30-60 min building in Google Ads / Meta Ads Manager. If implementing output in ad platforms, add 20-30 min for test setup. Input is current ad performance and test goals. Output is Markdown testing plan with variants.

## User Intent Mapping

- "How do I test my ad creatives?" (methodology)
- "A/B test plan for Facebook ads" (platform-specific)
- "Which headline works best?" (element-specific)
- "Creative testing roadmap for Q2" (planning)
- "Our ads are fatiguing — need fresh creative tests" (refreshing)
- "Test video vs. image ads" (format testing)
- "Hook testing for TikTok ads" (element-specific)
- "How much budget for creative testing?" (budgeting)
- "Test UGC vs. branded content" (style testing)
- "When do I have a winner?" (statistical significance)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Current Ads | Text | Describe or paste your current ad creative (headline, image/video, body, CTA) |
| Platform(s) | Text | Where you're running ads |
| Test Goal | Text | What you want to learn (best hook, best format, best CTA, etc.) |

### If You Don't Have This Data

- **No current ads?** Claude generates initial test variants from scratch based on your product and audience.
- **No performance data?** Start testing with 2-3 variants from day one. Track CPA and CTR as your baseline metrics.
- **No design resources?** Test copy-only variables first (headlines, CTAs). Copy tests require no design changes.
- **No budget for testing?** Allocate 10-15% of total ad budget. Even $20/day per variant for 7 days yields directional data.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Performance Data | CSV | Current ad metrics (CTR, CPA, ROAS) |
| Target Audience | Text | Who sees these ads |
| Budget | Number | Available for testing |
| Past Test Results | Text | Previous tests and outcomes |
| Brand Guidelines | Text | Constraints on creative direction |

## Process

### Step 1: Testing Hierarchy
Test elements in order of impact:
1. **Concept/Angle** (biggest impact): Different value propositions or emotional appeals
2. **Format** (high impact): Video vs. image vs. carousel vs. UGC
3. **Hook** (high impact): First 3 seconds of video, headline for static
4. **Body Copy** (medium impact): Benefit framing, length, tone
5. **CTA** (medium impact): Button text, urgency, specificity
6. **Visual Details** (lower impact): Colors, layout, font treatment

### Step 2: Hypothesis Formation
For each test, state:
- **Hypothesis**: "Changing [variable] from [A] to [B] will [improve metric] because [reasoning]"
- **Primary metric**: The single metric that determines the winner
- **Secondary metrics**: Supporting metrics to understand why

### Step 3: Variant Design
Rules for controlled testing:
- Change ONE variable at a time (pure A/B) or test complete concepts (concept testing)
- Create 2-4 variants per test (more variants = more budget needed)
- Keep non-test elements identical across variants
- Label variants clearly: Control, Variant A, Variant B

### Step 4: Test Configuration
| Parameter | Recommendation |
|---|---|
| Budget per variant | Minimum $50-100/day or 2x target CPA, whichever is higher |
| Duration | 7-14 days minimum |
| Audience | Same audience across all variants |
| Placement | Same placements (or Advantage+ for consistency) |
| Statistical significance | 90-95% confidence before declaring winner |

### Step 5: Analysis & Iteration
- Calculate statistical significance using a significance calculator
- Document results: what won, why (hypothesis confirmed/rejected), learning
- Graduate winners to "control" status
- Design next test based on learnings
- Maintain a testing log for institutional knowledge

### Confidence & Sample Size
> **Confidence Note**: Minimum sample sizes for reliable creative testing: 1,000 impressions for CTR comparisons, 50-100 conversions per variant for CPA comparisons. Below these thresholds, random variance dominates results. A "winner" at 80% confidence may reverse with more data. Wait for 90%+ confidence. Day-of-week and time-of-day effects can skew short tests — always run tests for full weeks.

### ⚠️ Human Checkpoint
> Review test variants for brand consistency, legal compliance, and unintended messaging before launch. Verify that the test audience is large enough to reach significance within your timeline and budget.

> **Benchmark Context**: Systematic creative testing improves CPA by 20-40% over 3-6 months. Top advertisers test 10-20 creative variants per month. The #1 creative variable that drives performance is the concept/angle (not colors or fonts). 80% of ad spend should go to proven creative, 20% to testing (Statista 2024 Digital Advertising Report). Creative fatigue sets in 30-50% faster on TikTok vs. Meta.
## Output Contract

### Deliverable: Markdown Testing Plan

```markdown
# Creative Testing Plan: [Brand] — [Period]

## Test 1: [Name]
- Hypothesis: [statement]
- Variable: [what changes]
- Control: [current creative]
- Variant A: [description]
- Variant B: [description]
- Primary metric: [CPA / CTR / ROAS]
- Budget: $X per variant for Y days
- Minimum sample: [conversions or impressions needed]

## Test 2: [Name]
...

## Testing Calendar
| Week | Test | Variable | Budget | Platform |
|---|---|---|---|---|

## Results Log Template
| Test | Control | Variant A | Winner | Confidence | Learning |
|---|---|---|---|---|---|

## Creative Testing Rules
1. [Rule]
```

## Platform Implementation Steps

### Meta Ads Manager (A/B Test)
1. Campaign → A/B Test → Select variable (Creative)
2. Create ad sets with identical targeting and budget
3. Upload different creative per ad set
4. Set test duration (7-14 days recommended)
5. Meta auto-declares winner at significance threshold

### Google Ads (Ad Variations)
1. Campaigns → Experiments → Ad Variations
2. Select campaigns to test
3. Define variation (find and replace headline, description, etc.)
4. Set traffic split and duration
5. Review experiment results in the Experiments tab

### Manual Testing (Any Platform)
1. Create separate ad sets per variant with identical settings
2. Split budget equally
3. Run for 7-14 days without changes
4. Compare metrics in a spreadsheet
5. Use an online significance calculator to determine winner

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| No clear winner | Too similar variants or too little data | Test bolder differences; increase budget or duration |
| Winner in CTR but loser in CPA | Clickbait-y creative that doesn't convert | Optimize for CPA, not CTR; check landing page alignment |
| Results don't replicate | Seasonality or audience shift | Re-test with larger sample; control for time-of-week effects |
| Testing too many things at once | Multivariate without enough budget | Stick to 1 variable per test; run sequentially |

## How to Get Your Data

- **Current ads**: Screenshot or describe your running ads (headline, image, body, CTA)
- **Performance**: Export from ad platform → filter to the ads you want to test
- **No data**: Describe your product and audience — Claude generates initial test variants

## Example

**Input**: "Creative testing plan for our meal kit subscription. Current control: Single image ad with headline 'Healthy Meals Made Easy' and CTA 'Start Cooking'. Platform: Meta. Budget: $2,000/month for testing. Want to test hooks and formats."

**Output**: 3-test roadmap. Test 1 (Week 1-2): Hook testing — Control: 'Healthy Meals Made Easy' vs. Variant A: 'Stop Spending $50/Night on Takeout' vs. Variant B: '15-Minute Dinners Your Kids Will Actually Eat'. Hypothesis: Specific pain-point hooks outperform generic benefit hooks. Budget: $100/day split 3 ways, 14 days. Primary metric: CPA. Test 2 (Week 3-4): Format testing — winning hook in single image vs. UGC-style video vs. carousel (recipe steps). Hypothesis: UGC video converts 2x better than static on Meta Reels. Test 3 (Week 5-6): CTA testing — 'Start Cooking' vs. 'Get 50% Off Your First Box' vs. 'See This Week's Menu'. Hypothesis: Offer-specific CTA converts better than generic. Testing rules: never pause before 7 days, minimum 30 conversions per variant, document all results in testing log.

## Related Skills

- **[ad-copy-generator](./ad-copy-generator.md)** — Generate copy variants to use as test options in your creative testing framework.
- **[ab-test-designer](../cro/ab-test-designer.md)** — Apply rigorous statistical methodology to ensure your ad creative tests reach significance.
- **[ad-performance-analyzer](./ad-performance-analyzer.md)** — Analyze historical ad results to identify which creative variables have driven the biggest wins.
- **[campaign-angle-generator](../insights/campaign-angle-generator.md)** — Generate new angle hypotheses to test in your creative variants.
