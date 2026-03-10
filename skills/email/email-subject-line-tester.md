---
name: email-subject-line-tester
description: >
  Evaluate and improve email subject lines using proven frameworks.
  Use this skill whenever the user mentions email subject lines, email open rates,
  subject line testing, email headlines, A/B testing subject lines, or says things like
  "will this subject line work" or "help me write better email subjects" or "my open
  rates are low." Also trigger for email marketing optimization, email copy review,
  or when someone shares subject lines and asks for feedback. Even casual requests
  like "which of these subjects is better" should use this skill.
---

# Email Subject Line Tester

Scores email subject lines across 6 dimensions (clarity, urgency, curiosity, personalization, length optimization, spam risk) and generates 5 improved alternatives per line using proven copywriting frameworks.

## Granularity Check

> **Session time**: ~5 minutes data prep + ~10 minutes Claude session. If implementing output in a platform, add 10-20 minutes for setup. Input is 1-10 subject lines. Output is a scored analysis + improved variants.

## User Intent Mapping

- "Score these email subject lines" (direct command)
- "Which subject line will get more opens?" (comparison)
- "My email open rates are dropping, help with subject lines" (problem statement)
- "Write better subject lines for my product launch email" (generation)
- "A/B test ideas for my newsletter subject" (testing)
- "Is this subject line spammy?" (spam check)
- "Make this subject line more compelling" (improvement)
- "I need 5 subject line variants for this email" (variant generation)
- "Review my email subjects before I send" (pre-send check)
- "Help me improve my Mailchimp campaign subject lines" (tool-specific)

## Input Contract

### Required Input

| Field | Type | Description | Example |
|---|---|---|---|
| `subject_lines` | list of strings (1-10) | Subject lines to evaluate | `["Your Q2 Report Is Ready", "Don't Miss This Limited Offer"]` |

### If You Don't Have This Data

- **No email platform?** Start with Mailchimp's free tier (500 contacts) or use Google Sheets to draft sequences before importing.
- **No subscriber list?** This skill designs the sequence structure. Collect emails via a signup form first, then apply the output.
- **No performance benchmarks?** Industry averages: B2B open rates 20-25%, click rates 2-4%. B2C: open 18-22%, click 2-3%.
- **No segmentation?** Start with one sequence for all subscribers. Segment after you have 500+ contacts.

### Optional Input

| Field | Type | Default | Description |
|---|---|---|---|
| `industry` | string | `"general"` | Industry for benchmarking |
| `audience` | string | `"general"` | Target recipient description |
| `email_type` | string | `"marketing"` | newsletter, promotional, transactional, drip |
| `brand_tone` | string | `"professional"` | casual, professional, playful, urgent |
| `past_performance` | CSV | `null` | Historical subject line + open rate data |

### Input Validation Rules

1. At least 1 subject line required
2. Maximum 10 subject lines per batch
3. Subject lines should be 1-150 characters (warn outside range)

## Process

1. **Score each subject line** on 6 dimensions (1-10 scale):
   - **Clarity** — Is the value proposition immediately clear?
   - **Urgency** — Does it create time pressure or FOMO?
   - **Curiosity** — Does it create an information gap?
   - **Personalization** — Does it feel addressed to the reader?
   - **Length** — Is it optimized for mobile (30-50 chars ideal) and desktop?
   - **Spam Risk** — Does it use trigger words, ALL CAPS, or excessive punctuation?

2. **Calculate overall score** — Weighted average (clarity 25%, curiosity 20%, personalization 20%, length 15%, urgency 10%, spam risk 10%).

3. **Generate 5 alternatives** per subject line using frameworks:
   - **Curiosity gap:** Create an information gap the reader needs to close
   - **Benefit-driven:** Lead with what the reader gets
   - **Social proof:** Reference numbers, peers, or authority
   - **Question:** Ask a question the reader wants answered
   - **Personalized:** Use "you/your" and specific context

4. **Human checkpoint** — Present scores and top alternatives. Ask: "Do any of these alternatives match your brand voice? Want me to adjust the tone?"

5. **Finalize** — Deliver scored analysis with recommendations.


> **Benchmark Context**: Average B2B email open rate is 21.3%, click rate 2.6%. Welcome emails average 50-60% open rates — the highest of any email type. Segmented campaigns see 14% higher open rates than non-segmented. Best send times: B2B Tuesday-Thursday 9-11 AM local time.


### Confidence & Sample Size
> **Confidence Note**: Results are only as reliable as your input data. Small datasets (<50 records or <30 days of data) produce directional insights, not statistically significant conclusions. Always note your sample size when sharing results with stakeholders. Recommendations should be validated with A/B testing or additional data before making major strategic changes.

## Output Contract

### Output Format

| Output | Format | Contents |
|---|---|---|
| Scored analysis | Markdown | Dimension scores + overall grade per subject line |
| Improved variants | Markdown | 5 alternatives per original with rationale |

### Score Table Format

```markdown
| Subject Line | Clarity | Urgency | Curiosity | Personal | Length | Spam | Overall |
|---|---|---|---|---|---|---|---|
| "Original line" | 7 | 3 | 5 | 4 | 8 | 9 | 6.2 |
```

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
| Subject line is just a word | Too vague to score | Ask for full subject line with context |
| Non-English subject line | Language barrier | Note limitation; provide best-effort analysis |
| All lines score poorly | Fundamental messaging issue | Suggest rethinking the email's core value proposition |
| Subject line has merge tags | `{{first_name}}` syntax | Score with and without personalization token |
| Spam score is high | Trigger words detected | Identify specific triggers and suggest alternatives |

## How to Get Your Data

### From Mailchimp

1. Go to Campaigns → All Campaigns
2. Click on a past campaign
3. Note the subject line and open rate
4. Repeat for 5-10 campaigns to build a performance history

### From HubSpot

1. Go to Marketing → Email
2. Sort by open rate
3. Export the list with subject lines and metrics

### From Klaviyo

1. Go to Campaigns tab
2. Sort by open rate
3. Note top-performing vs. low-performing subject lines

## Example

**User prompt:** "Score these subject lines for our SaaS newsletter: 1) 'Your Weekly Product Update' 2) 'You're Missing This Feature (And It's Costing You Hours)' 3) '🚀 BIG NEWS: We Just Launched Something Amazing!!!'"

**Claude output:**

> | Subject Line | Clarity | Urgency | Curiosity | Personal | Length | Spam | Overall |
> |---|---|---|---|---|---|---|---|
> | "Your Weekly Product Update" | 9 | 1 | 2 | 5 | 9 | 10 | 5.7 |
> | "You're Missing This Feature..." | 7 | 6 | 8 | 8 | 6 | 8 | 7.3 |
> | "🚀 BIG NEWS: We Just Launched..." | 4 | 3 | 5 | 1 | 4 | 2 | 3.2 |
>
> **Analysis:**
> - Line 1 is clear but boring — zero curiosity or urgency. Reliable but won't drive high opens.
> - Line 2 is the strongest — creates curiosity gap with personal relevance.
> - Line 3 has multiple spam triggers: emoji, ALL CAPS, exclamation marks, vague claim.
>
> **Top 5 alternatives for Line 1:**
> 1. "3 features your team missed this week" (curiosity + specificity)
> 2. "What changed in [Product] this week (2-min read)" (benefit + time commitment)
> 3. "Your team is asking about these updates" (social proof + personalization)
> 4. "This week's update saves you 2 hours/week" (benefit-driven)
> 5. "Quick question about how you use [Feature]" (question + personalization)
