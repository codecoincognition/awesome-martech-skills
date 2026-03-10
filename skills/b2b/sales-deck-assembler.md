---
name: sales-deck-assembler
description: >
  Assemble a tailored sales presentation by selecting and customizing slides for a specific
  prospect's industry, pain points, and buying stage. Use this skill when the user says
  "build a sales deck", "customize our pitch deck", "tailor the presentation for this prospect",
  "assemble slides for the meeting", "create a prospect-specific deck", "sales presentation
  for this account", "customize pitch for this industry", "build a demo deck",
  "presentation for the discovery call", or "put together slides for the QBR". Also trigger
  when the user needs to pull from a slide library to create a targeted presentation.
---

# Sales Deck Assembler

Assembles a customized sales presentation by selecting relevant slides and tailoring messaging for a specific prospect's industry, pain points, deal stage, and buying committee. Outputs a structured slide outline with speaker notes.

## Granularity Check

> Can this be completed in a single Claude session? **Yes — expect ~5 min data prep → ~10 min Claude session → ~30-60 min customizing for your prospect.** If implementing output in a platform, add 10-20 min for setup. Input is prospect context + available slide topics. Output is a Markdown slide outline with speaker notes. No design tool access needed.

## User Intent Mapping

This skill should trigger when the user says things like:

- "Build a pitch deck for our meeting with Acme Corp" (direct request)
- "Customize our standard deck for a healthcare prospect" (industry tailoring)
- "Which slides should I use for a discovery call?" (stage-appropriate)
- "Assemble a QBR presentation for this account" (account review)
- "Tailor the case studies slide for financial services" (specific element)
- "Put together a 10-slide deck for the demo" (length-constrained)
- "Create speaker notes for each slide" (presentation prep)
- "Our generic deck doesn't work — make it specific" (problem statement)
- "What slides should I include for a technical audience?" (audience-tailored)
- "Build a deck for the executive sponsor meeting" (persona-targeted)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Prospect | Text | Company name, industry, size |
| Meeting Type | Text | Discovery, demo, proposal, QBR, executive briefing |
| Your Product | Text | What you sell, key value props |

### If You Don't Have This Data

- **No CRM data?** Export your email contacts, LinkedIn connections, or even a list of companies you've spoken to in a spreadsheet.
- **No deal outcome data?** Start with win/loss status on your last 20 deals. Even rough data is better than none.
- **No content library?** List every PDF, deck, and one-pager your sales team uses — even a 10-item list is a valid starting point.
- **No engagement metrics?** Track which content sales reps send in emails for the next 2 weeks. Manual tracking beats no tracking.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Audience | Text | Titles/roles who will be in the room |
| Known Pain Points | Text | Problems prospect has expressed |
| Competitive Context | Text | What they're comparing you against |
| Deal Stage | Text | Early, mid, late, renewal |
| Time Limit | Text | Presentation length (e.g., "20 minutes") |
| Slide Library | Text list | Available slide types/topics in your existing deck |
| Previous Meeting Notes | Text | Context from prior conversations |

## Process

### Step 1: Meeting Strategy
Define the presentation's primary objective:
- Discovery: Learn about their situation, build credibility
- Demo: Show product fit for their specific use case
- Proposal: Make the business case, handle objections
- QBR: Review value delivered, expand relationship
- Executive: High-level strategic alignment, ROI focus

### Step 2: Audience-Based Slide Selection
Select slides based on who's in the room:

| Audience | Include | Exclude |
|---|---|---|
| C-Suite | Market trends, ROI, strategic fit, customer logos | Technical architecture, feature details |
| Technical | Architecture, security, integrations, API | Pricing, company history |
| End Users | Workflow demos, day-in-the-life, ease of use | Financial analysis, org charts |
| Mixed | Balanced — lead with business, embed technical | Deep dives on any one area |

### Step 3: Slide Outline Assembly
Build the deck structure (adjust for meeting type):

1. **Opening** (1 slide): Agenda + meeting objective
2. **Context** (1-2 slides): Prospect's situation, industry trends, pain point validation
3. **Solution** (2-4 slides): How your product addresses their specific challenges
4. **Proof** (1-2 slides): Case studies from similar companies/industries
5. **Differentiation** (1 slide): Why you vs. alternatives (tailored to known competitors)
6. **Value/ROI** (1 slide): Quantified impact (tailored to their size/industry)
7. **How It Works** (1-3 slides): Architecture, implementation, timeline (for technical audience)
8. **Next Steps** (1 slide): Clear call to action appropriate to deal stage

### Step 4: Content Customization
For each slide, provide:
- **Headline**: Prospect-specific (not generic)
- **Key points**: 3-4 bullets tailored to their context
- **Speaker notes**: What to say, how to handle likely questions
- **Personalization cues**: Where to insert prospect-specific data, logos, or references

### Step 5: Presentation Flow Notes
Add transition guidance:
- How to move between sections
- Where to pause for questions
- Which slides to skip if running short on time
- Backup slides for anticipated deep-dive questions


### Confidence & Sample Size
> **Confidence Note**: Results are only as reliable as your input data. Small datasets (<50 records or <30 days of data) produce directional insights, not statistically significant conclusions. Always note your sample size when sharing results with stakeholders. Recommendations should be validated with A/B testing or additional data before making major strategic changes.

### ⚠️ Human Checkpoint
> Review the assembled outline before building the actual slides. Verify case studies are appropriate (no competitor conflicts), pricing is current, and claims are approved by marketing.


> **Benchmark Context**: Average B2B sales cycle is 102 days. Win rates average 20-30% for qualified opportunities (Gartner 2024 B2B Buying Journey Report). Top-performing sales orgs use 5-7 pieces of content per deal cycle (Gartner 2024 B2B Buying Journey Report). Sales reps spend ~30% of their time searching for content (Gartner 2024 B2B Buying Journey Report). (Gartner 2024 B2B Buying Journey Report).
## Output Contract

### Deliverable: Markdown Slide Outline

```markdown
# Sales Deck: [Prospect Name] — [Meeting Type]

## Deck Strategy
- **Objective**: [primary goal of this meeting]
- **Audience**: [who will be present]
- **Duration**: [target length]
- **Key Message**: [one sentence they should remember]

## Slide Outline

### Slide 1: [Title]
**Type**: Opening
**Headline**: "[prospect-specific headline]"
**Content**:
- [bullet 1]
- [bullet 2]
- [bullet 3]
**Speaker Notes**: [what to say, 2-3 sentences]
**Time**: [X minutes]

[...repeat for each slide...]

## Presentation Tips
- **If running long**: Skip slides [X, Y]
- **Likely questions**: [question + prepared response]
- **Transition moment**: After slide [X], pause and ask "[question]"

## Backup Slides
- [Topic]: Use if [condition]
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
| No prospect info | User just says "make a sales deck" | Ask for minimum: prospect name, industry, meeting type |
| No existing slides | Building from scratch, not assembling | Switch to full deck creation — structure from template |
| Too many slides | User wants everything included | Apply time limit constraint, recommend appendix for extras |
| Mismatched audience | Deck is too technical for executives (or vice versa) | Re-calibrate based on audience, split into two versions if needed |

## How to Get Your Data

- **CRM**: Pull account notes, past meeting records, deal stage
- **Your slide library**: List the slide types you have available (or just describe your product)
- **LinkedIn**: Research the attendees' roles and backgrounds
- **Previous meetings**: Review notes for expressed pain points, objections, interests
- **Sales playbook**: Reference your standard messaging for each persona/stage

## Example

**Input**: Prospect: "RetailMax" (mid-market e-commerce, 200 employees). Meeting: demo with VP Marketing + Marketing Ops Manager. Pain point: "We're drowning in manual reporting — takes 2 days every week." Your product: marketing analytics platform. Competitor: Google Analytics (free) + manual spreadsheets. 30 minutes.

**Output**: 8-slide deck outline. Opens with "RetailMax is spending 104 days/year on manual reporting" (their pain quantified). Slides tailored: automated dashboard demo (for VP — time savings), integration architecture with Shopify (for Ops Manager — technical fit), e-commerce case study (similar company saved 15 hours/week). Speaker notes include: "After slide 4, ask 'Walk me through your current reporting process' — this validates the pain and creates buy-in." Backup slide: pricing (include only if they ask). Skip slide 7 (roadmap) if running short.

## Related Skills

- **[Buying Committee Mapper](./buying-committee-mapper.md)** — Map decision makers before assembling decks to customize messaging per role.
- **[Account Research Synthesizer](./account-research-synthesizer.md)** — Research the target account first to identify their specific pain points and industry context.
- **[Campaign Angle Generator](../insights/campaign-angle-generator.md)** — Generate compelling value propositions and angles tailored to the prospect's situation.
- **[Sales Content Usage Analyzer](./sales-content-usage-analyzer.md)** — Use data on which slides and content get used most to prioritize slide selection.
