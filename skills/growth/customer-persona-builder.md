---
name: Customer Persona Builder
description: "Build detailed buyer personas in minutes. Need to understand your ideal customer? Want to create marketing personas from research? Have survey data but don't know how to synthesize it? Need buyer journey mapping? Creating customer psychographics from interviews? Building personas for different market segments? Want to identify customer objections and pain points? Need messaging angles for different audience segments? Create personas from analytics data? Developing targeting criteria for campaigns? This skill transforms survey data, interviews, analytics, and research into rich, actionable buyer personas with demographics, psychographics, pain points, goals, buying journeys, and messaging strategies."
---

## User Intent Mapping

| User Says | Underlying Need |
|-----------|-----------------|
| "Build a persona from our survey" | Synthesize survey data into persona format |
| "What does our customer look like?" | Demographics + psychographics summary |
| "Turn interview notes into personas" | Parse qualitative data into structured format |
| "Create personas from our analytics" | Extract audience segments from audience data |
| "I need 3 buyer personas" | Multiple persona generation and segmentation |
| "What are customer pain points?" | Pain point extraction and prioritization |
| "Build personas for our new market" | Persona creation from minimal data with inference |
| "How do customers buy from us?" | Buying journey and decision-making process |
| "What messaging resonates?" | Messaging angle and language preference extraction |
| "Identify customer objections" | Common objections and how to overcome them |

## Input Contract

**Option 1: Survey Data CSV**
| Column | Type | Description | Example |
|--------|------|-------------|---------|
| `respondent_id` | text | Unique identifier | "R001" |
| `age_range` | text | Age bracket | "25-34" |
| `job_title` | text | Current role | "Marketing Manager" |
| `company_size` | text | Company employees | "11-50" |
| `industry` | text | Industry vertical | "SaaS" |
| `pain_point` | text | Main challenge | "Lead generation takes 40% of time" |
| `goal` | text | Primary objective | "Automate lead qualification" |
| `buying_timeline` | text | Purchase timeline | "3-6 months" |
| `budget_range` | text | Budget authority | "$5k-$25k" |
| `preferred_channel` | text | How they research | "LinkedIn, YouTube, G2" |
| `objection` | text | Concern/barrier | "Needs third-party integration" |

**Option 2: Interview Notes (Text)**
- Paste or upload unstructured interview transcripts
- Can be bullet points, Q&A format, or narrative
- Minimum 3 interviews recommended per persona

**Option 3: Analytics Data CSV**
| Column | Type | Example |
|--------|------|---------|
| `segment_name` | text | "Mid-market SaaS" |
| `audience_size` | number | 15000 |
| `avg_age` | number | 38 |
| `top_interests` | text | "Marketing automation, AI tools" |
| `device_preference` | text | "Mobile + Desktop" |
| `engagement_rate` | number | 0.045 |

**Validation Rules:**
- At least 5 respondents for survey-based personas
- At least 3 interviews for interview-based personas
- All core fields (age, role, pain point) populated
- Text fields non-empty and >10 characters
- Numbers positive and realistic

**Sample Survey Input (5 respondents):**
```csv
respondent_id,age_range,job_title,company_size,industry,pain_point,goal,buying_timeline,budget_range,preferred_channel,objection
R001,35-44,VP Marketing,51-200,SaaS,Attribution across channels,Unified reporting,6-9 months,$25k-$50k,LinkedIn + Podcasts,Needs native Hubspot integration
R002,28-34,Marketing Manager,11-50,E-commerce,Manual data aggregation,Real-time dashboards,1-3 months,$5k-$15k,YouTube + Blogs,Team adoption risk
R003,40-50,Director of Demand Gen,201-500,B2B SaaS,Lead scoring accuracy,AI-powered lead prioritization,3-6 months,$50k+,Industry forums,Data privacy concerns
R004,25-27,Growth Manager,Startup,Fintech,Budget constraints,Low-cost scaling solution,Immediately,<$5k,Twitter + Discord,Technical integration complexity
R005,33-39,Product Marketing,51-200,MarTech,ROI measurement,Campaign performance clarity,3-6 months,$10k-$30k,LinkedIn + Podcasts,Learning curve for team
```

### If You Don't Have This Data

- **No customer data?** Interview 5 recent customers. Even informal conversations yield enough for a starter persona.
- **No analytics?** Describe your top 3 customers from memory: their role, company size, pain points, and how they found you.
- **No survey results?** Send a 3-question survey to your last 20 customers: biggest challenge, why they chose you, what they'd improve.
- **No market research?** Use publicly available reports, Reddit threads, and review sites to understand your audience.

## Process

1. **Data Collection & Normalization**
   - Accept survey CSV, interview notes, or analytics data
   - If interview notes: Extract structured data (age, role, pain points, goals)
   - If analytics: Aggregate into demographic + behavior segments
   - Validate completeness
   - **Human Checkpoint:** Confirm data represents real customer base

2. **Segmentation & Clustering**
   - Group respondents by primary job title/function
   - Secondary grouping: Company size or industry if applicable
   - Identify 2-4 distinct persona clusters
   - Note overlap and unique traits per segment
   - **Human Checkpoint:** Approve persona count and segmentation logic

3. **Demographic Synthesis**
   - Summarize age range, job title, company size for each persona
   - Extract industry/vertical focus
   - Identify seniority level and decision-making authority
   - Calculate average metrics (years in role, budget authority)
   - **Human Checkpoint:** Validate demographics feel representative

4. **Psychographic & Behavioral Extraction**
   - Identify core values and priorities
   - Extract primary pain points (top 3-5 per persona)
   - Map goals and success metrics
   - Determine preferred communication channels
   - Extract language patterns and personality traits
   - **Human Checkpoint:** Review psychographic summaries

5. **Buying Journey Mapping**
   - Identify awareness stage behaviors (how they discover solutions)
   - Map consideration stage (evaluation criteria, research sources)
   - Pinpoint decision stage (objections, final concerns)
   - Timeline from awareness to purchase decision
   - **Human Checkpoint:** Approve buying journey flow

6. **Messaging & Content Strategy**
   - Extract resonant language and phrases from source data
   - Identify objection themes and rebuttals
   - Define value propositions per persona
   - Recommend content types and channels
   - **Human Checkpoint:** Review messaging angles

7. **Output & Template Generation**
   - Create markdown persona documents
   - Generate persona comparison matrix
   - Produce implementation guide for marketing use


> **Benchmark Context**: Companies with documented buyer personas are 2-4x more effective at content marketing. Average NPS for SaaS is 31. Customer acquisition cost (CAC) benchmarks: B2B SaaS $200-$500 (SMB), $1,000-$5,000 (enterprise).


### Confidence & Sample Size
> **Confidence Note**: Results are only as reliable as your input data. Small datasets (<50 records or <30 days of data) produce directional insights, not statistically significant conclusions. Always note your sample size when sharing results with stakeholders. Recommendations should be validated with A/B testing or additional data before making major strategic changes.

## Output Contract

**Markdown Persona Document Structure:**

```markdown
# Persona: [Persona Name]

## Overview
- **Archetype:** [Title-based name, e.g., "Claire, the CMO"]
- **Primary Role:** [Job title]
- **Organization:** [Company size, industry]
- **Years Experience:** [Range]
- **Decision Authority:** [Sole/Approval/Influence]

## Demographics
- **Age Range:**
- **Geography:**
- **Seniority Level:**
- **Department:**
- **Team Size Managed:**

## Psychographics
- **Personality Traits:**
- **Core Values:**
- **Work Style:**
- **Tech Comfort Level:**
- **Risk Tolerance:**

## Pain Points (Priority-Ranked)
1. [Pain point with context]
2. [Pain point with context]
3. [Pain point with context]
4. [Pain point with context]
5. [Pain point with context]

## Goals & Success Metrics
- **Primary Goal:**
- **Secondary Goals:**
- **How They Measure Success:**
- **Time Horizon:**

## Current Solutions & Tools
- **Existing Tools:**
- **Budget Authority:**
- **Buying Process:**

## Buying Journey

### Awareness Stage
- **Trigger:** What initiates problem-awareness
- **Research Sources:** Where they discover solutions
- **Key Questions:** What they're searching for
- **Content Preferred:** Blog, video, whitepaper, webinar, etc.

### Consideration Stage
- **Evaluation Criteria:** What matters in solution selection
- **Comparison Sources:** G2, competitors, peer reviews
- **Key Objections:** Initial concerns
- **Decision Influencers:** Who influences the decision

### Decision Stage
- **Final Concerns:** Last-minute objections
- **Buying Signals:** When they're ready to buy
- **Deal-Breakers:** What kills deals
- **Preferred Vendors:** Traits of trusted suppliers

## Objections & Rebuttals

| Objection | Context | Rebuttal Strategy |
|-----------|---------|------------------|
| [Objection] | When/why they raise it | How to address |
| [Objection] | When/why they raise it | How to address |

## Preferred Communication

- **Channels:** Email, LinkedIn, Slack, etc.
- **Content Format:** Long-form, short-form, interactive
- **Communication Frequency:** Daily, weekly, monthly
- **Meeting Preference:** Sync vs. async

## Messaging Angles

### Primary Value Prop
[1-2 sentence pitch addressing core pain point]

### Secondary Messages
- Message for [pain point]
- Message for [goal]
- Message for [unique situation]

### Resonant Language & Phrases
"[Actual phrase from research]"
"[Actual phrase from research]"
"[Actual phrase from research]"

## Recommended Tactics

### Content Strategy
- [Content type] about [topic] to reach [awareness/consideration/decision stage]

### Campaign Approach
- [Channel] + [message angle] + [content] = optimal engagement

### Account-Based Approach (if B2B)
- Personalization opportunities
- Multi-threading strategy
- Champion identification

---
```

**Persona Comparison Matrix (XLSX):**
```
Dimension | Persona A | Persona B | Persona C
Age Range | 35-44 | 28-34 | 40-50
Pain Point #1 | Attribution | Data overload | ROI proof
Primary Goal | Unified reporting | Efficiency gain | Executive alignment
Buying Timeline | 6-9 mo | 1-3 mo | 3-6 mo
Budget Authority | $25k-$50k | $5k-$15k | $50k+
Decision Criterion | Integration capability | Ease of use | Proven ROI
```

**Markdown Persona Details Table:**
- One row per persona
- Columns: Name, Role, Company Size, Primary Pain, Goal, Timeline, Budget, Channels, Objections, Key Message

Can be pasted into Google Sheets or Excel for further analysis and team reference.

## Platform Implementation Steps

### Google Sheets / Excel
1. Create a new spreadsheet with the output schema columns
2. Import or paste the output data
3. Use conditional formatting for priority/tier columns
4. Create a pivot table for summary views
5. Share with growth team for alignment

### Notion / Confluence
1. Create a new page for the analysis
2. Paste the Markdown output directly (both support Markdown)
3. Add team members as viewers/editors
4. Create linked databases for tracking actions

### Miro / FigJam (Visual Workshop)
1. Create a new board
2. Add persona cards or journey maps as sticky notes
3. Use the output data points as labels
4. Collaborate with team to prioritize actions

## Failure Modes

| Scenario | Symptom | Resolution |
|----------|---------|------------|
| Insufficient data | <3 respondents or interviews | Flag warning; ask for more data; note assumptions made |
| Contradictory data | Persona A says "budget $5k", Persona B says "$50k" (both Marketing Manager) | Note as separate personas; don't average across roles |
| Generic survey | No differentiation between personas | Ask follow-up questions; recommend segmentation variable |
| Interview bias | All respondents from customer reference list (happy customers) | Note bias; recommend including churned/non-converted prospects |
| Missing pain points | Survey lacks pain point questions | Infer from goals (inverse of goal = problem area) and note assumption |
| Unclear job titles | "Manager" (of what?) | Ask for context; extract from company description or role details |

## How to Get Your Data

**Survey Creation & Distribution:**
1. Use Typeform, Google Forms, or SurveyMonkey
2. 10-15 questions minimum (demographics + pain + goals + buying)
3. Target 50+ respondents (aim for 20+ per persona cluster)
4. Distribute via: Email list, LinkedIn, customer interviews, community groups
5. Run for 2-4 weeks
6. Export as CSV

**Interview Approach:**
1. Conduct 15-min interviews (3-5 min per section)
2. Target 5-10 customers per persona segment
3. Use consistent question set (template provided below)
4. Record (with permission) and transcribe, or take detailed notes
5. Extract structured data into rows

**Analytics Data Sources:**
- Google Analytics: Audience > Demographics + Interests (GA4)
- LinkedIn Campaign Manager: Audience Insights
- HubSpot: Contacts dashboard (filter by lead source, company, role)
- Mixpanel/Amplitude: Cohort analysis by user properties
- Mailchimp: Audience segmentation data

**Interview Template (Use This):**
```
1. What's your job title and main responsibilities? [Extract: Role, seniority]
2. What are your top 3 challenges in [domain]? [Pain points]
3. What outcome would be a win for you? [Goals]
4. How do you currently solve this? [Current tools/process]
5. If I described [your solution], what concerns would you have? [Objections]
6. Where do you typically learn about new solutions? [Channels]
7. How soon do you need to solve this? [Timeline]
8. Who else needs to approve a purchase? [Decision authority]
```

## Example

**Scenario:** GreenLeaf Organics (e-commerce fresh produce delivery) surveyed 32 customers to build personas. Goal: improve product messaging and target audience segmentation.

**Input: Survey Data (5 responses shown):**
```csv
respondent_id,age_range,job_title,company_size,industry,pain_point,goal,buying_timeline,budget_range,preferred_channel,objection
R001,35-44,Marketing Manager,51-200,B2B SaaS,Finding organic suppliers,Reliable food supplier,6-9 months,$5k-$25k,LinkedIn + Email,Needs bulk pricing
R008,28-34,Nutritionist,Self-employed,Health & Wellness,Meal planning time,Save 8 hours/week,1-3 months,Premium,$0-$200/mo,Instagram + TikTok,Quality consistency
R015,42-50,CEO,11-50,Food Manufacturing,Supply chain traceability,Third-party verification,3-6 months,$15k-$50k,Industry forums,Needs compliance audit
R022,26-32,Fitness Coach,Startup,Fitness,Bulk ordering for clients,Cost-effective nutrition,Immediately,<$500/mo,YouTube + Community,Shipping speed concerns
R031,38-48,Parent,N/A,Household,Organic food access,Shop once/week instead of 3x,1-3 months,$150-$300/mo,Facebook,Freshness guarantee
```

**Generated Personas:**

### Persona 1: Maya, the Millennial Health Enthusiast (12 respondents, ages 26-34)
- **Role:** Individual/household buyer, fitness enthusiasts, nutritionists, wellness creators
- **Budget:** $150-$300/month personal, up to $500/mo for professional use
- **Primary Pain:** Finding time for healthy eating (meal planning + shopping)
- **Goal:** Save 8+ hours/week; sustainable, nutrient-dense food
- **Timeline:** 1-3 months (immediate need, high intent)
- **Key Objection:** "Will it arrive fresh? How quickly?" (freshness guarantee critical)
- **Resonant Message:** "Fresh organic delivered when you need it. Done in 10 minutes."

### Persona 2: Robert, the B2B Food Buyer (11 respondents, ages 35-50)
- **Role:** VP Procurement, CEO, Food Manufacturing, Corporate wellness managers
- **Budget:** $5k-$50k annually (significant decision, multiple approvers)
- **Primary Pain:** Finding suppliers meeting organic standards + compliance requirements
- **Goal:** Reliable, traceable supply chain with certifications
- **Timeline:** 3-9 months (deliberate, vendor selection process)
- **Key Objection:** "Can you pass a compliance audit?" (non-negotiable)
- **Resonant Message:** "Organic suppliers you can verify. Full traceability built in."

**Key Buying Triggers (from survey data):**
| Pain Point | Buying Trigger | Messaging |
|-----------|---|---|
| Organic supply reliability (14 mentions) | New dietary commitment or corporate initiative | "Never run out of the organic you need" |
| Food safety/traceability (11 mentions) | Regulatory requirement or media coverage | "Track your food from farm to door" |
| Time savings (9 mentions) | Scaling up usage (family growth, team expansion) | "One order replaces three shopping trips" |

**Content Recommendations:**
- TikTok: "7-day meal prep for $40" (Persona 1 audience)
- LinkedIn: "Sourcing audit case study" (Persona 2 audience)
- Email: Weekly meal plans + shopping list (retention driver)

---

## Full Example (SaaS benchmark)

**Scenario:** SaaS marketing automation platform conducts survey of 47 marketing professionals. Goal: Create 3 personas for product marketing.

**Raw Survey Data (5 responses shown):**
```csv
respondent_id,age_range,job_title,company_size,industry,pain_point,goal,buying_timeline,budget_range,preferred_channel,objection
R001,35-44,VP Marketing,51-200,SaaS,Attribution across channels,Unified reporting,6-9 months,$25k-$50k,LinkedIn + Podcasts,Needs HubSpot integration
R002,28-34,Marketing Manager,11-50,E-commerce,Manual data aggregation,Real-time dashboards,1-3 months,$5k-$15k,YouTube + Blogs,Team adoption risk
R047,41-50,Director Demand Gen,201-500,B2B SaaS,Lead scoring accuracy,AI-prioritized leads,3-6 months,$50k+,Industry forums,Data privacy concerns
```

**Generated Personas:**

### Persona 1: Claire, the CMO (14 respondents, 35-44 age range)
- **Role:** VP/CMO at mid-market SaaS (51-200 employees)
- **Budget:** $25k-$50k annually
- **Pain:** Attribution chaos; can't prove marketing ROI to CFO
- **Goal:** Unified reporting dashboard to show channel contribution
- **Timeline:** 6-9 months (standard RFP cycle)
- **Key Objection:** "Must integrate with HubSpot" (non-negotiable)
- **Resonant Message:** "Finally see which channels drive real revenue"

### Persona 2: Marcus, the Growth Manager (18 respondents, 28-34 age range)
- **Role:** Marketing Manager / Growth Manager at startup-to-mid-market
- **Budget:** $5k-$15k (scrappy, ROI-focused)
- **Pain:** Manual data aggregation eats 15+ hours/week
- **Goal:** Save time, enable real-time decision-making
- **Timeline:** 1-3 months (fast-moving)
- **Key Objection:** "Does the team have to learn a new platform?" (adoption risk)
- **Resonant Message:** "Stop copy-pasting data. Get automated insights in minutes."

### Persona 3: Sarah, the Demand Gen Director (15 respondents, 40-50 age range)
- **Role:** Director of Demand Gen / Head of Marketing at enterprise
- **Budget:** $50k+ (committed to scalable solutions)
- **Pain:** Lead scoring is manual; can't prioritize 1000+ leads/week effectively
- **Goal:** AI-powered lead prioritization to accelerate sales cycle
- **Timeline:** 3-6 months (deliberate, security-conscious)
- **Key Objection:** "How is customer data handled?" (privacy + compliance concern)
- **Resonant Message:** "Qualify leads faster. Let AI find your hottest prospects."

**Buying Journey Comparison:**
| Stage | Claire | Marcus | Sarah |
|-------|--------|--------|-------|
| Awareness | LinkedIn + industry reports | YouTube tutorials + blogs | Industry forums + peer networks |
| Consideration | Analyst reports (G2), peer reviews | Free trial + community feedback | Security audit + compliance review |
| Decision | Executive presentation required | Fast-track trial with support | Multi-stakeholder approval (IT, legal) |

**Implementation Guidance for Marketing:**
- **Claire:** Heavy B2B media outreach; thought leadership + ROI case studies
- **Marcus:** Content marketing + freemium trial; YouTube, Product Hunt
- **Sarah:** Account-based marketing; security/compliance documentation

---

**Next Steps:**
- Validate personas with 3-5 customer conversations
- Tailor messaging per persona for each campaign
- Create persona-specific landing pages
- Build buying journey content map
- Revisit personas quarterly as market evolves
