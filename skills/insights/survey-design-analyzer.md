---
name: survey-design-analyzer
description: >
  Design, review, and optimize marketing surveys for higher response rates and actionable insights.
  Use this skill when the user says "survey design", "marketing survey optimization", "customer survey
  best practices", "NPS survey design", "CSAT survey setup", "survey question review", "survey response
  rate optimization", "post-purchase survey design", "brand perception survey", "market research survey",
  or "survey analysis framework". Also trigger for questionnaire design, survey bias detection, or
  survey results interpretation.
---

# Survey Design & Analyzer

Designs, reviews, and optimizes marketing surveys for higher response rates, reduced bias, and actionable insights that drive marketing decisions.

## Granularity Check

> **Time**: ~5 min data prep → ~10 min Claude session → ~30-60 min synthesizing into your strategy deck. If implementing, add 2-4 hours for survey build and testing. Input is survey goals and draft questions. Output is Markdown survey design with optimized questions and analysis framework.

## User Intent Mapping

- "Design a customer satisfaction survey" (CSAT)
- "Review our survey questions for bias" (review)
- "NPS survey best practices" (NPS)
- "Post-purchase survey design" (transactional)
- "Brand perception survey" (brand)
- "Market research questionnaire" (research)
- "Our survey response rate is too low" (optimization)
- "How to analyze survey results" (analysis)
- "Survey is too long — what to cut?" (simplification)
- "A/B test our survey" (testing)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Survey Goal | Text | What decisions this survey will inform |
| Target Audience | Text | Who you're surveying |
| Survey Type | Text | NPS, CSAT, brand, product, market research |

### If You Don't Have This Data

- **No survey draft?** Claude designs the full survey from scratch based on your goals — questions, flow, logic, and distribution plan.
- **No past survey data?** Claude creates a baseline survey with benchmarks to establish your starting metrics.
- **Not sure what to ask?** Claude maps your business questions to survey questions that will actually answer them.
- **Low response rates?** Claude audits your survey length, question types, distribution timing, and incentive strategy.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Draft Questions | Text | Current or planned survey questions |
| Past Responses | CSV | Previous survey results |
| Response Rate | Text | Current response rate |
| Survey Tool | Text | Platform used (Typeform, SurveyMonkey, Google Forms) |
| Audience Size | Text | How many people will receive the survey |

## Process

### Step 1: Survey Goal Mapping
| Business Question | Survey Question Type | Analysis Method |
|---|---|---|
| How satisfied are customers? | NPS/CSAT scale | Score distribution, trend |
| Why do customers churn? | Multiple choice + open text | Theme analysis, coding |
| What features matter most? | Ranking or MaxDiff | Priority matrix |
| How is our brand perceived? | Semantic differential scales | Perception map |
| What's our market position? | Aided/unaided awareness | Share of mind |
| Where to invest next? | Conjoint/choice-based | Willingness to pay |

### Step 2: Question Design Rules
- **One concept per question** (double-barreled questions produce unusable data)
- **Neutral wording** (avoid leading: "How great is our product?" → "How would you rate our product?")
- **Specific timeframe** ("In the last 30 days" vs. "recently")
- **Exhaustive options** (include "Other" and "N/A" where appropriate)
- **Logical flow** (broad → specific, easy → hard, factual → opinion)
- **Consistent scales** (don't switch between 5-point, 7-point, and 10-point)

### Step 3: Response Rate Optimization
| Factor | Best Practice | Impact |
|---|---|---|
| Length | 5-10 questions (3-5 min completion) | -20% response per minute over 5 min |
| Subject line | Personalized, specific, value-focused | +30-50% open rate |
| Timing | Tuesday-Thursday, 10am-2pm local | +15-20% response |
| Incentive | Appropriate to audience (gift card, results access) | +10-30% response |
| Progress bar | Show completion percentage | +10-15% completion |
| Mobile-optimized | Single-column, large tap targets | +20-30% mobile completion |
| Sender | From a person, not "noreply@" | +15-25% open rate |

### Step 4: Bias Detection
| Bias Type | Example | Fix |
|---|---|---|
| Leading question | "How amazing was your experience?" | "How would you rate your experience?" |
| Acquiescence bias | All agree/disagree scales | Mix positive and negative statements |
| Social desirability | "Do you read industry publications?" | Frame as behavior, not virtue |
| Order effect | First option chosen more often | Randomize option order |
| Anchoring | "Most customers rate us 9/10" before question | Remove anchoring context |
| Recall bias | "How many times did you visit last year?" | Shorter timeframes or recent behavior |
| Survivorship bias | Only surveying active customers | Include churned/inactive customers |

### Step 5: Survey Flow Design
1. Welcome screen with purpose, time estimate, privacy note
2. Screening questions (if needed to qualify respondents)
3. Easy, factual questions first (warm-up)
4. Core measurement questions (NPS, CSAT, key metrics)
5. Deeper diagnostic questions (why, what, how)
6. Open-ended questions (limit to 1-2)
7. Demographics (at end, optional)
8. Thank you screen with next steps

### Step 6: Analysis Framework
| Data Type | Analysis Method | Output |
|---|---|---|
| NPS scores | Score calculation, segment breakdown | NPS score, promoter/detractor ratio |
| CSAT ratings | Mean, distribution, trend | Satisfaction trend line |
| Multiple choice | Frequency analysis, cross-tabs | Priority rankings |
| Open text | Theme coding, sentiment analysis | Theme frequency, quotes |
| Rankings | Average rank, top-box analysis | Priority matrix |
| Scales | Mean, standard deviation, correlation | Relationship mapping |

### Confidence & Sample Size

> **Confidence Note**: For 95% confidence at ±5% margin of error, you need ~385 responses from a large population. Smaller populations need fewer: 100 people → need 80 responses, 500 people → need 217 responses. NPS requires 200+ responses for stability. Open-ended questions provide rich data but need 50+ responses for reliable theme analysis. Response rates vary: email surveys average 10-30%, in-app surveys average 30-50%, post-interaction surveys average 40-60%.

### ⚠️ Human Checkpoint
> Pilot survey with 5-10 people before full launch to catch confusing questions. Review open-ended responses for unintended interpretations. Ensure survey complies with data privacy regulations (GDPR consent for EU respondents).

> **Benchmark Context**: Average email survey response rate is 10-30% (McKinsey 2024 State of AI Report) Every question added beyond 10 drops completion by 5-10%. . Personalized survey invitations increase response rates by 48% (Gartner 2024 Marketing Technology Survey) Mobile-optimized surveys see 30% higher completion (McKinsey 2024 State of AI Report) Surveys sent within 24 hours of an interaction get 2-3x higher response rates (McKinsey 2024 State of AI Report) (Gartner 2024 Marketing Technology Survey).
## Output Contract

### Deliverable: Markdown Survey Design

```markdown
# Survey Design: [Name/Purpose]

## Survey Overview
- Goal: [what decisions this informs]
- Audience: [who, how many]
- Type: [NPS/CSAT/brand/research]
- Length: [questions, estimated minutes]
- Distribution: [channel, timing]

## Questions
### Q1: [Question text]
- Type: [scale/MC/open/ranking]
- Options: [if applicable]
- Logic: [skip logic if applicable]
- Purpose: [what this measures]

[Repeat for each question]

## Distribution Plan
| Channel | Audience Segment | Timing | Expected Response Rate |
|---|---|---|---|

## Analysis Plan
| Question | Metric | Benchmark | Action Trigger |
|---|---|---|---|

## Sample Size Requirements
- Target responses: [number]
- Confidence level: [95%]
- Margin of error: [±X%]
```

## Platform Implementation Steps

### Survey Tools
1. Build survey in platform (Typeform, SurveyMonkey, Google Forms, Qualtrics)
2. Set up skip logic and conditional branching
3. Enable response randomization for multiple-choice options
4. Configure progress bar and mobile-responsive layout
5. Test on desktop, mobile, and tablet before launch

### Distribution
1. Segment audience by survey relevance
2. Schedule email invitations with personalized subject lines
3. Set up reminder sequence (Day 3 and Day 7 after initial send)
4. For in-app surveys: trigger based on user action or session count
5. Monitor response rate daily and adjust distribution if below target

### Analysis
1. Export responses to spreadsheet or analytics tool
2. Calculate headline metrics (NPS score, CSAT average, response rate)
3. Segment results by customer type, plan, tenure, etc.
4. Code open-ended responses into themes (manually or with AI)
5. Create summary report with key findings and recommended actions

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Low response rate (<10%) | Too long, wrong timing, no incentive | Shorten to 5 questions; test new send times; add incentive |
| Biased results | Leading questions or self-selection bias | Review for bias; compare respondent demographics to full population |
| Data not actionable | Questions too vague or not tied to decisions | Redesign questions to directly inform specific business decisions |
| Survey fatigue | Surveying too frequently | Limit to quarterly for long surveys; use micro-surveys for ongoing |

## How to Get Your Data

- **Survey results**: Export from survey platform (CSV or dashboard)
- **Response rates**: Survey platform → campaign analytics
- **Benchmarks**: Industry benchmarks from platform providers (SurveyMonkey, Qualtrics)
- **No survey yet**: Describe your goals and audience — Claude designs the full survey from scratch

## Example

**Input**: "Design a post-purchase NPS survey for our SaaS product. 5,000 active users. Currently no survey in place. Want to measure satisfaction and identify churn risks. Using Typeform."

**Output**: Survey design (6 questions, ~2 minutes): Q1 — NPS: "How likely are you to recommend [Product] to a colleague?" (0-10 scale). Q2 — Open text: "What's the primary reason for your score?" Q3 — CSAT: "How satisfied are you with [Product] overall?" (1-5 stars). Q4 — Feature value: "Which feature is most valuable to you?" (multiple choice: top 5 features + other). Q5 — Improvement: "What one thing would you improve?" (open text). Q6 — Usage frequency: "How often do you use [Product]?" (daily/weekly/monthly/rarely). Distribution: in-app trigger after 30 days of use, then quarterly. Email follow-up for non-respondents at Day 3 and Day 7. Expected response rate: 25-35% (in-app), 15-20% (email). Sample size: need 357 responses for 95% confidence at ±5%. At 25% response rate, survey 1,400+ users per wave. Analysis plan: segment NPS by usage frequency, feature preference, and tenure. Detractor responses flagged to customer success team within 24 hours for follow-up.

## Related Skills

- **[Voice of Customer Miner](./voice-of-customer-miner.md)** — Complement surveys with open-ended Reddit data mining for deeper customer insights.
- **[Audience Persona Builder](./audience-persona-builder.md)** — Use survey data to validate and refine audience personas.
- **[Market Trend Scanner](./market-trend-scanner.md)** — Design surveys to test hypothesized market trends.
- **[NPS Survey Design](../analytics/dashboard-requirement-gatherer.md)** — Use this skill to design effective NPS and customer satisfaction surveys.
