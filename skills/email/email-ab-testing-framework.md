---
name: email-ab-testing-framework
description: >
  Design and analyze email A/B tests for subject lines, content, send times, and CTAs.
  Use this skill when the user says "email A/B testing", "email split test", "test email
  subject lines", "email experiment design", "which email performs better", "email testing
  framework", "email optimization tests", "email send time test", "CTA testing for email",
  "email content testing", or "email test results analysis". Also trigger for email
  multivariate testing, statistical significance for email tests, or email testing roadmap.
---

# Email A/B Testing Framework

Designs structured email A/B tests with hypothesis formation, controlled variables, sample size calculations, and statistical analysis for continuous email optimization.

## Granularity Check

> **Time**: ~5 min data prep → ~10 min Claude session → ~30-45 min setup in Mailchimp / Klaviyo / HubSpot. If running tests, add 1-2 weeks per test cycle. Input is current email performance and test ideas. Output is Markdown testing plan with analysis framework.

## User Intent Mapping

- "How do I A/B test my emails?" (getting started)
- "Design an email subject line test" (subject line)
- "What should we test in our emails?" (ideation)
- "Is this test result statistically significant?" (analysis)
- "Email testing roadmap for the quarter" (roadmap)
- "Send time optimization test" (send time)
- "CTA button test for email" (CTA)
- "How big should my test sample be?" (sample size)
- "Our A/B tests never show clear winners" (troubleshooting)
- "Multivariate email testing plan" (advanced)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Test Element | Text | What you want to test (subject line, CTA, content, send time, etc.) |
| List Size | Number | Subscribers receiving the email |
| Current Metrics | Text | Baseline open rate, click rate, conversion rate |

### If You Don't Have This Data

- **No baseline metrics?** Send 3-5 untested emails first and average the results. Claude uses industry benchmarks as a starting baseline.
- **Small list?** Claude adjusts test design for smaller samples — fewer variations, longer test windows, binary decisions.
- **No testing experience?** Claude provides a step-by-step beginner testing plan starting with high-impact, easy-to-test elements.
- **No testing tool?** Most ESPs (Mailchimp, HubSpot, Klaviyo) have built-in A/B testing. Claude works with whatever your ESP offers.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Past Test Results | CSV/Text | Previous A/B tests and outcomes |
| ESP | Text | Which email platform you use |
| Test History | Text | What you've already tested |
| Business Goals | Text | What you're optimizing for (opens, clicks, revenue) |
| Send Frequency | Text | How often you email your list |

## Process

### Step 1: Test Prioritization
Rank test ideas by impact and ease:
| Test Element | Impact | Ease | Priority |
|---|---|---|---|
| Subject line | High (affects opens) | Easy | 1 |
| CTA (text, color, placement) | High (affects clicks) | Easy | 2 |
| Send time/day | Medium (affects opens) | Easy | 3 |
| Email length | Medium (affects clicks) | Medium | 4 |
| Personalization | High (affects engagement) | Medium | 5 |
| Content layout | Medium (affects clicks) | Medium | 6 |
| From name | Medium (affects opens) | Easy | 7 |

### Step 2: Hypothesis Formation
Structure each test as:
- **Hypothesis**: "If we [change], then [metric] will [improve/decline] because [reason]."
- **Variable**: One element being tested (never test multiple things simultaneously)
- **Control**: The current version (unchanged)
- **Variant**: The new version (one change from control)
- **Primary metric**: The one metric that determines the winner

### Step 3: Sample Size & Duration
- Minimum sample: 1,000 per variant for open rate tests, 5,000+ for click/conversion tests
- Use a sample size calculator: input baseline rate, minimum detectable effect (MDE), and significance level
- For small lists (<5,000): run the test across the full list; accept wider confidence intervals
- Test duration: minimum 24 hours for send time tests, full send for content tests

### Step 4: Test Execution
- Split: random, equal-sized groups (50/50 for A/B, smaller for winner rollout)
- Send simultaneously (unless testing send time)
- Don't change anything else during the test period
- Wait for the full measurement window before declaring a winner

### Step 5: Statistical Analysis
- Statistical significance: aim for 95% confidence
- Calculate lift: ((Variant - Control) / Control) × 100
- Check practical significance: is the difference meaningful for business impact?
- Account for multiple comparison bias if testing 3+ variants
- Document results including sample size and confidence level

### Step 6: Testing Calendar
- Test one element per send (don't stack tests)
- Maintain a testing log with hypotheses, results, and learnings
- Build on winners: winning elements become the new control
- Retest periodically: audience behavior changes over time

### Confidence & Sample Size
> **Confidence Note**: Most email A/B tests are underpowered — small sample sizes lead to false positives. A 2% open rate difference needs 15,000+ subscribers per variant to detect reliably. If your list is small, focus on tests with large expected effect sizes (5%+ difference). "No significant difference" is also a valid result — it means both versions perform similarly.

### ⚠️ Human Checkpoint
> Review test results for statistical significance before implementing winners. Don't cherry-pick metrics — declare your primary metric before the test starts. Ensure test variants don't violate brand guidelines or compliance requirements.

> **Benchmark Context**: Companies that A/B test every email achieve 37% higher ROI (Mailchimp 2024 Email Marketing Benchmarks). Subject line tests show the widest performance variance (up to 40% open rate difference. Personalized subject lines increase opens by 26% on average (HubSpot 2024 State of Marketing). Send time optimization typically yields 5-15% improvement (Campaign Monitor 2024 Email Benchmarks). The average A/B test needs 2,500 subscribers per variant for reliable results at 95% confidence (Mailchimp 2024 Email Marketing Benchmarks). (HubSpot 2024 State of Marketing).
## Output Contract

### Deliverable: Markdown Testing Framework

```markdown
# Email A/B Testing Framework: [Brand]

## Testing Roadmap
| Test # | Element | Hypothesis | Primary Metric | Timeline |
|---|---|---|---|---|

## Test Design: [Current Test]
- Hypothesis: [statement]
- Control (A): [description]
- Variant (B): [description]
- Sample size: [per variant]
- Duration: [time]
- Primary metric: [metric]
- MDE: [minimum detectable effect]

## Sample Size Calculator
- Baseline rate: [%]
- MDE: [%]
- Significance: 95%
- Required sample: [per variant]

## Results Template
| Metric | Control | Variant | Lift | Significant? |
|---|---|---|---|---|

## Testing Log
| Date | Test | Result | Learning | Next Action |
|---|---|---|---|---|

## Best Practices Checklist
- [ ] One variable per test
- [ ] Primary metric declared before test
- [ ] Sample size sufficient
- [ ] Random, equal split
- [ ] Simultaneous send
```

## Platform Implementation Steps

### Mailchimp
1. Campaigns → Create Campaign → A/B Test
2. Select test variable (subject line, from name, content, send time)
3. Set sample size and winning criteria
4. Choose automatic winner selection or manual review
5. Review results in Campaign Reports

### HubSpot
1. Marketing → Email → Create A/B Test Email
2. Select variation type and create variants
3. Set distribution (equal split or sample + remainder)
4. Define winning metric and send
5. Analyze in Email Performance dashboard

### Klaviyo
1. Campaigns → Create Campaign → A/B Test
2. Add variants (up to 4 for multivariate)
3. Set test distribution and winning criteria
4. Send to test group, then auto-send winner to remainder
5. Review results with statistical significance indicator

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Tests never reach significance | Sample size too small for the effect size | Increase sample or test bigger changes |
| False positives | Running too many tests or checking results too early | Wait for full measurement window; use 95% confidence threshold |
| Winning variant doesn't hold | Novelty effect or seasonal bias | Retest winners after 30 days; compare across multiple sends |
| No actionable learnings | Testing trivial differences | Test meaningfully different approaches, not minor word swaps |

## How to Get Your Data

- **Current metrics**: ESP dashboard → Campaign reports → average open/click rates
- **Past test results**: ESP → A/B test reports → export results
- **Sample size calculator**: Use calculators at optimizely.com or evanmiller.org/ab-testing/
- **No data**: Provide your list size — Claude designs tests appropriate for your scale

## Example

**Input**: "Design email A/B tests for our SaaS newsletter. 18K subscribers, 32% open rate, 4.2% click rate. Using HubSpot. Haven't done any testing before."

**Output**: Testing roadmap (8 tests over 4 months): Test 1: Subject line — question vs. statement format (hypothesis: questions increase opens 5%+, 9K per variant, sufficient). Test 2: CTA — "Learn More" vs. "Read the Guide" (hypothesis: specific CTAs increase clicks 15%+). Test 3: Send day — Tuesday vs. Thursday (hypothesis: Thursday performs better for B2B). Test 4: From name — company name vs. person name. Test 5: Email length — 200 words vs. 500 words. Test 6: Personalization — company name in subject line vs. generic. Test 7: Preview text — descriptive vs. curiosity-driven. Test 8: Layout — single CTA vs. multiple links. Start with Test 1 next send. Sample size: 9K per variant gives 95% confidence for detecting 3%+ open rate difference. Expected learning: after 8 tests, optimized email template should achieve 38-42% open rate and 5.5-6.5% click rate.

## Related Skills

- **[Email Subject Line Tester](./email-subject-line-tester.md)** — Use to generate and test subject line variants before running full A/B tests across your email list.
- **[Email Performance Analyzer](./email-performance-analyzer.md)** — Use after tests complete to analyze results and extract actionable insights from the data.
- **[Email Sequence Builder](./email-sequence-builder.md)** — Use to design the sequences where you'll run tests and implement winning variations.
- **[Email Copywriting Framework](./email-copywriting-framework.md)** — Use to create copy variations for body content and CTA testing.
