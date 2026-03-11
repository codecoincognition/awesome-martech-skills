---
name: retention-analysis-framework
description: >
  Analyze user retention patterns and design strategies to reduce churn.
  Use this skill when the user says "retention analysis", "churn analysis", "why are users
  leaving", "retention rate improvement", "cohort analysis", "churn prevention strategy",
  "customer retention plan", "reduce churn rate", "retention metrics", "user lifecycle analysis",
  or "customer health scoring". Also trigger for churn prediction modeling, win-back campaign
  design, or retention curve analysis.
---

# Retention Analysis Framework

Analyzes retention data to identify churn patterns, build cohort analyses, design retention strategies, and create churn prevention playbooks with early warning systems.

## Granularity Check

> **Time**: ~5 min data prep → ~10 min Claude session → ~60-120 min implementing in your product / tools. If implementing output, add 1-2 weeks for strategy execution. Input is user activity or cohort data. Output is Markdown retention report with action plan.

## User Intent Mapping

- "Why are our users churning?" (root cause analysis)
- "Retention analysis for our app" (full analysis)
- "Build a cohort analysis" (cohort analysis)
- "Our Day 7 retention is dropping" (metric-specific)
- "Churn prevention strategy" (strategy)
- "Customer health scoring model" (scoring)
- "Win-back campaign for churned users" (re-engagement)
- "What's our retention curve look like?" (curve analysis)
- "How to improve monthly retention" (improvement)
- "Retention benchmarks for SaaS" (benchmarking)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| User Activity Data | CSV | user_id, signup_date, last_active_date, activity_events |
| Product Type | Text | SaaS, app, e-commerce, marketplace, etc. |
| Retention Definition | Text | What counts as "retained" (daily login, weekly use, monthly purchase) |

### If You Don't Have This Data

- **No cohort data?** Export your user list with signup dates and last login dates. Claude can build basic cohort analysis from this.
- **No activity events?** Use login dates as a proxy. Track: signup date, last login, total logins, key feature usage.
- **No churn reasons?** Survey 10-20 churned users with a simple email: "What made you stop using [product]?" Even 5 responses reveal patterns.
- **No benchmarks?** Claude uses industry benchmarks. Track your own metrics monthly for 3 months to establish your baseline.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Churn Survey Results | Text | Why users say they left |
| Feature Usage | CSV | Features used by retained vs. churned users |
| Pricing Tier | CSV | Retention by plan level |
| Support Tickets | CSV | Ticket volume before churn |
| Revenue Data | CSV | MRR, expansion, contraction, churn revenue |

## Process

### Step 1: Retention Curve Analysis
- Plot retention curve (% users active over time)
- Identify critical drop-off points (Day 1, Day 7, Day 30)
- Compare to industry benchmarks
- Segment by acquisition channel, plan, or user type

### Step 2: Cohort Analysis
- Group users by signup week/month
- Track retention rate over time per cohort
- Identify improving or declining trends
- Spot cohort anomalies (product changes, seasonal effects)

### Step 3: Churn Pattern Identification
Analyze differences between retained and churned users:
- Feature usage patterns (what do retained users do differently?)
- Time to first value (how quickly did they activate?)
- Engagement frequency (daily, weekly, sporadic?)
- Support interactions (more tickets = higher churn risk?)
- Revenue tier (free vs. paid retention differences)

### Step 4: Health Score Model
Build a composite score:
| Signal | Weight | Healthy | At Risk | Churning |
|---|---|---|---|---|
| Login Frequency | 25% | Daily | Weekly | None in 14 days |
| Feature Breadth | 25% | 5+ features | 2-3 features | 1 feature |
| Support Sentiment | 20% | Positive | Neutral | Negative |
| Usage Trend | 15% | Increasing | Stable | Declining |
| Contract/Billing | 15% | Auto-renew | Monthly | Overdue |

### Step 5: Retention Strategy
Interventions by lifecycle stage:
- **Day 1-7**: Onboarding optimization, quick-win emails
- **Day 7-30**: Feature discovery, engagement hooks, habit formation
- **Day 30-90**: Value reinforcement, community connection, expansion
- **Day 90+**: Advocacy programs, loyalty rewards, health monitoring
- **At-risk**: Re-engagement campaign, personal outreach, special offers
- **Churned**: Win-back sequence (30/60/90 day), exit survey

### Confidence & Sample Size
> **Confidence Note**: Retention analysis requires minimum 3 months of data and 500+ users per cohort for reliable patterns. Monthly cohorts with <100 users produce noisy retention curves. Churn reasons from surveys are self-reported and may not reflect true causes — cross-reference with behavioral data. Seasonal effects can distort retention (holiday signups often churn faster).

### ⚠️ Human Checkpoint
> Validate churn reasons with actual user conversations (surveys alone can be misleading). Review health score thresholds with customer success team. Verify that retention interventions don't annoy retained users (frequency caps on re-engagement).

> **Benchmark Context**: See OpenView 2024 Product Benchmarks, and ProfitWell 2024 SaaS Benchmarks for current industry benchmarks relevant to this analysis.
## Output Contract

### Deliverable: Markdown Retention Report

```markdown
# Retention Analysis: [Product] — [Period]

## Executive Summary
- Overall retention: [Day 1 / Day 7 / Day 30 rates]
- Critical drop-off: [where]
- Top churn reason: [reason]
- Key recommendation: [action]

## Retention Curve
| Day | Users | Retention Rate | Benchmark |
|---|---|---|---|

## Cohort Analysis
| Cohort | Month 1 | Month 2 | Month 3 | Trend |
|---|---|---|---|---|

## Churn Patterns
| Pattern | % of Churners | Root Cause | Intervention |
|---|---|---|---|

## Health Score Model
| Signal | Weight | Threshold |
|---|---|---|

## Retention Strategy
### Immediate (This Sprint)
1. [Action]
### Short-Term (30 Days)
1. [Action]
### Long-Term (90 Days)
1. [Action]

## Win-Back Campaign
| Segment | Timing | Offer | Channel |
|---|---|---|---|
```

## Platform Implementation Steps

### Analytics (Mixpanel/Amplitude/PostHog)
1. Set up retention report with your activation event
2. Build cohort table grouped by signup week
3. Create behavioral segments: retained vs. churned
4. Compare feature usage between segments

### CRM (HubSpot/Salesforce)
1. Create "Health Score" custom property
2. Build workflow: health score < threshold → alert CSM
3. Create "At Risk" lifecycle stage with automated nurture
4. Track win-back campaign outcomes

### Email (Customer.io/Intercom)
1. Build re-engagement sequence triggered by inactivity
2. Create win-back campaigns for 30/60/90-day churned users
3. Design milestone celebration emails for retained users
4. Set up NPS survey at Day 30 and Day 90

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Retention didn't improve | Addressed symptom not cause | Dig deeper with user interviews; look at product issues |
| Re-engagement emails annoyed users | Too aggressive or irrelevant | Reduce frequency; personalize based on usage data |
| Health score has too many false positives | Thresholds too sensitive | Calibrate with historical churn data; add more signals |
| Win-back campaign low response | Wrong timing or weak offer | Test different intervals and offers; try personal outreach |

## How to Get Your Data

- **Mixpanel/Amplitude**: Retention report → export cohort data as CSV
- **Database query**: SELECT user_id, signup_date, last_active_date, event_count FROM users
- **Google Analytics**: Cohort Analysis report (limited but useful for web products)
- **No data**: Describe your product and share any metrics you know — Claude builds from benchmarks

## Example

**Input**: "Retention analysis for a fitness app. 50K monthly signups. Day 1: 45%, Day 7: 22%, Day 30: 8%. Most users drop off after completing onboarding but before establishing a workout habit. Subscription: $9.99/month."

**Output**: Critical drop-off: Day 1 to Day 7 (45% → 22%) — users who complete onboarding aren't forming a habit. Analysis: retained users log 3+ workouts in week 1; churned users average 0.8 workouts. Aha moment: completing 3rd workout. Strategy: (1) Day 1-3: push notification sequence with personalized workout suggestions, reduce first workout from 45 min to 15 min "starter" workout; (2) Day 3-7: habit hook — streak counter with daily reminders, social accountability feature (workout with a friend); (3) Day 7-14: introduce variety (new workout types) to prevent boredom; (4) At-risk (no workout in 5 days): "We miss you" push + 7-day free premium content unlock. Health score: workout frequency (40%), app opens (25%), content completion (20%), social features used (15%). Win-back: Day 30 email with "Your personalized comeback plan" + 50% off next month. Expected impact: Day 7 retention from 22% to 30-35%.

## Related Skills

- **[cohort-analysis-builder](../analytics/cohort-analysis-builder.md)** — Build cohort analyses to understand retention patterns by segment.
- **[onboarding-flow-optimizer](./onboarding-flow-optimizer.md)** — Optimize onboarding based on activation and early retention signals.
- **[customer-persona-builder](./customer-persona-builder.md)** — Segment retention by persona to identify highest-value users.
- **[growth-experiment-designer](./growth-experiment-designer.md)** — Design retention improvement experiments informed by churn analysis.
