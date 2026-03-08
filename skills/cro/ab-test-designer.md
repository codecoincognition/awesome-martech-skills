---
name: ab-test-designer
description: >
  Design statistically sound A/B tests for marketing assets.
  Use this skill whenever the user mentions A/B testing, split testing, experiment design,
  statistical significance, sample size calculation, test duration, or says things like
  "should I A/B test this" or "how long should my test run" or "design a test for my
  landing page." Also trigger for multivariate testing design, conversion rate experiments,
  minimum detectable effect calculations, or any request to validate a marketing change.
---

# A/B Test Designer

Designs statistically sound A/B tests with hypothesis, variant descriptions, sample size calculation, duration estimate, success criteria, and implementation guide. Prevents common testing mistakes like stopping tests too early.

## Granularity Check

> Completable in one 10-minute session. Input is element to test + current metrics. Output is a complete test plan.

## User Intent Mapping

- "Design an A/B test for my landing page headline" (direct command)
- "How long should I run this A/B test?" (duration question)
- "How much traffic do I need to test this?" (sample size)
- "Is this result statistically significant?" (analysis)
- "What should I A/B test first?" (prioritization)
- "Set up a test for my email subject lines" (channel-specific)
- "I want to test a new pricing page" (specific asset)
- "Help me design an experiment for our signup flow" (product)
- "My boss wants to test everything — help me prioritize" (strategic)
- "Calculate the sample size for my test" (statistical)

## Input Contract

### Required Input

| Field | Type | Description | Example |
|---|---|---|---|
| `element_to_test` | string | What you're testing | `"Landing page headline"` |
| `baseline_rate` | float (0-1) | Current conversion rate | `0.03` (3%) |
| `daily_traffic` | integer | Daily visitors/recipients | `500` |

### Optional Input

| Field | Type | Default | Description |
|---|---|---|---|
| `desired_lift` | float | `0.20` | Minimum relative improvement to detect (20% = 3% → 3.6%) |
| `confidence_level` | float | `0.95` | Statistical confidence (0.90, 0.95, 0.99) |
| `power` | float | `0.80` | Statistical power |
| `num_variants` | integer | `2` | Number of variants (including control) |
| `test_context` | string | `""` | Business context for hypothesis |

### Input Validation Rules

1. `baseline_rate` must be between 0 and 1
2. `daily_traffic` must be positive
3. `desired_lift` must be positive (relative, not absolute)
4. `confidence_level` must be 0.80-0.99

## Process

1. **Validate inputs and calculate sample size** using the two-proportion z-test formula:
   - n = (Zα/2 + Zβ)² × [p1(1-p1) + p2(1-p2)] / (p2 - p1)²
   - Where p1 = baseline rate, p2 = baseline × (1 + desired_lift)
   - For 95% confidence, 80% power: Zα/2 = 1.96, Zβ = 0.84

2. **Calculate test duration** — Required sample ÷ daily traffic ÷ traffic allocation (typically 100% for simple A/B). Add 1 full business cycle (minimum 7 days) to account for day-of-week effects.

3. **Write hypothesis** — Structured format: "If we [change], then [metric] will [direction] by at least [amount], because [reasoning]."

4. **Design variants** — Describe control and treatment with specific changes. Each variant tests exactly one variable.

5. **Human checkpoint** — Present test plan summary. Ask: "Does the test duration work for your timeline? Is the minimum detectable effect meaningful for your business?"

6. **Define success criteria** — Clear decision matrix:
   - Significant winner → implement winner
   - No significant difference → keep control (lower risk)
   - Significant loser → keep control, investigate why

7. **Add guardrail metrics** — Identify metrics that should NOT decrease during the test.

## Output Contract

### Output Format

| Output | Format | Contents |
|---|---|---|
| Test plan | Markdown | Complete A/B test specification |

### Test Plan Structure

```markdown
# A/B Test Plan: [Element]

## Hypothesis
If we [change], then [metric] will [improve] by [amount], because [reasoning].

## Test Configuration
- Sample size needed: X per variant (X total)
- Test duration: X days (at X visitors/day)
- Confidence level: 95%
- Minimum detectable effect: X% relative lift
- Traffic allocation: 50/50

## Variants
- Control (A): [description]
- Treatment (B): [description]

## Success Criteria
| Outcome | Action |
|---|---|
| B wins (p < 0.05) | Implement B |
| No difference | Keep A |
| B loses | Keep A, investigate |

## Guardrail Metrics
- [Metric] must not decrease by more than X%

## Implementation Checklist
- [ ] QA both variants
- [ ] Set up tracking
- [ ] Confirm even traffic split
- [ ] Set calendar reminder for minimum duration
- [ ] DO NOT peek at results before minimum duration
```

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Sample size too large | Low traffic + small desired lift | Suggest testing a higher-impact change or accepting larger MDE |
| Test would take > 90 days | Insufficient traffic | Recommend a less granular test or different channel |
| Baseline rate unknown | No historical data | Recommend running for 2 weeks to establish baseline first |
| Too many variants | User wants to test 5 things | Recommend sequential tests or a multivariate approach |
| Seasonal interference | Test spans a holiday or event | Flag the risk; suggest pre/post-event test windows |

## Example

**User prompt:** "Design an A/B test for our signup page headline. Current conversion rate is 3%, we get about 800 visitors per day, and we want to detect at least a 15% improvement."

**Claude output:**

> # A/B Test Plan: Signup Page Headline
>
> ## Hypothesis
> If we change the headline from "Manage Projects Better" to "Stop Losing 5 Hours/Week to Status Meetings", then signup rate will increase by at least 15% (3.0% → 3.45%), because specific pain-point headlines outperform generic benefit headlines.
>
> ## Test Configuration
> - **Sample size needed:** 17,200 per variant (34,400 total)
> - **Test duration:** 43 days minimum (at 800 visitors/day)
> - **Confidence level:** 95% | **Power:** 80%
> - **Minimum detectable effect:** 0.45 percentage points (15% relative)
> - **Traffic allocation:** 50/50
>
> The test duration is just over 6 weeks. This is long because a 15% relative lift on a 3% baseline is a small absolute change (0.45pp). If you can accept detecting a 25% lift instead, the test drops to 18 days.
>
> ## Guardrail Metrics
> - Bounce rate must not increase by more than 5%
> - Pages per session must not decrease by more than 10%
