---
name: form-optimization-toolkit
description: >
  Optimize web forms for higher completion rates — field reduction, UX improvements, and multi-step design.
  Use this skill when the user says "form optimization", "form conversion rate", "lead form
  optimization", "form completion rate improvement", "form field reduction", "multi-step form
  design", "form UX best practices", "signup form optimization", "contact form optimization",
  "form abandonment reduction", or "form A/B testing". Also trigger for progressive profiling
  form design, conditional form logic, or form analytics setup.
---

# Form Optimization Toolkit

Optimizes web forms for higher completion rates through field reduction, UX improvements, multi-step design, progressive profiling, and data-driven testing.

## Granularity Check

> **Time**: ~5 min data prep → ~10 min Claude session → ~30-60 min implementing in your testing tool / CMS. If implementing, add 1-3 days for form redesign. Input is current form design and conversion data. Output is Markdown optimization plan with specific form recommendations.

## User Intent Mapping

- "Our form conversion is too low" (optimization)
- "How many form fields is optimal?" (field count)
- "Multi-step vs. single-step form" (design)
- "Lead form best practices" (best practices)
- "Form A/B test ideas" (testing)
- "Progressive profiling setup" (progressive)
- "Mobile form optimization" (mobile)
- "Form abandonment — which field do people drop off?" (analytics)
- "Signup form optimization" (signup)
- "Contact form isn't getting submissions" (contact)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Form Purpose | Text | Lead gen, signup, contact, checkout |
| Current Fields | Text | List of form fields |
| Current Conversion Rate | Text | Form starts vs. completions |

### If You Don't Have This Data

- **No form analytics?** Claude recommends tracking setup (form starts, field-level drop-off, completions) and provides optimization based on form review.
- **No conversion data?** Claude uses industry benchmarks and UX best practices to identify improvement opportunities.
- **Can't reduce fields?** Claude focuses on UX improvements (layout, copy, validation) that increase completion without removing fields.
- **No development resources?** Claude recommends no-code form tools (Typeform, Tally, HubSpot) with built-in optimization features.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Form Analytics | CSV | Field-level completion rates and drop-off data |
| Heatmap Data | Screenshots | Where users click, scroll, and hesitate |
| Mobile Conversion | Text | Mobile vs. desktop form completion rates |
| A/B Test History | Text | Past form tests and results |
| Lead Quality Data | Text | How form leads convert downstream |

## Process

### Step 1: Form Audit
- Field count (benchmark: 3-5 fields for lead gen, 5-8 for qualification)
- Required vs. optional fields (are all required fields truly necessary?)
- Field types (text vs. dropdown vs. radio — match input to data type)
- Field labels and placeholder text (clear, concise, unambiguous)
- Error handling (inline validation vs. submit-and-fail)
- CTA button text (specific action vs. generic "Submit")
- Mobile experience (thumb-friendly, appropriate keyboard types)

### Step 2: Field Reduction Analysis
| Field | Business Need | Alternative | Recommendation |
|---|---|---|---|
| Phone number | Sales callback | Make optional or defer to follow-up | Remove or make optional |
| Company name | Lead qualification | Enrich from email domain | Remove, auto-populate |
| Company size | Lead scoring | Progressive profiling | Defer to second interaction |
| Job title | Persona matching | LinkedIn enrichment | Remove, enrich later |
| Address | Shipping only | Ask only when needed | Remove from lead forms |

### Step 3: UX Optimization
- Single-column layout (25% higher completion than multi-column)
- Top-aligned labels (fastest to complete)
- Inline validation with positive feedback (green checkmarks)
- Smart defaults and autocomplete (email domain suggestion, address autocomplete)
- Progress indicator for multi-step forms
- Social login options (reduce typing for signups)
- Mobile-first design (large tap targets, appropriate keyboards)

### Step 4: Multi-Step Form Design
When to use multi-step:
- More than 5 fields required
- Mix of easy and hard questions (start easy)
- Need to qualify without overwhelming

Structure:
- Step 1: Low-commitment fields (name, email) — establish investment
- Step 2: Qualifying fields (company, role) — they're already invested
- Step 3: Detailed fields (budget, timeline) — committed users only
- Each step: progress indicator, back button, save progress

### Step 5: Copy Optimization
- Headline: clear value proposition above form ("Get Your Free Audit")
- Subheadline: what they get + how long it takes ("30-second signup")
- Field labels: conversational, not database-like ("Work email" not "Business email address")
- CTA: specific action + value ("Get My Free Report" not "Submit")
- Social proof: near form (testimonials, customer logos, user count)
- Privacy: brief reassurance near email field ("No spam, ever")

### Step 6: Progressive Profiling
- First form: name + email only (highest conversion)
- Second touchpoint: company + role (gated content download)
- Third touchpoint: size + budget (demo request)
- CRM enrichment: auto-fill firmographic data from email domain
- Each interaction: only ask what you don't already know

### Confidence & Sample Size

> **Confidence Note**: Form optimization A/B tests need 200+ completions per variant for statistical significance. Reducing one field typically increases conversion 5-10%. The biggest gains come from reducing fields, not polishing UX. Lead quality may change when you simplify forms — track downstream conversion, not just form completion. Mobile form optimization often yields 2-3x the lift of desktop optimization.

### ⚠️ Human Checkpoint
> Verify that field reductions don't eliminate data needed for lead routing or qualification. Test form changes across devices and browsers. Confirm CRM integration still works after form modifications.

> **Benchmark Context**: See Contentsquare 2024 Digital Experience Benchmark, and Unbounce 2024 Conversion Benchmark Report for current industry benchmarks relevant to this analysis.
## Output Contract

### Deliverable: Markdown Form Optimization Plan

```markdown
# Form Optimization: [Form Name]

## Current State
- Fields: [count]
- Conversion rate: [%]
- Mobile conversion: [%]

## Field Analysis
| Field | Status | Recommendation | Expected Impact |
|---|---|---|---|

## Optimized Form Design
### Fields (Recommended)
1. [Field] — [type] — [required/optional]

### Layout
- [Design specifications]

### Copy
- Headline: [text]
- CTA: [text]
- Social proof: [element]

## Multi-Step Design (if applicable)
### Step 1:
- Fields: [list]
### Step 2:
- Fields: [list]

## A/B Test Plan
| Test | Control | Variant | Metric |
|---|---|---|---|

## Expected Results
- Conversion: [current] → [target]
- Lead volume change: [estimate]
```

## Platform Implementation Steps

### HubSpot Forms
1. Forms → edit existing form or create new
2. Remove unnecessary fields; mark others as optional
3. Enable progressive profiling (Enterprise: Smart Fields)
4. Set up dependent fields (show/hide based on answers)
5. Configure follow-up automation based on form data

### WordPress (Gravity Forms, WPForms)
1. Audit and reduce form fields
2. Enable conditional logic for relevant fields
3. Add multi-step pagination for long forms
4. Configure Ajax submission (no page reload)
5. Set up form analytics (MonsterInsights or native)

### No-Code (Typeform, Tally)
1. Create conversational multi-step form
2. Add logic jumps based on answers
3. Embed on website with optimized sizing
4. Connect to CRM via Zapier or native integration

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Higher completion but lower lead quality | Removed qualifying fields | Add progressive profiling; enrich data post-submission; score leads |
| Form breaks on mobile | Desktop-first design | Test on multiple devices; use responsive form builders; simplify for mobile |
| CRM integration fails | Field mapping changed | Test CRM sync after every form change; verify data flows end-to-end |
| Multi-step abandonment | Steps too long or confusing | Keep 2-4 fields per step; add progress indicator; allow saving |

## How to Get Your Data

- **Form analytics**: HubSpot → Forms → Performance; or Google Analytics → Events → form interactions
- **Field-level data**: Hotjar/FullStory → form analysis; or CRM → check which fields are most/least filled
- **Conversion rate**: Form views ÷ form submissions (GA4 or form platform analytics)
- **No data**: Share your current form fields and purpose — Claude identifies optimization opportunities

## Example

**Input**: "Form optimization for B2B SaaS demo request form. 9 fields: first name, last name, work email, phone, company, job title, company size, industry, message. Current conversion: 4.2%. Mobile: 2.1%. 500 monthly form views."

**Output**: Problem: 9 fields is 2x the optimal for a demo request. Phone, industry, and message are likely causing friction. Recommended form (4 fields): work email (required), first name (required), company (required), company size (dropdown, required for routing). Removed fields: last name (enrichable from email), phone (ask on demo scheduling page), job title (enrich from LinkedIn/Clearbit), industry (enrich from company domain), message (unnecessary for demo booking). Design: single-column, inline validation, CTA: "Book My Demo — 30 minutes, no commitment." Add below form: "Join 500+ companies using [Product]" with 3 customer logos. Mobile: large input fields, auto-focus first field, numeric keyboard for phone if kept. Progressive profiling: after form submit, redirect to Calendly/Chilipiper scheduling page that captures phone and additional context. Expected results: conversion 4.2% → 9-11% (120-160% improvement). Monthly leads: 21 → 45-55. Lead quality maintained via enrichment (Clearbit or similar auto-fills company size, industry, revenue from email domain).

## Related Skills

- **ab-test-designer** (./ab-test-designer.md) — Design A/B tests for form changes (field count, copy, multi-step vs. single-step); use to validate which optimizations drive highest completion.
- **cta-optimization-framework** (./cta-optimization-framework.md) — Optimize form button copy and design; use to make form CTAs more compelling and action-oriented.
- **heatmap-analysis-toolkit** (./heatmap-analysis-toolkit.md) — Analyze where users click, hesitate, and abandon forms using heatmaps; identify which form fields cause friction.
- **landing-page-optimizer** (./landing-page-optimizer.md) — Optimize form context (headline, copy, social proof above form); use to create compelling form pages that drive completion.
