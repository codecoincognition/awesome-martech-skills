---
name: contract-clause-extractor
description: >
  Extract and analyze key clauses from vendor, agency, or partner contracts — term length,
  auto-renewal, termination, SLAs, payment terms, IP ownership, liability, and data handling.
  Use this skill when the user says "extract contract terms", "summarize this contract",
  "what are the key clauses", "review vendor agreement", "contract analysis", "find the
  auto-renewal clause", "what's the termination policy", "contract red flags", "review
  agency contract", "SLA terms in this contract", "parse this MSA", or "flag risky contract
  clauses". Also trigger when the user pastes contract text and wants a plain-language summary.
---

# Contract Clause Extractor

Extracts key clauses from marketing vendor, agency, and partner contracts, providing plain-language summaries, risk flags, and a negotiation priority list. Turns dense legal text into actionable intelligence.

## Granularity Check

> Can this be completed in a single Claude session? **Yes — expect ~5 min data prep → ~10 min Claude session → ~30-60 min implementing in your MarTech stack.** If implementing output in a platform, add 10-20 min for setup. Input is pasted contract text. Output is a Markdown summary. No legal database needed.

## User Intent Mapping

This skill should trigger when the user says things like:

- "Summarize the key terms of this vendor contract" (direct request)
- "What's the auto-renewal clause in this agreement?" (specific clause)
- "Flag any risky clauses in this MSA" (risk scan)
- "Review this agency contract before I sign" (pre-signature review)
- "Extract SLA terms from this service agreement" (specific extraction)
- "What are my termination rights in this contract?" (specific question)
- "Compare the key terms of these two vendor contracts" (comparison)
- "Plain-language summary of this agreement" (translation)
- "Find the IP ownership clause" (specific search)
- "What should I negotiate in this contract?" (advisory)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Contract Text | Text | Full or partial contract text (pasted from document or PDF extract) |

### If You Don't Have This Data

- **No brand guidelines?** Document your current logo, colors (use a color picker on your website), and 3 tone-of-voice adjectives. That's a starting brand guide.
- **No asset inventory?** Search your Google Drive/Dropbox for common marketing file types (.pdf, .pptx, .png). The list IS your inventory.
- **No compliance checklist?** Start with industry basics: GDPR consent, CAN-SPAM footer, accessibility alt text. This skill helps you build the full checklist.
- **No vendor data?** List every tool your marketing team pays for. Include name, monthly cost, and primary user. That's your vendor inventory.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Contract Type | Text | "SaaS", "agency retainer", "partnership", "NDA", "SOW", "MSA" |
| Your Role | Text | "buyer" or "vendor" (affects risk perspective) |
| Priority Concerns | Text | Specific areas to focus on (e.g., "data handling", "IP ownership") |

## Process

### Step 1: Clause Identification
Scan the contract text and extract these clause categories:

| Clause Category | What to Extract |
|---|---|
| Term & Duration | Start date, end date, initial term length |
| Auto-Renewal | Renewal terms, notice period for non-renewal, escalation caps |
| Termination | For cause vs. convenience, notice period, cure period, termination fees |
| SLA & Performance | Uptime guarantees, response times, penalties for SLA breach, credits |
| Payment Terms | Pricing, payment schedule, net terms, late fees, price escalation |
| IP Ownership | Who owns deliverables, work product, pre-existing IP, license grants |
| Liability | Cap on liability, indemnification, exclusions, consequential damages |
| Data Handling | Data ownership, processing terms, breach notification, deletion rights |
| Non-Compete / Exclusivity | Restrictions on working with competitors, exclusivity clauses |
| Confidentiality | Duration, scope, exceptions, survival period |

### Step 2: Plain-Language Translation
For each extracted clause:
- Quote the relevant contract language (verbatim, key sentences)
- Translate to plain language ("This means...")
- Note what's standard vs. unusual for this contract type

### Step 3: Risk Assessment
Flag clauses by risk level:
- **CRITICAL** 🔴: Auto-renewal without notice, unlimited liability, broad IP assignment to vendor, no termination for convenience
- **HIGH** 🟠: Short cure periods, aggressive price escalation, weak SLA penalties, broad non-compete
- **MEDIUM** 🟡: One-sided indemnification, vague data handling, no audit rights
- **LOW** 🟢: Standard terms, minor favorable adjustments possible

### Step 4: Key Dates & Deadlines
Extract all dates into a timeline:
- Contract effective date
- Auto-renewal notice deadline
- Payment due dates
- SLA review dates
- Termination notice windows

### Step 5: Negotiation Recommendations
For CRITICAL and HIGH risk clauses, provide:
- What to push back on
- Suggested alternative language
- Priority level (must-have vs. nice-to-have)


### Confidence & Sample Size
> **Confidence Note**: Results are only as reliable as your input data. Small datasets (<50 records or <30 days of data) produce directional insights, not statistically significant conclusions. Always note your sample size when sharing results with stakeholders. Recommendations should be validated with A/B testing or additional data before making major strategic changes.

### ⚠️ Human Checkpoint
> This is contract analysis assistance, NOT legal advice. Have qualified legal counsel review any contract before signing. Do not rely solely on this analysis for legal decisions.


> **Benchmark Context**: See Gartner 2024 Marketing Technology Survey for current industry benchmarks relevant to this analysis.
## Output Contract

### Deliverable: Markdown Contract Summary

```markdown
# Contract Analysis: [Vendor/Partner Name]

## Quick Facts
| Item | Detail |
|---|---|
| Contract Type | [type] |
| Parties | [your company] ↔ [vendor] |
| Term | [duration] |
| Total Value | [if determinable] |
| Auto-Renewal | Yes/No — [notice deadline] |
| Termination | [for convenience: Yes/No] — [notice period] |

## Key Dates
| Date | Event | Action Required |
|---|---|---|
| [date] | Renewal notice deadline | Must notify by this date to prevent auto-renewal |

## Clause Analysis
### 1. Term & Duration
**Contract language**: "[quote]"
**Plain language**: [translation]
**Risk**: [level + explanation]

[...repeat for each clause category...]

## Risk Summary
- 🔴 CRITICAL: [count] issues
- 🟠 HIGH: [count] issues
- 🟡 MEDIUM: [count] issues

## Negotiation Priorities
| Priority | Clause | Current Risk | Recommended Change |
|---|---|---|---|
| 1 (Must-have) | [clause] | [risk] | [suggestion] |

## ⚖️ Disclaimer
Contract analysis assistance only. Consult legal counsel before signing.
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
| Partial contract | User pasted only some sections | Analyze what's available, note which clause categories are missing |
| Heavily redacted | Key terms blacked out or removed | Flag gaps, recommend requesting full version |
| Non-English contract | Contract in another language | Note limitation, recommend professional translation |
| Extremely long contract (50+ pages) | Too much text for single session | Focus on the 10 key clause categories, summarize high-level |

## How to Get Your Data

- **PDF contracts**: Copy-paste the text, or use a PDF text extraction tool
- **DocuSign/PandaDoc**: Download as PDF, then extract text
- **Email attachments**: Open the attachment, copy the full text
- **Word documents**: Copy all text (Ctrl+A, Ctrl+C)

## Example

**Input**: 12-page SaaS vendor contract for marketing automation platform, $2,400/month.

**Output**: 2 CRITICAL flags (auto-renewal with only 30-day notice window, vendor retains perpetual license to all data uploaded), 1 HIGH (99.5% uptime SLA with credits capped at 1 month's fees), 2 MEDIUM (annual 8% price escalation, broad non-compete preventing use of similar tools). Key deadline: renewal notice due November 1st. Top negotiation priority: change data license from perpetual to term-limited, extend renewal notice to 90 days.

## Related Skills

- **[Vendor Performance Scorecard](./vendor-performance-scorecard.md)** — Use contract terms extracted to track contract compliance and SLA performance.
- **[SLA Document Generator](./sla-document-generator.md)** — Create internal SLAs based on contract terms learned from external agreements.
- **[Marketing Compliance Pre-Checker](./marketing-compliance-pre-checker.md)** — Review contracts for compliance clauses that affect marketing activities.
- **[Approval Bottleneck Analyzer](./approval-bottleneck-analyzer.md)** — Track approval clauses and requirements found in contracts.
