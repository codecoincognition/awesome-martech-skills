---
name: ecommerce-seo-optimizer
description: >
  Optimize e-commerce SEO — product pages, category pages, faceted navigation, and product schema.
  Use this skill when the user says "e-commerce SEO optimization", "product page SEO",
  "category page optimization", "Shopify SEO", "WooCommerce SEO", "product schema markup",
  "e-commerce keyword strategy", "faceted navigation SEO", "product description SEO",
  "shopping feed optimization", "e-commerce site architecture", or "product listing SEO".
  Also trigger for product review SEO, seasonal e-commerce SEO, or marketplace SEO optimization.
---

# E-commerce SEO Optimizer

Optimizes e-commerce SEO across product pages, category pages, site architecture, faceted navigation, product schema, and shopping feeds for organic traffic and conversion.

## Granularity Check

> **Time**: ~5 min data prep → ~10 min Claude session → ~30-60 min implementation in Google Search Console / CMS. If implementing, add 4-10 hours for site-wide changes. Input is product data and site structure. Output is Markdown optimization plan with template recommendations.

## User Intent Mapping

- "Optimize our product pages for SEO" (product pages)
- "Category page SEO strategy" (category)
- "Faceted navigation is causing duplicate content" (technical)
- "Product schema markup for e-commerce" (structured data)
- "E-commerce site architecture for SEO" (architecture)
- "Shopify SEO checklist" (platform-specific)
- "Product descriptions for SEO" (content)
- "Shopping feed optimization" (Google Shopping)
- "Seasonal SEO strategy for e-commerce" (seasonal)
- "Thin content on product pages" (content quality)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Platform | Text | Shopify, WooCommerce, Magento, BigCommerce, custom |
| Product Count | Number | Total SKUs and categories |
| Top Categories | Text list | Highest-revenue or highest-traffic categories |

### If You Don't Have This Data

- **No SEO tool?** Use Google Search Console for current organic performance. Manually search your top product categories to see competitors.
- **No product data export?** Describe your product types, categories, and URL structure. Claude optimizes the template and strategy.
- **No competitor benchmarks?** Claude uses e-commerce SEO best practices. Browse top-ranking competitor product and category pages for qualitative analysis.
- **No faceted navigation issues yet?** If you have filters (size, color, price, brand), you likely have or will have duplicate content issues. Proactive optimization prevents problems.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Product Feed | CSV | Product titles, descriptions, categories, prices |
| GSC Data | CSV | Top queries driving traffic to product/category pages |
| Site Architecture | Text | Category hierarchy and URL structure |
| Competitor Sites | Text list | Top 3 e-commerce competitors |
| Conversion Data | Text | Which products/categories convert best from organic |

## Process

### Step 1: Site Architecture Optimization
- Category hierarchy: Homepage → Category → Subcategory → Product (max 3 clicks)
- URL structure: /category/subcategory/product-name (descriptive, keyword-rich)
- Breadcrumb navigation with schema markup
- Internal linking strategy (related products, cross-sells, category links)
- Pagination handling (rel=canonical to view-all or component URLs)

### Step 2: Category Page Optimization
- Unique, keyword-rich category descriptions (150-300 words)
- H1 optimization with primary category keyword
- Product grid with SEO-friendly product names
- Filter/sort options that don't create duplicate URLs
- Category-specific FAQ sections for long-tail keywords

### Step 3: Product Page Optimization
- Unique product descriptions (avoid manufacturer copy)
- Product title formula: [Brand] + [Product Type] + [Key Feature] + [Size/Color]
- Image optimization: descriptive alt text, WebP format, lazy loading
- User-generated content integration (reviews, Q&A, photos)
- Related products and cross-sell sections for internal linking

### Step 4: Faceted Navigation SEO
- Identify which filter combinations should be indexable (high-volume combinations)
- Noindex/canonical strategy for low-value filter pages
- URL parameter handling in GSC
- Ajax-based filtering vs. URL-based filtering decision
- Crawl budget management for large catalogs

### Step 5: Product Schema Implementation
- Product schema: name, description, price, availability, brand, SKU
- AggregateRating schema from reviews
- Offer schema with price and availability
- BreadcrumbList schema for navigation
- Organization schema on homepage
- FAQ schema on category pages

### Step 6: Shopping Feed Optimization
- Google Merchant Center feed optimization
- Product title optimization for Shopping results
- GTIN/MPN requirements
- Product category mapping
- Custom labels for campaign segmentation

### Confidence & Sample Size
> **Confidence Note**: E-commerce SEO changes should be tested on a sample of pages before site-wide rollout. Product page template changes affect all products — verify on 10-20 pages first. Faceted navigation changes can accidentally deindex valuable pages — test thoroughly. Seasonal SEO (holiday, back-to-school) should be prepared 3-4 months in advance.

### ⚠️ Human Checkpoint
> Review product data accuracy before implementing schema (price, availability, ratings). Verify faceted navigation changes don't break user experience. Ensure product descriptions are accurate and compliant with regulations.

> **Benchmark Context**: See Semrush 2024 State of Search, and Ahrefs 2024 Search Traffic Study for current industry benchmarks relevant to this analysis.
## Output Contract

### Deliverable: Markdown E-commerce SEO Plan

```markdown
# E-commerce SEO Optimization: [Store]

## Site Architecture
- Current structure: [description]
- Recommended changes: [list]
- URL template: [pattern]

## Category Page Template
| Element | Current | Optimized | Impact |
|---|---|---|---|

## Product Page Template
| Element | Current | Optimized | Impact |
|---|---|---|---|

## Faceted Navigation Plan
| Filter | Indexable? | URL Strategy | Canonical |
|---|---|---|---|

## Schema Implementation
| Page Type | Schema Types | JSON-LD Template |
|---|---|---|

## Shopping Feed Optimization
| Field | Current | Optimized |
|---|---|---|

## Priority Action Plan
| Action | Pages Affected | Effort | Impact |
|---|---|---|---|
```

## Platform Implementation Steps

### Shopify
1. Edit theme.liquid for meta tags and schema markup
2. Use Shopify SEO apps (SEO Manager, JSON-LD for SEO) for structured data
3. Configure URL handles for products and collections
4. Set up redirects via Settings → Navigation → URL Redirects
5. Optimize collection page templates with unique descriptions

### WooCommerce
1. Install Yoast SEO or Rank Math for product SEO fields
2. Configure permalink structure: /%category%/%postname%/
3. Use WooCommerce-specific schema plugins for Product markup
4. Set up faceted navigation handling via robots.txt or plugin
5. Optimize product archive pages with category descriptions

### Google Merchant Center
1. Set up product feed (manual CSV or plugin-generated)
2. Map product categories to Google's taxonomy
3. Include GTINs/MPNs for all products
4. Optimize product titles with keywords
5. Monitor feed diagnostics for errors

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Duplicate content from filters | Faceted navigation creating indexable URL variants | Implement canonical tags or noindex on filter combinations |
| Product pages not ranking | Manufacturer-copied descriptions (duplicate across web) | Rewrite top 50 product descriptions with unique content |
| Schema errors in GSC | Invalid price format or missing required fields | Validate with Rich Results Test; fix template-level issues |
| Category pages thin | No unique content beyond product grid | Add 150-300 word category descriptions and FAQ sections |

## How to Get Your Data

- **Product data**: Export from your e-commerce platform (Products → Export)
- **GSC data**: Performance → Pages → filter product and category URLs
- **Crawl data**: Screaming Frog → crawl your site → filter by page type
- **No data**: Describe your store, platform, and categories — Claude optimizes from best practices

## Example

**Input**: "E-commerce SEO for a Shopify fashion store. 2,000 products, 25 collections. Faceted filters: size, color, price range, brand. Product descriptions are mostly manufacturer copy. No schema markup."

**Output**: Architecture: current 2-level (collection → product) is good; add subcollections for "Women's Tops → T-Shirts, Blouses, Tank Tops" to target specific keywords. Category pages: add unique 200-word descriptions to all 25 collections — prioritize top 10 by traffic. Product pages: rewrite descriptions for top 100 products (highest traffic + highest revenue); use formula: opening benefit statement + 3 feature bullets + sizing/material details. Faceted navigation: make size and brand filter URLs indexable (/collections/womens-tops/brand-nike, /collections/jeans/size-32), noindex color and price filters (low search volume). Schema: add Product schema to all product pages via JSON-LD for SEO app (covers price, availability, reviews), BreadcrumbList to all pages. Quick wins: (1) install JSON-LD schema app (30 min, affects all 2,000 products), (2) write top 10 collection descriptions (2 hours), (3) add alt text to product images using formula "Brand + Product + Color" (batch via CSV import).

## Related Skills

- **[On Page SEO Auditor](./on-page-seo-auditor.md)** — Use to audit and optimize individual product and category page elements before implementing site-wide changes.
- **[Technical SEO Auditor](./technical-seo-auditor.md)** — Use to ensure e-commerce site architecture, faceted navigation, and structured data are technically sound.
- **[Page Speed Optimizer](./page-speed-optimizer.md)** — Use to optimize product page load speeds and Core Web Vitals, critical for e-commerce conversion rates.
- **[Content Repurposer](../content/content-repurposer.md)** — Use to turn product descriptions and reviews into multi-channel marketing content.
