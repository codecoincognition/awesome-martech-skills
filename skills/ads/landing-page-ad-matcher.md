---
name: landing-page-ad-matcher
description: >
  Audit the alignment between your ads and landing pages for quality score and conversion impact.
  Use this skill whenever the user mentions ad-to-landing-page alignment, message match, quality
  score optimization, landing page relevance, ad message consistency, "my quality score is low",
  "my ads and landing page don't match", conversion scent, pre-click to post-click alignment,
  landing page audit for ads, ad-landing page mismatch, "why is my CPC so high", ad relevance
  diagnosis, or wants to check if their ads and landing pages are telling the same story. Also
  trigger on "optimize my quality score" or "why isn't my landing page converting ad traffic".
---

# Landing Page Ad Matcher

Audit the message alignment between your ad copy and landing page content. Scores consistency across headlines, keywords, CTAs, and value propositions. Identifies mismatches that hurt quality score and conversion rate.

## Granularity Check

> Can this be completed in a single 10-minute Claude session? **Yes.** Input is ad copy + landing page content. Output is a scored alignment audit with specific fixes.

## User Intent Mapping

Trigger when the user says:

- "Check if my ad matches my landing page" (direct audit)
- "My Google Ads quality score is low" (quality score diagnosis)
- "Why isn't my landing page converting paid traffic?" (conversion diagnosis)
- "Audit my ad-to-page message match" (alignment check)
- "My CPC keeps increasing" (quality score symptom)
- "Does my landing page match my ad copy?" (consistency check)
- "Improve my ad relevance score" (optimization)
- "Check conversion scent from ad to page" (CRO term)
- "I'm getting clicks but no conversions" (funnel diagnosis)
- "Review my PPC landing page" (ad-specific page review)

## Input Contract

### Required Input

| Field | Type | Description |
|---|---|---|
| `ad_copy` | text | Full ad: headlines, descriptions, extensions |
| `landing_page_content` | text | Page content: headline, subheadline, body, CTA |
| `target_keyword` | string | Primary keyword the ad targets |

### Optional Input

| Field | Type | Description |
|---|---|---|
| `ad_platform` | string | Google Ads / Meta / LinkedIn (affects scoring criteria) |
| `quality_score` | integer | Current Google Ads quality score (1-10) |
| `conversion_rate` | float | Current landing page conversion rate |
| `bounce_rate` | float | Current bounce rate from paid traffic |
| `ad_group_keywords` | list | All keywords in the ad group |

### Sample Input

```
Target keyword: project management software

Ad copy:
Headline 1: Best Project Management Software
Headline 2: Free 14-Day Trial - No Credit Card
Headline 3: Trusted by 10,000+ Teams
Description 1: Streamline your projects with intuitive task management, Gantt charts, and team collaboration. Start your free trial today.
Description 2: Replace spreadsheets with real project management. Track deadlines, assign tasks, and see progress at a glance.

Landing page:
H1: The Task Management Tool Your Team Will Actually Use
Subheadline: Organize work, hit deadlines, and collaborate seamlessly
Body: [page content]
CTA: Start Free Trial
```

### Input Validation Rules

1. Both ad copy and landing page content required
2. Target keyword is essential for relevance scoring
3. If only partial landing page provided, note what couldn't be analyzed
4. Flag if ad copy uses dynamic keyword insertion ({KeyWord:default})

## Process

1. **Extract key elements** from both ad and landing page:
   - **Ad elements:** Headlines, descriptions, CTA, display URL, extensions, USPs, offers
   - **Page elements:** H1, subheadline, hero section, CTA button, body copy, social proof, form fields, images

2. **Score alignment across 6 dimensions (each 1-10):**

   **a. Headline Continuity (weight: 25%)**
   - Does the page H1 echo or extend the ad headline?
   - Same keyword present in both?
   - Emotional/logical consistency?
   - Score 10: Page H1 is a natural extension of ad headline
   - Score 1: Completely unrelated headlines

   **b. Keyword Presence (weight: 20%)**
   - Target keyword on the landing page? In H1? In first 100 words?
   - Semantic variations present?
   - Keyword in page title tag?

   **c. Value Proposition Match (weight: 20%)**
   - Same benefits mentioned in both?
   - Ad promises = page delivers?
   - No bait-and-switch (ad says "free", page says "starting at $29")

   **d. CTA Alignment (weight: 15%)**
   - Ad CTA matches page CTA? (e.g., "Start Free Trial" → "Start Free Trial" button)
   - Offer consistency (same discount, same trial length)
   - Single clear next step on page?

   **e. Visual/Emotional Continuity (weight: 10%)**
   - Same tone (if ad is urgent, page should feel urgent)
   - Consistent branding signals
   - Trust elements on page (ad mentions "Trusted by 10K+" → page shows logos)

   **f. Experience Quality (weight: 10%)**
   - Form length appropriate?
   - Page load considerations (note if heavy content)
   - Mobile responsiveness indicators
   - Distracting elements (navigation, competing CTAs)

3. **Calculate overall alignment score** — Weighted average (1-100).

4. **Generate specific fixes** — For each misalignment:
   - Current state (what's wrong)
   - Impact (how it hurts quality score / conversion)
   - Fix (specific rewrite or change)
   - Priority (Critical / High / Medium / Low)

5. **Human checkpoint** — Present the score card. Ask: "Should I rewrite the mismatched elements?"

6. **Generate output** — Audit report with rewrites.

## Output Contract

### Output Format

| Output | Format | Contents |
|---|---|---|
| Alignment audit | Markdown | Scored report with dimension breakdown |
| Fix list | Markdown | Prioritized fixes with rewrites |

### Audit Report Structure

```markdown
# Ad-Landing Page Alignment Audit
Target keyword: [keyword]
Overall Alignment Score: [X]/100 — [Poor/Fair/Good/Excellent]

## Score Card
| Dimension | Score | Weight | Status |
|---|---|---|---|
| Headline Continuity | 6/10 | 25% | ⚠️ Partial match |
| Keyword Presence | 8/10 | 20% | ✅ Good |
| Value Prop Match | 4/10 | 20% | ❌ Mismatch found |
| CTA Alignment | 9/10 | 15% | ✅ Strong |
| Visual/Emotional | 5/10 | 10% | ⚠️ Tone mismatch |
| Experience Quality | 7/10 | 10% | ✅ Acceptable |

## Mismatches Found

### 1. Headline Disconnect (Critical)
**Ad says:** "Best Project Management Software"
**Page says:** "The Task Management Tool Your Team Will Actually Use"
**Problem:** "Project management" → "task management" creates cognitive discontinuity. Visitor questions if they're on the right page.
**Fix — Rewrite page H1:** "Project Management Software Your Team Will Actually Use"

### 2. Value Prop Gap (High)
**Ad promises:** "Gantt charts and team collaboration"
**Page mentions:** Neither Gantt charts nor collaboration in hero section
**Fix:** Add "Gantt charts • Team collaboration • Task tracking" below the H1

[Continue for each mismatch]

## Rewritten Elements
[Ready-to-use rewrites for all flagged issues]

## Expected Impact
- Quality score improvement: [current] → [estimated] (based on fixes)
- Estimated CPC reduction: [X-Y%]
- Estimated conversion rate improvement: [X-Y%]
```

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Can't see landing page | Only URL provided, no content | Ask user to paste page content or HTML source |
| Dynamic ad copy (DKI) | Ad changes per search query | Analyze the default version + note DKI considerations |
| Multiple ads per landing page | Several ad variants | Audit each ad-page pair separately |
| Landing page is a homepage | Not a dedicated landing page | Flag as critical issue — recommend building dedicated landing page |
| No CTA on page | Missing conversion element | Flag as critical — page needs clear CTA |

## How to Get Your Data

### From Google Ads

1. Go to Google Ads → Ads & assets → Ads
2. Click on the ad you want to audit
3. Copy all headlines and descriptions
4. Note the final URL

### Landing Page Content

1. Open the landing page URL
2. Copy all visible text (Ctrl+A → Ctrl+C)
3. Or right-click → "View Page Source" for full HTML
4. Paste into Claude alongside ad copy

### From Google Ads Editor

1. Download account in Google Ads Editor
2. Select ads from target campaign
3. Export ad details
4. Provide alongside landing page content

## Example

**User prompt:** "My Google Ads quality score is 5/10. Check if my ad and landing page match. [provides ad copy and page content]"

**Claude responds:**

> ## Ad-Landing Page Alignment Audit
> **Overall Score: 52/100 — Fair**
>
> | Dimension | Score | Status |
> |---|---|---|
> | Headline Continuity | 4/10 | ❌ Major disconnect |
> | Keyword Presence | 7/10 | ⚠️ Keyword in body but not H1 |
> | Value Prop Match | 5/10 | ⚠️ 2 of 4 ad promises missing from page |
> | CTA Alignment | 9/10 | ✅ Both say "Start Free Trial" |
> | Visual/Emotional | 4/10 | ❌ Ad tone is urgent, page is passive |
> | Experience Quality | 7/10 | ✅ Clean form, single CTA |
>
> **Critical fix:** Your ad headline says "Project Management Software" but your page headline says "Task Management Tool." This mismatch alone likely accounts for 1-2 quality score points.
>
> **Rewritten page H1:** "Project Management Software Your Team Will Actually Use"
>
> Implementing these 4 fixes should improve quality score from 5 → 7-8 and reduce CPC by 15-20%.
>
> Want me to rewrite all the flagged elements?
