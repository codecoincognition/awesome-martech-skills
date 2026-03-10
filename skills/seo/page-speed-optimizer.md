---
name: page-speed-optimizer
description: >
  Optimize page speed and Core Web Vitals for SEO and user experience.
  Use this skill when the user says "page speed optimization", "Core Web Vitals fix",
  "LCP optimization", "CLS fix", "INP optimization", "site speed audit", "PageSpeed
  Insights analysis", "web performance optimization", "render blocking resources",
  "image optimization for speed", "lazy loading implementation", or "page load time
  reduction". Also trigger for Lighthouse score improvement, TTFB optimization, or
  JavaScript performance tuning.
---

# Page Speed Optimizer

Analyzes and optimizes page speed and Core Web Vitals (LCP, INP, CLS) with prioritized fixes for SEO ranking improvements and better user experience.

## Granularity Check

> **Session time**: ~5 min data prep + ~10 min Claude session. If implementing fixes, add 2-10 hours depending on issues. Input is PageSpeed Insights or Lighthouse data. Output is Markdown optimization plan with prioritized fixes.

## User Intent Mapping

- "Our site is slow — how to fix it" (general speed)
- "Core Web Vitals failing in GSC" (CWV)
- "LCP is too high — how to reduce it" (specific metric)
- "CLS issues on mobile" (layout shift)
- "INP is failing — interaction is slow" (responsiveness)
- "Improve our Lighthouse score" (Lighthouse)
- "Image optimization for page speed" (images)
- "Render-blocking CSS and JavaScript" (resources)
- "Page speed for SEO rankings" (SEO focus)
- "TTFB is too slow" (server)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Site URL | Text | Pages to optimize |
| PageSpeed Data | Text/Screenshot | PageSpeed Insights or Lighthouse results |
| Priority | Text | SEO rankings, user experience, conversion rate |

### If You Don't Have This Data

- **No performance data?** Run PageSpeed Insights (free) on your top 5 pages and paste the results. Claude prioritizes fixes by impact.
- **No developer access?** Claude identifies which fixes need a developer and which can be done via CMS settings or plugins.
- **No CDN?** Claude includes CDN setup as a recommendation with free options (Cloudflare free tier).
- **No image optimization?** Claude provides specific image compression recommendations and format conversion guidance.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| CrUX Data | Text | Chrome User Experience Report (field data) |
| Hosting Info | Text | Server, CDN, hosting provider |
| CMS/Framework | Text | WordPress, React, Next.js, Shopify, etc. |
| Page Types | Text | Which page types are slowest |
| Traffic Volume | Text | Monthly visitors (affects optimization priority) |

## Process

### Step 1: Core Web Vitals Assessment
| Metric | Good | Needs Improvement | Poor |
|---|---|---|---|
| LCP | ≤ 2.5s | 2.5-4.0s | > 4.0s |
| INP | ≤ 200ms | 200-500ms | > 500ms |
| CLS | ≤ 0.1 | 0.1-0.25 | > 0.25 |

### Step 2: LCP Optimization
Common LCP issues and fixes:
- Slow server response (TTFB > 800ms) → CDN, server upgrade, caching
- Render-blocking resources → defer non-critical CSS/JS, inline critical CSS
- Large hero images → WebP/AVIF format, responsive sizing, preload
- Client-side rendering → server-side rendering or static generation
- Unoptimized web fonts → font-display: swap, preload fonts

### Step 3: INP Optimization
- Long JavaScript tasks → break into smaller chunks, use web workers
- Heavy event handlers → debounce, requestAnimationFrame
- Third-party scripts → defer, lazy load, or remove
- DOM size → reduce node count, virtualize long lists
- Main thread blocking → optimize JavaScript execution

### Step 4: CLS Optimization
- Images without dimensions → add width/height attributes
- Ads/embeds without reserved space → set explicit dimensions
- Dynamic content insertion → reserve space before loading
- Web fonts causing FOIT/FOUT → font-display: swap + preload
- Late-loading CSS → inline critical CSS above the fold

### Step 5: Resource Optimization
- Image optimization: WebP/AVIF, responsive srcset, lazy loading
- JavaScript: minify, tree-shake, code-split, defer
- CSS: minify, remove unused, inline critical CSS
- Fonts: subset, preload, self-host
- Third-party scripts: audit, defer, or remove unnecessary ones

### Step 6: Infrastructure Optimization
- CDN implementation for global delivery
- Browser caching headers (Cache-Control, Expires)
- Compression (Brotli > Gzip)
- HTTP/2 or HTTP/3 enabled
- DNS prefetch and preconnect for third-party origins

### Confidence & Sample Size
> **Confidence Note**: Lab data (Lighthouse, PageSpeed Insights) shows potential issues; field data (CrUX) shows real user experience. Google uses field data (CrUX) for ranking signals, not lab data. Performance varies by device and network — optimize for the 75th percentile of users. CWV improvements take 28 days to reflect in CrUX data after deployment.

### ⚠️ Human Checkpoint
> Have a developer review all optimization recommendations before implementation. Test changes in staging environment first. Performance optimizations can occasionally break functionality — verify all features work after changes.

> **Benchmark Context**: Pages passing all Core Web Vitals are 24% less likely to be abandoned. Improving LCP by 1 second can increase conversions by 27%. Sites in the top CWV bracket rank higher than those failing. 53% of mobile site visitors leave if a page takes longer than 3 seconds to load. Brotli compression reduces file sizes 15-20% more than Gzip.

## Output Contract

### Deliverable: Markdown Speed Optimization Plan

```markdown
# Page Speed Optimization: [Site]

## Current Performance
| Page | LCP | INP | CLS | Performance Score |
|---|---|---|---|---|

## Critical Issues
| Issue | Metric Affected | Impact | Fix | Effort |
|---|---|---|---|---|

## Optimization Plan
### Phase 1: Quick Wins (< 1 day)
1. [Fix] — Expected improvement: [metric]

### Phase 2: Medium Effort (1-3 days)
1. [Fix] — Expected improvement: [metric]

### Phase 3: Infrastructure (1-2 weeks)
1. [Fix] — Expected improvement: [metric]

## Image Optimization
| Image | Current Size | Optimized Size | Format | Savings |
|---|---|---|---|---|

## Third-Party Script Audit
| Script | Purpose | Load Impact | Recommendation |
|---|---|---|---|

## Expected Results
- LCP: [current] → [target]
- INP: [current] → [target]
- CLS: [current] → [target]
```

## Platform Implementation Steps

### WordPress
1. Install caching plugin (WP Rocket, LiteSpeed Cache, or W3 Total Cache)
2. Install image optimization plugin (ShortPixel, Imagify, or Smush)
3. Use Autoptimize or Perfmatters for CSS/JS optimization
4. Enable lazy loading for images (native or plugin-based)
5. Use a CDN plugin (Cloudflare, BunnyCDN, or hosting CDN)

### Shopify
1. Compress and convert images to WebP before upload
2. Minimize app installs (each adds JavaScript)
3. Use system fonts or preload custom fonts
4. Defer non-critical JavaScript using theme.liquid
5. Enable Shopify CDN (automatic) and set cache headers

### Next.js / React
1. Use next/image for automatic image optimization
2. Implement code splitting with dynamic imports
3. Enable server-side rendering or static generation for key pages
4. Use React.lazy and Suspense for component-level code splitting
5. Configure next.config.js for compression and caching

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Optimization broke layout | CSS changes caused styling issues | Revert; test critical CSS inlining more carefully |
| Lazy loading hurt LCP | Hero image was lazy loaded | Exclude above-fold images from lazy loading; preload LCP image |
| Third-party removal broke features | Essential script was deferred or removed | Re-add with async attribute; find lighter alternative |
| No CrUX improvement after 30 days | Changes didn't reach enough real users or lab-only issues | Verify deployment; check CrUX data volume; focus on field data issues |

## How to Get Your Data

- **PageSpeed Insights**: pagespeed.web.dev → enter URL → review results
- **Lighthouse**: Chrome DevTools → Lighthouse tab → run audit
- **CrUX**: GSC → Core Web Vitals report; or CrUX Dashboard on BigQuery
- **WebPageTest**: webpagetest.org → detailed waterfall analysis
- **No tools**: Paste your site URL — Claude provides recommendations based on common issues for your CMS

## Example

**Input**: "Page speed optimization for a WordPress blog. LCP: 4.8s, INP: 310ms, CLS: 0.18. Lighthouse score: 42. Using 12 plugins, no CDN, images are PNG/JPEG, no caching plugin. 500K monthly visitors."

**Output**: Critical fixes: (1) Install WP Rocket caching plugin — expected LCP improvement 1.5-2s alone. (2) Convert images to WebP via ShortPixel — 25 hero images average 2.4MB each (target <200KB). (3) Enable Cloudflare free CDN — TTFB improvement ~40%. (4) Defer 8 of 12 plugin scripts (social share, analytics, chat widget) — INP improvement ~100ms. CLS fixes: add width/height to all images (theme.php edit), reserve ad space dimensions (CSS). Plugin audit: remove 3 unused plugins, replace 2 heavy plugins with lighter alternatives. Phase 1 (day 1): install WP Rocket + Cloudflare → LCP 4.8→3.0s. Phase 2 (day 2-3): image optimization → LCP 3.0→2.2s. Phase 3 (week 2): JS defer + plugin cleanup → INP 310→180ms. Expected results: Lighthouse 42→85+, all CWV passing within 2 weeks.
