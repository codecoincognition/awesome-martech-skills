---
name: checkout-funnel-optimizer
description: >
  Optimize checkout and purchase funnels to reduce cart abandonment and increase conversion rates.
  Use this skill when the user says "checkout optimization", "cart abandonment fix", "checkout
  funnel analysis", "purchase flow optimization", "reduce cart abandonment", "checkout UX
  improvement", "payment page optimization", "checkout conversion rate", "one-page checkout
  design", "shipping page optimization", or "checkout friction reduction". Also trigger for
  guest checkout optimization, checkout A/B testing, or payment method optimization.
---

# Checkout Funnel Optimizer

Analyzes and optimizes checkout and purchase funnels to reduce abandonment, eliminate friction, and increase conversion rates across cart, shipping, payment, and confirmation steps.

## Granularity Check

> **Time**: ~5 min data prep → ~10 min Claude session → ~30-60 min implementing in your testing tool / CMS. If implementing, add 1-3 weeks for UX and development. Input is checkout analytics and current flow. Output is Markdown optimization plan with prioritized fixes.

## User Intent Mapping

- "Our cart abandonment rate is too high" (abandonment)
- "Optimize our checkout flow" (optimization)
- "Checkout funnel analysis" (analysis)
- "Should we do one-page or multi-step checkout?" (UX)
- "Payment page isn't converting" (payment)
- "Shipping page drop-off" (shipping)
- "Guest checkout vs. account creation" (friction)
- "Checkout A/B test ideas" (testing)
- "Mobile checkout optimization" (mobile)
- "Add payment methods to increase conversion" (payments)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Checkout Funnel Data | CSV/Text | Visitors and drop-offs per checkout step |
| Current Checkout Flow | Text/Screenshots | Steps in your checkout process |
| Cart Abandonment Rate | Text | Current abandonment percentage |

### If You Don't Have This Data

- **No funnel data?** Claude uses industry benchmarks (70% cart abandonment average) and common friction points to recommend fixes.
- **No analytics setup?** Claude recommends tracking implementation and provides a list of critical checkout events to track.
- **Can't change checkout?** Claude focuses on pre-checkout optimizations (cart page, trust signals, abandonment recovery).
- **Using hosted checkout?** Claude optimizes what you can control and recommends platform-specific settings.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Heatmaps/Session Recordings | Screenshots | Visual data on user behavior in checkout |
| Customer Complaints | Text | Common checkout complaints from support |
| Mobile vs. Desktop Split | Text | Conversion rate by device |
| Payment Methods | Text | Currently accepted payment methods |
| AOV | Text | Average order value |

## Process

### Step 1: Funnel Analysis
| Step | Visitors | Drop-off | Rate | Benchmark |
|---|---|---|---|---|
| Product page | [N] | - | - | - |
| Add to cart | [N] | [%] | [%] | 8-12% add-to-cart |
| Cart page | [N] | [%] | [%] | 30% cart drop-off |
| Checkout start | [N] | [%] | [%] | 25% drop at info entry |
| Shipping | [N] | [%] | [%] | 15% drop at shipping |
| Payment | [N] | [%] | [%] | 10% drop at payment |
| Confirmation | [N] | - | [%] | 2-4% overall conversion |

### Step 2: Friction Identification
| Friction Point | Impact | Common Causes | Fix |
|---|---|---|---|
| Account creation required | High | Forced signup before checkout | Offer guest checkout |
| Unexpected shipping costs | Very high | Costs shown late in funnel | Show shipping early; free shipping threshold |
| Too many form fields | High | Unnecessary data collection | Remove non-essential fields |
| Limited payment options | Medium | Missing preferred payment method | Add Apple Pay, Google Pay, BNPL |
| Slow page load | High | Heavy checkout page | Optimize performance |
| Security concerns | High | Missing trust signals | Add badges, SSL, reviews |

### Step 3: Cart Page Optimization
- Order summary with product images and easy quantity editing
- Shipping cost estimate or free shipping threshold indicator
- Promo code field (but not too prominent — causes people to leave and search for codes)
- Trust signals (security badges, return policy, support contact)
- Cross-sell recommendations (frequently bought together)
- Save cart / wishlist option for non-converters

### Step 4: Checkout Flow Optimization
- Guest checkout as default (account creation optional at confirmation)
- Address autocomplete (Google Places API)
- Minimal form fields (only what's necessary for the order)
- Progress indicator showing checkout steps
- Inline validation (real-time error feedback)
- Mobile-optimized input types (numeric keyboard for phone/zip)
- Express checkout options (Shop Pay, Apple Pay, Google Pay)

### Step 5: Payment Page Optimization
- Multiple payment methods (credit card, PayPal, Apple Pay, Google Pay, BNPL)
- Saved payment methods for returning customers
- Clear security indicators (lock icon, encryption messaging)
- Order total visible at all times
- BNPL option for orders over $50 (increases AOV 20-30%)
- Clear error messaging for declined cards

### Step 6: Abandonment Recovery
- Exit-intent popup with incentive (5-10% off or free shipping)
- Cart abandonment email sequence (1 hour, 24 hours, 72 hours)
- SMS abandonment recovery (if opted in)
- Retargeting ads showing abandoned products
- Persistent cart (saved for returning visitors)

### Confidence & Sample Size

> **Confidence Note**: Checkout optimization requires at least 100 completions per variant for reliable A/B testing. Small changes (button color, copy) have small effects — focus on structural changes (removing steps, adding payment methods) for bigger impact. Mobile checkout optimization has outsized ROI since mobile conversion is typically 50% lower than desktop. Test one change at a time to isolate impact.

### ⚠️ Human Checkpoint
> Have QA test entire checkout flow on all devices before launching changes. Verify payment processing works correctly after any checkout modifications. Review abandonment email content for accuracy (pricing, product images, links).

> **Benchmark Context**: Average cart abandonment rate is 70% (Baymard Institute 2024 Cart Abandonment Statistics). Top reason for abandonment: unexpected shipping costs (48%). Guest checkout increases conversion 14% vs (Baymard Institute 2024 Cart Abandonment Statistics). required account creation. Express checkout (Apple Pay, etc.) increases mobile conversion by 20-30% (Unbounce 2024 Conversion Benchmark Report). Cart abandonment emails recover 5-15% of abandoned carts (Baymard Institute 2024 Cart Abandonment Statistics). BNPL increases AOV by 20-30% and conversion by 20% (Unbounce 2024 Conversion Benchmark Report). (Unbounce 2024 Conversion Benchmark Report).
## Output Contract

### Deliverable: Markdown Checkout Optimization Plan

```markdown
# Checkout Optimization: [Brand]

## Funnel Analysis
| Step | Current Rate | Benchmark | Gap | Priority |
|---|---|---|---|---|

## Friction Points
| Issue | Impact | Step | Fix | Effort |
|---|---|---|---|---|

## Optimization Plan
### Phase 1: Quick Wins
1. [Fix] — Expected lift: [%]

### Phase 2: UX Improvements
1. [Fix] — Expected lift: [%]

### Phase 3: Advanced
1. [Fix] — Expected lift: [%]

## Abandonment Recovery Plan
| Tactic | Timing | Expected Recovery |
|---|---|---|

## A/B Test Roadmap
| Test | Hypothesis | Metric | Priority |
|---|---|---|---|

## Expected Results
- Cart abandonment: [current] → [target]
- Checkout conversion: [current] → [target]
- Revenue impact: [estimate]
```

## Platform Implementation Steps

### Shopify
1. Settings → Checkout → enable guest checkout, Shop Pay, accelerated checkout
2. Add trust badges via theme customization or app (Trust Badge Master)
3. Install abandonment recovery app (Klaviyo, Privy) for email + SMS
4. Enable address autocomplete (Shopify built-in or Google Places app)

### WooCommerce
1. Install checkout optimization plugin (CheckoutWC, Fluid Checkout)
2. Configure guest checkout in WooCommerce → Settings → Accounts
3. Add payment gateways (Stripe for cards, PayPal, Apple Pay, BNPL via Afterpay/Klarna)
4. Set up abandonment recovery via Klaviyo or AutomateWoo

### Custom/Headless
1. Implement express checkout APIs (Stripe Payment Element, PayPal JS SDK)
2. Add address autocomplete with Google Places API
3. Implement persistent cart with session storage
4. Build checkout analytics tracking (step-by-step funnel events)

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Checkout breaks after changes | Incomplete testing across devices/browsers | Full QA before launch; roll back immediately if errors; test payments end-to-end |
| Abandonment emails annoy customers | Too frequent or irrelevant | Limit to 3 emails max; include easy unsubscribe; personalize with actual cart items |
| Express checkout not working | Payment provider misconfiguration | Test with real transactions; verify domain and SSL setup |
| No conversion lift despite changes | Changes too small or wrong friction identified | Focus on bigger structural changes; use session recordings to identify real friction |

## How to Get Your Data

- **Funnel data**: GA4 → Explore → Funnel Exploration with checkout steps
- **Abandonment rate**: E-commerce platform → checkout analytics or GA4 → E-commerce → Checkout
- **Session recordings**: Hotjar, FullStory, or Microsoft Clarity → filter for checkout sessions
- **No data**: Describe your checkout flow — Claude identifies likely friction points based on common patterns

## Example

**Input**: "Checkout optimization for DTC furniture brand. Shopify Plus. AOV: $850. Cart abandonment: 78%. 4-step checkout (info → shipping → payment → review). Mobile: 65% of traffic but only 1.2% conversion (vs. 3.1% desktop). No express checkout, no BNPL."

**Output**: Critical issues: 78% cart abandonment (8 points above average, 18 points above best-in-class for high-AOV). Root causes: (1) No BNPL — at $850 AOV, monthly payments are essential. Adding Affirm/Klarna expected to increase conversion 20-30% and AOV 15%. (2) No express checkout — mobile 1.2% conversion is 60% below desktop; Apple Pay/Google Pay expected to lift mobile 25-35%. (3) 4-step checkout — consolidate to 2 steps (info+shipping → payment+review). (4) Shipping costs shown late — $99 shipping appearing at step 2 causes sticker shock. Fix: show shipping estimate on product page and cart. Phase 1 (week 1): enable Shop Pay + Apple Pay + Google Pay (Shopify Plus built-in). Add Affirm BNPL. Expected lift: mobile conversion 1.2% → 1.8%. Phase 2 (week 2): consolidate checkout to 2 steps. Add shipping estimate on cart page. Expected lift: overall conversion 2.0% → 2.6%. Phase 3 (week 3): cart abandonment email + SMS sequence via Klaviyo (1hr, 24hr, 72hr). Expected recovery: 8-12% of abandoned carts. Revenue impact: at current traffic, improving conversion from 2.0% to 2.6% + recovering 10% of abandoned carts = estimated $180K additional annual revenue.

## Related Skills

- **ab-test-designer** (./ab-test-designer.md) — Design A/B tests for checkout changes (new payment methods, form field reductions, flow steps); use to validate which optimizations drive highest lift.
- **landing-page-optimizer** (./landing-page-optimizer.md) — Design post-purchase confirmation pages and cart summary messaging; use to build confidence and reduce purchase anxiety.
- **retargeting-campaign-builder** (../ads/retargeting-campaign-builder.md) — Build abandonment recovery campaigns with retargeting ads; use to recover lost carts through dynamic product ads.
- **funnel-drop-off-analyzer** (../analytics/funnel-drop-off-analyzer.md) — Analyze where users drop off in your checkout funnel; use to prioritize optimization opportunities.
