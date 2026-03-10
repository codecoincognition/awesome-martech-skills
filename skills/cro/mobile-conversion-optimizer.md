---
name: mobile-conversion-optimizer
description: >
  Optimize mobile web and app experiences for higher conversion rates through UX, speed, and mobile-specific design.
  Use this skill when the user says "mobile conversion optimization", "mobile UX improvement", "mobile checkout
  optimization", "responsive design conversion", "mobile-first CRO", "mobile bounce rate reduction", "mobile
  form optimization", "thumb-friendly design", "mobile page speed optimization", "mobile landing page optimization",
  or "app store conversion optimization". Also trigger for mobile funnel analysis, progressive web app optimization,
  or mobile-specific A/B testing.
---

# Mobile Conversion Optimizer

Optimizes mobile web and app experiences for higher conversion rates through mobile-specific UX patterns, speed optimization, thumb-zone design, and mobile funnel analysis.

## Granularity Check

> **Time**: ~5 min data prep → ~10 min Claude session → ~30-60 min implementing in your testing tool / CMS. If implementing, add 1-2 weeks for design and development changes. Input is mobile analytics data and current mobile experience details. Output is Markdown optimization plan with mobile-specific fixes.

## User Intent Mapping

- "Our mobile conversion rate is half of desktop" (gap analysis)
- "Mobile users aren't converting" (general optimization)
- "Mobile checkout is broken" (checkout)
- "High mobile bounce rate" (engagement)
- "Mobile page loads too slowly" (speed)
- "Mobile forms are hard to fill out" (forms)
- "Responsive design isn't converting" (design)
- "Mobile-first redesign" (redesign)
- "Mobile vs. desktop behavior differences" (comparison)
- "App store listing optimization" (app store)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Mobile Analytics | Text/CSV | Mobile traffic, bounce rate, conversion rate |
| Page/Flow | Text | Which pages or funnels to optimize |
| Current Experience | Text/Screenshots | How the mobile experience works today |

### If You Don't Have This Data

- **No mobile-specific analytics?** Claude shows you how to segment mobile data in GA4 (2-minute setup) and provides industry benchmarks to identify gaps.
- **No screenshots?** Describe your mobile experience or share your URL — Claude provides optimization recommendations based on common mobile UX issues.
- **No conversion tracking?** Claude recommends mobile-specific tracking setup and prioritizes optimizations based on engagement metrics (bounce rate, scroll depth, time on page).
- **Don't know mobile vs. desktop split?** Industry average is 60% mobile — Claude provides category-specific benchmarks.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Desktop Metrics | Text | Desktop conversion rate for comparison |
| Device Breakdown | Text | iOS vs. Android, phone vs. tablet |
| Page Speed Data | Text | Mobile page speed scores (Lighthouse, PageSpeed Insights) |
| Heatmap Data | Screenshots | Mobile-specific click and scroll maps |
| Competitor Mobile | Text | How competitors' mobile experiences perform |

## Process

### Step 1: Mobile Gap Analysis
| Metric | Desktop Benchmark | Mobile Benchmark | Gap Signal |
|---|---|---|---|
| Conversion rate | Baseline | 50-70% of desktop | >40% gap = critical UX issues |
| Bounce rate | Baseline | 10-20% higher than desktop | >25% higher = engagement problem |
| Pages per session | Baseline | 20-30% fewer than desktop | >40% fewer = navigation issue |
| Avg session duration | Baseline | 30-40% shorter than desktop | >50% shorter = content/speed issue |
| Cart abandonment | Baseline | 10-15% higher than desktop | >20% higher = checkout friction |

### Step 2: Mobile UX Audit
| Area | Check | Common Issue |
|---|---|---|
| Tap targets | 48px minimum height and width | Too small = frustrating taps, rage clicks |
| Thumb zone | Primary actions in bottom 60% of screen | Key CTAs in hard-to-reach corners |
| Text size | 16px minimum body text | Small text forces pinch-to-zoom |
| Forms | Input type attributes (tel, email, number) | Wrong keyboard shows for input field |
| Images | Responsive, lazy-loaded, properly sized | Oversized images killing load time |
| Navigation | Hamburger menu, bottom nav, or simplified | Complex desktop nav crammed into mobile |
| White space | Adequate spacing between elements | Cramped layout = accidental taps |
| Orientation | Works in portrait and landscape | Breaks in landscape mode |

### Step 3: Mobile Speed Optimization
| Factor | Target | Fix |
|---|---|---|
| First Contentful Paint | < 1.8s | Optimize critical rendering path, inline critical CSS |
| Largest Contentful Paint | < 2.5s | Compress images, use WebP/AVIF, lazy load below-fold |
| Cumulative Layout Shift | < 0.1 | Set image dimensions, avoid dynamic content injection |
| Interaction to Next Paint | < 200ms | Reduce JavaScript, defer non-critical scripts |
| Total page size | < 1.5 MB | Compress assets, remove unused CSS/JS, optimize fonts |
| HTTP requests | < 50 | Combine files, use sprites, eliminate unnecessary calls |

### Step 4: Mobile Checkout Optimization
- Single-column layout (no side-by-side fields)
- Auto-detect and format credit card type
- Address autocomplete (Google Places API)
- Express checkout options (Apple Pay, Google Pay, PayPal)
- Guest checkout default (account creation optional, post-purchase)
- Progress indicator showing steps remaining
- Persistent order summary (collapsible on mobile)
- Sticky "Complete Purchase" button at bottom of screen

### Step 5: Mobile Form Best Practices
- Minimize fields (every field removed increases conversion 5-10%)
- Use input type attributes: `type="tel"`, `type="email"`, `type="number"`
- Show/hide password toggle
- Inline validation (validate as user types, not on submit)
- Auto-advance between fields (for OTP, phone number)
- Avoid dropdowns for < 5 options (use radio buttons or segmented controls)
- Place labels above fields (not inline placeholder text)
- Sticky submit button visible above keyboard

### Step 6: Mobile-Specific Design Patterns
| Pattern | Use Case | Impact |
|---|---|---|
| Bottom sheet | Product details, filters, options | Keeps context, thumb-friendly |
| Sticky CTA bar | E-commerce, SaaS signup | CTA always visible (+15-25% CTR) |
| Swipeable cards | Product galleries, testimonials | Native-feeling interaction |
| Pull-to-refresh | Content feeds, dashboards | Familiar mobile pattern |
| Floating action button | Primary action (add, compose, buy) | Persistent, accessible |
| Accordion sections | FAQ, product specs, long content | Reduces scroll, user controls depth |

### Confidence & Sample Size

> **Confidence Note**: Mobile optimization often yields larger conversion lifts than desktop because mobile UX is typically worse — there's more low-hanging fruit. However, mobile users also have different intent patterns (more research, less purchase on mobile for high-value items). Don't assume all mobile visitors should convert at desktop rates — segment by intent. Speed improvements have diminishing returns after reaching "good" thresholds — going from 5s to 2.5s load time matters more than going from 2.5s to 1.8s. Test on real devices, not just browser emulators.

### ⚠️ Human Checkpoint
> Test all mobile changes on actual devices (iOS and Android, multiple screen sizes). Browser dev tools mobile emulation misses real-world issues like touch behavior, keyboard interactions, and network conditions. Get QA to test on the 5 most common devices in your analytics.

> **Benchmark Context**: Mobile commerce accounts for 60%+ of e-commerce traffic but only 40-45% of revenue — the conversion gap is real and fixable (Unbounce 2024 Conversion Benchmark Report). 53% of mobile users abandon sites that take longer than 3 seconds to load. Mobile cart abandonment rate averages 85% vs (Baymard Institute 2024 Cart Abandonment Statistics). 70% on desktop. Every 0.1s improvement in mobile page speed increases conversion by 8% (Unbounce 2024 Conversion Benchmark Report). Mobile-optimized checkout with express payment options increases conversion by 20-35% (Baymard Institute 2024 Cart Abandonment Statistics). (Baymard Institute 2024 Cart Abandonment Statistics).
## Output Contract

### Deliverable: Markdown Mobile Optimization Plan

```markdown
# Mobile Conversion Optimization: [Site/App]

## Mobile Gap Analysis
| Metric | Desktop | Mobile | Gap | Priority |
|---|---|---|---|---|

## UX Audit Findings
| Issue | Location | Severity | Fix | Effort |
|---|---|---|---|---|

## Speed Optimization
| Factor | Current | Target | Fix | Impact |
|---|---|---|---|---|

## Mobile-Specific Fixes
| Page | Change | Rationale | Expected Lift |
|---|---|---|---|

## Checkout/Form Optimization
| Current | Proposed | Rationale |
|---|---|---|

## A/B Test Plan
| Test | Hypothesis | Metric | Duration |
|---|---|---|---|

## Implementation Roadmap
| Phase | Changes | Timeline | Expected Impact |
|---|---|---|---|
```

## Platform Implementation Steps

### Analytics Setup
1. GA4 → create mobile segment (device category = mobile)
2. Compare mobile vs. desktop for all key metrics
3. Set up device-specific conversion funnels
4. Track mobile-specific events (tap, swipe, scroll depth)
5. Monitor Core Web Vitals by device in Search Console

### Speed Optimization
1. Run Google PageSpeed Insights on top 5 mobile pages
2. Implement critical CSS inlining and defer non-critical CSS
3. Convert images to WebP/AVIF with responsive srcset
4. Enable lazy loading for below-fold images and videos
5. Audit and remove unused JavaScript (Coverage tab in DevTools)

### Design Implementation
1. Audit tap target sizes (48px minimum, Chrome DevTools → Rendering → tap highlight)
2. Implement sticky CTA bars on conversion pages
3. Convert multi-column layouts to single-column on mobile
4. Add appropriate input types to all form fields
5. Test on top 5 devices from your analytics device report

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Mobile redesign tanks conversion | Changed too much at once, broke user expectations | Roll back; implement changes incrementally with A/B tests |
| Speed improvements don't help conversion | Speed was already acceptable; other UX issues dominate | Focus on UX fixes (forms, CTAs, navigation) instead of speed |
| Mobile-specific features break on some devices | Tested on too few devices or only emulators | Expand device testing matrix; use BrowserStack or real device lab |
| Express checkout has low adoption | Users don't have wallets set up, or trust the implementation | Add visual trust cues; ensure badges (Apple Pay, Google Pay) are prominent |

## How to Get Your Data

- **Mobile analytics**: GA4 → Reports → Tech → Overview → filter by device category
- **Page speed**: Google PageSpeed Insights → enter URL → select Mobile tab
- **Mobile heatmaps**: Hotjar or Clarity → filter by device type → mobile
- **No data**: Share your website URL — Claude reviews mobile experience and provides recommendations based on common patterns

## Example

**Input**: "Mobile conversion optimization for our e-commerce site. Desktop conversion: 3.2%, mobile conversion: 1.1% (65% gap). Mobile traffic is 68% of total. Mobile bounce rate: 62% (desktop: 38%). Lighthouse mobile score: 45. Checkout is 4 steps on mobile. No express checkout options."

**Output**: Critical gap: mobile converts at 34% of desktop rate with 68% of traffic — fixing this is highest-ROI project available. Priority fixes: (1) P0 — Speed (Lighthouse 45 is poor): compress images (saves ~40% page weight), defer non-critical JS, implement lazy loading. Target: Lighthouse 75+ in 2 weeks. Expected: bounce rate drop from 62% to 45-50%. (2) P0 — Add Apple Pay + Google Pay to checkout. Single-tap checkout eliminates 3 of 4 checkout steps for 30-40% of mobile users. Expected: 20-30% conversion lift on mobile checkout. (3) P1 — Consolidate 4-step checkout to 2 steps (shipping + payment on one page, confirmation on second). Add progress indicator. Expected: 15-20% reduction in checkout abandonment. (4) P1 — Sticky "Add to Cart" button on product pages (currently scrolls off screen). Expected: 10-15% more add-to-cart on mobile. (5) P2 — Implement bottom sheet for product variants instead of dropdown selectors. Combined expected impact: mobile conversion from 1.1% to 2.0-2.5% within 8 weeks, representing significant revenue increase given 68% mobile traffic share.

## Related Skills

- **checkout-funnel-optimizer** (./checkout-funnel-optimizer.md) — Optimize mobile checkout specifically; use to address friction points in mobile payment flows.
- **ab-test-designer** (./ab-test-designer.md) — Design A/B tests for mobile changes (button placement, form fields, page speed improvements); validate mobile optimizations with statistical testing.
- **heatmap-analysis-toolkit** (./heatmap-analysis-toolkit.md) — Analyze mobile user behavior with heatmaps; use to identify specific mobile UX friction points.
- **form-optimization-toolkit** (./form-optimization-toolkit.md) — Optimize mobile forms specifically; reduce fields and improve mobile-specific interactions (input types, keyboard handling).
