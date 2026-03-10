---
name: email-sequence-builder
description: >
  Design multi-step email sequences with timing, subject lines, body copy, and conditional logic.
  Use this skill whenever the user mentions email sequence, email drip campaign, nurture sequence,
  onboarding emails, re-engagement emails, email automation, email workflow, multi-email series,
  "build an email sequence", "create a drip campaign", email cadence, lead nurturing emails,
  follow-up email series, post-purchase email sequence, trial-to-paid email flow, or any request
  to create a connected series of automated emails. Also trigger on "set up email automation",
  "plan my email drips", or "design an email nurture flow". For welcome emails specifically,
  chain with welcome-series-creator for deeper welcome flow design.
---

# Email Sequence Builder

Design complete multi-step email sequences for any purpose: nurture, onboarding, re-engagement, post-purchase, trial conversion, event follow-up. Includes timing, subject lines, body copy, conditional branching, and platform-ready export.

## Granularity Check

> Can this be completed in a single Claude session? **Yes — expect ~5 min data prep → ~10 min Claude session → ~30-45 min setup in Mailchimp / Klaviyo / HubSpot.** If implementing output in a platform, add 10-20 min for setup. Input is sequence purpose + audience context. Output is a complete email sequence with full copy. No integrations needed.

## User Intent Mapping

Trigger when the user says:

- "Build a 5-email nurture sequence" (direct request)
- "Create a drip campaign for new leads" (lead nurture)
- "Design onboarding emails for trial users" (onboarding)
- "I need re-engagement emails for inactive subscribers" (win-back)
- "Plan a post-purchase email series" (customer journey)
- "Build an email sequence to convert free trial to paid" (conversion)
- "Create follow-up emails after a webinar" (event follow-up)
- "Design an email cadence for cold prospects" (outbound sales)
- "I need abandoned cart recovery emails" (e-commerce)
- "Set up a lead nurturing workflow" (marketing automation)

## Input Contract

### Required Input

| Field | Type | Description |
|---|---|---|
| `sequence_type` | string | Nurture / Onboarding / Re-engagement / Post-purchase / Trial conversion / Event follow-up / Cold outreach |
| `audience` | string | Who receives this sequence |
| `goal` | string | What you want recipients to do |

### If You Don't Have This Data

- **No email platform?** Start with Mailchimp's free tier (500 contacts) or use Google Sheets to draft sequences before importing.
- **No subscriber list?** This skill designs the sequence structure. Collect emails via a signup form first, then apply the output.
- **No performance benchmarks?** Industry averages: B2B open rates 20-25%, click rates 2-4%. B2C: open 18-22%, click 2-3%.
- **No segmentation?** Start with one sequence for all subscribers. Segment after you have 500+ contacts.

### Optional Input

| Field | Type | Default | Description |
|---|---|---|---|
| `num_emails` | integer | 5 | Number of emails in sequence |
| `brand_voice` | string | Professional | Tone and style |
| `product_description` | string | Generic SaaS | What you're selling/promoting |
| `key_benefits` | list | Inferred | Top 3-5 product/service benefits |
| `cta_url` | string | [CTA link] | Primary call-to-action destination |
| `sender_name` | string | [Company] Team | From name |
| `exit_conditions` | list | Conversion | When to stop the sequence |
| `platform` | string | Generic | HubSpot / Mailchimp / ActiveCampaign / Klaviyo / Generic |
| `include_conditional_logic` | boolean | true | Include if/then branching |

### Input Validation Rules

1. Sequence type determines template structure — ask if ambiguous
2. Number of emails should be 3-10 (warn if >10 — likely needs splitting)
3. Goal should be specific and measurable (e.g., "book a demo" not "engage leads")
4. If brand voice examples provided, match them closely

## Process

1. **Define sequence architecture:**
   - Map sequence type to proven framework
   - **Nurture:** Problem → Education → Social proof → Differentiation → CTA
   - **Onboarding:** Welcome → Quick win → Core feature → Advanced feature → Habit
   - **Re-engagement:** "Miss you" → Value reminder → Special offer → Last chance → Sunset
   - **Trial conversion:** Welcome → Quick win → Aha moment → Social proof → Upgrade CTA → Last day
   - **Post-purchase:** Thank you → Getting started → Pro tip → Cross-sell → Review request

2. **Set timing cadence:**
   - Email 1: Immediate trigger (or Day 0)
   - Calculate optimal gaps based on sequence type:
     - Nurture: 3-5 days between emails
     - Onboarding: 1-2 days (faster cadence)
     - Re-engagement: 4-7 days
     - Trial conversion: aligned with trial duration (e.g., Day 1, 3, 5, 10, 13 for 14-day trial)

3. **Write each email with:**
   - **Subject line:** 3 options per email (A/B test ready) with character count
   - **Preview text:** 40-90 characters that complement the subject
   - **Body copy:** Full email content with formatting markers
   - **CTA:** Button text + link destination
   - **Send timing:** Day + optimal time of day
   - **Goal of this email:** What it should accomplish in the sequence

4. **Add conditional logic:**
   - What happens if they click? (move to next email faster or skip ahead)
   - What happens if they don't open? (resend with new subject line)
   - Exit conditions: conversion, unsubscribe, N-day inactivity

5. **Human checkpoint** — Present the sequence structure (email purposes + timing). Ask: "Does this flow make sense? Any emails to add, remove, or reorder?"

6. **Generate output** — Full sequence document with all copy + CSV for platform import.


> **Benchmark Context**: Average B2B email open rate is 21.3%, click rate 2 (Mailchimp 2024 Email Marketing Benchmarks). 6% (Mailchimp 2024 Email Marketing Benchmarks) Welcome emails average 50-60% open rates — the highest of any email type (Mailchimp 2024 Email Marketing Benchmarks) Segmented campaigns see 14% higher open rates than non-segmented (Mailchimp 2024 Email Marketing Benchmarks) Best send times: B2B Tuesday-Thursday 9-11 AM local time (Campaign Monitor 2024 Email Benchmarks) (Mailchimp 2024 Email Marketing Benchmarks)


### Confidence & Sample Size.
> **Confidence Note**: Results are only as reliable as your input data. Small datasets (<50 records or <30 days of data) produce directional insights, not statistically significant conclusions. Always note your sample size when sharing results with stakeholders. Recommendations should be validated with A/B testing or additional data before making major strategic changes.

## Output Contract

### Output Format

| Output | Format | Contents |
|---|---|---|
| Full sequence | Markdown | Complete emails with copy and logic |
| Import-ready data | CSV | Subject, body, timing for platform import |

### Sequence Document Structure

```markdown
# Email Sequence: [Name]
Type: [Nurture/Onboarding/etc.]
Emails: [N]
Duration: [X days]
Goal: [Primary conversion action]

## Sequence Flow
[Visual flow with timing]
Trigger → Email 1 (Day 0) → Wait 3 days → Email 2 (Day 3) → ...

## Email 1: [Purpose Name]
**Send:** Day 0, triggered by [event]
**Subject lines:**
  A: [subject] (42 chars)
  B: [subject] (38 chars)
  C: [subject] (45 chars)
**Preview text:** [preview]
**From:** [sender name]
**Goal:** [what this email should accomplish]

---
[Full email body with formatting]
---

**CTA:** [Button text] → [URL]
**If opened + clicked:** Move to Email 2 immediately
**If not opened after 48h:** Resend with Subject B
**Exit if:** [condition]

[Repeat for each email]

## Conditional Logic Summary
[Decision tree / branching rules]
```

### CSV Export Columns

| Column | Type | Description |
|---|---|---|
| `email_number` | integer | Position in sequence |
| `email_name` | string | Internal reference name |
| `subject_line_a` | string | Primary subject |
| `subject_line_b` | string | A/B test variant |
| `preview_text` | string | Preheader text |
| `body_html` | string | Email body (basic HTML) |
| `cta_text` | string | Button copy |
| `cta_url` | string | Button destination |
| `send_delay_days` | integer | Days after trigger |
| `send_time` | string | Optimal send time |

## Platform Implementation Steps

### Mailchimp
1. Navigate to Campaigns → Create Campaign → Email
2. Choose your audience/segment
3. Paste subject lines and preview text into the header fields
4. Build email body using the drag-and-drop editor or paste HTML
5. Schedule or send using the recommended timing

### HubSpot Email
1. Go to Marketing → Email → Create Email
2. Select template, paste content into modules
3. Use Personalization Tokens for dynamic fields
4. Set up A/B test on subject line if applicable
5. Select recipient list and schedule

### Any ESP (Generic)
1. Create a new campaign/email in your platform
2. Copy subject line and preview text into header fields
3. Paste body content and format using your template
4. Test send to yourself before scheduling
5. Monitor open rates and click rates for 48 hours post-send

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Unclear sequence type | "Just send some emails" | Ask: "What event triggers email 1? What should recipients do by the last email?" |
| Too many emails (>10) | Over-ambitious scope | Suggest splitting into two sequences with a re-qualification step |
| No product context | Generic request | Ask for product description + key benefits; use as foundation |
| Conflicting goals | Multiple CTAs | Recommend one primary CTA per sequence; secondary CTAs in specific emails only |
| No exit conditions | Incomplete design | Default to: stop on conversion, unsubscribe, or sequence completion |

## How to Get Your Data

### Starting Fresh (Most Common)

1. Tell Claude the sequence type, audience, and goal
2. Provide product/service description and key benefits
3. Claude designs the complete sequence

### From Existing Emails (Improvement)

1. Paste your current email sequence
2. Claude analyzes flow, timing, and copy quality
3. Generates improved version with recommendations

### From CRM/Platform Export

1. Export current sequence from HubSpot/Mailchimp/etc.
2. Include performance data if available (open rates, click rates)
3. Claude redesigns underperforming emails

## Example

**User prompt:** "Build a 5-email nurture sequence for SaaS leads who downloaded our 'Project Management Guide'. Goal is to get them to start a free trial."

**Claude responds:**

> Here's the sequence architecture:
>
> **Sequence:** Guide Download → Free Trial Conversion
> **Duration:** 14 days | **Emails:** 5
>
> | # | Day | Purpose | Subject Line (A) |
> |---|---|---|---|
> | 1 | 0 | Deliver guide + quick win | Your PM Guide is ready (+ a 2-min tip inside) |
> | 2 | 3 | Educate on core problem | The #1 reason projects go over budget |
> | 3 | 7 | Social proof | How [Company X] cut project delays by 34% |
> | 4 | 10 | Product differentiation | What most PM tools get wrong |
> | 5 | 14 | Direct CTA + urgency | Ready to fix your project management? |
>
> Each email includes 3 subject line options, preview text, full body copy, and CTA.
>
> **Conditional logic:**
> - If they click CTA in any email → skip remaining and trigger "Trial Welcome" sequence
> - If email 3 not opened → resend with subject B after 48h
> - If no opens after email 5 → add to "Cold re-engagement" list
>
> Want me to generate the full copy for all 5 emails?

## Related Skills

- **[Email Copywriting Framework](./email-copywriting-framework.md)** — Use to write compelling copy for each email in your sequence.
- **[Email List Segmentation](./email-list-segmentation.md)** — Use to create targeted sequences for specific audience segments identified in your segmentation strategy.
- **[Email Automation Workflow](./email-automation-workflow.md)** — Use to translate your sequences into triggered automation workflows with branching logic.
- **[Email Performance Analyzer](./email-performance-analyzer.md)** — Use after sequences launch to analyze performance and optimize future sequences.
