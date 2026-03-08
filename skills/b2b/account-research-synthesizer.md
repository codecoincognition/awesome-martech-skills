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

# Account Research Synthesizer

Synthesizes all available information about a target account into a structured account brief — combining firmographic data, technology stack, recent news, organizational structure, and engagement history into a narrative that ABM teams can act on.

## Granularity Check

> Can this be completed in a single 10-minute Claude session? **Yes.** Input is account data from various sources. Output is a Markdown account brief. Web search supplements available data.

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

### ⚠️ Human Checkpoint
> Validate organizational mapping with sales team — org charts change. Confirm technology stack assumptions before building messaging around displacement plays.

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
