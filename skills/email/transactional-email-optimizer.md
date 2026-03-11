---
name: transactional-email-optimizer
description: >
  Optimize transactional emails — order confirmations, receipts, shipping updates, and account notifications.
  Use this skill when the user says "transactional email optimization", "order confirmation email",
  "shipping notification email", "receipt email design", "password reset email", "account notification
  email", "transactional email best practices", "transactional vs marketing email", "order status
  email", "transactional email cross-sell", or "transactional email revenue". Also trigger for
  transactional email compliance, delivery notification optimization, or invoice email design.
---

# Transactional Email Optimizer

Optimizes transactional emails (order confirmations, shipping updates, receipts, account notifications) for clarity, brand consistency, cross-sell opportunities, and customer experience.

## Granularity Check

> **Time**: ~5 min data prep → ~10 min Claude session → ~30-45 min setup in Mailchimp / Klaviyo / HubSpot. If implementing, add 2-4 hours for template redesign. Input is current transactional emails and business context. Output is Markdown optimization plan with template recommendations.

## User Intent Mapping

- "Optimize our order confirmation emails" (order confirmation)
- "Our transactional emails look generic" (branding)
- "Add cross-sell to transactional emails" (revenue)
- "Shipping notification email best practices" (shipping)
- "Password reset email isn't converting" (account)
- "Transactional email compliance" (legal)
- "Receipt email design" (receipts)
- "Our transactional emails have low engagement" (engagement)
- "Transactional email vs. marketing email — what's the difference?" (strategy)
- "Invoice email template" (invoicing)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Email Types | Text | Which transactional emails you send (order confirmation, shipping, etc.) |
| Business Type | Text | E-commerce, SaaS, marketplace, services |
| Current Issues | Text | What's wrong with current transactional emails |

### If You Don't Have This Data

- **No transactional email analytics?** Most transactional ESPs (SendGrid, Postmark, Mailgun) provide open/click data. Claude recommends tracking setup.
- **No current templates?** Claude designs transactional email templates from scratch based on your business type.
- **Using default platform emails?** That's the most common situation. Claude provides optimized versions that maintain your brand while improving UX.
- **Not sure which emails are transactional?** Claude classifies your emails and advises which are transactional (exempt from unsubscribe requirements) vs. marketing.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Current Templates | Image/HTML | Screenshots or code of existing transactional emails |
| Open/Click Rates | Text | Engagement metrics for transactional emails |
| Brand Guidelines | Text | Colors, fonts, logo for consistent branding |
| Platform | Text | E-commerce platform and transactional ESP |
| Revenue Data | Text | Cross-sell revenue from transactional emails |

## Process

### Step 1: Transactional Email Inventory
| Email Type | Trigger | Primary Purpose | Opportunity |
|---|---|---|---|
| Order Confirmation | Purchase | Confirm order details | Cross-sell, referral |
| Shipping Confirmation | Shipment created | Provide tracking | Product education |
| Delivery Confirmation | Package delivered | Confirm receipt | Review request |
| Receipt/Invoice | Payment processed | Record of payment | Upsell, loyalty |
| Account Welcome | Registration | Confirm account | Onboarding |
| Password Reset | User request | Security action | Re-engagement |
| Subscription Renewal | Billing cycle | Confirm charge | Upgrade prompt |

### Step 2: Content Optimization
Per transactional email:
- **Primary content**: essential transaction information (clear, prominent)
- **Secondary content**: brand-building elements (logo, consistent design)
- **Tertiary content**: revenue opportunities (cross-sell, referral, review request)
- Rule: transactional content must be >80% of the email to maintain transactional status

### Step 3: Design Optimization
- Consistent branding with marketing emails (same header, colors, footer)
- Mobile-responsive layout (60%+ of transactional emails opened on mobile)
- Clear information hierarchy (order number, items, total, next steps)
- Scannable format (avoid walls of text)
- Prominent action buttons (Track Order, View Receipt, Contact Support)

### Step 4: Revenue Opportunities
- Product recommendations based on purchase (related items, frequently bought together)
- Referral prompt ("Share with a friend, get $10")
- Review request timing (post-delivery, not post-order)
- Loyalty program enrollment or points reminder
- Subscription/upgrade prompt for one-time buyers
- Note: keep promotional content under 20% to maintain transactional classification

### Step 5: Compliance Review
- CAN-SPAM: transactional emails don't require unsubscribe but must include sender address
- Transactional classification: primary purpose must be transactional (not promotional)
- GDPR: processing data for transactional emails falls under "legitimate interest"
- Include company name and contact information
- Don't disguise marketing emails as transactional

### Confidence & Sample Size
> **Confidence Note**: Transactional emails have the highest open rates (80-85%) and engagement of any email type — optimization here has outsized impact. Cross-sell in transactional emails converts at 2-4x the rate of marketing emails. However, over-promoting in transactional emails can erode trust — keep the balance heavily in favor of transactional content.

### ⚠️ Human Checkpoint
> Verify all order and transaction data accuracy in email templates. Review cross-sell recommendations for appropriateness. Ensure transactional emails maintain their primary transactional purpose (legal classification). Test delivery speed — transactional emails should arrive within seconds.

> **Benchmark Context**: See Mailchimp 2024 Email Marketing Benchmarks for current industry benchmarks relevant to this analysis.
## Output Contract

### Deliverable: Markdown Transactional Email Plan

```markdown
# Transactional Email Optimization: [Brand]

## Email Inventory
| Email | Current State | Issues | Priority |
|---|---|---|---|

## Template Specifications

### [Email Type]
- Trigger: [event]
- Send timing: [immediate/delayed]
- Primary content: [list]
- Cross-sell opportunity: [recommendation]
- Design: [specs]
- CTA: [button text and action]

## Revenue Opportunities
| Email | Opportunity | Expected Revenue | Effort |
|---|---|---|---|

## Compliance Checklist
- [ ] [Requirement]

## Implementation Plan
| Email | Template Changes | Cross-Sell Addition | Timeline |
|---|---|---|---|
```

## Platform Implementation Steps

### Shopify
1. Settings → Notifications → customize each transactional email template
2. Use Shopify's Liquid templating for dynamic product recommendations
3. Add branded header/footer consistent with marketing emails
4. Install apps (OrderlyEmails, Conversio) for enhanced transactional emails

### SendGrid / Postmark / Mailgun
1. Create dynamic templates with handlebars for order data
2. Set up event tracking for opens and clicks on transactional emails
3. Configure transactional email analytics dashboard
4. Set up webhook notifications for delivery/bounce events

### Stripe (Receipts)
1. Customize receipt template in Stripe Dashboard → Settings → Emails
2. Add brand colors, logo, and custom footer
3. Configure which receipt emails are sent automatically
4. Use Stripe's receipt webhook for custom receipt emails

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Email classified as marketing | Too much promotional content (>20%) | Reduce cross-sell content; keep transactional content dominant |
| Delayed delivery | Transactional email queued with marketing | Use separate sending infrastructure for transactional |
| Cross-sell feels spammy | Irrelevant recommendations or too aggressive | Use purchase-based recommendations; limit to 1-2 products |
| Missing transaction details | Template error or data mapping issue | QA test all transactional email triggers with test orders |

## How to Get Your Data

- **Current emails**: Place a test order → screenshot all transactional emails received
- **Performance data**: Transactional ESP → analytics → open/click rates per template
- **Revenue data**: E-commerce platform → track clicks from transactional emails to purchases
- **No data**: Describe your business type and transaction flow — Claude designs optimal templates

## Example

**Input**: "Optimize transactional emails for a DTC supplement brand on Shopify. Currently using default Shopify emails — no branding, no cross-sell. 15K orders/month. Using SendGrid for delivery."

**Output**: 5 transactional emails optimized: (1) Order Confirmation — add branded header, order summary with product images, estimated delivery date, "How to get the most from your supplements" CTA linking to blog, cross-sell: related product recommendation (1 product max). (2) Shipping Confirmation — tracking link prominent, expected delivery date, "What to expect" section for first-time buyers, cross-sell: subscribe & save prompt for reorder. (3) Delivery Confirmation — "Your order has arrived" with review request CTA, referral offer ("Give $15, Get $15"), usage tips for purchased products. (4) Account Welcome — brand story, "Complete your profile" for personalization, first-purchase incentive if not yet ordered. (5) Subscription Renewal — clear billing summary, easy manage/cancel link (reduces support tickets), loyalty points earned. Revenue opportunity: at 15K orders/month with 85% open rate, even 1% cross-sell conversion = 127 additional orders/month. Implementation: Phase 1 (week 1) — branded templates for all 5 emails; Phase 2 (week 2) — add cross-sell to order and delivery confirmations; Phase 3 (week 3) — review request and referral in delivery confirmation.

## Related Skills

- **[Email Template Designer](./email-template-designer.md)** — Use to design transactional email templates with your brand colors and layout.
- **[Email Copywriting Framework](./email-copywriting-framework.md)** — Use to optimize transactional email copy and CTAs for conversions.
- **[Email Deliverability Auditor](./email-deliverability-auditor.md)** — Use to ensure transactional emails have proper authentication and aren't flagged as spam.
- **[Customer Onboarding Optimizer](../crm/customer-onboarding-optimizer.md)** — Use to optimize the transactional emails sent during the customer onboarding journey.
