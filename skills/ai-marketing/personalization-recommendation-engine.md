---
name: personalization-recommendation-engine
description: >
  Design product and content recommendation systems for e-commerce and media platforms.
  Use this skill when the user says "recommendation engine design", "product recommendations",
  "personalized recommendations", "recommendation algorithm", "you might also like feature",
  "cross-sell recommendations", "content recommendations", "recommendation system setup",
  "collaborative filtering for marketing", "recommendation widget optimization", or "AI product
  suggestions". Also trigger for recommendation A/B testing, recommendation placement strategy,
  or recommendation engine evaluation.
---

# Personalization & Recommendation Engine

Designs product and content recommendation systems — algorithm selection, placement strategy, cold-start solutions, and performance optimization for e-commerce and content platforms.

## Granularity Check

> **Session time**: ~10 min context gathering + ~15 min Claude session. If implementing, add 2-6 weeks for engineering. Input is product catalog, user behavior data, and platform. Output is Markdown recommendation strategy with algorithm selection and placement plan.

## User Intent Mapping

- "Build product recommendations for our site" (e-commerce)
- "Content recommendation engine" (media/blog)
- "You might also like — how to implement" (implementation)
- "Recommendation algorithm selection" (algorithm)
- "Cross-sell recommendations" (cross-sell)
- "Our recommendations aren't relevant" (optimization)
- "Cold start problem — new users have no data" (cold start)
- "Recommendation placement strategy" (placement)
- "A/B test our recommendations" (testing)
- "Recommendation engine ROI" (ROI)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Catalog Size | Text | Number of products or content pieces |
| User Behavior Data | Text | What interaction data you collect |
| Platform | Text | E-commerce, blog, SaaS, media |

### If You Don't Have This Data

- **No behavioral data?** Claude designs a rule-based recommendation system (best sellers, trending, category-based) while you build up data for personalization.
- **Small catalog?** Claude focuses on cross-sell logic and manual curation rules rather than algorithmic recommendations.
- **No recommendation engine?** Claude starts with simple implementations (Shopify apps, WordPress plugins) before custom solutions.
- **No engineering resources?** Claude recommends third-party recommendation services (Nosto, Dynamic Yield, Algolia Recommend) by budget.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Purchase/Engagement Data | CSV | User interaction history |
| Conversion Data | Text | Current recommendation conversion rates |
| Category Structure | Text | Product/content taxonomy |
| Business Rules | Text | Margin, inventory, or promotional priorities |
| Competitor Approach | Text | How competitors handle recommendations |

## Process

### Step 1: Algorithm Selection
| Algorithm | Type | Best For | Data Needed |
|---|---|---|---|
| Best sellers/trending | Non-personalized | Cold start, small catalogs | Aggregate sales |
| Category-based | Rule-based | Related items in same category | Category taxonomy |
| Collaborative filtering | Personalized | "Users who bought X also bought Y" | User-item interactions |
| Content-based filtering | Personalized | Similar product attributes | Product metadata |
| Hybrid | Personalized | Best overall performance | Both behavioral + product data |
| Association rules | Rule-based | Frequently bought together | Transaction data |

### Step 2: Recommendation Types
| Type | Placement | Algorithm | Business Impact |
|---|---|---|---|
| "You may also like" | Product page | Collaborative + content-based | Cross-sell |
| "Frequently bought together" | Cart page | Association rules | AOV increase |
| "Recently viewed" | Homepage, category | Session-based | Re-engagement |
| "Trending now" | Homepage | Popularity-based | Discovery |
| "Based on your history" | Homepage, email | Collaborative filtering | Retention |
| "Complete the look" | Product page | Curated + algorithmic | Bundle sales |

### Step 3: Placement Strategy
- **Product page**: Related items and complementary products (highest conversion placement)
- **Cart/checkout**: Cross-sell and frequently bought together (highest AOV impact)
- **Homepage**: Personalized for returning users, trending for new visitors
- **Category page**: Featured and best-selling within category
- **Search results**: Sponsored or recommended within search results
- **Email**: Personalized product picks in post-purchase and browse abandonment
- **Post-purchase**: Replenishment and complementary in transactional emails

### Step 4: Cold Start Solutions
| Scenario | Solution |
|---|---|
| New user, no history | Show best sellers, trending, or editorially curated picks |
| New user, some context | Use referral source, landing page, or stated preferences |
| New product, no data | Feature in "New Arrivals"; use content-based similarity to existing products |
| New product + new user | Category-based recommendations + popularity fallback |

### Step 5: Business Rules Layer
- Minimum margin filter (don't recommend low-margin items)
- Inventory awareness (don't recommend out-of-stock)
- Promotional boosting (weight current promotions in recommendations)
- Diversity rules (don't show 4 variants of the same product)
- Suppression rules (don't recommend already-purchased items, unless replenishable)
- Freshness weighting (boost newer products in recommendations)

### Step 6: Performance Measurement
| Metric | Description | Target |
|---|---|---|
| Click-through rate | % of users who click a recommendation | 5-15% |
| Conversion rate | % of recommendation clicks that convert | 10-20% |
| Revenue per impression | Revenue generated per recommendation shown | Varies |
| Coverage | % of catalog appearing in recommendations | >50% |
| Diversity | Variety of recommendations shown | Avoid filter bubbles |

### Confidence & Sample Size

> **Confidence Note**: Recommendation engines need at least 1,000 monthly interactions to train collaborative filtering effectively. Rule-based recommendations are perfectly valid for smaller catalogs (<500 items). A/B test every recommendation placement — position and algorithm together. The "you might also like" section on product pages typically generates 10-30% of total site revenue. Don't over-optimize for clicks at the expense of customer experience.

### ⚠️ Human Checkpoint
> Review recommendation output for relevance and appropriateness before launch. Verify business rules (margin, inventory) are properly applied. Test cold-start experience for new users. Monitor for filter bubble effects (users seeing same recommendations repeatedly).

> **Benchmark Context**: Product recommendations drive 10-30% of e-commerce revenue. Personalized recommendations increase conversion by 150-300% vs. non-personalized. Cart page recommendations increase AOV by 10-15%. "Frequently bought together" has 2-3x higher conversion than "similar products." Recommendation engines provide 35% of Amazon's revenue. Email product recommendations increase click rates by 300%.

## Output Contract

### Deliverable: Markdown Recommendation Strategy

```markdown
# Recommendation Engine Strategy: [Brand]

## Algorithm Selection
| Recommendation Type | Algorithm | Placement | Data Source |
|---|---|---|---|

## Placement Plan
| Location | Rec Type | Widget Design | Expected Impact |
|---|---|---|---|

## Cold Start Strategy
| Scenario | Fallback Logic |
|---|---|

## Business Rules
| Rule | Logic | Override Condition |
|---|---|---|

## Implementation Plan
| Phase | Component | Timeline | Effort |
|---|---|---|---|

## Measurement
| Metric | Baseline | Target | Tracking |
|---|---|---|---|
```

## Platform Implementation Steps

### Shopify
1. Evaluate recommendation apps (Nosto, LimeSpot, Wiser, Rebuy)
2. Configure product recommendation widgets for PDP, cart, and homepage
3. Set up "frequently bought together" on product pages
4. Enable email recommendations via Klaviyo or app integration

### Custom/Headless
1. Evaluate recommendation APIs (Algolia Recommend, Amazon Personalize, Recombee)
2. Build data pipeline for user interaction events
3. Implement recommendation widgets in frontend
4. Set up A/B testing framework for recommendation experiments

### WordPress/Content
1. Install recommendation plugin (JEPTO, Jeeng, or custom)
2. Configure related posts by category, tag, and engagement
3. Add "popular posts" widget using analytics data
4. Set up personalized content recommendations for returning visitors

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Irrelevant recommendations | Poor data quality or wrong algorithm | Audit training data; switch algorithm; add business rules |
| Low click-through | Bad placement or generic titles | A/B test positions; improve widget design; use dynamic titles |
| Filter bubble | Over-personalization | Add diversity rules; mix personalized with discovery items |
| Recommending out-of-stock | No inventory integration | Add real-time inventory check to recommendation pipeline |

## How to Get Your Data

- **User behavior**: Analytics → user interaction events (views, clicks, purchases)
- **Product data**: E-commerce platform → product catalog with categories, attributes, prices
- **Transaction data**: Order history with products per order (for association rules)
- **No data**: Describe your product catalog and customer behavior — Claude designs a rule-based starter system

## Example

**Input**: "Recommendation engine for fashion e-commerce. 5,000 SKUs across clothing, shoes, accessories. 200K monthly visitors, 8K orders/month. Using Shopify Plus. Currently showing 'You may also like' with random products from same category. AOV is $75, want to increase to $90."

**Output**: Current: random same-category recommendations = minimal personalization value. Recommended approach: (1) Product page — "Complete the Look" (outfit-based recommendations using style/color/occasion matching) + "Customers Also Bought" (collaborative filtering via Nosto or Rebuy). Expected: 15% of PDP visitors click recommendations, 8% conversion on clicks. (2) Cart page — "Frequently Bought Together" (association rules from order history) + free shipping threshold prompt ("Add $X to get free shipping" with curated suggestions). Expected: 12% add complementary item = $12 AOV increase. (3) Homepage — "Recommended for You" (personalized for returning visitors based on browse/purchase history), "Trending Now" (for new visitors). (4) Post-purchase email — "Complete Your Order" with complementary items, 3 days after delivery. (5) Browse abandonment — personalized picks based on viewed products, 2 hours after session. Implementation: Phase 1 (week 1-2) — install Rebuy on Shopify Plus, configure PDP and cart widgets. Phase 2 (week 3-4) — set up homepage personalization and email recommendations via Klaviyo. Expected results: AOV $75 → $88-92 within 3 months. Recommendation revenue: 15-20% of total site revenue.
