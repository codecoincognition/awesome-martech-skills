---
name: campaign-brief-synthesizer
description: >
  Synthesize inputs from multiple stakeholders into a unified, actionable campaign brief.
  Use this skill when the user says "create a campaign brief", "synthesize campaign inputs",
  "unify our campaign requirements", "build a creative brief", "campaign brief from stakeholder
  inputs", "combine feedback into a brief", "campaign planning document", "brief the agency",
  "campaign kickoff document", "consolidate campaign requirements", or "write up the campaign
  brief from these notes". This is different from a content brief (which is SEO-focused) —
  this covers full campaign planning across channels.
---

# Campaign Brief Synthesizer

Synthesizes inputs from multiple stakeholders (product, sales, leadership, creative) into a single, unified campaign brief. Resolves conflicting requirements, identifies gaps, and produces an actionable document that creative teams and agencies can execute against.

## Granularity Check

> Can this be completed in a single Claude session? **Yes — expect ~5 min data prep + ~10 min Claude session.** If implementing output in a platform, add 10-20 min for setup. Input is stakeholder notes/requirements. Output is a Markdown campaign brief. No external access needed.

## User Intent Mapping

This skill should trigger when the user says things like:

- "Turn these meeting notes into a campaign brief" (synthesis)
- "Combine feedback from product, sales, and marketing into one brief" (multi-stakeholder)
- "Create a brief for our agency" (external handoff)
- "Synthesize these conflicting campaign requirements" (conflict resolution)
- "Campaign kickoff document from these inputs" (project initiation)
- "We have notes from 3 meetings — make a coherent brief" (consolidation)
- "Write a creative brief for this campaign" (creative direction)
- "Build a campaign brief for Q2 product launch" (campaign type)
- "Brief the design team on this campaign" (internal handoff)
- "What's missing from our campaign plan?" (gap analysis)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Campaign Context | Text | What's the campaign for (product launch, seasonal, awareness, demand gen) |
| Stakeholder Inputs | Text | Notes, emails, or requirements from different stakeholders |

### If You Don't Have This Data

- **No content strategy?** Describe your product and your top 3 customer pain points. That's enough to generate an outline.
- **No keyword research?** List 5 questions your customers frequently ask. These become your topics.
- **No brand voice guide?** Provide 2-3 examples of content you like the tone of. Claude can infer the voice from examples.
- **No performance data?** Start fresh. After publishing, track views, time-on-page, and conversions for 30 days.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Target Audience | Text | Who the campaign targets |
| Budget | Number | Campaign budget |
| Timeline | Text | Launch date, duration, key milestones |
| Channels | Text | Channels to use (paid, organic, email, social, events) |
| Brand Guidelines | Text | Voice, visual style, mandatory elements |
| Success Metrics | Text | KPIs and targets |
| Competitive Context | Text | What competitors are doing |
| Constraints | Text | Legal, brand, timing, or resource limitations |

## Process

### Step 1: Input Consolidation
Organize all stakeholder inputs by category:
- **Objectives**: What each stakeholder wants to achieve
- **Audience**: Who they think the target is
- **Messaging**: Key messages each stakeholder wants to convey
- **Channels**: Where they think the campaign should run
- **Timing**: Deadlines and milestones from each perspective
- **Success metrics**: How each stakeholder would measure success

### Step 2: Conflict Identification
Flag areas where stakeholders disagree:
- Different target audiences
- Conflicting messages or priorities
- Budget allocation disagreements
- Timeline conflicts
- Success metric misalignment

For each conflict, note the positions and recommend a resolution.

### Step 3: Gap Analysis
Identify missing elements that no stakeholder addressed:
- No clear CTA defined
- No competitive differentiation articulated
- Budget not allocated by channel
- No measurement plan
- Missing creative requirements (formats, sizes, specs)

### Step 4: Brief Assembly
Structure the unified brief with all standard sections:
1. Campaign overview and objective
2. Target audience (primary + secondary)
3. Key message and supporting messages
4. Channel strategy
5. Creative requirements
6. Timeline with milestones
7. Budget allocation
8. Success metrics and measurement plan
9. Approval process

### Step 5: Decision Log
Document all synthesis decisions:
- Which stakeholder input was prioritized and why
- Conflicts that were resolved (and how)
- Gaps that were filled with recommendations
- Open items that need stakeholder sign-off


### Confidence & Sample Size
> **Confidence Note**: Results are only as reliable as your input data. Small datasets (<50 records or <30 days of data) produce directional insights, not statistically significant conclusions. Always note your sample size when sharing results with stakeholders. Recommendations should be validated with A/B testing or additional data before making major strategic changes.

### ⚠️ Human Checkpoint
> Share the synthesized brief with all contributing stakeholders before execution. Unresolved conflicts should be flagged for a decision meeting, not silently resolved.


> **Benchmark Context**: Blog posts averaging 1,500-2,500 words tend to rank highest in search. Content marketing generates 3x more leads than outbound at 62% less cost. Average time to write a 1,500-word blog post is 4-6 hours (research + writing + editing).

## Output Contract

### Deliverable: Markdown Campaign Brief

```markdown
# Campaign Brief: [Campaign Name]

## Overview
- **Campaign Type**: [launch / seasonal / awareness / demand gen / retention]
- **Objective**: [one sentence]
- **Timeline**: [start] → [end]
- **Budget**: $[amount]
- **Brief Owner**: [name]
- **Approval Date**: [pending]

## Target Audience
### Primary
[Demographics, psychographics, pain points, where they spend time]
### Secondary
[If applicable]

## Key Message
**Core message**: [one sentence the audience should remember]
**Supporting messages**:
1. [message + evidence/proof point]
2. [message + evidence/proof point]
3. [message + evidence/proof point]

**Tone**: [descriptors]
**Mandatory inclusions**: [legal disclaimers, brand elements, etc.]

## Channel Strategy
| Channel | Role | Budget | Key Assets Needed | Timeline |
|---|---|---|---|---|

## Creative Requirements
| Asset | Format/Size | Copy Length | Due Date |
|---|---|---|---|

## Timeline
| Date | Milestone | Owner |
|---|---|---|

## Success Metrics
| KPI | Target | Source | Cadence |
|---|---|---|---|

## Decision Log
| Topic | Stakeholder Inputs | Resolution | Rationale |
|---|---|---|---|

## Open Items
- [ ] [Item needing stakeholder decision]
```

## Platform Implementation Steps

### WordPress
1. Log in to wp-admin → Posts → Add New
2. Paste the content outline into the editor
3. Use the Heading blocks (H2, H3) for structure
4. Add Featured Image and set Category/Tags before publishing

### Google Docs (Collaboration)
1. Create a new Google Doc
2. Paste the output and use Suggesting Mode for team review
3. Use Insert → Table of Contents for navigation
4. Share with stakeholders for feedback

### CMS-Agnostic
1. Copy Markdown output as-is into any CMS that supports Markdown
2. For HTML-based CMS platforms, convert Markdown to HTML using any converter
3. Adapt headings and formatting to match your site's style guide

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Contradictory objectives | Stakeholders want awareness AND immediate conversions | Recommend phased approach or primary/secondary objectives |
| Too many messages | Everyone wants their point included | Apply the "billboard test" — limit to 1 core message + 3 supporting |
| No budget | Budget TBD | Build channel strategy with relative allocations, flag for finance |
| Missing stakeholder | Key voice (e.g., sales) not represented | Note gap, recommend additional input before finalizing |

## How to Get Your Data

- **Meeting notes**: Copy from Notion, Google Docs, or email
- **Slack threads**: Export relevant campaign planning discussions
- **Strategy documents**: Link or paste relevant sections
- **Email threads**: Copy stakeholder feedback and requirements
- **Previous briefs**: Share past campaign briefs as format reference

## Example

**Input**: Product team wants to emphasize "AI-powered analytics" (technical). Sales wants "save 10 hours per week" (benefit-driven). CMO wants "category leadership" (positioning). Target: VP Marketing at mid-market SaaS. Budget: $50K. Launch: April 1.

**Output**: Unified brief resolving messaging conflict: core message leads with benefit ("Save 10 hours per week on reporting"), supported by mechanism ("AI-powered analytics"), positioned within a category narrative ("The analytics platform built for modern marketing teams"). Decision log: "Led with benefit per sales input, as buyer research shows VPs respond to time-savings over technical features. AI positioning used as supporting proof point rather than headline." Channel strategy: LinkedIn Ads ($20K), content marketing ($10K), webinar ($8K), email nurture ($5K), sales enablement ($7K). Open items: need customer testimonial for launch day, legal review of "save 10 hours" claim.
