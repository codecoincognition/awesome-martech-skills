---
name: social-commerce-optimizer
description: >
  Optimize social commerce strategy — shoppable posts, product tagging, and conversion funnels.
  Use this skill when the user says "social commerce strategy", "shoppable posts optimization",
  "Instagram shopping", "TikTok Shop strategy", "Facebook Shops", "social selling strategy",
  "product tagging best practices", "social commerce funnel", "live shopping strategy", "social
  storefront optimization", or "Pinterest shopping ads". Also trigger for social checkout
  optimization, social commerce analytics, or social-to-purchase conversion improvements.
---

# Social Commerce Optimizer

Analyzes and optimizes social commerce performance across platforms — product catalog setup, shoppable content strategy, conversion funnel optimization, and live shopping planning.

## Granularity Check

> **Time**: ~5 min data prep → ~10 min Claude session → ~20-40 min scheduling in Buffer / Hootsuite / native platform. If implementing output in a platform, add 20-30 min for catalog/shop setup. Input is product catalog info and social commerce data. Output is Markdown optimization report with action plan.

## User Intent Mapping

- "How do I set up Instagram Shopping?" (platform setup)
- "Our social commerce conversion rate is low" (optimization)
- "TikTok Shop strategy for our brand" (platform-specific)
- "Best practices for shoppable posts" (content strategy)
- "Live shopping plan for our product launch" (live commerce)
- "Optimize our Facebook Shop" (storefront)
- "Social commerce funnel analysis" (analytics)
- "Which products should we feature on social?" (merchandising)
- "Pinterest shopping strategy" (platform-specific)
- "Social checkout vs. website checkout — what converts better?" (funnel decision)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Products/Services | Text | What you sell, price range, top sellers |
| Platform(s) | Text | Instagram, TikTok, Facebook, Pinterest, or all |
| Current Setup | Text | What you've already set up (catalog, shop, tagging) |

### If You Don't Have This Data

- **No social shop yet?** Describe your products and target platform. Claude generates a setup checklist and launch strategy.
- **No sales data?** Start with product tagging on your top 5 posts. Track clicks and saves for 2 weeks to establish a baseline.
- **No product catalog?** List your top 10 products with names, prices, and image descriptions. That's enough to start.
- **No competitor benchmarks?** Claude uses industry averages. Browse competitor shops on Instagram/TikTok for qualitative benchmarks.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Sales Data | CSV | Product, platform, clicks, conversions, revenue |
| Top Products | Text list | Best-selling items to prioritize |
| Content Performance | CSV | Posts with product tags, engagement, click-through |
| Target Audience | Text | Demographics and shopping behavior |
| Budget | Text | Ad spend for boosting shoppable content |

## Process

### Step 1: Platform Audit
Evaluate current setup per platform:

| Platform | Shop Features | Best For |
|---|---|---|
| Instagram | Shop tab, product tags, Checkout, Live Shopping | Visual products, fashion, beauty, home |
| TikTok | TikTok Shop, product links, LIVE shopping, affiliate | Impulse buys, trending items, sub-$50 products |
| Facebook | Facebook Shops, Marketplace, product tags | Broad demographics, local businesses |
| Pinterest | Product Pins, Shopping ads, Catalogs | Home decor, fashion, DIY, wedding, food |

### Step 2: Catalog Optimization
- Product title optimization (keyword-rich, benefit-led)
- Product description best practices (features + social proof)
- Image requirements per platform (dimensions, lifestyle vs. product shots)
- Collection/category structure recommendations
- Pricing display strategy (anchor pricing, bundles)

### Step 3: Shoppable Content Strategy
- Content mix: product showcases (30%), lifestyle/UGC (40%), educational (20%), promotional (10%)
- Product tagging frequency and placement
- Carousel vs. single image vs. Reels for product content
- UGC integration (customer photos with product tags)
- Seasonal and trending product promotion calendar

### Step 4: Conversion Funnel Optimization
- Discovery → Click → Cart → Purchase funnel analysis
- Friction point identification (checkout abandonment, price hesitation)
- In-app checkout vs. website redirect decision framework
- Retargeting strategy for social commerce abandoners
- Social proof integration (reviews, ratings, "X people bought this")

### Step 5: Live Shopping Plan (if applicable)
- Live shopping event calendar
- Host selection (founder, influencer, employee)
- Product staging and demo flow
- Limited-time offers and urgency mechanics
- Post-live content repurposing

### Confidence & Sample Size
> **Confidence Note**: Social commerce is evolving rapidly. Platform features change frequently — verify current capabilities before implementing. Conversion benchmarks vary wildly by product category and price point. Test for minimum 2 weeks before drawing conclusions.

### ⚠️ Human Checkpoint
> Review product catalog for pricing accuracy, inventory availability, and platform policy compliance (prohibited products vary by platform) before publishing.

> **Benchmark Context**: Social commerce global revenue reached $700B in 2024. . Average conversion rate for shoppable posts is 1-3% (Buffer 2024 State of Social) Products under $50 convert 2-3x better on TikTok Shop (Buffer 2024 State of Social) Instagram Shopping drives 130M product tag taps per month. . Live shopping conversion rates are 10-20x higher than traditional e-commerce. . (Later 2024 Social Media Industry Report).
## Output Contract

### Deliverable: Markdown Optimization Report

```markdown
# Social Commerce Optimization: [Brand]

## Platform Audit
| Platform | Status | Priority Actions |
|---|---|---|

## Catalog Recommendations
- [Product title rewrites]
- [Image improvements]
- [Collection structure]

## Shoppable Content Plan
| Week | Content Type | Products Featured | Platform |
|---|---|---|---|

## Conversion Funnel
- Current: [estimated funnel]
- Optimized: [target funnel]
- Key fixes: [list]

## Live Shopping Calendar (if applicable)
| Date | Theme | Products | Host |
|---|---|---|---|

## Quick Wins
1. [Action] — Expected impact: [metric]
```

## Platform Implementation Steps

### Instagram Shopping
1. Connect Facebook catalog via Commerce Manager
2. Submit shop for review (1-3 business days)
3. Enable product tagging on posts and Reels
4. Create Collections for curated shopping experiences
5. Set up Instagram Checkout (US only) or link to website

### TikTok Shop
1. Register at seller.tiktok.com
2. Upload product catalog with required attributes
3. Enable product links in videos and LIVE streams
4. Set up TikTok Shop affiliate program for creator partnerships
5. Use Shop Ads to boost shoppable content

### Pinterest Shopping
1. Claim your website and connect product feed
2. Create Product Pins from your catalog
3. Set up Shopping Ads campaigns
4. Organize products into themed Boards
5. Enable Rich Pins for real-time pricing

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Low click-through on tags | Poor product placement in content | Feature products prominently; use lifestyle contexts |
| High cart abandonment | Checkout friction or price shock | Simplify checkout; add trust signals; test free shipping |
| Shop not approved | Policy violations or missing info | Review platform commerce policies; fix catalog issues |
| Low live shopping attendance | Poor promotion or wrong timing | Promote 48 hours in advance; test different time slots |

## How to Get Your Data

- **Instagram**: Insights → Content → Shopping → Product performance
- **TikTok Shop**: Seller Center → Analytics → Product performance
- **Facebook**: Commerce Manager → Performance → Product insights
- **Pinterest**: Analytics → Conversions → Product Pin performance
- **Manual**: Track tagged product posts and compare engagement vs. non-tagged

## Example

**Input**: "Optimize social commerce for a DTC skincare brand. Platforms: Instagram + TikTok. 15 SKUs, $25-$65 price range. Currently have Instagram Shop set up but low conversion. No TikTok Shop yet."

**Output**: Instagram audit: catalog images are product-only (need lifestyle shots), no collections set up, product tags only on 20% of posts. Recommendations: create 4 collections (Routine Builder, Best Sellers, Gifts, New Arrivals), increase tagging to 80% of posts, add UGC with product tags. TikTok Shop launch plan: register seller account, upload top 5 SKUs, partner with 3-5 micro-influencers for affiliate program, plan weekly LIVE shopping demos. Content calendar: 3 shoppable Reels/week on Instagram, 2 TikTok product videos/week. Quick win: add "Shop the Look" carousel to top 10 performing posts (expected 2x click-through lift).

## Related Skills

- **[Social Content Calendar](./social-content-calendar.md)** — Use to plan product-focused content for shoppable posts and shopping features.
- **[Ecommerce SEO Optimizer](../seo/ecommerce-seo-optimizer.md)** — Use to optimize product pages and metadata that feed into social commerce platforms.
- **[Social Engagement Analyzer](./social-engagement-analyzer.md)** — Use to measure conversion rates and engagement from shoppable posts.
- **[Checkout Funnel Optimizer](../cro/checkout-funnel-optimizer.md)** — Use to optimize the final checkout experience after customers are driven from social shopping features.
