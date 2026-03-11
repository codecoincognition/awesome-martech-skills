---
name: ab-test-result-analyzer
description: >
  Analyze A/B test results for statistical significance, practical impact, and actionable recommendations.
  Use this skill when the user says "A/B test analysis", "split test results", "experiment results
  interpretation", "is this test result significant", "A/B test statistical significance", "multivariate
  test analysis", "test winner determination", "sample size calculator", "experiment design review",
  "conversion rate experiment", or "test result confidence level". Also trigger for hypothesis testing,
  experiment post-mortem, or testing program optimization.
---

# A/B Test Result Analyzer

Analyzes A/B and multivariate test results for statistical significance, practical significance, and business impact — providing clear recommendations on whether to implement, iterate, or discard variants.

## Granularity Check

> **Time**: ~5 min data prep → ~10 min Claude session → ~30-60 min building in Google Sheets / Looker / GA4. If designing new tests, add 1-2 weeks for implementation. Input is test data (visitors, conversions, variants). Output is Markdown analysis with statistical assessment, business impact estimate, and next steps.

## User Intent Mapping

- "Is this A/B test result significant?" (significance)
- "How long should I run this test?" (duration)
- "Analyze these split test results" (analysis)
- "Should we implement the winning variant?" (decision)
- "Our test shows a 5% lift — is that real?" (validation)
- "Sample size for our next test" (planning)
- "Multivariate test results interpretation" (MVT)
- "A/B test post-mortem" (learning)
- "Test didn't reach significance — now what?" (inconclusive)
- "Testing roadmap for our site" (program)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Variant Data | Text | Visitors and conversions per variant (control + test) |
| Test Duration | Text | How long the test ran |
| Primary Metric | Text | What you're measuring (conversion rate, revenue, etc.) |

### If You Don't Have This Data

- **No testing tool?** Claude recommends free tools (Google Optimize successor, VWO free, PostHog) and helps you set up your first test in under an hour.
- **Test still running?** Claude estimates time to significance based on current data and traffic — tells you when to check back.
- **Not sure what to test?** Claude identifies high-impact test opportunities from your funnel data and prioritizes by expected impact and ease of implementation.
- **Small traffic volume?** Claude adjusts analysis for small samples, recommends longer test durations, and suggests higher-impact changes that need fewer visitors to detect.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Segment Data | Text | Results broken down by segment (device, channel, etc.) |
| Secondary Metrics | Text | Additional metrics tracked (revenue per user, bounce rate) |
| Test Hypothesis | Text | What you expected and why |
| Historical Data | Text | Baseline conversion rates and past test results |
| Traffic Volume | Text | Average daily/weekly visitors to the tested page |

## Process

### Step 1: Statistical Significance Assessment

| Component | What to Check | Threshold |
|---|---|---|
| Confidence level | Probability result isn't due to chance | 95% minimum (p < 0.05) |
| Statistical power | Probability of detecting a real effect | 80% minimum |
| Sample size | Total observations per variant | Depends on baseline rate and MDE |
| Minimum detectable effect | Smallest meaningful difference | 5-10% relative lift for most tests |
| Test duration | Minimum time to account for cyclicality | 1-2 full business cycles (7-14 days minimum) |

Quick significance check:
- **Clearly significant**: p < 0.05, 1000+ conversions per variant, ran 14+ days
- **Likely significant**: p < 0.10, 500+ conversions per variant, ran 7+ days
- **Inconclusive**: p > 0.10, or fewer than 200 conversions per variant
- **Not significant**: p > 0.20, adequate sample size, ran full duration

### Step 2: Practical Significance Assessment

| Question | Why It Matters | How to Assess |
|---|---|---|
| Is the lift meaningful? | A 0.5% lift might be statistically significant but not worth implementing | Compare lift to implementation cost |
| Revenue impact | Convert percentage lift to actual revenue | Lift % × baseline revenue × confidence |
| Implementation cost | What does it take to implement the winner? | Dev time, design time, ongoing maintenance |
| Risk assessment | Could the change harm other metrics? | Check secondary metrics, segment performance |
| Long-term sustainability | Is the lift a novelty effect? | Compare first-week vs. last-week performance |

### Step 3: Common Pitfalls Detection

| Pitfall | How to Detect | Fix |
|---|---|---|
| Peeking (checking too early) | Test called significant before planned sample size | Set sample size in advance; don't stop early |
| Simpson's paradox | Winner overall but loser in key segments | Always check segment-level results |
| Novelty effect | Lift decreases over time within test period | Compare first-half vs. second-half results |
| Pollution | Test groups contaminated (users see both variants) | Verify randomization and cookie settings |
| Multiple testing | Many variants or metrics inflating false positives | Apply Bonferroni or Holm correction |
| Selection bias | Test traffic isn't representative | Verify traffic distribution matches normal patterns |

### Step 4: Sample Size Planning

| Baseline Rate | MDE (Relative) | Sample Size Per Variant | At 1K/day |
|---|---|---|---|
| 1% | 20% (0.2pp) | ~160,000 | 320 days |
| 1% | 50% (0.5pp) | ~26,000 | 52 days |
| 3% | 10% (0.3pp) | ~78,000 | 156 days |
| 3% | 20% (0.6pp) | ~20,000 | 40 days |
| 5% | 10% (0.5pp) | ~30,000 | 60 days |
| 5% | 20% (1.0pp) | ~8,000 | 16 days |
| 10% | 10% (1.0pp) | ~8,000 | 16 days |
| 10% | 20% (2.0pp) | ~2,000 | 4 days |

Formula factors: 95% confidence, 80% power, two-tailed test.

### Step 5: Decision Framework

| Result | Confidence | Action |
|---|---|---|
| Clear winner (p < 0.05, meaningful lift) | High | Implement winner, document learnings |
| Marginal winner (p < 0.10, small lift) | Medium | Extend test or iterate on variant |
| Flat result (no significant difference) | High (with adequate power) | Implement whichever is easier to maintain |
| Loser (control wins significantly) | High | Discard variant, analyze why hypothesis was wrong |
| Inconclusive (underpowered) | Low | Run longer, increase traffic, or test bigger change |
| Mixed (wins some metrics, loses others) | Variable | Prioritize by primary metric; investigate trade-offs |

### Step 6: Learning Documentation

| Element | What to Capture | Why |
|---|---|---|
| Hypothesis | What you tested and why | Prevents re-testing the same idea |
| Result | Outcome with specific numbers | Builds institutional knowledge |
| Surprise findings | Unexpected segment differences or secondary metric impacts | Generates new hypotheses |
| Implementation notes | What was changed, technical details | Enables replication or rollback |
| Next test idea | What this result suggests testing next | Maintains testing momentum |

### Confidence & Sample Size

> **Confidence Note**: Statistical significance (p < 0.05) means there's less than a 5% chance the result is due to random variation — it doesn't mean the result is definitely real. With enough traffic, even tiny differences become "significant" — always check practical significance too. A/B tests should run for at least one full business cycle (typically 7 days) even if they reach statistical significance earlier, to account for day-of-week effects. Never stop a test early because it looks like it's winning or losing — this inflates false positive rates by 2-5x.

### ⚠️ Human Checkpoint
> Verify that test groups had comparable traffic quality (same sources, no campaign overlap). Check that the test didn't overlap with other site changes or campaigns that could confound results. Review segment-level results before implementing — a winner overall can be a loser for your most valuable segment.

> **Benchmark Context**: See VWO 2024 A/B Testing Report for current industry benchmarks relevant to this analysis.
## Output Contract

### Deliverable: Markdown Test Analysis

```markdown
# A/B Test Analysis: [Test Name]

## Test Summary
- Hypothesis: [what you tested and expected]
- Duration: [days ran]
- Primary metric: [what was measured]
- Traffic: [visitors per variant]

## Results
| Variant | Visitors | Conversions | Rate | vs. Control |
|---|---|---|---|---|

## Statistical Analysis
- Confidence level: [%]
- P-value: [value]
- Statistical power: [%]
- Minimum detectable effect: [%]

## Verdict: [WINNER / INCONCLUSIVE / NO DIFFERENCE / LOSER]

## Business Impact
- Expected annual revenue impact: [$]
- Confidence range: [$low - $high]
- Implementation effort: [low/medium/high]

## Segment Analysis
| Segment | Control | Variant | Lift | Significant? |
|---|---|---|---|---|

## Recommendations
| Action | Rationale | Priority |
|---|---|---|

## Next Test Ideas
| Hypothesis | Metric | Expected Impact |
|---|---|---|
```

## Platform Implementation Steps

### Testing Tool Setup
1. Choose testing tool (Google Optimize successor, VWO, Optimizely, PostHog)
2. Install tracking code and verify data collection
3. Define conversion events that match your primary metric
4. Set up test with proper traffic allocation (50/50 for two variants)
5. Configure test to run for calculated minimum duration

### Analysis Process
1. Wait until minimum sample size is reached (no peeking before)
2. Export raw data: visitors, conversions, and secondary metrics per variant
3. Calculate statistical significance using built-in tool or external calculator
4. Check segment-level results (device, channel, new vs. returning)
5. Document findings in learning repository

### Testing Program Management
1. Maintain a hypothesis backlog prioritized by impact × confidence
2. Run 2-4 tests per month (depending on traffic)
3. Track cumulative testing impact (aggregate lift from implemented winners)
4. Share test learnings across teams monthly
5. Review and update testing priorities quarterly

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| False positive (implement a non-winner) | Stopped test too early, peeked at results | Pre-register sample size; use sequential testing methods if you must check early |
| False negative (miss a real winner) | Test underpowered, not enough traffic | Test bigger changes; increase traffic; extend duration |
| Test velocity too slow | Too few ideas, slow implementation, long test durations | Build hypothesis backlog; prioritize high-traffic pages; increase minimum detectable effect |
| Results don't replicate | Seasonal effects, novelty, or external changes | Re-test important winners; compare pre/post implementation metrics |

## How to Get Your Data

- **Testing tool**: Export results directly from VWO, Optimizely, or similar
- **GA4**: GA4 → Explore → create segments for control and variant → compare
- **Manual**: Record visitors and conversions per variant in a spreadsheet
- **No tool yet**: Describe what you want to test — Claude calculates required sample size and recommends setup

## Example

**Input**: "A/B test on our pricing page CTA. Control: 'Start Free Trial' (blue button). Variant: 'Try It Free — No Credit Card' (green button, larger). Ran 21 days. Control: 12,450 visitors, 498 conversions (4.0%). Variant: 12,380 visitors, 572 conversions (4.62%). Is this significant? Should we implement?"

**Output**: Statistical analysis: observed lift is +15.5% relative (4.0% → 4.62%, +0.62 percentage points). P-value: 0.024 (significant at 95% confidence). Statistical power: 85% (adequate). Test ran 21 days with 24,830 total visitors — sample size is sufficient. Verdict: WINNER — the variant wins with high confidence. Segment check needed: (1) Verify the lift holds across mobile and desktop separately. (2) Check that downstream conversion (trial → paid) isn't lower — "No Credit Card" may attract less-committed users. (3) Compare first week vs. last week to rule out novelty effect. Business impact: if baseline is 498 conversions/month and lift is 15.5%, that's ~77 additional trials per month. At your trial-to-paid rate of 25% and $200/month average revenue, that's ~19 additional customers × $200 = $3,800/month incremental revenue ($45,600/year). Recommendation: implement the variant, but monitor trial-to-paid conversion for the next 60 days. If trial-to-paid drops more than 5 percentage points, the "No Credit Card" copy may be attracting lower-quality leads. Next test: try the winning copy with the original blue button color (isolate whether copy or color drove the lift).

## Related Skills

- **ab-test-designer** (../cro/ab-test-designer.md) — Design statistically sound tests before you run them; use this to plan future tests based on learnings from past results.
- **landing-page-optimizer** (../cro/landing-page-optimizer.md) — Audit the page you're testing to identify hypotheses; use heatmap insights to design better test variants.
- **campaign-performance-benchmarker** (./campaign-performance-benchmarker.md) — Compare your test results against industry benchmarks; understand whether your lift is exceptional or expected.
- **marketing-roi-calculator** (./marketing-roi-calculator.md) — Calculate the financial impact of your test results; convert statistical significance to revenue impact.
