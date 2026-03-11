---
name: buying-committee-mapper
description: >
  Map the buying committee within a target account — roles, priorities, objections, content
  preferences, and engagement strategy per persona. Use this skill when the user says "map
  the buying committee", "who are the decision makers", "identify the buying group",
  "stakeholder mapping", "who do we need to convince", "decision maker analysis", "buying
  committee personas", "account stakeholder map", "ABM persona mapping", "who influences
  this deal", or "multi-threaded selling strategy". Also trigger when the user needs to
  move beyond single-threaded selling and engage multiple stakeholders in an enterprise deal.
---

# Buying Committee Mapper

Maps the full buying committee for a target account, defining each stakeholder's role, decision criteria, likely objections, preferred content formats, and recommended engagement strategy. Essential for multi-threaded ABM and enterprise selling.

## Granularity Check

> Can this be completed in a single Claude session? **Yes — expect ~5 min data prep → ~10 min Claude session → ~30-60 min customizing for your prospect.** If implementing output in a platform, add 10-20 min for setup. Input is account context + known contacts. Output is a Markdown committee map. No system access needed.

## User Intent Mapping

This skill should trigger when the user says things like:

- "Map the buying committee at Acme Corp" (direct request)
- "Who are all the stakeholders in this deal?" (discovery)
- "We're single-threaded — help us go multi-threaded" (sales strategy)
- "What does the CFO care about vs. the CMO?" (persona differentiation)
- "Build personas for the buying group" (persona creation)
- "Who might block this deal and why?" (risk identification)
- "Engagement strategy for each decision maker" (channel planning)
- "What content should we send each stakeholder?" (content mapping)
- "Map the org chart for this account" (organizational view)
- "Stakeholder influence map for enterprise deal" (strategic planning)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Company Name | Text | Target account |
| Your Product | Text | What you sell and the problem it solves |
| Deal Size / Type | Text | Enterprise, mid-market, etc. + approximate deal value |

### If You Don't Have This Data

- **No CRM data?** Export your email contacts, LinkedIn connections, or even a list of companies you've spoken to in a spreadsheet.
- **No deal outcome data?** Start with win/loss status on your last 20 deals. Even rough data is better than none.
- **No content library?** List every PDF, deck, and one-pager your sales team uses — even a 10-item list is a valid starting point.
- **No engagement metrics?** Track which content sales reps send in emails for the next 2 weeks. Manual tracking beats no tracking.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Known Contacts | Text/CSV | Names, titles, past interactions |
| Industry | Text | Industry-specific buying patterns |
| Sales Stage | Text | Early discovery, evaluation, negotiation, etc. |
| Competitive Situation | Text | Competitors being evaluated |
| CRM Notes | Text | Any intelligence from conversations |
| Company Size | Text | Employees / revenue (affects committee size) |

## Process

### Step 1: Define Committee Roles
Map the standard B2B buying committee roles to the specific account:

| Role | Description | Typical Title |
|---|---|---|
| **Economic Buyer** | Controls budget, makes final yes/no | C-suite, VP, Director |
| **Technical Evaluator** | Assesses technical fit, integration, security | IT, Engineering, Ops |
| **User Buyer** | Will use the product daily | Manager, Analyst, Coordinator |
| **Champion** | Internal advocate, drives momentum | Any level, typically the initiator |
| **Coach** | Provides insider intelligence | Often a past relationship |
| **Influencer** | Doesn't decide but shapes opinion | Adjacent team leads, consultants |
| **Gatekeeper** | Controls access or process | Procurement, Legal, Compliance |
| **Blocker** | May resist change or prefer a competitor | Incumbent vendor champion, risk-averse leader |

### Step 2: Persona Deep Dive
For each identified committee member, define:
- **Decision criteria**: What they evaluate (ROI, ease of use, security, time to value)
- **Key question**: The one question they need answered
- **Primary objection**: Most likely pushback
- **Win condition**: What makes them say yes
- **Risk signal**: Behavior that indicates they're going cold or hostile

### Step 3: Content Mapping
Match content types to each persona:

| Persona | Content Format | Topic Focus |
|---|---|---|
| Economic Buyer | ROI calculator, executive brief, customer reference | Business impact, competitive advantage |
| Technical Evaluator | Architecture docs, security whitepaper, API docs | Integration, compliance, scalability |
| User Buyer | Product demo, trial, day-in-the-life video | Ease of use, time savings, workflow fit |
| Champion | Internal pitch deck, value summary, competitive comparison | Ammunition to sell internally |

### Step 4: Engagement Sequencing
For each persona, recommend:
- **When to engage** (which stage of the deal)
- **How to reach** (direct outreach, warm intro, event, content)
- **Messaging angle** (specific to their role and priorities)
- **Engagement cadence** (how often, through what channel)
- **Escalation trigger** (when to bring in your leadership)

### Step 5: Committee Health Assessment
Score the overall buying committee status:
- How many roles are identified? (coverage)
- How many are actively engaged? (engagement)
- Is there a champion? (momentum)
- Are blockers identified and addressed? (risk mitigation)
- Is multi-threading happening? (resilience)


### Confidence & Sample Size
> **Confidence Note**: Results are only as reliable as your input data. Small datasets (<50 records or <30 days of data) produce directional insights, not statistically significant conclusions. Always note your sample size when sharing results with stakeholders. Recommendations should be validated with A/B testing or additional data before making major strategic changes.

### ⚠️ Human Checkpoint
> Validate the committee map with your champion or coach inside the account. Organizational structures vary — don't assume based on title alone. Update the map as the deal progresses.


> **Benchmark Context**: See Gartner 2024 B2B Buying Journey Report for current industry benchmarks relevant to this analysis.
## Output Contract

### Deliverable: Markdown Buying Committee Map

```markdown
# Buying Committee Map: [Company Name]

## Committee Overview
- **Committee Size**: [estimated count]
- **Coverage**: [X of Y roles identified]
- **Engagement Level**: [Strong / Moderate / Weak]
- **Champion Status**: [Identified / Not Yet / At Risk]
- **Deal Risk Level**: [Low / Medium / High]

## Stakeholder Map

### 1. [Role]: [Name or "TBD"] — [Title]
- **Decision Criteria**: [what matters to them]
- **Key Question**: "[the one thing they need answered]"
- **Primary Objection**: "[most likely pushback]"
- **Win Condition**: [what makes them say yes]
- **Content to Send**: [specific assets]
- **Engagement Channel**: [email / LinkedIn / event / exec sponsor]
- **When to Engage**: [deal stage]
- **Current Status**: 🟢 Engaged / 🟡 Aware / 🔴 Not Contacted / ⚫ Blocker

[...repeat for each stakeholder...]

## Engagement Timeline
| Week | Stakeholder | Action | Channel | Goal |
|---|---|---|---|---|
| 1 | Champion | Share case study | Email | Build internal case |
| 2 | Technical | Security whitepaper | Direct | Address compliance |
| 3 | Economic | ROI calculator | Exec-to-exec | Justify budget |

## Risk Factors
1. [Risk + mitigation strategy]

## Missing Intelligence
- [Questions to answer to complete the map]
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
| Unknown org structure | Can't identify specific people | Map by role, flag as TBD, recommend discovery tactics |
| Single contact | Only know one person at the account | Use that contact to map the rest, recommend multi-threading |
| Flat organization | Small company with overlapping roles | Combine roles, note that fewer stakeholders needed |
| Complex matrix org | Dotted-line reporting, shared decision rights | Map both formal and informal influence, note complexity |

## How to Get Your Data

- **LinkedIn**: Company page → People tab (filter by department)
- **CRM**: Account record → associated contacts
- **Sales Navigator**: Account page → recommended leads
- **Company website**: About/Team page, leadership bios
- **Your champion**: Ask directly — "Who else will be involved in this decision?"
- **Annual reports**: For public companies, leadership structure

## Example

**Input**: Target: "GlobalHealth Systems" (2,000 employees, healthcare IT). Selling: data analytics platform, $150K deal. Known contact: Director of Marketing Analytics (attended demo, enthusiastic). Competitor: Tableau (entrenched in IT department).

**Output**: 7-person committee mapped. Champion: Director of Marketing Analytics (user buyer + champion). Economic Buyer: CMO (needs ROI story, engage week 3 via exec sponsor). Technical Evaluator: VP of IT (Tableau advocate = potential blocker — needs integration story, not replacement story). Gatekeeper: Procurement (engage early with pre-approved pricing structure). Key risk: IT blocker comfortable with Tableau. Mitigation: position as "complements Tableau for marketing-specific use cases" rather than replacement. Missing intelligence: who is the CISO (security approval needed for healthcare data).

## Related Skills

- **[Account Research Synthesizer](./account-research-synthesizer.md)** — Use before committee mapping to gather firmographic and organizational data about the target account.
- **[Sales Deck Assembler](./sales-deck-assembler.md)** — Customize presentations per committee member role and priorities identified in your mapping.
- **[Audience Persona Builder](../insights/audience-persona-builder.md)** — Build data-driven personas from buying committee insights to inform broader marketing strategy.
- **[Campaign Angle Generator](../insights/campaign-angle-generator.md)** — Generate messaging angles tailored to each committee member's priorities and objections.
