---
name: cohort-analysis-builder
description: >
  Build cohort analyses to track user behavior, retention, and lifetime value over time.
  Use this skill when the user says "cohort analysis", "retention cohort", "user retention analysis",
  "customer cohort tracking", "cohort-based reporting", "week-over-week retention", "monthly cohort
  metrics", "LTV by acquisition cohort", "behavioral cohort segmentation", "churn cohort analysis",
  or "subscription cohort tracking". Also trigger for time-based user analysis, acquisition cohort
  comparison, or cohort retention curves.
---

# Cohort Analysis Builder

Builds cohort analyses to track user behavior, retention, revenue, and lifetime value over time — identifying which acquisition channels, time periods, or user segments produce the best long-term outcomes.

## Granularity Check

> **Time**: ~10 min data prep → ~15 min Claude session → ~30-60 min building in Google Sheets / Looker / GA4. If building automated cohort reports, add 1-2 weeks for implementation. Input is user-level data with timestamps (signup, activity, revenue). Output is Markdown cohort analysis framework with retention tables, visualization specs, and actionable insights.

## User Intent Mapping

- "Build a retention cohort analysis" (retention)
- "Which acquisition month has best retention?" (comparison)
- "Track user behavior over time" (behavioral)
- "LTV by signup cohort" (revenue)
- "Are our users getting stickier?" (trend)
- "Churn analysis by cohort" (churn)
- "Subscription retention by signup month" (subscription)
- "Compare free vs. paid user retention" (segment)
- "Product usage cohorts" (product)
- "Marketing cohort performance" (acquisition)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| User Data | CSV | Users with signup dates and activity/event timestamps |
| Cohort Definition | Text | How to group users (signup month, acquisition channel, plan type) |
| Analysis Goal | Text | What you want to learn (retention, revenue, engagement) |

### If You Don't Have This Data

- **No user-level data?** Claude shows you how to extract cohort data from GA4, Mixpanel, Amplitude, or your database — includes sample SQL queries.
- **Only aggregate data?** Claude builds approximate cohorts from monthly active user counts and shows you how to set up proper cohort tracking.
- **Small user base?** Claude recommends minimum cohort sizes (50+ users per cohort for retention analysis) and suggests weekly vs. monthly cohorts for faster insights.
- **No activity data?** Claude helps you define meaningful activity events and set up tracking — you can have cohort data within 30 days.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Revenue Data | CSV | Revenue per user over time |
| Channel Data | Text | Acquisition source per user |
| Segment Data | Text | User attributes (plan, industry, geography) |
| Product Events | CSV | Feature usage, milestones, actions |
| Benchmark Data | Text | Industry retention benchmarks |

## Process

### Step 1: Cohort Definition

| Cohort Type | Group By | Use Case |
|---|---|---|
| Acquisition cohort | Signup month/week | Standard retention analysis |
| Behavioral cohort | First action taken | Feature adoption impact |
| Channel cohort | Acquisition source | Channel quality comparison |
| Plan cohort | Subscription tier | Plan-based retention |
| Size cohort | Company size or user segment | Segment performance |
| Campaign cohort | Marketing campaign | Campaign long-term impact |

### Step 2: Retention Table Structure

| Cohort | Size | Month 0 | Month 1 | Month 2 | Month 3 | Month 6 | Month 12 |
|---|---|---|---|---|---|---|---|
| Jan 2026 | 500 | 100% | 45% | 35% | 30% | 22% | 15% |
| Feb 2026 | 550 | 100% | 48% | 38% | 33% | — | — |
| Mar 2026 | 600 | 100% | 52% | 42% | — | — | — |

Key metrics per cohort:
- **Initial retention** (Month 1): Activation quality
- **Stabilization point**: Where retention curve flattens
- **Long-term retention** (Month 6-12): Product stickiness
- **Cohort trend**: Are newer cohorts retaining better?

### Step 3: Analysis Dimensions

| Dimension | Question | Method |
|---|---|---|
| Time trend | Are newer cohorts retaining better? | Compare same-period retention across cohorts |
| Channel quality | Which channels produce sticky users? | Overlay cohorts by acquisition channel |
| Activation impact | Does completing onboarding improve retention? | Compare activated vs. non-activated within cohorts |
| Revenue per cohort | Which cohorts generate more lifetime revenue? | Cumulative revenue per user by cohort |
| Feature correlation | Which features predict retention? | Behavioral cohort analysis |
| Segment differences | Do enterprise users retain differently? | Segment overlay on retention curves |

### Step 4: Retention Curve Patterns

| Pattern | Shape | Meaning | Action |
|---|---|---|---|
| Steep early drop, then flat | L-curve | Normal — activation is the gate | Focus on onboarding and first-week experience |
| Gradual continuous decline | Linear decline | No habit formation | Find and promote the "aha moment" |
| Drop then recovery | Smile curve | Re-engagement working | Identify what triggers re-engagement |
| Flat from start | Horizontal | Strong product-market fit | Scale acquisition confidently |
| Accelerating decline | Concave down | Growing dissatisfaction | Urgent product/experience issues |

### Step 5: LTV Cohort Analysis

| Cohort | Users | Month 1 Rev | Month 3 Rev | Month 6 Rev | Month 12 Rev | LTV |
|---|---|---|---|---|---|---|
| Jan 2026 | 500 | $25K | $55K | $85K | $110K | $220/user |
| Feb 2026 | 550 | $28K | $62K | $95K | — | Projected: $240/user |

Calculate per cohort:
- **Revenue per user** at each interval
- **Cumulative revenue** per cohort
- **Payback period**: When cumulative revenue exceeds acquisition cost
- **Projected LTV**: Extrapolate using retention curve

### Step 6: Actionable Insights Framework

| Finding | So What | Now What |
|---|---|---|
| Month 1 retention improved 10% | Recent changes are working | Document what changed; maintain momentum |
| Organic cohorts retain 2x paid | Paid acquisition quality is lower | Improve paid targeting or landing experience |
| Users who complete setup retain 3x | Setup completion is critical | Invest in onboarding, reduce friction |
| Enterprise cohorts have 2x LTV | Enterprise segment is more valuable | Shift acquisition focus toward enterprise |

### Confidence & Sample Size

> **Confidence Note**: Cohort analysis requires at least 50 users per cohort for directionally useful retention data and 200+ for statistically reliable comparisons. Monthly cohorts need 6-12 months of data to show meaningful retention curves. Weekly cohorts give faster insights but smaller sample sizes — use for high-volume products. Retention improvements of less than 5 percentage points may be noise unless your cohort sizes are large (500+). Always compare same-age retention across cohorts (Month 3 vs. Month 3), never different-age retention within a cohort.

### ⚠️ Human Checkpoint
> Validate cohort definitions with your product and data teams — inconsistent user definitions will invalidate the entire analysis. Ensure your "active user" definition is meaningful (logged in ≠ engaged). Check for data quality issues like duplicate users, test accounts, or incomplete event tracking.

> **Benchmark Context**: Consult current industry reports for up-to-date benchmarks relevant to this analysis.

## Output Contract

### Deliverable: Markdown Cohort Analysis

```markdown
# Cohort Analysis: [Product/Service]

## Cohort Definition
- Type: [acquisition/behavioral/channel/segment]
- Grouping: [monthly/weekly]
- Activity definition: [what counts as "active"]
- Date range: [period analyzed]

## Retention Table
| Cohort | Size | M0 | M1 | M2 | M3 | M6 | M12 |
|---|---|---|---|---|---|---|---|

## Key Findings
| Finding | Impact | Confidence |
|---|---|---|

## Cohort Comparisons
| Dimension | Best Cohort | Worst Cohort | Delta | Implication |
|---|---|---|---|---|

## Retention Curve Analysis
- Pattern: [curve shape]
- Stabilization point: [month/week]
- Critical drop-off: [where biggest loss occurs]

## Revenue by Cohort (if applicable)
| Cohort | Cumulative Rev/User | Projected LTV | Payback Period |
|---|---|---|---|

## Recommendations
| Priority | Action | Expected Impact | Metric to Track |
|---|---|---|---|
```

## Platform Implementation Steps

### SQL-Based Cohort Query
1. Define cohort assignment query (user signup month)
2. Define activity query (what counts as active per period)
3. Join cohorts with activity to build retention matrix
4. Calculate retention percentages per cohort per period
5. Export to spreadsheet or BI tool for visualization

### Analytics Platform (Mixpanel / Amplitude)
1. Define "New User" event and cohort grouping (signup date)
2. Define "Return" event (what constitutes activity)
3. Build retention report with cohort grouping
4. Add breakdowns by channel, plan, or segment
5. Set up automated weekly cohort report

### Spreadsheet Approach
1. Export user data with signup date and activity dates
2. Assign cohort labels (signup month) to each user
3. Create pivot table: cohort rows × period columns
4. Calculate retention percentage per cell
5. Apply conditional formatting (heatmap colors)

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| All cohorts look the same | Cohorts too broad or activity definition too loose | Narrow cohort definition; tighten "active" criteria |
| Cohort sizes too small | Too many segments or too short time periods | Combine smaller segments; use monthly instead of weekly |
| Misleading improvement | Seasonal effect, not real improvement | Compare same calendar periods year-over-year |
| Data quality issues | Duplicate users, missing events, timezone mismatches | Audit data pipeline; reconcile user counts across systems |

## How to Get Your Data

- **SaaS / web app**: Database query → users table (signup date) + events table (activity dates)
- **Mixpanel / Amplitude**: Built-in retention reports → export CSV
- **GA4**: Explore → Cohort exploration → export
- **Spreadsheet**: User list with signup dates + monthly login/activity dates
- **No data yet**: Describe your product — Claude designs a cohort tracking plan and provides benchmark retention curves for your category

## Example

**Input**: "Cohort analysis for our project management SaaS. Monthly acquisition cohorts for Jan-Jun 2026. Data: Jan (450 users, M1: 42%, M3: 28%, M6: 18%), Feb (520, M1: 44%, M3: 30%), Mar (480, M1: 48%, M3: 35%), Apr (550, M1: 51%), May (600, M1: 50%), Jun (580, M1: 52%). We launched new onboarding in March."

**Output**: Clear finding: new onboarding (March) created a measurable retention improvement. Pre-onboarding cohorts (Jan-Feb): M1 average 43%. Post-onboarding cohorts (Mar-Jun): M1 average 50.3% — a 7-point improvement. Month 3 also improved: Jan 28% → Mar 35% (7-point lift). Analysis: (1) The onboarding change is working — 7-point M1 lift is significant across 4 cohorts (2,210 users). (2) Projecting Mar cohort forward: if the M1→M3 ratio holds (48%→35% = 73% of M1 retained), Jun cohort should hit M3: 38% — which would be your best ever. (3) M6 retention at 18% for Jan cohort is below SaaS benchmark (20-25%) — the onboarding fix may help but monitor M6 for newer cohorts. Recommendations: (1) Keep current onboarding — it's working. (2) Now focus on M1→M3 drop (50% to ~35%): identify what makes users churn in months 2-3 and build engagement triggers. (3) Track M6 for Mar cohort (data available September) to confirm onboarding impact persists. (4) Break cohorts by channel to see if the onboarding improvement is uniform or channel-dependent.

## Related Skills

- **[ab-test-result-analyzer](./ab-test-result-analyzer.md)** — Use after cohort analysis to validate retention improvements with statistical testing.
- **[retention-analysis-framework](../growth/retention-analysis-framework.md)** — Complements cohort analysis to identify churn patterns and design retention strategies.
- **[marketing-roi-calculator](./marketing-roi-calculator.md)** — Analyze cohort value and LTV per acquisition cohort to optimize marketing ROI.
- **[customer-persona-builder](../growth/customer-persona-builder.md)** — Segment cohorts by persona to understand which customer types retain best.
