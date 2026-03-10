---
name: account-research-synthesizer
description: >
  Synthesize firmographic, technographic, and intent signals into a comprehensive account
  brief for ABM campaigns. Use this skill when the user says "research this account",
  "build an account brief", "account intelligence report", "ABM account research",
  "what do we know about this company", "synthesize account data", "account profile for ABM",
  "target account brief", "compile account research", "account dossier", or "pre-campaign
  account analysis". Also trigger when preparing for an ABM campaign launch and needing
  account-level intelligence.
---

> **How this skill works:** You provide or export account information (from web searches, LinkedIn, your CRM, industry databases, etc.) as notes or CSV, and Claude synthesizes research into an action brief. Claude cannot pull live data from platforms directly — you bring the source information, Claude brings the synthesis.

# Account Research Synthesizer

Synthesizes all available information about a target account into a structured account brief — combining firmographic data, technology stack, recent news, organizational structure, and engagement history into a narrative that ABM teams can act on.

## Granularity Check

> Can this be completed in a single Claude session? **Yes — expect ~5 min data prep + ~10 min Claude session.** If implementing output in a platform, add 10-20 min for setup. Input is account data from various sources. Output is a Markdown account brief. Web search supplements available data.

## User Intent Mapping

This skill should trigger when the user says things like:

- "Build an account brief for Acme Corp" (direct request)
- "What do we know about this target account?" (discovery)
- "Compile research on our top 10 ABM accounts" (batch prep)
- "Synthesize our data on this prospect company" (data synthesis)
- "Create an account profile for the sales team" (sales enablement)
- "ABM account dossier for campaign planning" (campaign prep)
- "Combine CRM data with web research on this company" (multi-source)
- "Account intelligence for our enterprise push" (strategic initiative)
- "Research this company before we launch the ABM play" (pre-campaign)
- "Tell me everything relevant about this target account" (comprehensive)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Company Name | Text | Target account name |
| Your Product/Service | Text | What you sell (to tailor relevance) |

### If You Don't Have This Data

- **No CRM data?** Export your email contacts, LinkedIn connections, or even a list of companies you've spoken to in a spreadsheet.
- **No deal outcome data?** Start with win/loss status on your last 20 deals. Even rough data is better than none.
- **No content library?** List every PDF, deck, and one-pager your sales team uses — even a 10-item list is a valid starting point.
- **No engagement metrics?** Track which content sales reps send in emails for the next 2 weeks. Manual tracking beats no tracking.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| CRM Data | Text/CSV | Known contacts, engagement history, deal history |
| Website URL | Text | For technographic and content analysis |
| Industry Focus | Text | Specific industry angle to emphasize |
| ICP Criteria | Text | Your ideal customer profile for fit scoring |
| Known Pain Points | Text | Intelligence from sales conversations |
| Competitor Intel | Text | Which competitors they're evaluating or using |

## Process

### Step 1: Firmographic Profile
Compile or verify:
- Company size (employees, revenue range)
- Industry and sub-industry
- Headquarters and key office locations
- Founding year and growth stage
- Ownership structure (public/private, PE-backed, subsidiary)
- Recent funding rounds (if applicable)

### Step 2: Organizational Mapping
Identify the likely buying committee:
- Economic buyer (who controls budget)
- Technical evaluator (who assesses fit)
- End users (who will use the product)
- Champions (who advocates internally)
- Blockers (who might resist, e.g., incumbent vendor relationships)

### Step 3: Technology Stack Analysis
From available data, identify:
- Current tech stack relevant to your product category
- Complementary technologies (integration opportunities)
- Competing solutions in use (displacement targets)
- Technology maturity signals (early adopter vs. conservative)

### Step 4: Business Context
Synthesize recent signals:
- Earnings calls or press releases (public companies)
- Hiring patterns (what roles they're filling)
- News mentions and industry coverage
- Strategic initiatives mentioned publicly
- Pain points or challenges disclosed in public forums

### Step 5: Engagement History
If CRM data provided:
- Past interactions (meetings, emails, events)
- Content consumed (what topics interested them)
- Deal history (won, lost, stalled — why)
- Current pipeline status

### Step 6: Account Brief Synthesis
Combine all findings into a narrative brief with:
- ICP fit score (if criteria provided)
- Key messaging angles (tailored to their situation)
- Recommended entry points (which persona, what hook)
- Potential objections and responses
- Competitive positioning (if competitors known)


### Confidence & Sample Size
> **Confidence Note**: Results are only as reliable as your input data. Small datasets (<50 records or <30 days of data) produce directional insights, not statistically significant conclusions. Always note your sample size when sharing results with stakeholders. Recommendations should be validated with A/B testing or additional data before making major strategic changes.

### ⚠️ Human Checkpoint
> Validate organizational mapping with sales team — org charts change. Confirm technology stack assumptions before building messaging around displacement plays.


> **Benchmark Context**: Average B2B sales cycle is 102 days. Win rates average 20-30% for qualified opportunities. Top-performing sales orgs use 5-7 pieces of content per deal cycle. Sales reps spend ~30% of their time searching for content.

## Output Contract

### Deliverable: Markdown Account Brief

```markdown
# Account Brief: [Company Name]

## Snapshot
| Field | Detail |
|---|---|
| Industry | [industry] |
| Size | [employees] / [revenue range] |
| HQ | [location] |
| ICP Fit Score | [X/100] |
| Recommended Priority | [Tier 1/2/3] |

## Business Overview
[2-3 paragraph narrative on who they are, what they're focused on, and why they're a target]

## Buying Committee
| Role | Likely Title | Priority | Approach |
|---|---|---|---|
| Economic Buyer | [title] | High | [messaging angle] |
| Technical Evaluator | [title] | High | [messaging angle] |
| End User | [title] | Medium | [messaging angle] |
| Champion | [title] | High | [how to activate] |

## Technology Context
[Current stack, integration opportunities, displacement targets]

## Key Business Signals
[Recent news, hiring patterns, strategic priorities — with implications for your product]

## Recommended ABM Plays
1. [Play 1]: [Hook + channel + persona]
2. [Play 2]: ...

## Potential Objections
| Objection | Response |
|---|---|
| [objection] | [response] |

## Engagement History
[Summary of past interactions, if available]
```

## Platform Implementation Steps

### Salesforce
1. Navigate to Reports → New Report → select relevant object
2. Add columns matching the output schema
3. Use filters to scope the data
4. Export as CSV for input, or build dashboard from output

### HubSpot
1. Go to Contacts/Companies → Import → select CSV
2. Map columns to HubSpot properties
3. Use Lists → Create List to filter by output criteria
4. Dashboards → Create Dashboard for ongoing tracking

### Google Sheets (No CRM)
If no CRM is available:
1. Create a new Google Sheet
2. Structure columns per the output schema
3. Use Data → Filter Views for dynamic sorting
4. Share with team via link for collaboration

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Unknown company | Very small or private company with no public data | Use available inputs only, note data gaps, recommend direct outreach for discovery |
| No CRM data | New target, no prior engagement | Skip engagement history section, focus on public intelligence |
| Stale information | Company recently pivoted or restructured | Note data freshness, recommend validation |
| Broad company | Huge enterprise with many divisions | Ask which business unit or division to focus on |

## How to Get Your Data

- **CRM**: Export account record + associated contacts + activity history
- **LinkedIn**: Company page for firmographic data, employees for org mapping
- **Built With / Wappalyzer**: Technology stack data
- **Crunchbase**: Funding, leadership, company details
- **Company website**: About page, careers page, press/news section
- **Google News**: Recent mentions and press coverage

## Example

**Input**: Target account: "MedTech Solutions" (500 employees, B2B healthcare SaaS). Your product: marketing automation platform. CRM shows 3 past contacts — VP Marketing attended a webinar 6 months ago.

**Output**: Account brief showing ICP fit score 82/100. Buying committee mapped (VP Marketing as champion, CFO as economic buyer, Marketing Ops Manager as technical evaluator). Tech stack: currently using Mailchimp (underweight for their size — displacement opportunity). Key signal: just raised Series C, hiring 5 marketing roles (expansion = budget for new tools). Recommended play: re-engage VP Marketing with case study from similar healthcare company, position as "growth-stage upgrade from Mailchimp." Top objection: migration cost/risk — counter with healthcare-specific migration playbook.
