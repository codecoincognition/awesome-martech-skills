---
name: rfp-response-builder
description: >
  Generate structured RFP/RFI responses from product knowledge and past answers. Use this
  skill when the user says "help with this RFP", "respond to this RFI", "RFP response",
  "answer these vendor questions", "fill out this security questionnaire", "proposal response",
  "bid response document", "RFP answer generation", "vendor evaluation response",
  "complete this procurement questionnaire", or "draft RFP answers". Also trigger when the
  user pastes a list of questions from a prospect's procurement process.
---

# RFP Response Builder

Generates structured, professional responses to RFP (Request for Proposal) and RFI (Request for Information) questions based on product knowledge, past answers, and best practices. Produces a ready-to-submit response document.

## Granularity Check

> Can this be completed in a single 10-minute Claude session? **Yes.** Input is RFP questions + product context. Output is a Markdown response document. No system access needed.

## User Intent Mapping

This skill should trigger when the user says things like:

- "Help me respond to this RFP" (direct request)
- "Answer these vendor evaluation questions" (specific task)
- "We got an RFI — draft responses" (document type)
- "Fill out this security questionnaire for the prospect" (compliance)
- "Draft answers for this procurement process" (procurement)
- "Our proposal is due Friday — help me write it" (deadline pressure)
- "Respond to these technical requirements" (specific section)
- "Here are 50 questions from the prospect" (batch processing)
- "Make our RFP responses sound more compelling" (quality improvement)
- "Customize our standard RFP answers for healthcare" (industry tailoring)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| RFP Questions | Text | The questions to answer (pasted from the RFP document) |
| Product/Company Info | Text | What you do, key capabilities, differentiators |

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Past RFP Answers | Text | Previously approved responses to reuse/adapt |
| Industry | Text | Prospect's industry (for tailored language) |
| Prospect Name | Text | For personalization |
| Compliance Certs | Text | SOC 2, ISO 27001, HIPAA, GDPR certifications |
| Competitor Context | Text | Who you're competing against in this RFP |
| Win Themes | Text | Key differentiators to emphasize throughout |
| Word/Character Limits | Text | Any length constraints per answer |

## Process

### Step 1: Question Categorization
Classify each question into categories:
- **Company Overview**: History, financials, references, team
- **Technical Capabilities**: Features, architecture, integrations, scalability
- **Security & Compliance**: Data handling, certifications, incident response
- **Implementation**: Timeline, methodology, training, support
- **Pricing & Commercial**: Licensing, SLAs, contract terms
- **Differentiators**: Innovation, roadmap, unique capabilities

### Step 2: Response Drafting
For each question, draft a response following RFP best practices:
- **Lead with "yes"**: Start with a clear affirmative when possible
- **Be specific**: Replace vague claims with concrete details
- **Quantify**: Use numbers (99.9% uptime, 500+ integrations, 48-hour response)
- **Differentiate**: Weave in win themes without being heavy-handed
- **Evidence**: Include customer examples, certifications, metrics
- **Compliant**: Directly address what was asked before adding context

### Step 3: Consistency Check
Across all answers, ensure:
- Terminology is consistent (don't call the same feature by 3 names)
- Claims don't contradict each other
- Tone is professional and confident without overpromising
- Company name and product names are used consistently

### Step 4: Compliance Flagging
Flag any questions where:
- The honest answer is "no" or "partial" — draft diplomatically
- The answer requires legal or security team review
- A claim needs verification before submission
- The question reveals a requirement you can't meet

### Step 5: Executive Summary
Draft a 1-page executive summary for the RFP response:
- Why your company is the right choice
- Top 3 differentiators for this specific prospect
- Relevant experience and references
- Commitment statement

### ⚠️ Human Checkpoint
> Review all responses before submission. Verify technical accuracy, confirm pricing with finance, ensure legal has approved compliance claims. Never submit without internal review.

## Output Contract

### Deliverable: Markdown RFP Response

```markdown
# RFP Response: [Prospect Name]

## Executive Summary
[1-page overview: why you, key differentiators, relevant experience]

## Responses

### Section 1: [Category Name]

**Q1: [Question text]**
[Structured response — 2-4 paragraphs or formatted list as appropriate]

**Q2: [Question text]**
[Response]

[...continue for all questions...]

## Flagged Items
| Question # | Issue | Action Required |
|---|---|---|
| Q7 | Partial capability — needs product team input | Verify roadmap timeline |
| Q15 | Legal claim — needs counsel review | Confirm compliance status |

## Response Metadata
- **Total Questions**: [count]
- **Fully Answered**: [count]
- **Flagged for Review**: [count]
- **Recommended Win Themes Used**: [list]
```

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Insufficient product knowledge | User provided limited product info | Answer what's possible, flag gaps, ask for product documentation |
| Highly technical questions | Deep technical specs beyond available info | Draft framework response, flag as "needs engineering input" |
| Contradictory requirements | RFP asks for conflicting capabilities | Note the contradiction, answer each part honestly |
| Massive RFP (200+ questions) | Too many for single session | Batch into sections, handle one category per session |

## How to Get Your Data

- **RFP document**: Copy-paste the questions section (or the entire document)
- **Past RFP responses**: Check your sales enablement folder, Google Drive, or Confluence
- **Product documentation**: Feature lists, security documentation, architecture guides
- **Certifications**: SOC 2 report, ISO certificates, compliance documentation
- **Customer references**: Approved reference list with use cases

## Example

**Input**: 25-question RFP from a healthcare company evaluating marketing analytics platforms. Product: SaaS analytics platform with HIPAA compliance. Competitor: Looker.

**Output**: Full response document with executive summary emphasizing healthcare-specific compliance (HIPAA BAA, SOC 2 Type II), 25 answers categorized into 5 sections, 3 flagged items (pricing needs finance sign-off, custom integration timeline needs engineering estimate, reference customer needs permission). Win themes woven throughout: purpose-built for marketing teams (vs. Looker's general-purpose approach), HIPAA-compliant by default, 2-week implementation vs. typical 6-8 weeks.
