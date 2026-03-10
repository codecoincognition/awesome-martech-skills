---
name: audience-persona-builder
description: >
  Build data-driven audience personas from analytics, CRM, survey, and behavioral data for marketing targeting.
  Use this skill when the user says "build buyer personas", "audience persona development", "customer persona
  creation", "data-driven personas", "ideal customer profile", "ICP development", "persona research",
  "who is our target audience", "audience segmentation for personas", "persona validation",
  or "persona-based marketing strategy". Also trigger for buyer persona workshop, persona prioritization,
  or jobs-to-be-done persona mapping.
---

# Audience Persona Builder

Builds data-driven audience personas from multiple data sources for targeted marketing, content strategy, and product positioning.

## Granularity Check

> **Time**: ~10 min data prep → ~15 min Claude session → ~30-60 min synthesizing into your strategy deck. If doing primary research, add 2-4 weeks. Input is customer data, analytics, and qualitative insights. Output is Markdown persona profiles with marketing applications.

## User Intent Mapping

- "Build buyer personas for our business" (creation)
- "Who is our ideal customer?" (ICP)
- "Data-driven persona development" (data-driven)
- "Update our outdated personas" (refresh)
- "Persona for our new product" (new product)
- "How to validate our personas" (validation)
- "Jobs-to-be-done persona mapping" (JTBD)
- "B2B buyer persona with buying committee" (B2B)
- "Persona prioritization — which to focus on" (prioritization)
- "Persona-based content strategy" (application)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Business Description | Text | What you sell and to whom |
| Customer Data | Text/CSV | Any data about current customers |
| Business Goals | Text | What you want personas to inform |

### If You Don't Have This Data

- **No customer data?** Claude builds hypothesis personas from your business model, industry patterns, and competitive research — then recommends validation methods.
- **Small customer base?** Claude works with qualitative data (interviews, support tickets, sales conversations) to build personas from 10-20 data points.
- **Only demographics, no psychographics?** Claude enriches demographic data with behavioral and motivational patterns typical for your market.
- **Not sure how many personas?** Claude recommends 3-5 personas maximum, prioritized by revenue potential and marketing reach.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Analytics Data | CSV | Website demographics, behavior flows |
| CRM Data | Text | Customer attributes, deal sizes, win rates |
| Survey Results | CSV | Customer research survey responses |
| Interview Notes | Text | Qualitative customer insights |
| Social Data | Text | Audience demographics from social platforms |

## Process

### Step 1: Data Collection Matrix
| Data Source | What It Tells You | Persona Element |
|---|---|---|
| CRM | Who buys, deal size, sales cycle | Demographics, firmographics |
| Analytics | How they find you, what content they consume | Channels, interests |
| Surveys | Why they buy, what they value | Motivations, pain points |
| Interviews | Decision process, objections, language | Buying journey, messaging |
| Support tickets | What problems they have | Pain points, feature needs |
| Social media | How they describe themselves, what they share | Psychographics, language |
| Sales team | Common objections, decision-makers, competitors considered | Buying criteria |

### Step 2: Persona Components
| Component | Description | Source |
|---|---|---|
| Demographics | Age, role, company size, industry | CRM, analytics |
| Goals | What they're trying to achieve | Interviews, surveys |
| Pain points | Problems they need solved | Support, sales, surveys |
| Buying triggers | What causes them to look for a solution | Sales, interviews |
| Decision criteria | How they evaluate solutions | Win/loss, interviews |
| Information sources | Where they learn and research | Analytics, surveys |
| Objections | What holds them back from buying | Sales, win/loss |
| Success metrics | How they measure whether the solution worked | Interviews, support |

### Step 3: Persona Prioritization
| Criteria | Weight | How to Assess |
|---|---|---|
| Revenue potential | 30% | Average deal size × addressable market |
| Acquisition cost | 20% | Marketing spend to acquire this persona |
| Retention/LTV | 20% | Churn rate and expansion potential |
| Product fit | 15% | How well your product serves this persona |
| Growth rate | 15% | Is this segment growing or shrinking? |

### Step 4: B2B Buying Committee Mapping
| Role | Involvement | Priorities | Content Needs |
|---|---|---|---|
| Champion | Day-to-day user, drives evaluation | Ease of use, features | Product demos, case studies |
| Decision-maker | Signs off on budget | ROI, strategic fit | Executive summaries, ROI calculators |
| Influencer | Provides technical evaluation | Integration, security | Technical docs, architecture guides |
| Gatekeeper | Controls information flow | Compliance, vendor requirements | Security questionnaires, compliance docs |
| End user | Uses the product daily | Usability, workflow | Tutorial content, training materials |

### Step 5: Jobs-to-Be-Done Layer
Per persona:
- **Functional job**: What task they need to accomplish
- **Emotional job**: How they want to feel
- **Social job**: How they want to be perceived
- **Hiring criteria**: What would make them "hire" your product
- **Firing criteria**: What would make them "fire" your product

### Step 6: Persona Activation
| Application | How Persona Informs |
|---|---|
| Content strategy | Topics, formats, channels per persona |
| Ad targeting | Audience parameters, messaging angles |
| Email marketing | Segmentation, messaging, send cadence |
| Sales enablement | Talking points, objection handling per persona |
| Product development | Feature prioritization by persona value |
| Website | Page structure, messaging hierarchy |

### Confidence & Sample Size

> **Confidence Note**: Personas based on fewer than 10 data points (interviews + data) are hypotheses, not validated personas. Aim for 15-20 customer interviews per persona for reliable qualitative patterns. Quantitative validation requires 200+ data points per persona. Personas should be updated annually — markets and customers change. The biggest persona mistake is creating too many (5+ active personas dilute marketing focus). Avoid "aspirational" personas (who you wish your customers were) — base personas on actual buyers.

### ⚠️ Human Checkpoint
> Validate persona profiles with sales team and customer success before using for targeting. Ensure personas represent actual customer patterns, not internal assumptions or wishful thinking. Test persona-based messaging with real customers before full rollout.

> **Benchmark Context**: Companies using personas see 2-5x improvement in email open rates and ad CTR (Gartner 2024 Marketing Technology Survey). Persona-based content generates 18x more revenue than broadcast content (Gartner 2024 Marketing Technology Survey). 71% of companies that exceed revenue goals have documented personas (Gartner 2024 Marketing Technology Survey). Only 44% of B2B marketers actually use their personas for content decisions (Gartner 2024 Marketing Technology Survey). Companies with 3-4 active personas outperform those with 1 or 7+ (Gartner 2024 Marketing Technology Survey). (Gartner 2024 Marketing Technology Survey).
## Output Contract

### Deliverable: Markdown Persona Profiles

```markdown
# Audience Personas: [Brand]

## Persona Overview
| Persona | Segment | Revenue Priority | Marketing Priority |
|---|---|---|---|

## Persona 1: [Name]
### Demographics
- Role: [title/role]
- Company: [size, industry, stage]
- Background: [education, experience]

### Goals & Motivations
- Primary goal: [what they want to achieve]
- Secondary goal: [supporting objective]
- Success metric: [how they measure results]

### Pain Points
1. [Pain point with context]
2. [Pain point with context]
3. [Pain point with context]

### Buying Journey
- Trigger: [what starts the search]
- Research: [where they look, who they ask]
- Evaluation: [criteria, competitors considered]
- Decision: [who else is involved, timeline]
- Objections: [common reasons for no-decision]

### Marketing Application
- **Channels**: [where to reach them]
- **Content**: [what topics and formats]
- **Messaging**: [key messages that resonate]
- **CTA**: [what action to drive]

### Quotes (Composite)
> "[Representative quote capturing their perspective]"

[Repeat for each persona]

## Persona Activation Plan
| Persona | Content Priorities | Channel Focus | Campaign Angle |
|---|---|---|---|
```

## Platform Implementation Steps

### CRM Setup
1. Add persona field to contact/account records
2. Create persona-based segments and views
3. Tag existing contacts to personas (manual or rule-based)
4. Set up persona tracking in lead scoring
5. Report on pipeline and revenue by persona

### Marketing Automation
1. Create persona-based email segments
2. Design nurture sequences per persona
3. Set up dynamic content rules by persona
4. Personalize landing pages by persona (UTM or smart content)
5. Track campaign performance by persona segment

### Content Planning
1. Map content calendar topics to persona priorities
2. Tag all content assets by target persona
3. Create persona-specific content pathways on website
4. Brief writers with persona context for every piece
5. Measure content performance by persona engagement

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Personas sit in a deck unused | No activation plan; too abstract | Make personas actionable with specific marketing applications |
| Too many personas | Tried to cover every customer type | Consolidate to 3-4 based on revenue and marketing priority |
| Personas don't match reality | Based on assumptions, not data | Validate with customer interviews and quantitative data |
| Team doesn't adopt personas | Personas feel like marketing fluff | Include sales and product teams in persona development |

## How to Get Your Data

- **CRM data**: Export customer list with demographics, deal size, industry, role
- **Analytics**: GA4 → Reports → Demographics → Overview; Acquisition → Traffic
- **Surveys**: Send 5-question persona validation survey to customer list
- **Interviews**: Schedule 30-minute calls with 5 customers per suspected persona
- **No data**: Describe your product and who you think buys it — Claude creates hypothesis personas

## Example

**Input**: "Build buyer personas for our HR tech SaaS. We sell to mid-market companies (100-1,000 employees). Current customers: 60% HR directors, 25% CHROs, 15% People Ops managers. Average deal: $15K/year. Main use case: employee onboarding and offboarding."

**Output**: 3 personas recommended: (1) "Director Dana" (HR Director, 100-500 employees) — 60% of revenue, primary persona. Goal: streamline onboarding to reduce time-to-productivity. Pain: manual processes, compliance risk, scaling hiring. Trigger: new leadership demanding HR efficiency OR compliance audit. Channels: LinkedIn, HR conferences, peer recommendations. Content: ROI calculators, compliance guides, "how we do it" case studies. Messaging: "Onboard in days, not weeks." (2) "CHRO Chris" (CHRO, 500-1,000 employees) — 25% of revenue, highest deal size ($25K avg). Goal: strategic HR transformation. Pain: too much time on operations, not enough on strategy. Trigger: board pressure to modernize HR. Channels: executive events, analyst reports, CHRO communities. Content: strategic whitepapers, analyst endorsements, executive case studies. Messaging: "Automate operations so you can focus on strategy." (3) "People Ops Pat" (People Ops Manager, 100-500 employees) — 15% of revenue, strongest champion. Goal: not get burned by missed steps in onboarding/offboarding. Pain: checklist chaos, no single source of truth. Trigger: a bad offboarding incident. Channels: People Ops communities (Slack, Reddit), product-led growth (free trial). Content: templates, checklists, product tutorials. Messaging: "Never miss a step." Activation: focus 60% of content on Persona 1, use Persona 3 as product-led entry point, create executive-level content for Persona 2 during enterprise deals.

## Related Skills

- **[Customer Segmentation Engine](../ai-marketing/customer-segmentation-engine.md)** — Operationalize personas into data-driven CRM segments for targeted marketing.
- **[Campaign Angle Generator](./campaign-angle-generator.md)** — Use persona insights to generate messaging angles that resonate with each persona.
- **[Customer Journey Mapper](./customer-journey-mapper.md)** — Map persona-specific journeys to understand touchpoints and friction by archetype.
- **[Survey Design Analyzer](./survey-design-analyzer.md)** — Validate personas through primary research with targeted surveys per persona.
