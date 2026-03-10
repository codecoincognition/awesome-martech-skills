---
name: audience-targeting-builder
description: >
  Build audience targeting strategies across ad platforms with segmentation, layering, and exclusions.
  Use this skill when the user says "build ad audiences", "audience targeting strategy", "who
  should I target with ads", "ad audience segmentation", "custom audience setup", "lookalike
  audience strategy", "interest targeting", "behavioral targeting", "audience layering",
  "exclusion audience strategy", or "audience overlap analysis". Also trigger for first-party
  data audience building, intent-based targeting, or contextual targeting setup.
---

# Audience Targeting Builder

Designs comprehensive audience targeting strategies across ad platforms with segment definitions, targeting layers, exclusion lists, and testing frameworks.

## Granularity Check

> **Time**: ~5 min data prep → ~10 min Claude session → ~30-60 min building in Google Ads / Meta Ads Manager. If implementing output in ad platforms, add 20-30 min for audience creation. Input is ICP and customer data. Output is Markdown targeting strategy with audience definitions.

## User Intent Mapping

- "Who should I target with my ads?" (strategy)
- "Build lookalike audiences from my customer list" (lookalike)
- "Interest targeting for a fitness app" (interest-based)
- "How to layer audiences on Google Ads" (platform-specific)
- "My ads are reaching the wrong people" (targeting fix)
- "First-party data audience strategy" (data-driven)
- "Audience exclusion strategy" (waste reduction)
- "Test different audience segments" (testing)
- "B2B audience targeting on LinkedIn and Meta" (cross-platform)
- "Contextual vs. behavioral targeting — which is better?" (strategy comparison)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Product/Service | Text | What you're advertising |
| Ideal Customer | Text | Demographics, behaviors, pain points |
| Platform(s) | Text | Google, Meta, LinkedIn, TikTok, Pinterest, etc. |

### If You Don't Have This Data

- **No customer data?** Describe your best 5 customers: what they do, how they found you, why they bought. Claude builds audience profiles from this.
- **No CRM list?** Start with platform-native targeting (interests, demographics). Build custom audiences as you collect data.
- **No conversion data?** Use engagement signals (time on site, pages viewed) as proxy intent signals for audience building.
- **No competitor intel?** Check Meta Ad Library for competitor audience clues (their creative reveals who they target).

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Customer List | CSV | Email list for custom/lookalike audiences |
| Website Analytics | Text | Top traffic sources, user demographics |
| Current Targeting | Text | What you're targeting now |
| Budget | Number | Affects audience size recommendations |
| Competitor Targeting | Text | What competitors seem to target |

## Process

### Step 1: Customer Segmentation
Define 3-5 audience segments:
- **Primary**: Highest-value, most likely to convert
- **Secondary**: Good fit, needs more education
- **Expansion**: Adjacent audiences with potential
- **Exclusion**: People who should NOT see your ads

### Step 2: Targeting Layer Design
Build targeting per platform:

| Layer | Google | Meta | LinkedIn | TikTok |
|---|---|---|---|---|
| Demographics | Age, gender, income, parental | Age, gender, life events | Seniority, function | Age, gender |
| Interests | In-market, affinity | Interests, behaviors | Skills, groups | Interests, hashtags |
| Custom | Customer Match, website visitors | Custom Audiences, lookalikes | Matched Audiences | Custom Audiences |
| Contextual | Keywords, topics, placements | N/A | N/A | Hashtags |

### Step 3: Audience Sizing
- Google Search: 1,000+ for observation, any size for targeting
- Google Display: 100+ (minimum), 10,000+ (recommended)
- Meta: 1,000+ (minimum), 100,000-1,000,000 (sweet spot for prospecting)
- LinkedIn: 50,000+ for Sponsored Content, 15,000+ for Message Ads
- Too small = limited delivery. Too broad = wasted spend.

### Step 4: Exclusion Strategy
Essential exclusions:
- Existing customers (from prospecting campaigns)
- Recent converters (7-30 day window)
- Employees and internal stakeholders
- Irrelevant geographies
- Known non-buyers (bounced, unsubscribed)

### Step 5: Testing Framework
- Test 3-5 audiences per campaign
- Isolate one variable per test (demographics vs. interests vs. lookalike)
- Minimum 1,000 impressions per audience before judging
- Use audience overlap tools to ensure segments are distinct
- Graduate winners from test to evergreen campaigns

### Confidence & Sample Size
> **Confidence Note**: Audience performance varies significantly by creative, offer, and season. An audience that performs poorly with one creative may excel with another. Test audiences with 2-3 different creatives before declaring a winner or loser. Platform targeting suggestions (interest categories, audience expansion) are based on algorithmic inference and may not be precise.

### ⚠️ Human Checkpoint
> Review audience definitions for inadvertent discrimination (housing, employment, credit ads have legal restrictions). Verify exclusion lists don't violate platform policies. Ensure custom audience uploads comply with privacy regulations (GDPR/CCPA consent).

> **Benchmark Context**: Lookalike audiences typically outperform interest targeting by 20-40% on CPA. Narrower audiences have higher CPMs but lower CPA. Broad targeting with strong creative often outperforms hyper-targeted campaigns on Meta. First-party data audiences are 2-5x more effective than third-party data segments. Customer Match rates: Google 30-50%, Meta 50-75%, LinkedIn 30-70%.

## Output Contract

### Deliverable: Markdown Targeting Strategy

```markdown
# Audience Targeting Strategy: [Business]

## Customer Segments
| Segment | Description | Estimated Size | Priority |
|---|---|---|---|

## Platform Targeting Specs

### Google Ads
| Audience | Targeting Method | Criteria | Campaign Type |
|---|---|---|---|

### Meta Ads
| Audience | Type | Definition | Estimated Size |
|---|---|---|---|

### [Additional Platforms]

## Exclusion Lists
| Exclusion | Source | Apply To |
|---|---|---|

## Testing Plan
| Test | Audience A | Audience B | Success Metric | Duration |
|---|---|---|---|---|

## Audience Refresh Cadence
| Audience Type | Refresh Frequency | Method |
|---|---|---|
```

## Platform Implementation Steps

### Meta Ads Manager
1. Audiences → Create Custom Audience → upload customer list or set website rules
2. Create Lookalike: Select source audience → choose percentage (1% = most similar)
3. Create Saved Audiences with interest/demographic targeting
4. Apply audiences to ad sets; set exclusions at the ad set level

### Google Ads
1. Audience Manager → Create Custom Segment → define by keywords, URLs, or apps
2. Upload Customer Match list (minimum 1,000 emails)
3. Apply audiences to campaigns: Observation (monitor) or Targeting (restrict)
4. Set bid adjustments for high-performing audience segments

### LinkedIn Campaign Manager
1. Create Matched Audience → upload company or contact list
2. Build targeting with Job Title + Industry + Company Size layers
3. Use Audience Expansion cautiously (broadens beyond your criteria)
4. Review Audience Insights tab to validate targeting accuracy

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Audience too narrow, no delivery | Over-layered targeting | Remove one targeting layer at a time until delivery starts |
| Audience too broad, high CPA | Insufficient targeting specificity | Add exclusions; test interest layers |
| Lookalike underperforming | Source audience too small or low-quality | Use top 25% customers by LTV as seed; minimum 1,000 source records |
| Audience overlap waste | Multiple ad sets targeting same people | Use Audience Overlap tool; add exclusions between ad sets |

## How to Get Your Data

- **Customer list**: Export from CRM (email, first name, last name minimum). More fields = better match rate.
- **Website audience**: Google Analytics → Audience → Demographics/Interests for profile data
- **No data**: Describe your ideal customer — Claude builds targeting from description

## Example

**Input**: "Audience targeting for a project management SaaS. ICP: startup founders and ops managers at companies with 10-200 employees. Platforms: Meta + LinkedIn. Have a customer list of 2,500 emails."

**Output**: 4 segments: (1) Startup Founders — Meta: Lookalike 1% based on customer list + interests (entrepreneurship, startup, SaaS); LinkedIn: Job Title (Founder, CEO, Co-Founder) + Company Size (11-200); (2) Ops/Project Managers — Meta: Lookalike 2% + interests (project management, productivity); LinkedIn: Job Function (Operations, Project Management) + Seniority (Manager+); (3) Expansion: Tech-forward SMBs — Meta: Lookalike 3-5% broadened; LinkedIn: Industry (Technology, Software) + Company Size (11-200); (4) Retargeting: Website visitors 30-day, pricing page visitors 14-day. Exclusions: existing customers, competitors, companies <10 employees. Testing plan: Week 1-2 test Segment 1 vs. 2 on Meta with same creative; Week 3-4 test LinkedIn targeting layers. Audience refresh: monthly lookalike rebuild, weekly retargeting refresh.

## Related Skills

- **[customer-persona-builder](../growth/customer-persona-builder.md)** — Build detailed personas first to inform your audience segmentation strategy.
- **[ad-copy-generator](./ad-copy-generator.md)** — Generate audience-specific copy variants that speak to each targeted segment.
- **[ad-performance-analyzer](./ad-performance-analyzer.md)** — Analyze audience performance to refine which segments convert best.
- **[retargeting-campaign-builder](./retargeting-campaign-builder.md)** — Build retargeting audiences to reach engaged prospects at different stages.
