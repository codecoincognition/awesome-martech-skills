---
name: utm-tracking-manager
description: >
  Generate and manage UTM parameters for marketing campaigns.
  Use this skill whenever the user mentions UTM tracking, campaign URLs, tracking links,
  UTM tags, campaign tagging, URL parameters, link tracking, or needs to create trackable
  URLs for any marketing campaign. Also trigger when someone says "I need tracking links
  for my campaign" or "help me set up UTM parameters" or "create campaign URLs for GA4."
  Use for any task involving UTM_source, UTM_medium, UTM_campaign, UTM_content, or UTM_term.
---

# UTM Tracking Manager

Generates properly formatted UTM-tagged URLs with consistent naming conventions. Produces a campaign tracking spreadsheet with all URLs, a naming convention reference, and import-ready formats for Google Analytics and HubSpot.

## Granularity Check

> **Time**: ~5 min data prep → ~10 min Claude session → ~30-60 min implementing in your MarTech stack. If implementing output in a platform, add 10-20 minutes for setup. Input is campaign details (CSV or natural language). Output is XLSX with URLs and naming docs.

## User Intent Mapping

- "Create UTM links for my email campaign" (direct command)
- "I need tracking URLs for this launch" (goal-oriented)
- "Help me set up campaign tracking" (general tracking)
- "Generate UTM parameters for Google Ads" (platform-specific)
- "My UTM naming is a mess, help me standardize" (cleanup)
- "Create a tracking spreadsheet for Q2 campaigns" (batch request)
- "What UTM parameters should I use for social posts?" (guidance)
- "Build campaign URLs for my newsletter" (specific channel)
- "I need to track which emails drive the most signups" (attribution)
- "Set up UTM tracking for a product launch across 5 channels" (multi-channel)

## Input Contract

### Option A: Structured CSV

| Column | Type | Description | Example |
|---|---|---|---|
| `campaign_name` | string (required) | Campaign identifier | `"spring-sale-2026"` |
| `source` | string (required) | Traffic source | `"google"`, `"newsletter"`, `"linkedin"` |
| `medium` | string (required) | Marketing medium | `"cpc"`, `"email"`, `"social"`, `"organic"` |
| `destination_url` | string (required) | Landing page URL | `"https://example.com/pricing"` |
| `content` | string (optional) | Ad/content variant | `"hero-banner"`, `"cta-button"` |
| `term` | string (optional) | Paid keyword term | `"project management"` |

### Option B: Natural Language

User describes the campaign in plain text. Example: "I'm running a spring sale across Google Ads, Facebook, our email list, and LinkedIn. Landing page is example.com/spring-sale."

### Input Validation Rules

1. `destination_url` must be a valid URL with protocol (https://)
2. No spaces in UTM values (auto-convert to hyphens)
3. All values lowercase (auto-convert)
4. No special characters except hyphens and underscores
5. `campaign_name` should follow pattern: `[topic]-[descriptor]-[year/quarter]`

**If validation fails:** Auto-fix common issues (spaces → hyphens, uppercase → lowercase) and show the user what was changed.

### If You Don't Have This Data

- **No brand guidelines?** Document your current logo, colors (use a color picker on your website), and 3 tone-of-voice adjectives. That's a starting brand guide.
- **No asset inventory?** Search your Google Drive/Dropbox for common marketing file types (.pdf, .pptx, .png). The list IS your inventory.
- **No compliance checklist?** Start with industry basics: GDPR consent, CAN-SPAM footer, accessibility alt text. This skill helps you build the full checklist.
- **No vendor data?** List every tool your marketing team pays for. Include name, monthly cost, and primary user. That's your vendor inventory.

## Process

1. **Parse input** — Accept CSV or natural language. If natural language, extract campaign name, channels, and destination URL.

2. **Standardize naming** — Apply naming conventions:
   - Sources: `google`, `facebook`, `linkedin`, `twitter`, `email`, `newsletter`
   - Mediums: `cpc`, `cpm`, `social`, `email`, `referral`, `organic`, `display`
   - Campaigns: `[topic]-[type]-[YYYY]` or `[topic]-[type]-[QN]`

3. **Generate UTM URLs** — Build complete URLs with all parameters. URL-encode special characters.

4. **Human checkpoint** — Present the generated URLs in a table. Ask: "Do these look correct? Any naming changes needed before I finalize the spreadsheet?"

5. **Build output spreadsheet** — Create XLSX with tracking URLs, naming convention reference, and a quick-reference card.


> **Benchmark Context**: See Gartner 2024 Marketing Technology Survey for current industry benchmarks relevant to this analysis.


### Confidence & Sample Size.
> **Confidence Note**: Results are only as reliable as your input data. Small datasets (<50 records or <30 days of data) produce directional insights, not statistically significant conclusions. Always note your sample size when sharing results with stakeholders. Recommendations should be validated with A/B testing or additional data before making major strategic changes.

## Output Contract

### Output Format

| Output | Format | Contents |
|---|---|---|
| Campaign tracking sheet | Markdown tables | URLs + naming reference |
| Quick reference | Markdown | Copy-pasteable URL list |

### Table 1: Campaign URLs

| Column | Type | Description |
|---|---|---|
| `campaign_name` | string | Campaign identifier |
| `source` | string | utm_source value |
| `medium` | string | utm_medium value |
| `content` | string | utm_content value |
| `term` | string | utm_term value |
| `destination_url` | string | Base URL |
| `full_utm_url` | string | Complete URL with parameters |

### Table 2: Naming Convention Reference

| Column | Description |
|---|---|
| `parameter` | UTM parameter name |
| `allowed_values` | List of standardized values |
| `format_rule` | Naming pattern |
| `examples` | 2-3 examples |

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
| Invalid URL | Missing protocol or malformed domain | Auto-add https:// and validate; ask user to confirm |
| Inconsistent naming | User mixes formats | Standardize all and show before/after |
| Too many parameters | User adds custom UTM params | Warn that only standard 5 UTM params are supported |
| Duplicate URLs | Same source/medium/campaign combo | Flag duplicates and ask which to keep |

## How to Get Your Data

### Starting from Scratch

Just describe your campaign: channels, landing page, campaign name. No export needed.

### From Google Analytics 4

1. Go to GA4 → Advertising → Attribution
2. Review existing campaign names for naming patterns
3. Use the same naming conventions for consistency

### From HubSpot

1. Go to Marketing → Ads or Email
2. Note existing tracking URL patterns
3. Match the naming convention in your new UTMs

## Example

**User prompt:** "Create tracking URLs for our Q2 webinar promotion. We're promoting on Google Ads, LinkedIn, email newsletter, and organic Twitter. Landing page is https://taskflow.com/webinar-q2."

**Claude output:**

> Here are your UTM-tagged URLs:
>
> | Channel | Full URL |
> |---|---|
> | Google Ads | `https://taskflow.com/webinar-q2?utm_source=google&utm_medium=cpc&utm_campaign=webinar-q2-2026&utm_content=search-ad` |
> | LinkedIn | `https://taskflow.com/webinar-q2?utm_source=linkedin&utm_medium=social&utm_campaign=webinar-q2-2026&utm_content=sponsored-post` |
> | Newsletter | `https://taskflow.com/webinar-q2?utm_source=newsletter&utm_medium=email&utm_campaign=webinar-q2-2026&utm_content=primary-cta` |
> | Twitter | `https://taskflow.com/webinar-q2?utm_source=twitter&utm_medium=social&utm_campaign=webinar-q2-2026&utm_content=organic-tweet` |
>
> Do these look right? I'll generate the full XLSX with naming convention docs once you confirm.

## Related Skills

- **[Marketing Attribution Modeler](../ai-marketing/marketing-attribution-modeler.md)** — Use consistent UTM tagging to enable accurate multi-touch attribution.
- **[Campaign Performance Benchmarker](../analytics/campaign-performance-benchmarker.md)** — Compare campaign performance across channels using properly tagged UTM data.
- **[Marketing Dashboard Builder](../analytics/marketing-dashboard-builder.md)** — Build dashboards that rely on UTM-tagged traffic data for channel performance insights.
- **[Google Ads Campaign Builder](../ads/google-ads-campaign-builder.md)** — Tag Google Ads campaigns with standardized UTM parameters for consistent tracking.
