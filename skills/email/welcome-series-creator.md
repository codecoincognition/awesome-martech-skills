---
name: welcome-series-creator
description: >
  Generate a complete welcome email series (3-7 emails) with progressive profiling, value delivery,
  and soft CTA escalation. Use this skill whenever the user mentions welcome emails, welcome series,
  welcome sequence, new subscriber emails, new user onboarding emails, first-touch email series,
  "what emails should new subscribers get", new customer welcome, sign-up email flow, subscriber
  onboarding, "create welcome emails for my list", or any request specifically about emails for
  brand-new subscribers or sign-ups. This is more specialized than email-sequence-builder — it
  focuses specifically on the critical first-impression welcome window (first 7-14 days).
---

# Welcome Series Creator

Create a complete welcome email series that turns new subscribers into engaged audience members or customers. Focuses on the critical first-impression window with progressive value delivery, expectation setting, and gentle conversion nudges.

## Granularity Check

> Can this be completed in a single Claude session? **Yes — expect ~5 min data prep → ~10 min Claude session → ~30-45 min setup in Mailchimp / Klaviyo / HubSpot.** If implementing output in a platform, add 10-20 min for setup. Input is business context + subscriber source. Output is 3-7 complete emails with full copy.

## User Intent Mapping

Trigger when the user says:

- "Create welcome emails for new subscribers" (direct request)
- "What should I send people when they first sign up?" (question)
- "Build a welcome series for my newsletter" (newsletter-specific)
- "Design onboarding emails for new app users" (SaaS onboarding)
- "I need a welcome sequence for e-commerce customers" (e-commerce)
- "Set up emails for when someone joins my email list" (list building)
- "Create a first-touch email experience" (experience design)
- "My welcome email is just one email — I need a series" (improvement)
- "Build progressive profiling into my welcome flow" (advanced)
- "What's the best welcome email sequence?" (best practices)

## Input Contract

### Required Input

| Field | Type | Description |
|---|---|---|
| `business_type` | string | SaaS / E-commerce / Newsletter / B2B Services / Course/Education |
| `subscriber_source` | string | How they signed up (lead magnet, newsletter, free trial, purchase) |
| `primary_value_prop` | string | Main reason someone subscribes/signs up |

### If You Don't Have This Data

- **No email platform?** Start with Mailchimp's free tier (500 contacts) or use Google Sheets to draft sequences before importing.
- **No subscriber list?** This skill designs the sequence structure. Collect emails via a signup form first, then apply the output.
- **No performance benchmarks?** Industry averages: B2B open rates 20-25%, click rates 2-4%. B2C: open 18-22%, click 2-3%.
- **No segmentation?** Start with one sequence for all subscribers. Segment after you have 500+ contacts.

### Optional Input

| Field | Type | Default | Description |
|---|---|---|---|
| `num_emails` | integer | 5 | 3-7 emails |
| `brand_voice` | string | Friendly professional | Tone |
| `lead_magnet` | string | null | What they downloaded/received at sign-up |
| `key_content` | list | null | Best content to share (top blog posts, resources) |
| `conversion_goal` | string | Engagement | Purchase / Trial start / Upgrade / Engagement |
| `social_channels` | list | null | Social profiles to promote |
| `frequency_expectation` | string | Weekly | How often you'll email after welcome series |
| `segmentation_questions` | list | null | Questions for progressive profiling |

### Input Validation Rules

1. Business type determines series structure — ask if unclear
2. Subscriber source affects email 1 content (deliver the lead magnet vs. confirm subscription)
3. 3-7 emails is the sweet spot — fewer misses opportunities, more risks fatigue
4. If no content to share, Claude suggests content topics to create

## Process

1. **Design the welcome arc** — Map the emotional journey:
   - **Email 1 (Day 0):** Deliver + delight — exceed expectations on sign-up promise
   - **Email 2 (Day 1-2):** Introduce yourself — brand story, mission, what to expect
   - **Email 3 (Day 3-4):** Quick win — most popular/useful resource
   - **Email 4 (Day 5-7):** Social proof — testimonials, community, results
   - **Email 5 (Day 8-10):** Progressive profile — learn about them (survey/preference)
   - **Email 6 (Day 11-13):** Soft conversion — gentle CTA aligned with their interest
   - **Email 7 (Day 14):** Set expectations — transition to regular email cadence

2. **Write each email:**
   - Subject line: 3 options, optimized for opens (curiosity, benefit, personal)
   - Preview text: complementary teaser (40-90 chars)
   - Body: conversational, scannable, single-focus per email
   - CTA: one primary action (don't split attention)
   - P.S. line: secondary link or personal touch

3. **Progressive profiling** — In email 5, include a micro-survey or preference selector:
   - 2-3 questions maximum
   - Multiple choice (clickable links that tag/segment)
   - "What topics interest you most?" / "What's your biggest challenge?"
   - Used to personalize remaining emails + ongoing content

4. **Human checkpoint** — Present series structure. Ask: "Does this arc feel right for your audience? Should I adjust the conversion timing or add/remove emails?"

5. **Generate output** — Complete series with all copy.


> **Benchmark Context**: Average email open rate is 42.35% and click-through rate is 2.09% (MailerLite 2025 Email Marketing Benchmarks). Average email ROI is $36 per $1 spent (Forbes Advisor, 2025). Automated emails achieve 42.1% open rates and 5.4% click rates, generating 320% more revenue than manual campaigns (Genesys Growth, 2025).


### Confidence & Sample Size.
> **Confidence Note**: Results are only as reliable as your input data. Small datasets (<50 records or <30 days of data) produce directional insights, not statistically significant conclusions. Always note your sample size when sharing results with stakeholders. Recommendations should be validated with A/B testing or additional data before making major strategic changes.

## Output Contract

### Output Format

| Output | Format | Contents |
|---|---|---|
| Welcome series | Markdown | Full email copy for all emails |
| Series summary | Markdown | Arc overview + timing |

### Series Document Structure

```markdown
# Welcome Series: [Business Name]
Emails: [N] | Duration: [X days] | Goal: [conversion goal]
Subscriber source: [how they signed up]

## Series Arc
Day 0: Deliver & Delight → Day 2: Brand Story → Day 4: Quick Win → ...

## Email 1: "The Welcome" (Day 0)
**Purpose:** Deliver the sign-up promise + set expectations
**Subject lines:**
  A: [subject] (chars)
  B: [subject] (chars)
  C: [subject] (chars)
**Preview text:** [text]

---
Hi [First Name],

[Full email body]

[CTA Button: Text]

P.S. [secondary hook]
---

**Design notes:** [layout suggestions — image placement, button color, etc.]
**Segment tag:** new-subscriber, source:[lead-magnet-name]

[Repeat for each email]

## Progressive Profiling Setup (Email 5)
**Questions:**
1. [Question → segment tag per answer]
2. [Question → segment tag per answer]

## Post-Series Transition
After email [N], subscriber moves to:
- Regular newsletter cadence ([frequency])
- Segmented content based on profile answers
- [Conversion path if not yet converted]
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
| No lead magnet | Subscriber source is organic | Email 1 becomes a curated "best of" content delivery |
| No existing content to share | New business | Email 3 delivers original insight or tip instead of linking to content |
| Too sales-heavy | User wants hard sell in welcome | Push conversion CTA to email 5-6; front-load value |
| Unclear subscriber expectations | No context on what they signed up for | Ask: "What did subscribers expect to receive when they signed up?" |
| B2C vs B2B mismatch | Wrong tone for audience | Ask: "Is your audience consumers or businesses?" to adjust voice |

## How to Get Your Data

### Starting Fresh (Most Common)

1. Tell Claude your business type, how people subscribe, and your main value
2. Optionally share your top 3-5 pieces of content (URLs or descriptions)
3. Claude builds the complete series

### Improving an Existing Welcome Email

1. Paste your current welcome email
2. Tell Claude what's working and what isn't
3. Claude expands it into a full 5-7 email series

### From Email Platform Templates

1. Check your ESP (Mailchimp, ConvertKit, etc.) for welcome series templates
2. Share the template structure with Claude
3. Claude customizes with your content and voice

## Example

**User prompt:** "I run a B2B newsletter about marketing analytics. People sign up for a free 'Data-Driven Marketing Cheat Sheet' PDF. Build a 5-email welcome series."

**Claude responds:**

> Here's your welcome series arc:
>
> | # | Day | Purpose | Subject Line |
> |---|---|---|---|
> | 1 | 0 | Deliver cheat sheet + introduce newsletter | Your Data-Driven Marketing Cheat Sheet is here |
> | 2 | 2 | Share your story + top insight | The analytics mistake I see in 80% of marketing teams |
> | 3 | 5 | Quick win — most popular resource | The GA4 report every CMO should see (2-min setup) |
> | 4 | 8 | Social proof + progressive profile | How 3 marketing teams used data to 2x their ROI |
> | 5 | 12 | Soft conversion + expectations | What's coming next (and a question for you) |
>
> **Progressive profiling (Email 4):**
> "Which analytics challenge matters most to you?"
> - Attribution modeling → tag: interest-attribution
> - Dashboard building → tag: interest-dashboards
> - Experiment design → tag: interest-experimentation
>
> Each email includes 3 subject lines, preview text, full copy, and CTA.
> Transition: After email 5, subscribers enter weekly newsletter + segmented content.
>
> [Full email copy follows]

## Related Skills

- **[Email Sequence Builder](./email-sequence-builder.md)** — Use to structure the welcome series flow and timing between emails.
- **[Email Copywriting Framework](./email-copywriting-framework.md)** — Use to write compelling copy for each email in the welcome series.
- **[Email List Segmentation](./email-list-segmentation.md)** — Use to segment new subscribers for more targeted welcome experiences.
- **[Customer Onboarding Optimizer](../crm/customer-onboarding-optimizer.md)** — Use to align your welcome series with the broader customer onboarding journey.
