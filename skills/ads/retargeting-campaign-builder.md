---
name: retargeting-campaign-builder
description: >
  Design retargeting campaigns across platforms with audience segmentation and creative strategy.
  Use this skill when the user says "retargeting campaign", "remarketing strategy", "retarget
  website visitors", "cart abandonment ads", "retargeting audience segments", "dynamic retargeting",
  "sequential retargeting", "retargeting creative strategy", "cross-platform retargeting",
  "retargeting frequency cap", or "retargeting funnel". Also trigger for pixel-based retargeting
  setup, retargeting exclusion strategy, or retargeting ad fatigue solutions.
---

# Retargeting Campaign Builder

Designs multi-platform retargeting campaigns with audience segmentation by intent signal, creative sequencing, frequency management, and conversion optimization.

## Granularity Check

> **Time**: ~5 min data prep → ~10 min Claude session → ~30-60 min building in Google Ads / Meta Ads Manager. If implementing output in ad platforms, add 30-45 min for audience and campaign setup. Input is website traffic data and conversion funnel info. Output is Markdown retargeting blueprint.

## User Intent Mapping

- "Set up retargeting for our website" (full setup)
- "Cart abandonment retargeting campaign" (specific funnel stage)
- "Our retargeting ads aren't converting" (optimization)
- "Sequential retargeting strategy" (advanced)
- "Dynamic product retargeting" (e-commerce)
- "Retargeting frequency — how often is too often?" (frequency management)
- "Cross-platform retargeting plan" (multi-platform)
- "Retargeting creative ideas" (creative)
- "Exclude converters from retargeting" (audience hygiene)
- "Retargeting budget allocation" (budget)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Website/App | Text | What your site does, key conversion actions |
| Conversion Funnel | Text | Steps from visit to conversion (e.g., visit → product page → cart → purchase) |
| Platforms | Text | Where to run retargeting (Google, Meta, LinkedIn, etc.) |

### If You Don't Have This Data

- **No tracking pixel?** Install Meta Pixel and Google Ads tag first. Claude can guide setup after you have tracking in place.
- **No audience sizes?** Check your analytics: if you get 1,000+ monthly visitors, you have enough for retargeting. Minimum viable audience is 100-1,000 depending on platform.
- **No conversion data?** Start retargeting all website visitors (broadest audience) and narrow segments as data accumulates.
- **No creative assets?** Start with static image ads featuring your product + testimonial. Dynamic retargeting needs a product feed.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Monthly Traffic | Number | Unique visitors per month |
| Conversion Rate | Number | Current site conversion rate |
| Average Order Value | Number | For ROAS calculations |
| Product Catalog | CSV | For dynamic retargeting (product ID, name, image URL, price) |
| Current Retargeting | Text | What you're already running |

## Process

### Step 1: Audience Segmentation
Segment by intent signal:

| Segment | Intent Level | Window | Priority |
|---|---|---|---|
| Cart/Form Abandoners | Very High | 1-7 days | Highest |
| Product/Pricing Viewers | High | 1-14 days | High |
| Blog/Content Readers | Medium | 7-30 days | Medium |
| Homepage Visitors | Low-Medium | 7-30 days | Lower |
| Past Customers | Re-purchase | 30-90 days | Medium-High |
| Video Viewers (50%+) | Medium | 7-30 days | Medium |
| Social Engagers | Medium | 7-30 days | Medium |

### Step 2: Creative Sequencing
Design creative per segment and time window:
- **Day 1-3**: Reminder ad (product image, "Still interested?")
- **Day 4-7**: Social proof ad (testimonial, review count, case study)
- **Day 8-14**: Incentive ad (discount, free trial extension, bonus)
- **Day 15-30**: Value proposition ad (different angle, comparison)
- **Day 30+**: Brand awareness or pause (reduce frequency)

### Step 3: Platform-Specific Setup
| Platform | Retargeting Type | Best For |
|---|---|---|
| Meta | Pixel, Custom Audiences, Dynamic Product Ads | E-commerce, B2C lead gen |
| Google Display | Remarketing lists, Dynamic remarketing | Broad reach, e-commerce |
| Google Search | RLSA (Remarketing Lists for Search Ads) | High-intent search capture |
| LinkedIn | Website retargeting, Contact list | B2B, account-based |
| TikTok | Pixel audiences, Engagement audiences | Brand re-engagement |

### Step 4: Frequency & Exclusion Management
- Frequency cap: 3-5 impressions per user per day (display), 1-2 per day (social)
- Exclude: Converters (30-90 day window), bounced visitors (<5 seconds), bot traffic
- Burn pixel: Stop showing ads immediately after conversion
- Cross-platform deduplication: Reduce total frequency across platforms

### Step 5: Budget Allocation
- Cart/form abandoners: 40% of retargeting budget
- Product/pricing viewers: 30%
- Content readers + homepage: 20%
- Testing/experimentation: 10%

### Confidence & Sample Size
> **Confidence Note**: Retargeting audiences shrink over time as users convert or windows expire. Minimum viable audience size is 100 (Meta), 100 (Google Display), 300 (LinkedIn). Smaller audiences mean higher CPMs but higher conversion rates. Track view-through conversions — retargeting often assists conversions attributed to other channels.

### ⚠️ Human Checkpoint
> Review audience exclusions to avoid annoying converted customers. Verify frequency caps are set to prevent ad fatigue. Check creative for compliance with platform policies and privacy regulations (GDPR/CCPA consent requirements for retargeting).

> **Benchmark Context**: Average Google Ads CTR is 6.66% for search and 0.46% for display (WordStream 2025 Industry Benchmarks). Average Meta Ads CTR ranges from 1.5-1.7% across industries (Meta 2025 Advertising Benchmarks).
## Output Contract

### Deliverable: Markdown Retargeting Blueprint

```markdown
# Retargeting Blueprint: [Business]

## Audience Segments
| Segment | Definition | Size (est.) | Window | Priority |
|---|---|---|---|---|

## Creative Sequence
| Days | Segment | Creative Theme | Format | CTA |
|---|---|---|---|---|

## Platform Campaigns
| Platform | Campaign | Audience | Budget | Format |
|---|---|---|---|---|

## Frequency & Exclusions
- Frequency cap: [setting]
- Exclusions: [list]
- Burn pixel: [setup]

## Budget Allocation
| Segment | % of Budget | Monthly Spend |
|---|---|---|

## Performance Targets
| Metric | Target | Measurement |
|---|---|---|
```

## Platform Implementation Steps

### Meta Ads Manager
1. Create Custom Audiences: Events Manager → Custom Audiences → Website
2. Set up audience segments with URL rules and time windows
3. Create Dynamic Product Ads: Connect product catalog → Create DPA campaign
4. Set frequency cap: Ad Set level → Optimization → Frequency Cap

### Google Ads
1. Audience Manager → Create Remarketing List → Website visitors
2. Set up URL-based segments matching funnel stages
3. Dynamic remarketing: Link Google Merchant Center → Create Dynamic Display campaign
4. RLSA: Add remarketing audiences to Search campaigns → Set bid adjustments

### Cross-Platform
1. Create matching audience segments across all platforms
2. Use UTM parameters to track cross-platform attribution
3. Monitor combined frequency using a third-party tool or manual tracking
4. Sync exclusion lists across platforms (converters, existing customers)

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Audience too small | Low traffic or narrow segmentation | Broaden windows; combine similar segments |
| High frequency, low conversion | Ad fatigue, wrong creative | Rotate creative weekly; reduce frequency cap |
| Retargeting cannibalizing organic | Showing ads to users who'd convert anyway | Test holdout group (10% of audience, no ads) to measure incremental lift |
| Privacy regulation issues | Missing consent for retargeting | Implement consent management platform; respect opt-outs |

## How to Get Your Data

- **Google Analytics**: Audience → Overview → check monthly traffic by page
- **Meta Events Manager**: Custom Conversions → view event volumes
- **E-commerce platform**: Shopify/WooCommerce → Analytics → funnel reports
- **No data**: Describe your site, traffic, and funnel — Claude builds from benchmarks

## Example

**Input**: "Retargeting for a SaaS product. Funnel: homepage → features page → pricing page → free trial signup. 15,000 monthly visitors, 2% conversion rate. Platforms: Google + Meta. Budget: $2,000/month for retargeting."

**Output**: 4 audience segments: (1) Pricing page visitors, no signup — 7-day window, ~450/month, highest priority; (2) Features page visitors — 14-day window, ~1,200/month; (3) Homepage only — 30-day window, ~3,000/month; (4) Trial users who didn't convert to paid — 30-day window, from CRM list. Creative sequence: Day 1-3 (reminder + key benefit), Day 4-7 (customer testimonial), Day 8-14 (extended trial offer or demo CTA). Budget: Pricing viewers $800/mo (40%), Features viewers $600/mo (30%), Homepage $400/mo (20%), Testing $200/mo (10%). Platforms: Meta for pricing + features retargeting (visual ads), Google RLSA for branded search bid boost on all segments. Frequency cap: 3/day on Meta, 5/day on Google Display. Exclusions: converted trial users, existing paid customers.

## Related Skills

- **audience-targeting-builder** (./audience-targeting-builder.md) — Segment your website visitors into retargeting audiences; use this skill to define audience rules before setting up campaigns.
- **ad-copy-generator** (./ad-copy-generator.md) — Generate compelling copy for each stage of the retargeting sequence (reminder, social proof, incentive, value prop); essential for creative effectiveness.
- **ad-creative-testing-framework** (./ad-creative-testing-framework.md) — Test which retargeting creative sequences drive highest conversion rates; use to optimize frequency and messaging.
- **marketing-roi-calculator** (../analytics/marketing-roi-calculator.md) — Calculate the ROAS of your retargeting campaigns and allocate budget across segments; cross-category analytics for performance measurement.
