---
name: ad-copy-generator
description: >
  Generate ad copy variants for Google Ads, Meta Ads, and LinkedIn Ads.
  Use this skill whenever the user needs ad copy, wants to write ads, needs PPC copy,
  mentions Google Ads headlines, Facebook ad text, LinkedIn sponsored content copy,
  or says things like "write ads for my product" or "I need ad variants" or "help me
  with my Google Ads copy." Also trigger for ad creative briefs, A/B test copy variants,
  responsive search ad headlines, or any paid advertising copywriting task.
---

# Ad Copy Generator

Generates 10+ ad copy variants per platform (Google Ads, Meta Ads, LinkedIn Ads), organized by persuasion angle and respecting each platform's character limits. Includes A/B testing recommendations.

## Granularity Check

> Completable in one 10-minute session. Input is product/audience description. Output is Markdown with organized ad variants.

## User Intent Mapping

- "Write Google Ads headlines for my product" (platform-specific)
- "I need Facebook ad copy for a product launch" (platform-specific)
- "Generate ad variants for A/B testing" (testing)
- "Help me write LinkedIn sponsored content" (platform-specific)
- "Create responsive search ad headlines and descriptions" (Google-specific)
- "I need ad copy for my landing page campaign" (campaign-specific)
- "Write ads that highlight our free trial" (offer-specific)
- "Generate copy for different ad angles" (strategic)
- "My ads aren't converting, help me rewrite them" (problem statement)
- "I need 15 headline options for Google Ads" (quantity-specific)

## Input Contract

### Required Input

| Field | Type | Description | Example |
|---|---|---|---|
| `product_description` | string | What you're selling | `"TaskFlow: project management for remote teams, $12/mo"` |
| `target_audience` | string | Who you're targeting | `"Startup CTOs managing 5-25 person teams"` |
| `platform` | string | Ad platform(s) | `"google"`, `"meta"`, `"linkedin"`, or `"all"` |

### Optional Input

| Field | Type | Default | Description |
|---|---|---|---|
| `usps` | list of strings | extracted from product_description | Unique selling points |
| `campaign_objective` | string | `"conversions"` | awareness, traffic, conversions, leads |
| `competitor_names` | list | `[]` | Competitors to differentiate from |
| `tone` | string | `"professional"` | professional, casual, urgent, playful |
| `offer` | string | `""` | Specific offer: "free trial", "20% off", etc. |
| `landing_page_url` | string | `""` | For display URL suggestions |

### Input Validation Rules

1. `product_description` must be at least 20 characters
2. `platform` must be one of: google, meta, linkedin, all
3. `target_audience` must not be empty

## Process

1. **Analyze product** — Extract key benefits, features, and differentiators from the product description and USPs.

2. **Apply platform constraints:**

   **Google Ads (Responsive Search Ads):**
   - Headlines: 30 characters max, need 15 variants
   - Descriptions: 90 characters max, need 4 variants
   - Display path: 15 chars per segment

   **Meta Ads:**
   - Primary text: 125 characters (visible without "See more")
   - Headline: 40 characters
   - Description: 30 characters
   - Link description: 30 characters

   **LinkedIn Ads:**
   - Introductory text: 150 characters (visible without truncation)
   - Headline: 70 characters
   - Description: 100 characters

3. **Generate by angle** — Create variants for each persuasion angle:
   - **Benefit-driven:** Lead with the outcome ("Save 5 hours/week")
   - **Fear/pain point:** Address what they'll lose ("Stop losing projects to chaos")
   - **Social proof:** Numbers and authority ("Join 10,000+ teams")
   - **Urgency:** Time pressure ("Free trial ends Friday")
   - **Curiosity:** Information gap ("The PM tool CTOs are switching to")

4. **Human checkpoint** — Present top 5 variants per platform. Ask: "Which angles resonate most with your brand? Should I lean into any specific direction?"

5. **Finalize** — Deliver complete variant set with A/B testing recommendations.

## Output Contract

### Output Format

| Output | Format | Contents |
|---|---|---|
| Ad copy variants | Markdown | Organized by platform and angle |
| A/B test plan | Markdown | Which variants to test first |

### Output Structure

```markdown
## Google Ads — Responsive Search Ad

### Headlines (30 char max)
| # | Headline | Angle | Chars |
|---|---|---|---|
| 1 | "Manage Projects Smarter" | Benefit | 23 |

### Descriptions (90 char max)
| # | Description | Angle | Chars |
|---|---|---|---|

## Meta Ads

### Variant 1: [Angle Name]
- **Primary text:** [125 chars]
- **Headline:** [40 chars]
- **Description:** [30 chars]

## A/B Test Recommendations
- Test 1: [Variant A] vs [Variant B] — tests [hypothesis]
```

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Product description too vague | "We sell software" | Ask for 3 specific benefits and target audience |
| Character limit violations | Copy exceeds platform limits | Auto-trim and flag; offer shorter alternatives |
| No differentiation possible | Generic product | Ask for competitor names to identify differentiation angles |
| Regulated industry | Healthcare, finance, legal | Flag compliance requirements; avoid claims that need disclaimers |
| Multiple products in one request | User wants ads for everything | Recommend one ad group per product; start with highest-priority |

## How to Get Your Data

### No data needed — just describe your product, audience, and platform.

### For improvement — export existing ad performance:

**Google Ads:** Ads → Table → Download (CSV with headline, impressions, clicks, CTR)

**Meta Ads Manager:** Ads tab → Export → CSV (includes copy, reach, conversions)

**LinkedIn Campaign Manager:** Ads → Export → CSV

## Example

**User prompt:** "Write Google Ads copy for TaskFlow — a project management tool for remote teams. $12/mo. Key benefit: saves 5 hours/week on status updates. Target: startup CTOs."

**Claude output:**

> ## Google Ads — Headlines (30 char max)
>
> | # | Headline | Angle | Chars |
> |---|---|---|---|
> | 1 | Save 5 Hours Every Week | Benefit | 23 |
> | 2 | Remote PM Made Simple | Benefit | 21 |
> | 3 | Stop Chasing Status Updates | Pain | 27 |
> | 4 | 10,000+ Remote Teams Use This | Social Proof | 30 |
> | 5 | Try TaskFlow Free Today | Urgency | 23 |
> | 6 | Project Management at $12/mo | Value | 28 |
> | 7 | Built for Remote-First Teams | Specificity | 27 |
> | 8 | No More Monday Status Calls | Pain | 27 |
> | 9 | Your Team, Any Time Zone | Benefit | 23 |
> | 10 | The PM Tool CTOs Love | Social Proof | 21 |
>
> ## Google Ads — Descriptions (90 char max)
>
> | # | Description | Angle |
> |---|---|---|
> | 1 | TaskFlow replaces status meetings with async updates. Your team saves 5 hrs/week. Try free. | Benefit |
> | 2 | Stop losing projects to time zone chaos. TaskFlow keeps remote teams aligned. Plans from $12/mo. | Pain |
> | 3 | Join 10,000+ startup teams managing projects without endless check-ins. Free 14-day trial. | Social Proof |
> | 4 | Your remote team deserves better than Slack threads for project updates. See why CTOs switch. | Curiosity |
