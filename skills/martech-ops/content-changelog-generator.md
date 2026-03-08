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

> Can this be completed in a single 10-minute Claude session? **Yes.** Input is two text versions. Output is a Markdown changelog. No external tools needed.

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

### ⚠️ Human Checkpoint
> Review any changes flagged as "removed" — especially disclaimers, legal language, or data claims. Removals can carry compliance risk.

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
