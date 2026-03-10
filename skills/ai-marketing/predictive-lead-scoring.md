---
name: predictive-lead-scoring
description: >
  Build predictive lead scoring models using behavioral and firmographic data for sales prioritization.
  Use this skill when the user says "predictive lead scoring", "lead scoring model", "AI lead
  scoring", "lead prioritization model", "predictive scoring for sales", "lead quality scoring",
  "behavioral lead scoring", "firmographic scoring model", "lead score optimization", "MQL scoring
  criteria", or "which leads to prioritize". Also trigger for lead scoring recalibration,
  intent-based scoring, or scoring model accuracy improvement.
---

# Predictive Lead Scoring

Builds predictive lead scoring models combining behavioral signals, firmographic data, and intent indicators to prioritize leads for sales teams and optimize marketing-to-sales handoff.

## Granularity Check

> **Session time**: ~10 min data prep + ~15 min Claude session. If implementing in CRM, add 1-2 weeks. Input is lead data, conversion history, and sales feedback. Output is Markdown scoring model with rules and implementation plan.

## User Intent Mapping

- "Build a lead scoring model" (new model)
- "Our lead scoring isn't working" (optimization)
- "Which leads should sales focus on?" (prioritization)
- "Predictive scoring for our funnel" (predictive)
- "Lead scoring criteria for our CRM" (CRM setup)
- "MQL definition and scoring" (MQL)
- "Behavioral vs. firmographic scoring" (model design)
- "Lead score recalibration" (recalibration)
- "Intent-based lead scoring" (intent)
- "Lead scoring for product-led growth" (PLG)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Lead Data | CSV/Text | Attributes collected on leads (company size, title, etc.) |
| Conversion History | CSV/Text | Which leads converted to opportunities/customers |
| Sales Process | Text | How leads move from marketing to sales to close |

### If You Don't Have This Data

- **No conversion data?** Claude builds a rule-based scoring model from best practices and your ICP definition. Track conversions for 90 days, then calibrate.
- **Limited lead attributes?** Claude maximizes the signals you have and recommends additional data collection.
- **No current scoring?** Claude designs a scoring model from scratch based on your business type and sales process.
- **Small dataset?** Claude uses rule-based scoring (not statistical) until you have 200+ conversions to train a predictive model.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| ICP Definition | Text | Ideal customer profile attributes |
| Sales Feedback | Text | What sales says about lead quality |
| Product Usage | CSV | Feature adoption, login frequency (for PLG) |
| Intent Data | CSV | Third-party intent signals |
| Win/Loss Data | CSV | Why deals were won or lost |

## Process

### Step 1: Scoring Dimensions
| Dimension | Weight | Signals | Score Range |
|---|---|---|---|
| Firmographic fit | 30% | Company size, industry, revenue, location | 0-30 pts |
| Demographic fit | 20% | Title, role, seniority, department | 0-20 pts |
| Behavioral engagement | 35% | Content downloads, page visits, email engagement | 0-35 pts |
| Intent signals | 15% | Third-party intent, search behavior, product trials | 0-15 pts |

### Step 2: Firmographic Scoring Rules
| Attribute | Ideal (max pts) | Good (mid pts) | Poor (low pts) |
|---|---|---|---|
| Company size | [ICP match] | [Adjacent] | [Non-ICP] |
| Industry | [Target industries] | [Related] | [Non-target] |
| Revenue | [ICP range] | [Adjacent range] | [Too small/too large] |
| Geography | [Target markets] | [Secondary markets] | [Non-serviceable] |

### Step 3: Behavioral Scoring Rules
| Action | Points | Decay | Rationale |
|---|---|---|---|
| Visited pricing page | +15 | 14 days | High purchase intent |
| Downloaded case study | +10 | 30 days | Evaluation stage |
| Attended webinar | +10 | 30 days | Topic engagement |
| Opened 3+ emails | +5 | 14 days | Active engagement |
| Visited careers page | -10 | Never | Job seeker, not buyer |
| Unsubscribed | -20 | Never | Disengaged |

### Step 4: Lead Grade Classification
| Score Range | Grade | Action | SLA |
|---|---|---|---|
| 80-100 | A (Hot) | Immediate sales outreach | < 1 hour |
| 60-79 | B (Warm) | Sales qualified, schedule call | < 24 hours |
| 40-59 | C (Nurture) | Marketing nurture sequence | Automated |
| 20-39 | D (Early) | Educational content | Automated |
| 0-19 | F (Unqualified) | Suppress from sales | None |

### Step 5: Model Validation
- Back-test against historical conversions (does high score = high conversion?)
- Calculate precision: what % of A-leads actually convert?
- Calculate recall: what % of actual conversions were scored A/B?
- Compare to random assignment (does scoring outperform random?)
- A/B test: sales team works scored leads vs. unscored — compare conversion rates

### Step 6: Ongoing Calibration
- Monthly review: sales acceptance rate by score grade
- Quarterly: recalculate point values based on actual conversion correlation
- Bi-annual: full model rebuild with updated conversion data
- Continuous: adjust for new lead sources, product changes, market shifts

### Confidence & Sample Size

> **Confidence Note**: Rule-based scoring models are effective starting points but require calibration with real conversion data. Predictive models need 200+ conversions to train reliably. Lead scores decay — a lead who was hot 6 months ago may not be today. The biggest risk is scoring on vanity signals (newsletter opens) vs. buying signals (pricing page visits). Sales feedback is essential — if sales rejects high-scored leads, the model needs adjustment.

### ⚠️ Human Checkpoint
> Validate scoring model with sales team before go-live. Review scoring rules quarterly against actual conversion data. Ensure scoring doesn't introduce bias (geographic, company size, or demographic biases that exclude good leads).

> **Benchmark Context**: Companies with lead scoring see 77% lift in lead generation ROI. Sales teams using lead scoring spend 30% less time on unqualified leads. Predictive scoring models outperform rule-based by 25-40% when sufficient training data exists. Only 44% of companies use lead scoring despite its proven impact. Companies that align scoring with sales feedback see 20% higher win rates.

## Output Contract

### Deliverable: Markdown Lead Scoring Model

```markdown
# Lead Scoring Model: [Company]

## Scoring Dimensions
| Dimension | Weight | Max Points |
|---|---|---|

## Firmographic Rules
| Attribute | Criteria | Points |
|---|---|---|

## Behavioral Rules
| Action | Points | Decay |
|---|---|---|

## Negative Scoring
| Signal | Points | Rationale |
|---|---|---|

## Grade Thresholds
| Grade | Score Range | Action | SLA |
|---|---|---|---|

## MQL Definition
- Criteria: [definition]
- Handoff process: [steps]

## Validation Plan
| Test | Method | Success Criteria |
|---|---|---|

## Calibration Schedule
| Frequency | Review | Owner |
|---|---|---|
```

## Platform Implementation Steps

### HubSpot
1. Properties → create custom score property
2. Workflows → build scoring automation (add/subtract points per trigger)
3. Lists → create smart lists for each lead grade
4. Dashboards → lead score distribution and conversion by grade

### Salesforce
1. Setup → Lead Scoring Rules or Einstein Lead Scoring
2. Create score fields and workflow rules for point assignment
3. Set up lead assignment rules based on score thresholds
4. Build reports comparing conversion rates by score grade

### Marketo
1. Admin → Scoring → create scoring program
2. Smart campaigns → trigger point changes on behavioral events
3. Revenue Cycle Modeler → map scores to lifecycle stages
4. Analytics → lead score distribution and conversion reporting

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Sales ignores scores | Model doesn't match sales experience | Recalibrate with sales input; show conversion data by grade |
| Too many A-leads | Thresholds too low; too many high-point actions | Raise thresholds; reduce points for low-intent actions |
| Good leads scored low | Missing key signals in model | Add new behavioral triggers; check data collection gaps |
| Score inflation over time | Points accumulate without decay | Implement score decay; reset scores after extended inactivity |

## How to Get Your Data

- **Lead data**: CRM → export leads with attributes and lifecycle stage
- **Conversion data**: CRM → closed-won opportunities with original lead source and attributes
- **Behavioral data**: Marketing automation → engagement history per lead
- **No CRM data**: Describe your ICP and sales process — Claude builds a rule-based starter model

## Example

**Input**: "Build lead scoring model. B2B SaaS, $5K-50K ACV. ICP: 50-500 employees, tech/SaaS/fintech, VP+ in marketing or growth. Using HubSpot. 500 leads/month, 15% MQL rate, 5% close rate. Sales says too many unqualified MQLs."

**Output**: New scoring model (100-point scale): Firmographic (30 pts max): company size 50-500 = 15 pts, 500-2000 = 10 pts, <50 = 0 pts. Industry match = 10 pts. Revenue $5M-100M = 5 pts. Demographic (20 pts): VP/Director/C-level = 20 pts, Manager = 10 pts, Individual contributor = 0 pts. Marketing/Growth department = bonus 5 pts. Behavioral (35 pts): pricing page visit = 15 pts, demo request form = 20 pts (auto-MQL), case study download = 10 pts, 3+ blog visits in 7 days = 5 pts, email click = 3 pts (max 9 pts from emails). Intent (15 pts): free trial signup = 15 pts (auto-MQL), product comparison page = 10 pts, competitor keyword search = 5 pts. Negative: careers page = -10, student email = -20, competitor company = -30. Grades: A (75+) = immediate SDR outreach, B (55-74) = SDR within 24h, C (35-54) = nurture, D (<35) = no sales action. Expected result: MQL volume drops 30% but MQL-to-SQL conversion doubles from 20% to 40%.
