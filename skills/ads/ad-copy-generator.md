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

> **Time**: ~5 min data prep → ~10 min Claude session → ~30-60 min building in Google Ads / Meta Ads Manager. If implementing output in a platform, add 10-20 minutes for setup. Input is product/audience description. Output is Markdown with organized ad variants.

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

### If You Don't Have This Data

- **No product description?** Write 2-3 sentences about what you sell, who buys it, and why they choose you over alternatives.
- **No target audience?** Start with your last 10 customers — what do they have in common? Use that as your audience.
- **No performance data?** That's fine — this skill generates fresh copy from scratch. Performance data only helps with optimization iterations.
- **No competitor info?** Search your primary keyword on Google — the ads that appear are your competitors. Note their headlines.

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


> **Benchmark Context**: See LinkedIn 2024 B2B Marketing Benchmark, and Meta 2024 Advertising Benchmarks for current industry benchmarks relevant to this analysis.
> **Confidence Note**: Results are only as reliable as your input data. Small datasets (<50 records or <30 days of data) produce directional insights, not statistically significant conclusions. Always note your sample size when sharing results with stakeholders. Recommendations should be validated with A/B testing or additional data before making major strategic changes.

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

## Platform Implementation Steps

### Google Ads
1. Navigate to Google Ads → Campaigns → select your campaign → Ads & Assets
2. Click "+" to add new responsive search ad
3. Paste headlines into the 15 headline slots (one per slot)
4. Paste descriptions into the 4 description slots
5. Use "Ad Strength" indicator to verify — aim for "Good" or "Excellent"

### Meta Ads Manager
1. Open Meta Business Suite → Ads Manager → select campaign
2. At Ad level, click "Edit" on your ad
3. Paste Primary Text, Headline, and Description into respective fields
4. Preview across placements (Feed, Stories, Reels) before publishing

### LinkedIn Campaign Manager
1. Open Campaign Manager → select campaign → Ads tab
2. Click "Create new ad" → Single Image Ad or other format
3. Paste Introductory Text, Headline, and Description
4. Preview on both desktop and mobile before saving

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

## Related Skills

- **[ad-creative-testing-framework](./ad-creative-testing-framework.md)** — Use after writing copy variants to systematically test which angles and hooks perform best.
- **[google-ads-campaign-builder](./google-ads-campaign-builder.md)** — Use to structure complete campaigns once you've finalized ad copy.
- **[ad-compliance-checker](./ad-compliance-checker.md)** — Validate your ad copy against platform policies and regulations before launch.
- **[campaign-angle-generator](../insights/campaign-angle-generator.md)** — Generate additional persuasion angles and messaging strategies to inform your ad copy variants.
