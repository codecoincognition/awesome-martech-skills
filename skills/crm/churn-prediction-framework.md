---
name: churn-prediction-framework
description: >
  Identify at-risk customers and design retention strategies using CRM engagement and usage data signals.
  Use this skill when the user says "churn prediction", "customer retention strategy", "at-risk customer
  identification", "churn risk scoring", "customer health score", "retention campaign design",
  "reduce churn rate", "customer attrition analysis", "early warning churn signals", "customer
  health monitoring", or "win-back campaign strategy". Also trigger for customer success scoring,
  renewal risk assessment, or proactive retention playbook design.
---

> **How this skill works:** You export your CRM or customer data (HubSpot, Salesforce, or any platform) as a CSV with customer activity history, and Claude analyzes it to identify churn risk patterns. Claude cannot connect to live platforms or pull data directly — you bring the data, Claude brings the predictive analysis.

# Churn Prediction Framework

Identifies at-risk customers using engagement, usage, and behavioral signals, then designs proactive retention strategies to reduce churn.

## Granularity Check

> **Session time**: ~10 min data prep + ~15 min Claude session. If implementing, add 1-2 weeks for scoring setup and automation. Input is customer data, usage metrics, and churn history. Output is Markdown churn prediction model with health scores and retention playbooks.

## User Intent Mapping

- "How to predict which customers will churn" (prediction)
- "Our churn rate is too high" (reduction)
- "Customer health score setup" (health scoring)
- "At-risk customer identification" (risk ID)
- "Retention campaign for at-risk customers" (campaigns)
- "Win-back strategy for churned customers" (win-back)
- "Early warning signals for churn" (signals)
- "Customer success playbook" (playbook)
- "Renewal risk assessment" (renewal)
- "Reduce customer attrition" (attrition)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Customer Data | CSV/Text | Customer list with engagement/usage metrics |
| Churn Definition | Text | What counts as churn (cancellation, non-renewal, inactivity) |
| Current Churn Rate | Text | Monthly or annual churn rate |

### If You Don't Have This Data

- **No usage data?** Claude designs a health score using CRM engagement signals (email opens, support tickets, login frequency) as proxies.
- **Don't know churn rate?** Claude helps calculate it from your CRM data and establishes a baseline.
- **No historical churn data?** Claude builds a rule-based prediction model from known risk factors and recommends data collection for future predictive modeling.
- **Can't track product usage?** Claude focuses on relationship signals (communication frequency, support interactions, NPS scores) as churn predictors.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Product Usage Data | CSV | Feature adoption, login frequency, DAU/MAU |
| Support History | CSV | Ticket volume, sentiment, resolution time |
| NPS/CSAT Scores | CSV | Customer satisfaction scores over time |
| Contract Data | CSV | Contract value, renewal dates, terms |
| Churned Customer Data | CSV | Characteristics of customers who already churned |

## Process

### Step 1: Churn Signal Identification
| Signal Category | Indicator | Risk Level |
|---|---|---|
| Usage decline | 30%+ drop in usage over 30 days | High |
| Feature abandonment | Stopped using core feature | High |
| Support escalation | 3+ negative support tickets in 30 days | High |
| NPS drop | Score dropped 3+ points | Medium-High |
| Engagement decline | No email opens, no login in 14+ days | Medium |
| Payment issues | Failed payment, late invoice | Medium |
| Champion departure | Primary contact left the company | High |
| Contract nearing end | <90 days to renewal, no expansion discussions | Medium |
| Competitor activity | Visiting competitor sites, asking about alternatives | High |

### Step 2: Health Score Model
| Component | Weight | Scoring |
|---|---|---|
| Product usage | 30% | Login frequency, feature adoption, depth of use |
| Engagement | 25% | Email opens, event attendance, content consumption |
| Support health | 20% | Ticket volume trend, sentiment, response satisfaction |
| Relationship | 15% | NPS/CSAT trend, champion engagement, executive sponsor |
| Financial | 10% | Payment history, expansion signals, contract value trend |

Score ranges:
- **90-100**: Healthy — potential advocate
- **70-89**: Stable — maintain engagement
- **50-69**: At risk — proactive outreach needed
- **30-49**: High risk — escalated intervention
- **0-29**: Critical — executive involvement needed

### Step 3: Retention Playbooks
| Health Score | Playbook | Owner | Timeline |
|---|---|---|---|
| 70-89 (stable) | Quarterly business review, share product roadmap | CSM | Ongoing |
| 50-69 (at risk) | Proactive outreach, usage training, value reinforcement | CSM | Within 7 days |
| 30-49 (high risk) | Executive sponsor call, custom success plan, concessions if needed | CS Manager | Within 48 hours |
| 0-29 (critical) | VP/C-level intervention, retention offer, escalation path | CS Leadership | Within 24 hours |

### Step 4: Automated Interventions
| Trigger | Automated Action | Human Follow-Up |
|---|---|---|
| Usage drops 30% in 7 days | In-app message: "Need help?" + CSM alert | CSM call within 48 hours |
| No login for 14 days | Re-engagement email with value reminder | CSM email with check-in |
| NPS detractor (0-6) | Thank you + immediate CSM notification | CSM call within 24 hours |
| Support ticket unresolved 48h+ | Escalation to support manager | CSM follow-up post-resolution |
| 90 days before renewal | Renewal prep email to CSM with account health | CSM initiates renewal conversation |

### Step 5: Win-Back Strategy
For churned customers:
| Timing | Action | Message |
|---|---|---|
| Day 1 (churn) | Exit survey email | "We'd love to learn how we can improve" |
| Day 30 | Check-in email | "Here's what's new since you left" |
| Day 60 | Value reminder | Share new feature/improvement addressing their reason |
| Day 90 | Win-back offer | Special pricing or trial of new features |
| Day 180 | Final attempt | "We've changed — here's how" with social proof |

### Step 6: Churn Analysis & Prevention
- Analyze churned customers for common patterns (industry, size, onboarding quality, usage depth)
- Identify "time bombs" — accounts with patterns matching churned customers
- Build prevention into onboarding (first 90 days are highest risk)
- Track leading indicators monthly, not just lagging churn rate

### Confidence & Sample Size

> **Confidence Note**: Predictive churn models need 100+ churn events in your dataset to identify reliable patterns. Rule-based models (health scores) work with smaller datasets but require regular calibration. The best churn predictor is product usage decline — if you don't track usage, start immediately. Health scores should be validated against actual churn every quarter. False positives (flagging healthy customers as at-risk) waste CSM time but are less costly than false negatives (missing actual churn risk).

### ⚠️ Human Checkpoint
> Validate health scores with CSM team — they often have qualitative insights that data misses (e.g., "this customer is fine, they're just on vacation"). Review retention offers with finance — retention discounts affect margins. Ensure win-back campaigns comply with opt-out preferences.

> **Benchmark Context**: It costs 5-7x more to acquire a new customer than to retain an existing one. A 5% increase in retention increases profits by 25-95%. Companies with proactive churn prediction reduce churn by 10-30%. Average SaaS monthly churn: 3-8% for SMB, 1-2% for enterprise. 67% of churn is preventable with proactive intervention. Customers who receive proactive outreach during at-risk periods retain at 2x the rate of those who don't.

## Output Contract

### Deliverable: Markdown Churn Prediction Plan

```markdown
# Churn Prediction & Retention: [Company]

## Current State
- Churn rate: [current]
- Churn definition: [what counts as churn]
- Data available: [signals we can track]

## Health Score Model
| Component | Weight | Signals | Scoring |
|---|---|---|---|

## Risk Segments
| Segment | Health Score | Count | % of Base | Action |
|---|---|---|---|---|

## Churn Signals
| Signal | Detection Method | Risk Level | Response |
|---|---|---|---|

## Retention Playbooks
### [Risk Level]
- Trigger: [what activates]
- Actions: [step by step]
- Owner: [who]
- Timeline: [when]
- Escalation: [if not resolved]

## Automation Rules
| Trigger | Automated Action | Human Follow-Up |
|---|---|---|

## Win-Back Strategy
| Timing | Action | Expected Win-Back Rate |
|---|---|---|

## Measurement
| Metric | Baseline | Target | Timeline |
|---|---|---|---|
```

## Platform Implementation Steps

### CRM Setup
1. Create custom "Health Score" property on contact/company records
2. Build automated health score calculation (workflow or integration)
3. Create views/segments for each risk tier
4. Set up automated alerts for health score changes
5. Build health score dashboard for CS team

### Customer Success Platform
1. Configure health score in Gainsight, ChurnZero, Totango, or Vitally
2. Connect product usage data (Segment, Mixpanel, or direct integration)
3. Set up automated playbook triggers
4. Configure risk alerts and escalation rules
5. Build renewal forecast based on health scores

### Email/Marketing Automation
1. Create re-engagement sequences for declining engagement
2. Build win-back email campaigns with timing rules
3. Set up NPS detractor response automation
4. Configure usage milestone celebration emails
5. Design renewal reminder sequences

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Health score doesn't predict churn | Wrong signals or weights | Back-test against historical churn; adjust weights quarterly |
| CSMs overwhelmed by alerts | Too many false positives or low threshold | Raise alert threshold; focus on high-risk only |
| Retention offers too generous | Giving discounts to customers who would have stayed | Segment by actual risk; only offer to truly at-risk |
| Win-back doesn't work | Reaching out too late or with wrong message | Address original churn reason; personalize offer |

## How to Get Your Data

- **Usage data**: Product analytics (Mixpanel, Amplitude, Pendo) → export user activity
- **CRM engagement**: CRM → contact activity → email opens, meeting history, support tickets
- **Churn history**: CRM → closed-lost/cancelled accounts → export with dates and reasons
- **NPS/CSAT**: Survey tool → export scores by customer with dates
- **No data**: Describe your business model and customer base — Claude designs a rule-based health score from available signals

## Example

**Input**: "Churn prediction for our SaaS. 500 customers, $200/month average. Monthly churn: 5% (25 customers/month). We track: login frequency, feature usage, support tickets, email engagement. No health score currently. Using HubSpot CRM."

**Output**: 5% monthly churn = 46% annual churn — critical. Estimated annual revenue loss: $300K. Health score model: Usage (35% weight): login frequency + feature count + depth of use. Engagement (25%): email opens, event attendance, NPS responses. Support (25%): ticket volume, sentiment, resolution satisfaction. Financial (15%): payment on time, upgrade/downgrade history. Implementation: (1) HubSpot calculated property for health score (0-100). (2) Risk segments: Green (80-100, ~200 customers), Yellow (60-79, ~150 customers), Orange (40-59, ~100 customers), Red (0-39, ~50 customers). (3) Automated interventions: Red score → CSM alert within 24 hours + executive sponsor notification. Orange → CSM outreach within 1 week + usage training offer. Yellow → automated re-engagement email. (4) Expected impact: reducing churn from 5% to 3.5% saves ~$90K/year in lost revenue. Target: intervene with 80% of at-risk customers before they cancel.
