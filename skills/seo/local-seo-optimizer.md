---
name: local-seo-optimizer
description: >
  Optimize local SEO — Google Business Profile, local citations, map pack rankings, and local content.
  Use this skill when the user says "local SEO optimization", "Google Business Profile optimization",
  "local search rankings", "map pack strategy", "local citations audit", "local SEO audit",
  "Google Maps ranking", "local business SEO", "multi-location SEO", "local keyword strategy",
  or "near me search optimization". Also trigger for review management strategy, local link
  building, or NAP consistency audit.
---

# Local SEO Optimizer

Audits and optimizes local SEO performance — Google Business Profile, local citations, map pack rankings, review strategy, and local content with multi-location support.

## Granularity Check

> **Time**: ~5 min data prep → ~10 min Claude session → ~30-60 min implementation in Google Search Console / CMS. If implementing, add 2-5 hours for GBP optimization and citation cleanup. Input is GBP data and local search performance. Output is Markdown local SEO action plan.

## User Intent Mapping

- "Optimize our Google Business Profile" (GBP)
- "We don't show up in map pack results" (rankings)
- "Local citation audit for our business" (citations)
- "Multi-location local SEO strategy" (multi-location)
- "How do we rank for 'near me' searches?" (local keywords)
- "Review management strategy for local SEO" (reviews)
- "Our NAP is inconsistent across directories" (consistency)
- "Local content strategy" (content)
- "Google Maps optimization" (maps)
- "Local link building for SEO" (links)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Business Name | Text | Legal business name and any DBA |
| Location(s) | Text | Address(es), service areas |
| Business Category | Text | Primary and secondary categories |

### If You Don't Have This Data

- **No Google Business Profile?** Claude provides a step-by-step setup guide. Creating and verifying your GBP is the single highest-impact local SEO action.
- **No citation data?** Claude provides a top-50 citation source list for your industry. Manual audit takes 1-2 hours or use Moz Local / BrightLocal for automated scanning.
- **No review data?** Check your GBP directly for review count and rating. Claude works with whatever review data you have.
- **No local rank tracking?** Search your top 5 keywords incognito from your service area and note positions. This gives a baseline.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| GBP Insights | CSV/Text | Impressions, clicks, calls, direction requests |
| Review Count/Rating | Text | Current Google review count and average rating |
| Citation List | Text | Known directory listings |
| Competitor GBPs | Text | Top 3 local competitors |
| Service Area | Text | Geographic area served |

## Process

### Step 1: Google Business Profile Audit
- Profile completeness check (name, address, phone, hours, categories, description, photos)
- Category optimization (primary + secondary categories)
- Attribute selection (amenities, services, accessibility)
- Photo and video optimization (quality, quantity, recency)
- Post strategy (weekly updates, offers, events)
- Q&A section management

### Step 2: NAP Consistency Audit
- Name, Address, Phone consistency across all platforms
- Identify and fix inconsistencies in major directories
- Structured citation sources (Yelp, Yellow Pages, BBB, industry-specific)
- Unstructured citations (blog mentions, news articles, sponsorships)

### Step 3: Local Keyword Strategy
- "Near me" and geo-modified keyword research
- Service + location keyword mapping
- Local intent keyword identification
- Long-tail local queries (neighborhoods, landmarks, "best [service] in [city]")

### Step 4: Review Strategy
- Review velocity targets (how many reviews per month)
- Review solicitation workflow (timing, method, follow-up)
- Review response templates (positive and negative)
- Review monitoring and alerts

### Step 5: Local Content Plan
- Location pages (one per service area, unique content)
- Local blog content (community events, local partnerships, area guides)
- Local structured data (LocalBusiness schema)
- Local landing pages for paid campaigns

### Step 6: Local Link Building
- Local business associations and chambers of commerce
- Sponsorships and community involvement
- Local news and media coverage
- Partner cross-promotion
- Local event participation

### Confidence & Sample Size
> **Confidence Note**: Local SEO rankings vary significantly by searcher location — check rankings from multiple points within your service area. GBP insights data has a 3-day delay. Review velocity matters more than total count — a business with 10 reviews from this month outranks one with 50 reviews from 2 years ago. Multi-location businesses need separate strategies per location.

### ⚠️ Human Checkpoint
> Verify all business information (hours, phone, address) is accurate before updating across platforms. Incorrect NAP data can trigger GBP suspension. Never incentivize reviews with discounts or rewards (violates Google policy).

> **Benchmark Context**: 46% of all Google searches have local intent. The top 3 map pack results get 75% of local search clicks. Businesses with 40+ Google reviews earn 15% more revenue than average. GBP listings with 100+ photos get 520% more calls. Responding to reviews increases conversion by 16%. 88% of local mobile searches result in a call or visit within 24 hours.

## Output Contract

### Deliverable: Markdown Local SEO Plan

```markdown
# Local SEO Optimization: [Business]

## GBP Audit
| Element | Status | Action Required |
|---|---|---|

## NAP Consistency
| Platform | Name | Address | Phone | Status |
|---|---|---|---|---|

## Local Keyword Targets
| Keyword | Monthly Volume | Current Rank | Priority |
|---|---|---|---|

## Review Strategy
- Current: [count] reviews, [rating] avg
- Target: [count] reviews/month
- Solicitation workflow: [process]

## Local Content Calendar
| Month | Content | Target Keywords | Type |
|---|---|---|---|

## Citation Action Plan
| Directory | Status | Action |
|---|---|---|

## Quick Wins
1. [Action] — Expected impact: [metric]
```

## Platform Implementation Steps

### Google Business Profile
1. Claim and verify your listing at business.google.com
2. Complete every field (description, hours, categories, attributes, photos)
3. Add 10+ high-quality photos (exterior, interior, team, products)
4. Post weekly updates (events, offers, news)
5. Set up messaging and booking (if applicable)

### Citation Management
1. Use Moz Local, BrightLocal, or Yext for automated citation management
2. Manually claim top 20 directories (Yelp, Facebook, Apple Maps, Bing Places)
3. Fix any NAP inconsistencies immediately
4. Set calendar reminder for quarterly citation audit

### Review Management
1. Create a review request email/SMS template
2. Set up automated review request after service completion
3. Monitor reviews daily with Google Alerts or review management tool
4. Respond to all reviews within 24-48 hours

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| GBP suspended | Policy violation or incorrect business info | Fix the violation; submit reinstatement request |
| Rankings dropped after NAP update | Google re-evaluating due to data change | Wait 2-4 weeks; ensure all citations match exactly |
| Fake negative reviews | Competitor or disgruntled non-customer | Flag for removal via GBP; respond professionally |
| Location pages flagged as thin content | Duplicate content across location pages | Unique content per page: local testimonials, staff, area info |

## How to Get Your Data

- **GBP Insights**: Google Business Profile → Performance (formerly Insights)
- **Citation scan**: BrightLocal free scan or manual search for your business name
- **Review data**: Check your GBP listing directly
- **No data**: Provide business name, address, and category — Claude builds the full plan

## Example

**Input**: "Local SEO for a dental practice. Single location in Austin, TX. 45 Google reviews (4.3 stars). Ranking 5th-7th in map pack for 'dentist Austin'. Competitors have 150+ reviews."

**Output**: GBP audit: missing 6 secondary categories (add Cosmetic Dentist, Emergency Dental Service, Teeth Whitening Service, etc.), only 8 photos (add 20+: team, office, before/after, equipment), no weekly posts. Review strategy: target 10 reviews/month (currently ~3/month) — implement post-appointment SMS request, add QR code to checkout, train front desk on verbal ask. NAP: inconsistent phone number on Yelp and Healthgrades — fix immediately. Local keywords: target "emergency dentist Austin" (low competition, high intent), "cosmetic dentist South Austin" (geo-specific), "dentist near [neighborhood]" for 5 surrounding areas. Content: create 5 neighborhood-specific landing pages (South Austin, Downtown, East Austin, Cedar Park, Round Rock). Quick wins: (1) add missing GBP categories (10 min), (2) upload 15 new photos (30 min), (3) start weekly GBP posts (15 min/week), (4) fix NAP on Yelp/Healthgrades (20 min). Expected: move from position 5-7 to top 3 map pack within 90 days.

## Related Skills

- **[On Page SEO Auditor](./on-page-seo-auditor.md)** — Use to optimize page elements for local search, including local keywords, business information, and structured data.
- **[Technical SEO Auditor](./technical-seo-auditor.md)** — Use to ensure your site structure supports multi-location SEO and proper schema markup for local businesses.
- **[Content Localization Planner](../content/content-localization-planner.md)** — Use to create location-specific content that builds local relevance and authority.
- **[International SEO Strategy](./international-seo-strategy.md)** — Use if managing multiple regions or countries; local optimization is a component of international SEO strategy.
