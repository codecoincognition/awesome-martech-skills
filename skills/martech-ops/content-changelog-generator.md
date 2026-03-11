---
name: content-changelog-generator
description: >
  Generate a structured changelog comparing two versions of a document, highlighting what changed
  and why it matters. Use this skill when the user says "what changed between these versions",
  "compare these two documents", "content diff", "track content changes", "version comparison",
  "what's different in the new version", "document change log", "content revision history",
  "summarize the edits", or "changelog for this update". Also trigger when the user provides
  two versions of a landing page, email, blog post, or policy document and wants a clear summary.
---

# Content Changelog Generator

Compares two versions of a marketing document (landing page, email, blog post, policy) and generates a structured changelog showing what changed, categorizing edits by type and business impact.

## Granularity Check

> Can this be completed in a single Claude session? **Yes — expect ~5 min data prep → ~10 min Claude session → ~30-60 min implementing in your MarTech stack.** If implementing output in a platform, add 10-20 min for setup. Input is two text versions. Output is a Markdown changelog. No external tools needed.

## User Intent Mapping

This skill should trigger when the user says things like:

- "What changed between v1 and v2 of this page?" (direct comparison)
- "Summarize the edits to this landing page" (change summary)
- "Create a changelog for this document update" (formal changelog)
- "Compare the old and new email copy" (content diff)
- "What's different in the revised version?" (quick check)
- "Track changes between these two blog posts" (version tracking)
- "Write release notes for this page update" (stakeholder communication)
- "Document what we changed and why" (audit trail)
- "Before/after comparison of our homepage" (visual-style comparison)
- "Help me communicate these content changes to the team" (internal comms)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Version A (Before) | Text/Markdown | The original version of the content |
| Version B (After) | Text/Markdown | The updated version of the content |

### If You Don't Have This Data

- **No brand guidelines?** Document your current logo, colors (use a color picker on your website), and 3 tone-of-voice adjectives. That's a starting brand guide.
- **No asset inventory?** Search your Google Drive/Dropbox for common marketing file types (.pdf, .pptx, .png). The list IS your inventory.
- **No compliance checklist?** Start with industry basics: GDPR consent, CAN-SPAM footer, accessibility alt text. This skill helps you build the full checklist.
- **No vendor data?** List every tool your marketing team pays for. Include name, monthly cost, and primary user. That's your vendor inventory.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Document Name | Text | Name of the document being compared |
| Change Context | Text | Why the changes were made (e.g., "rebrand", "A/B test results", "legal review") |
| Audience | Text | Who will read the changelog (e.g., "marketing team", "legal", "executives") |

## Process

### Step 1: Structural Comparison
- Identify added, removed, and modified sections
- Detect structural changes (headings, section order, new blocks)
- Note length changes (word count delta)

### Step 2: Categorize Changes
Classify each change into one of these types:
- **Copy**: Wording, tone, or messaging changes
- **Structure**: Section additions, removals, reordering
- **CTA**: Call-to-action text, placement, or design changes
- **Legal/Compliance**: Disclaimers, terms, required disclosures
- **SEO**: Meta titles, descriptions, heading tags, keyword targeting
- **Data/Stats**: Updated numbers, dates, or factual claims
- **Visual**: Image/layout references changed

### Step 3: Impact Assessment
For each change, assess:
- **Impact level**: High (affects conversion/compliance), Medium (affects clarity/messaging), Low (cosmetic)
- **Business reason**: Why this change likely matters
- **Risk flag**: Any change that could cause issues (broken links, removed disclaimers, altered claims)

### Step 4: Generate Changelog
Format as a clean, scannable changelog appropriate for the audience.


### Confidence & Sample Size
> **Confidence Note**: Results are only as reliable as your input data. Small datasets (<50 records or <30 days of data) produce directional insights, not statistically significant conclusions. Always note your sample size when sharing results with stakeholders. Recommendations should be validated with A/B testing or additional data before making major strategic changes.

### ⚠️ Human Checkpoint
> Review any changes flagged as "removed" — especially disclaimers, legal language, or data claims. Removals can carry compliance risk.


> **Benchmark Context**: See Gartner 2024 Marketing Technology Survey for current industry benchmarks relevant to this analysis.
## Output Contract

### Deliverable: Markdown Changelog

```markdown
# Changelog: [Document Name]

**Compared**: Version A → Version B
**Date**: [date]
**Summary**: [1-2 sentence overview of the nature and scope of changes]
**Word Count**: [before] → [after] ([+/- delta])

## High-Impact Changes
1. **[Category]**: [Before → After summary]. Impact: [explanation].

## Medium-Impact Changes
1. ...

## Low-Impact Changes
1. ...

## Risk Flags
- ⚠️ [Description of any risky removal or alteration]

## Full Diff

| Section | Change Type | Before | After |
|---|---|---|---|
| Headline | Copy | "..." | "..." |
| CTA | CTA | "..." | "..." |
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
| Completely different documents | User provided two unrelated pages | Notify user, ask if these are truly versions of the same document |
| Minor whitespace-only differences | Formatting changes, no content diff | Report "No substantive content changes detected" |
| Very long documents | 5000+ word documents | Focus on structural changes and high-impact diffs, summarize minor edits |
| Missing context | No explanation of why changes were made | Generate changelog without "why" column, note that context would improve it |

## How to Get Your Data

- **Google Docs**: File → Version History → select two versions, copy each
- **WordPress**: Revisions panel → copy content from two revisions
- **CMS**: Export/copy the published version and the draft version
- **Email platforms**: Copy the sent version and the new draft
- **Manual**: Paste the "before" text and "after" text directly

## Example

**Input**: Version A of pricing page (leads with feature list, "Start Free Trial" CTA, no social proof) → Version B (leads with customer outcome headline, "See It In Action" CTA, added 3 testimonials, removed "unlimited" from free tier description).

**Output**: Changelog with 4 high-impact changes (headline reframed from features to outcomes, CTA changed from trial to demo, social proof added, free tier scope reduced), 1 risk flag (removing "unlimited" from free tier may affect existing customer expectations — verify with legal/support).

## Related Skills

- **[Approval Bottleneck Analyzer](./approval-bottleneck-analyzer.md)** — Track changelog patterns to identify what feedback is causing delays in approvals.
- **[Editorial Calendar Builder](../content/editorial-calendar-builder.md)** — Track content changes over time to inform calendar planning and version management.
- **[Content Performance Scorecard](../content/content-performance-scorecard.md)** — Compare performance of versions before/after major changes noted in changelog.
- **[Content Governance Framework](../content/content-governance-framework.md)** — Use changelog insights to establish change approval and documentation rules.
