---
name: brand-asset-compliance-checker
description: >
  Audit marketing assets for brand guideline compliance — logos, colors, fonts, tone, and messaging.
  Use this skill when the user says "check brand compliance", "audit brand consistency", "review assets
  against brand guidelines", "are these on-brand", "brand audit", "logo usage check", "color palette
  compliance", "brand standards review", "does this follow our style guide", "brand governance audit",
  or "check if this matches our brand guidelines". Also trigger when reviewing a batch of assets
  for consistency before a campaign launch or partner handoff.
---

# Brand Asset Compliance Checker

Audits marketing assets against documented brand guidelines, flagging violations in logo usage, color palette, typography, tone of voice, and messaging hierarchy. Produces a scored compliance report with specific fix instructions.

## Granularity Check

> Can this be completed in a single Claude session? **Yes — expect ~5 min data prep → ~10 min Claude session → ~30-60 min implementing in your MarTech stack.** If implementing output in a platform, add 10-20 min for setup. Input is brand guidelines + asset descriptions/content. Output is a scored compliance report in Markdown. No external tools needed.

## User Intent Mapping

This skill should trigger when the user says things like:

- "Check if these assets follow our brand guidelines" (direct command)
- "Audit this campaign for brand consistency" (campaign review)
- "Are these partner materials on-brand?" (co-marketing review)
- "Review these assets before we send to the agency" (pre-handoff check)
- "We updated our brand — what's now out of compliance?" (rebrand audit)
- "Check logo usage across these materials" (specific element)
- "Does this copy match our brand voice?" (tone review)
- "Score these assets against our style guide" (quantitative)
- "Brand compliance check for Q2 campaign" (batch review)
- "Flag any brand violations in these deliverables" (quality gate)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Brand Guidelines | Text/Markdown/PDF extract | Brand standards: colors (hex), fonts, logo rules, tone, messaging hierarchy |
| Assets to Audit | Text descriptions or content | Marketing copy, email content, landing page text, social posts, or asset descriptions |

### If You Don't Have This Data

- **No brand guidelines?** Document your current logo, colors (use a color picker on your website), and 3 tone-of-voice adjectives. That's a starting brand guide.
- **No asset inventory?** Search your Google Drive/Dropbox for common marketing file types (.pdf, .pptx, .png). The list IS your inventory.
- **No compliance checklist?** Start with industry basics: GDPR consent, CAN-SPAM footer, accessibility alt text. This skill helps you build the full checklist.
- **No vendor data?** List every tool your marketing team pays for. Include name, monthly cost, and primary user. That's your vendor inventory.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Asset Type | Text | "email", "social", "landing page", "presentation", "partner materials" |
| Severity Threshold | Text | "strict" (flag everything) or "practical" (major violations only) |
| Previous Audit | Markdown | Prior audit results to track improvement |

### Sample Input

```
Brand Guidelines:
- Primary colors: #1A73E8 (blue), #FFFFFF (white), #202124 (charcoal)
- Secondary: #34A853 (green), #FBBC04 (yellow) — accent only, max 10% of visual area
- Fonts: Inter (headings), Source Sans Pro (body), monospace for code only
- Logo: minimum 24px clear space, never on busy backgrounds, no rotation
- Tone: professional but approachable, avoid jargon, active voice preferred
- Messaging: lead with customer outcome, not features

Asset: Welcome Email
Subject: "🚀 Welcome to DataSync Pro — Your Powerful New Tool!"
Body uses Comic Sans, red CTA button (#FF0000), passive voice throughout,
leads with "Our AI-powered platform has 47 features..."
```

## Process

### Step 1: Parse Brand Guidelines
Extract auditable rules organized by category:
- **Visual**: colors (hex values), fonts (families + weights), logo usage rules, imagery style
- **Verbal**: tone descriptors, vocabulary preferences, messaging hierarchy, banned phrases
- **Structural**: layout rules, spacing requirements, hierarchy patterns

### Step 2: Catalog Assets
For each asset, identify:
- Asset type and intended channel
- Visual elements described (colors, fonts, imagery)
- Copy/messaging content
- CTA language and placement
- Overall composition notes

### Step 3: Compliance Audit
Score each asset across 8 dimensions (1-5 scale):

| Dimension | What to Check |
|---|---|
| Color Compliance | Hex values match palette, ratios respected, no off-brand colors |
| Typography | Correct font families, weights, sizes per hierarchy |
| Logo Usage | Clear space, placement, background, no modifications |
| Tone of Voice | Matches brand personality descriptors, avoids banned terms |
| Messaging Hierarchy | Leads with prescribed order (outcome → benefit → feature) |
| CTA Consistency | Button text, color, placement follows standards |
| Visual Consistency | Imagery style, iconography, whitespace patterns |
| Channel Appropriateness | Format and length fit the channel's best practices |

### Step 4: Generate Fix Instructions
For each violation, provide:
- **What's wrong**: specific element that violates guidelines
- **Guideline reference**: which rule it breaks
- **How to fix**: exact correction (e.g., "Change #FF0000 to #1A73E8")
- **Severity**: Critical (brand damage risk), Major (noticeable inconsistency), Minor (nitpick)


### Confidence & Sample Size
> **Confidence Note**: Results are only as reliable as your input data. Small datasets (<50 records or <30 days of data) produce directional insights, not statistically significant conclusions. Always note your sample size when sharing results with stakeholders. Recommendations should be validated with A/B testing or additional data before making major strategic changes.

### ⚠️ Human Checkpoint
> Review severity classifications before sharing with stakeholders. Context matters — a minor font inconsistency in an internal deck is different from a logo violation on a billboard.


> **Benchmark Context**: See Gartner 2024 Marketing Technology Survey for current industry benchmarks relevant to this analysis.
## Output Contract

### Deliverable: Markdown Compliance Report

```markdown
# Brand Compliance Audit Report

## Summary
- **Assets Audited**: [count]
- **Overall Score**: [X/40] ([percentage]%)
- **Critical Violations**: [count]
- **Major Violations**: [count]
- **Minor Violations**: [count]

## Scorecard

| Dimension | Score | Status |
|---|---|---|
| Color Compliance | 4/5 | ✅ Pass |
| Typography | 2/5 | ❌ Fail |
| Logo Usage | 5/5 | ✅ Pass |
| Tone of Voice | 3/5 | ⚠️ Needs Work |
| Messaging Hierarchy | 2/5 | ❌ Fail |
| CTA Consistency | 4/5 | ✅ Pass |
| Visual Consistency | 3/5 | ⚠️ Needs Work |
| Channel Fit | 4/5 | ✅ Pass |

## Violation Details

### Critical
1. **[Asset Name] — [Element]**: [Description]. Fix: [Exact correction].

### Major
1. ...

### Minor
1. ...

## Recommended Priority Fixes
1. [Highest-impact fix first]
2. ...
```

## Platform Implementation Steps

### Notion / Confluence (Documentation)
1. Create a new page for the audit/report
2. Paste Markdown output directly
3. Add status properties for tracking remediation
4. Assign team members to action items

### Google Sheets (Tracking)
1. Import CSV output into a new spreadsheet
2. Add a "Status" column for tracking fixes
3. Use conditional formatting for severity levels
4. Create a dashboard tab with summary charts

### Project Management (Asana/Jira/Linear)
1. Create tasks from each action item in the output
2. Set priority based on severity ratings
3. Assign to responsible team members
4. Set due dates based on priority tiers

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Vague guidelines | Brand doc uses subjective language ("modern feel") | Ask user to provide specific values — hex codes, font names, example copy |
| Missing visual data | Text-only asset descriptions miss visual details | Note which dimensions couldn't be scored, recommend visual review |
| Conflicting guidelines | Style guide contradicts itself | Flag the conflict, ask user which rule takes precedence |
| Over-flagging | Strict mode produces noise | Switch to "practical" threshold, focus on customer-facing violations |

## How to Get Your Data

**Brand Guidelines**: Usually a PDF or Google Doc from your design/brand team. Check your company wiki, Notion, or shared drive for "Brand Guidelines", "Style Guide", or "Brand Standards".

**Assets**: Copy-paste the text content of emails, landing pages, or social posts. For visual assets, describe the key elements (colors used, fonts, logo placement, imagery style).

## Example

**Input**: Brand guidelines (blue/white palette, Inter font, outcome-first messaging) + welcome email using Comic Sans, red buttons, feature-first copy.

**Output**: Compliance score 19/40 (47%). 2 critical violations (wrong font family, off-brand CTA color), 2 major (passive voice, feature-first messaging), 1 minor (emoji in subject line). Fix instructions: "Replace Comic Sans with Inter for all headings, Source Sans Pro for body. Change CTA button from #FF0000 to #1A73E8."

## Related Skills

- **[Digital Asset Audit Report](./digital-asset-audit-report.md)** — Run after compliance checks to audit metadata and organization of approved assets.
- **[Content Governance Framework](../content/content-governance-framework.md)** — Establish governance policies that prevent compliance violations in the first place.
- **[Marketing Compliance Pre-Checker](./marketing-compliance-pre-checker.md)** — Extend brand compliance checks to regulatory compliance screening for marketing claims.
- **[Vendor Performance Scorecard](./vendor-performance-scorecard.md)** — Score agencies and vendors partially on their brand compliance in delivered work.
