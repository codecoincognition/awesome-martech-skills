---
name: marketing-compliance-pre-checker
description: >
  Pre-screen marketing content for regulatory compliance — FTC endorsement rules, FDA supplement
  claims, advertising standards, CAN-SPAM, and GDPR marketing claims. Use this skill when the
  user says "check this for compliance", "is this ad copy legal", "FTC compliance check",
  "review marketing claims", "can we say this in our ad", "compliance pre-check", "regulatory
  review of marketing copy", "FDA marketing rules", "advertising standards audit",
  "check if these claims are compliant", or "legal review of marketing content". Also trigger
  when the user is in health, finance, or supplements and needs claims reviewed before publishing.
---

# Marketing Compliance Pre-Checker

Pre-screens marketing content for regulatory compliance issues across FTC, FDA, CAN-SPAM, GDPR marketing claims, and industry-specific advertising standards. Flags risky phrases and provides compliant alternatives.

## Granularity Check

> Can this be completed in a single Claude session? **Yes — expect ~5 min data prep → ~10 min Claude session → ~30-60 min implementing in your MarTech stack.** If implementing output in a platform, add 10-20 min for setup. Input is marketing copy + industry context. Output is a Markdown compliance report. No legal database access needed.

## User Intent Mapping

This skill should trigger when the user says things like:

- "Can we legally say this in our ad?" (direct question)
- "Check this email for CAN-SPAM compliance" (regulation-specific)
- "Review our supplement marketing claims" (industry-specific)
- "FTC endorsement compliance check" (regulation-specific)
- "Is this testimonial usage compliant?" (specific element)
- "Pre-check this landing page before legal review" (workflow step)
- "What claims can we make about our product?" (proactive guidance)
- "Flag any risky marketing language in this copy" (risk scan)
- "We're launching in the EU — check GDPR marketing rules" (market-specific)
- "Compliance review for our health product ads" (industry + regulation)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Marketing Content | Text | Ad copy, email, landing page, social post, or campaign content to review |
| Industry | Text | Product/service industry (health, finance, tech, food, beauty, general) |

### If You Don't Have This Data

- **No brand guidelines?** Document your current logo, colors (use a color picker on your website), and 3 tone-of-voice adjectives. That's a starting brand guide.
- **No asset inventory?** Search your Google Drive/Dropbox for common marketing file types (.pdf, .pptx, .png). The list IS your inventory.
- **No compliance checklist?** Start with industry basics: GDPR consent, CAN-SPAM footer, accessibility alt text. This skill helps you build the full checklist.
- **No vendor data?** List every tool your marketing team pays for. Include name, monthly cost, and primary user. That's your vendor inventory.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Target Markets | Text | Countries/regions (US, EU, CA, AU, UK) — default US |
| Content Type | Text | "ad", "email", "landing page", "social", "testimonial page" |
| Product Claims | Text | Specific claims the user wants to make |
| Existing Disclaimers | Text | Disclaimers already in place |

## Process

### Step 1: Regulatory Applicability
Determine which regulations apply based on industry + market + content type:
- **FTC Act Section 5**: All US marketing (deceptive/unfair practices)
- **FTC Endorsement Guides**: Testimonials, influencer content, reviews
- **FDA**: Health claims, supplement claims, drug marketing
- **CAN-SPAM**: Commercial email
- **GDPR Article 6/7**: EU consent-based marketing
- **FTC Health Claims**: "Clinically proven", "doctor recommended" etc.
- **Financial (SEC/FINRA)**: Investment returns, guarantees

### Step 2: Claim Scanning
Scan content for regulated language patterns:
- **Absolute claims**: "guaranteed", "100%", "always", "never fails"
- **Health claims**: "cures", "treats", "prevents", "clinically proven"
- **Financial claims**: "guaranteed returns", "risk-free", "double your money"
- **Comparative claims**: "best", "#1", "better than" without substantiation
- **Testimonial issues**: Atypical results without disclosure, missing material connections
- **Urgency manipulation**: "Act now or lose forever", false scarcity
- **Price claims**: "free" with hidden costs, bait-and-switch indicators

### Step 3: Risk Classification
For each flagged phrase:
- **CRITICAL**: Likely illegal, immediate legal risk (false health claims, undisclosed material connections)
- **HIGH**: Likely non-compliant, enforcement risk (unsubstantiated superlatives, missing disclaimers)
- **MEDIUM**: Gray area, should get legal review (comparative claims, implied guarantees)
- **LOW**: Best practice recommendation (could be clearer, add context)

### Step 4: Compliant Alternatives
For each flagged phrase, provide:
- The original problematic phrase
- Why it's flagged (which regulation, what the risk is)
- A compliant rewrite that preserves marketing intent
- Required disclaimer language (if applicable)


### Confidence & Sample Size
> **Confidence Note**: Results are only as reliable as your input data. Small datasets (<50 records or <30 days of data) produce directional insights, not statistically significant conclusions. Always note your sample size when sharing results with stakeholders. Recommendations should be validated with A/B testing or additional data before making major strategic changes.

### ⚠️ Human Checkpoint
> This skill provides guidance, NOT legal advice. All CRITICAL and HIGH flags should be reviewed by qualified legal counsel before publishing. Regulations change — verify current rules.


> **Benchmark Context**: See Gartner 2024 Marketing Technology Survey for current industry benchmarks relevant to this analysis.
## Output Contract

### Deliverable: Markdown Compliance Report

```markdown
# Marketing Compliance Pre-Check Report

## Summary
- **Content Type**: [type]
- **Industry**: [industry]
- **Applicable Regulations**: [list]
- **Overall Risk Level**: CRITICAL / HIGH / MEDIUM / LOW
- **Flags**: [count by severity]

## Flagged Items

### CRITICAL ❌
1. **"[phrase]"** — [regulation]: [explanation].
   Rewrite: "[compliant alternative]"
   Required disclaimer: "[if applicable]"

### HIGH ⚠️
1. ...

### MEDIUM 🔶
1. ...

### LOW 💡
1. ...

## Required Disclaimers
[List of disclaimers that must be added based on content]

## Compliance Checklist
- [ ] All testimonials include material connection disclosures
- [ ] Health claims are substantiated with cited studies
- [ ] Email includes physical address and unsubscribe link
- [ ] Price claims include all mandatory fees
- [ ] Comparative claims cite verifiable data source

## ⚖️ Disclaimer
This is an automated pre-screening tool, not legal advice. Consult qualified legal counsel for final compliance review.
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
| Unfamiliar industry | Niche regulations (alcohol, cannabis, gambling) | Flag as needing specialist legal review, apply general FTC rules |
| Multiple markets | Conflicting rules across jurisdictions | Flag conflicts, recommend most restrictive interpretation |
| Ambiguous claims | Implied rather than explicit claims | Flag as MEDIUM, note the implied interpretation |
| Evolving regulations | Rules changed after training data | Recommend user verify current regulations, note uncertainty |

## How to Get Your Data

Copy-paste your marketing content directly. For landing pages, copy the visible text. For emails, paste the full body content. For ads, include all copy variations. Include any existing disclaimers.

## Example

**Input**: Supplement landing page: "Our all-natural formula is clinically proven to boost energy by 300%. Doctors recommend TurboVitamin. Try it risk-free — 100% money-back guarantee! Join 50,000 happy customers. As seen on Dr. Oz."

**Output**: 3 CRITICAL flags ("clinically proven" needs specific study citation, "doctors recommend" implies endorsement without substantiation, "As seen on Dr. Oz" — celebrity endorsement requires disclosure), 2 HIGH flags ("300%" needs substantiation, "all-natural" has FDA-specific definition requirements), 1 MEDIUM ("risk-free" may imply no side effects vs. financial risk-free). Compliant rewrite provided for each. Required disclaimers: FDA structure/function disclaimer, typical results statement, money-back guarantee terms.

## Related Skills

- **[Brand Asset Compliance Checker](./brand-asset-compliance-checker.md)** — Extend compliance reviews to brand guideline compliance in addition to regulatory compliance.
- **[Ad Compliance Checker](../ads/ad-compliance-checker.md)** — Screen ad copy specifically for FTC and platform compliance rules.
- **[Email Compliance Checker](../email/email-compliance-checker.md)** — Screen email content for CAN-SPAM, GDPR, and other email-specific compliance requirements.
- **[Content Governance Framework](../content/content-governance-framework.md)** — Document compliance requirements into governance policies to prevent violations.
