---
name: landing-page-optimizer
description: >
  Audit landing page copy for conversion optimization.
  Use this skill whenever the user mentions landing page optimization, conversion rate
  optimization, CRO audit, landing page copy review, or says things like "why isn't my
  landing page converting" or "review my landing page" or "help me improve my signup page."
  Also trigger for value proposition clarity checks, CTA optimization, above-the-fold
  audits, or any request to improve a page's conversion rate. Even "is this page good?"
  when referencing a marketing page should trigger this skill.
---

# Landing Page Optimizer

Audits landing page copy across 5 conversion dimensions, scores each section, and provides specific rewritten copy using proven CRO frameworks (AIDA, PAS, Before-After-Bridge).

## Granularity Check

> Completable in one 10-minute session. Input is page copy or URL. Output is scored audit + rewritten sections.

## User Intent Mapping

- "Review my landing page for conversions" (direct command)
- "Why isn't my landing page converting?" (problem statement)
- "Optimize this signup page copy" (improvement)
- "Is my value proposition clear enough?" (specific check)
- "Rewrite my landing page CTA" (specific element)
- "Audit my product page for CRO" (audit request)
- "My landing page bounce rate is high" (problem-driven)
- "Compare my landing page to best practices" (benchmarking)
- "Help me improve my above-the-fold section" (specific section)
- "Make my landing page more persuasive" (general improvement)

## Input Contract

### Required Input

| Field | Type | Description | Example |
|---|---|---|---|
| `page_copy` | string | Full text from the landing page (or URL for web search) | All visible text, organized by section |

### Optional Input

| Field | Type | Default | Description |
|---|---|---|---|
| `target_action` | string | `"signup"` | What the page should drive: signup, purchase, download, demo |
| `target_audience` | string | `"general"` | Who visits this page |
| `current_conversion_rate` | float | `null` | Current conversion rate for benchmarking |
| `traffic_source` | string | `"mixed"` | Where visitors come from: ads, organic, email, social |
| `competitor_pages` | list of URLs | `[]` | Competitor pages for comparison |

### Input Validation Rules

1. `page_copy` must be at least 50 characters (otherwise too little to audit)
2. If URL provided, attempt web search to gather page content
3. `target_action` helps calibrate CTA scoring

## Process

1. **Parse page content** — Identify sections: headline, subheadline, hero, benefits, social proof, pricing, FAQ, CTA areas.

2. **Score 5 dimensions** (1-10 each):
   - **Value Proposition Clarity** — Can a visitor understand what you do in 5 seconds?
   - **CTA Strength** — Is the action clear, specific, and low-friction?
   - **Social Proof** — Are there testimonials, logos, numbers, case studies?
   - **Friction Points** — What might cause hesitation? (long forms, unclear pricing, no trust signals)
   - **Above-Fold Effectiveness** — Does the visible content without scrolling compel action?

3. **Apply CRO frameworks:**
   - **AIDA:** Attention → Interest → Desire → Action — is the page following this flow?
   - **PAS:** Problem → Agitation → Solution — does it agitate the pain before offering the fix?
   - **Before-After-Bridge:** Before (current pain) → After (desired state) → Bridge (your product)

4. **Human checkpoint** — Present scores and top 3 issues. Ask: "Do these issues match what you're seeing in your analytics? Any sections you want me to focus on rewriting?"

5. **Rewrite low-scoring sections** — For sections scoring below 7, provide rewritten copy with rationale for each change.

6. **Generate quick wins** — List 3-5 changes that take <30 minutes to implement.

## Output Contract

### Output Format

| Output | Format | Contents |
|---|---|---|
| Conversion audit | Markdown | Scores, analysis, framework evaluation |
| Rewritten sections | Markdown | Before/after copy with rationale |
| Quick wins | Markdown | Prioritized easy fixes |

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Too little copy | Single-sentence page | Ask for more context; may be a coming-soon page |
| URL inaccessible | Paywalled or JavaScript-rendered | Ask user to paste the copy directly |
| No clear CTA | Page has no conversion action | Flag as critical issue; recommend adding a CTA |
| Multiple CTAs competing | Too many actions on one page | Recommend primary vs. secondary CTA hierarchy |
| Copy is great but page still doesn't convert | Design, speed, or traffic issues | Note limitations of copy-only audit; suggest UX/speed checks |

## Example

**User prompt:** "Review this landing page copy for our project management tool signup page: [pastes hero section, benefits, pricing, CTA]"

**Claude output:**

> ## Conversion Audit: TaskFlow Signup Page
>
> | Dimension | Score | Notes |
> |---|---|---|
> | Value Proposition Clarity | 6/10 | "Manage projects better" is vague — what specifically improves? |
> | CTA Strength | 4/10 | "Get Started" is generic. No mention of free trial or time commitment. |
> | Social Proof | 3/10 | No testimonials, customer logos, or usage numbers visible. |
> | Friction Points | 7/10 | Short form (email only) is good. Pricing is clear. |
> | Above-Fold Effectiveness | 5/10 | Headline doesn't address a specific pain point. |
>
> **Overall: 5.0/10** — Page has structural foundation but copy needs significant work.
>
> ## Rewrites
>
> **Headline (Before):** "Manage Projects Better"
> **Headline (After):** "Stop Losing 5 Hours/Week to Status Meetings"
> **Rationale:** Specific pain point + quantified benefit > generic improvement claim.
>
> **CTA (Before):** "Get Started"
> **CTA (After):** "Start Your Free 14-Day Trial — No Credit Card"
> **Rationale:** Removes two friction points: cost uncertainty and commitment anxiety.
>
> ## Quick Wins (< 30 min each)
> 1. Add 3 customer logos above the fold
> 2. Change CTA from "Get Started" to "Try Free for 14 Days"
> 3. Add a testimonial quote next to the signup form
