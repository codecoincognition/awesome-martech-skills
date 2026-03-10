---
name: email-template-designer
description: >
  Design email templates with layout, visual hierarchy, mobile responsiveness, and brand consistency.
  Use this skill when the user says "email template design", "email layout best practices",
  "responsive email template", "email design system", "newsletter template design", "email
  visual hierarchy", "mobile email optimization", "email HTML template", "branded email
  template", "dark mode email design", or "email design guidelines". Also trigger for email
  module library, email accessibility, or email rendering troubleshooting.
---

# Email Template Designer

Designs email templates with optimal layout, visual hierarchy, mobile responsiveness, accessibility, and brand consistency — including modular component systems for scalable email production.

## Granularity Check

> **Time**: ~5 min data prep → ~10 min Claude session → ~30-45 min setup in Mailchimp / Klaviyo / HubSpot. If implementing, add 2-8 hours for HTML/CSS coding and testing. Input is brand guidelines and email types needed. Output is Markdown design specs with component recommendations.

## User Intent Mapping

- "Design an email template for our brand" (template design)
- "Our emails look bad on mobile" (mobile optimization)
- "Email design best practices" (best practices)
- "Create a modular email design system" (system)
- "Newsletter template layout" (newsletter)
- "Email accessibility for screen readers" (accessibility)
- "Dark mode email support" (dark mode)
- "Email template rendering issues" (troubleshooting)
- "Branded email template" (branding)
- "Email design that converts" (conversion optimization)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Brand Colors | Text | Primary, secondary, accent colors (hex codes) |
| Email Types | Text | Newsletter, promotional, transactional, announcement, etc. |
| Audience | Text | Who receives these emails and on what devices |

### If You Don't Have This Data

- **No brand guidelines?** Share your website URL or logo. Claude extracts colors and style direction from your existing brand presence.
- **No email design experience?** Claude provides pre-built layout recommendations based on your email type and industry.
- **No HTML/CSS skills?** Claude's specs can be implemented in drag-and-drop email builders (Mailchimp, Stripo, BEE Free).
- **No rendering testing tool?** Use free Litmus Previews or Email on Acid free trial to test across clients.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Logo | File/URL | Brand logo for email header |
| Font Preferences | Text | Brand fonts (note: web-safe fallbacks needed) |
| Existing Templates | Text/Image | Current email designs for audit |
| ESP | Text | Email platform (affects template capabilities) |
| Industry | Text | For industry-specific template norms |

## Process

### Step 1: Layout Architecture
| Layout | Best For | Mobile Behavior |
|---|---|---|
| Single column | Newsletters, announcements | Scales naturally |
| Two column | Product showcases, comparisons | Stacks on mobile |
| Hybrid | Feature-rich promotions | Columns stack, hero stays |
| Modular | All (scalable system) | Modules stack independently |

### Step 2: Visual Hierarchy
- **Hero section**: Primary message, CTA above the fold (first 300px)
- **Content blocks**: Supporting information in scannable sections
- **CTA placement**: Primary CTA visible without scrolling; repeat at bottom
- **White space**: Minimum 20px padding between sections
- **F-pattern reading**: Key content follows natural eye scanning path

### Step 3: Mobile Optimization
- Min font size: 14px body, 22px headlines (mobile)
- CTA button: minimum 44×44px touch target
- Single-column layout on screens <600px
- Images: responsive with max-width: 100%
- Stack multi-column layouts vertically on mobile
- Hide non-essential content on mobile with media queries

### Step 4: Typography & Color
- Web-safe font stacks with fallbacks (Arial, Helvetica, Georgia)
- Body text: 14-16px, line-height 1.5-1.6
- Headlines: 22-30px, bold weight
- Maximum 2 font families per email
- Color contrast ratio: minimum 4.5:1 for text
- Limit palette to 2-3 colors plus neutrals

### Step 5: Accessibility
- Alt text on all images (decorative images: alt="")
- Semantic HTML (headings, paragraphs, lists)
- Color is not the only indicator (add text labels)
- Table role="presentation" for layout tables
- Link text is descriptive (not "click here")
- Sufficient color contrast for text and buttons

### Step 6: Dark Mode Support
- Use transparent PNGs for logos when possible
- Set background colors on container elements (not just body)
- Test with both light and dark mode
- Use @media (prefers-color-scheme: dark) for targeted styling
- Avoid pure white (#ffffff) backgrounds — use #fafafa or similar

### Confidence & Sample Size
> **Confidence Note**: Email rendering varies significantly across clients (Gmail, Outlook, Apple Mail, Yahoo). What works in one client may break in another. Always test in the top 5 clients your audience uses. Mobile opens account for 41-60% of all email opens depending on industry — mobile-first design is not optional.

### ⚠️ Human Checkpoint
> Test all templates across major email clients before deploying. Verify links work and tracking is configured. Review accessibility with a screen reader. Check dark mode rendering in Apple Mail, Gmail, and Outlook dark mode.

> **Benchmark Context**: Emails with a clear visual hierarchy have 47% higher click rates (Mailchimp 2024 Email Marketing Benchmarks). Mobile-optimized emails generate 15% higher click rates (Mailchimp 2024 Email Marketing Benchmarks). Single-column layouts have 30% higher engagement on mobile. CTA buttons outperform text links by 28%. Emails that take >3 seconds to load lose 53% of mobile readers. Dark mode is used by 80%+ of mobile email readers. (Mailchimp 2024 Email Marketing Benchmarks).
## Output Contract

### Deliverable: Markdown Template Specs

```markdown
# Email Template Design: [Brand]

## Design System
- Colors: [palette with hex codes]
- Fonts: [primary + fallback stack]
- Spacing: [padding and margin system]

## Template: [Type]
### Layout Specification
- Width: [px]
- Columns: [count and behavior]
- Mobile breakpoint: [px]

### Component Library
| Module | Purpose | Layout | Mobile Behavior |
|---|---|---|---|

### Header
- Logo: [placement, size]
- Navigation: [links, mobile behavior]

### Hero Section
- Image: [dimensions, aspect ratio]
- Headline: [font, size, color]
- CTA: [button specs]

### Content Blocks
- [Specs per block type]

### Footer
- [Required elements: unsubscribe, address, social links]

## Accessibility Checklist
- [ ] [Item]

## Dark Mode Specs
- [Color adjustments for dark mode]

## Testing Checklist
- [ ] [Client and test status]
```

## Platform Implementation Steps

### Drag-and-Drop Builders
1. Use Stripo, BEE Free, or your ESP's built-in builder
2. Create master template matching the design specs
3. Build reusable content modules for headers, CTAs, product blocks
4. Save as template for team reuse
5. Test responsive behavior in preview mode

### Custom HTML/CSS
1. Use a responsive email framework (Foundation for Emails, MJML)
2. Code layout with tables for Outlook compatibility
3. Add media queries for mobile responsive behavior
4. Inline CSS for maximum client compatibility
5. Test with Litmus or Email on Acid across 20+ clients

### ESP-Specific
1. Upload custom HTML template to your ESP
2. Define editable regions for content team
3. Set up template variants for different email types
4. Configure dynamic content blocks for personalization
5. Version control templates and document changes

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Broken in Outlook | CSS not supported in Outlook | Use table-based layout; inline all CSS; use VML for backgrounds |
| Images not loading | Image blocking or slow load | Add alt text; ensure email makes sense without images |
| Dark mode breaks design | Colors invert unexpectedly | Set explicit background colors; use meta color-scheme |
| Mobile layout broken | Media queries not supported or CSS issues | Use fluid design as base; progressive enhancement for supported clients |

## How to Get Your Data

- **Brand assets**: Share your website URL, logo file, and brand color hex codes
- **Email client data**: ESP analytics → device and client breakdown of your audience
- **Current templates**: Share existing email designs for audit and improvement
- **No assets**: Describe your brand aesthetic — Claude designs a template system from scratch

## Example

**Input**: "Design email templates for a fintech startup. Colors: #1A73E8 (blue), #34A853 (green), #202124 (dark). Need: weekly newsletter, product announcement, transactional. Audience: 60% mobile, mostly Gmail and Apple Mail."

**Output**: Design system: 600px max-width, single-column primary layout, 20px section padding, font stack: 'Inter', Helvetica, Arial, sans-serif. Newsletter template: Header (logo left, one nav link right), Hero (full-width image 600×250, H1 24px #202124, CTA button 44px height #1A73E8 with white text), 3 content modules (icon + headline + 2 lines + link), footer (social icons, unsubscribe, address). Product announcement: simplified — hero + one content block + CTA + footer. Transactional: minimal — logo + content + action button + support link + footer. Mobile specs: single column stacks, 16px body text, 44px min button height, images max-width 100%. Dark mode: swap #202124 backgrounds to #303134, keep #1A73E8 buttons, add color-scheme meta tag. Accessibility: all images have alt text, 5.2:1 contrast ratio on body text, CTA buttons have descriptive text. Testing priority: Gmail (web + mobile), Apple Mail (light + dark mode), Outlook 365.

## Related Skills

- **[Email Copywriting Framework](./email-copywriting-framework.md)** — Use to write copy that fits within your template design and visual hierarchy.
- **[Email List Segmentation](./email-list-segmentation.md)** — Use to create segment-specific templates (e.g., different designs for mobile vs. desktop users).
- **[Brand Asset Compliance Checker](../martech-ops/brand-asset-compliance-checker.md)** — Use to ensure email templates comply with brand guidelines and standards.
- **[Email Performance Analyzer](./email-performance-analyzer.md)** — Use to measure how different template designs impact engagement metrics.
