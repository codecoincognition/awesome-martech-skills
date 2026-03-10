---
name: ugc-curation-strategy
description: >
  Plan user-generated content collection, curation, and amplification across marketing channels.
  Use this skill when the user says "UGC strategy", "user-generated content plan", "customer
  content curation", "UGC collection strategy", "how to get more UGC", "user-generated content
  campaign", "customer review strategy", "UGC rights management", "community content amplification",
  "testimonial collection plan", or "customer story program". Also trigger for UGC moderation
  policy, brand ambassador content, or customer advocacy program.
---

# UGC Curation Strategy

Plans user-generated content programs — collection mechanisms, curation workflows, rights management, and amplification strategies across marketing channels.

## Granularity Check

> **Session time**: ~5 min context gathering + ~10 min Claude session. If implementing, add 1-2 weeks for program setup. Input is current UGC sources and marketing goals. Output is Markdown UGC strategy with collection and amplification plan.

## User Intent Mapping

- "How to get more customer content" (collection)
- "UGC strategy for social media" (social UGC)
- "Customer review collection plan" (reviews)
- "UGC rights management" (legal)
- "Community content program" (community)
- "User-generated content campaign" (campaign)
- "Customer testimonial strategy" (testimonials)
- "UGC moderation policy" (moderation)
- "Brand ambassador program" (ambassadors)
- "How to use customer content in ads" (amplification)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Business Type | Text | E-commerce, SaaS, services, etc. |
| Current UGC Sources | Text | Reviews, social mentions, testimonials |
| Marketing Goals | Text | Where you want to use UGC |

### If You Don't Have This Data

- **No existing UGC?** Claude designs a collection program from scratch with specific tactics to generate your first UGC.
- **No social mentions?** Claude recommends monitoring setup and incentive strategies to generate mentions.
- **No rights management?** Claude provides a rights request template and policy framework.
- **Worried about negative UGC?** Claude includes moderation guidelines and response frameworks.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Social Channels | Text | Active platforms and follower counts |
| Customer Base | Text | Number and demographics of customers |
| Budget | Text | Budget for incentives or UGC platforms |
| Competitor UGC | Text | How competitors use UGC |
| Legal Constraints | Text | Industry regulations around testimonials |

## Process

### Step 1: UGC Type Mapping
| UGC Type | Source | Value | Collection Method |
|---|---|---|---|
| Reviews | Purchase follow-up | High (conversion) | Email request, in-app prompt |
| Social posts | Organic mentions | High (reach) | Hashtag campaigns, monitoring |
| Photos/Videos | Customer usage | Very high (authenticity) | Contests, incentives, unboxing prompts |
| Testimonials | Happy customers | High (trust) | Interview, survey, NPS follow-up |
| Case studies | Success stories | Very high (sales) | Customer success team referrals |
| Forum/Q&A | Community | Medium (SEO, support) | Community engagement, branded forums |

### Step 2: Collection Strategy
- **Passive collection**: Social listening tools, review monitoring, hashtag tracking
- **Active solicitation**: Post-purchase emails, NPS follow-up, loyalty program rewards
- **Campaign-driven**: Hashtag campaigns, photo contests, challenges, seasonal prompts
- **Incentivized**: Discounts, loyalty points, feature on brand channels, product seeding
- **Relationship-based**: Ambassador programs, customer advisory boards, beta tester groups

### Step 3: Rights Management
- Create standard rights request template (DM, email, or in-app)
- Include terms in purchase/signup for product review usage
- Track permissions in a UGC database (creator, content, permission status, expiration)
- Separate permissions by usage type (social, ads, website, email, print)
- Comply with FTC guidelines for endorsement disclosure

### Step 4: Curation Workflow
1. Monitor and collect (daily)
2. Review for quality and brand alignment (daily)
3. Request rights if not pre-authorized (within 24 hours)
4. Tag and categorize (by product, theme, quality tier)
5. Add to UGC library for team access
6. Schedule for distribution across channels

### Step 5: Amplification Plan
| Channel | UGC Format | Placement | Frequency |
|---|---|---|---|
| Social media | Reshares, carousel | Feed, Stories | 3-5x/week |
| Website | Reviews, photos | Product pages, homepage | Always-on |
| Email | Testimonials, photos | Campaigns, flows | 1-2x/month |
| Ads | Photos, videos | Social ads, display | Rotate monthly |
| Sales | Case studies, quotes | Proposals, decks | Per opportunity |

### Step 6: Moderation Policy
- Clear community guidelines (what's acceptable, what's not)
- Response protocol for negative UGC (respond, don't delete unless abusive)
- Escalation path for sensitive content (legal, PR, customer success)
- Content quality tiers (tier 1: ads-worthy, tier 2: social, tier 3: internal use)

### Confidence & Sample Size

> **Confidence Note**: UGC programs take 2-3 months to generate consistent volume. Not all UGC is equal — 10% will be high-quality enough for ads. Incentivized UGC must be disclosed (FTC requirement). Authenticity is the entire value of UGC — over-polishing defeats the purpose. Track conversion lift from UGC placement to justify program investment.

### ⚠️ Human Checkpoint
> Have legal review rights management templates and terms of use. Verify FTC compliance for incentivized content and endorsements. Review moderation policy with customer support team.

> **Benchmark Context**: UGC-based ads get 4x higher click-through rates than brand-created ads. 92% of consumers trust UGC more than traditional advertising. Products with UGC on product pages see 29% higher conversion rates. UGC photos are 5x more likely to convert than professional photos. Brands using UGC see 50% reduction in cost-per-acquisition.

## Output Contract

### Deliverable: Markdown UGC Strategy

```markdown
# UGC Strategy: [Brand]

## UGC Inventory
| Type | Current Volume | Quality | Source |
|---|---|---|---|

## Collection Plan
| Method | UGC Type | Expected Volume | Timeline | Cost |
|---|---|---|---|---|

## Rights Management
- Template: [rights request]
- Tracking: [system]
- Terms: [policy summary]

## Curation Workflow
| Step | Owner | Tool | Frequency |
|---|---|---|---|

## Amplification Plan
| Channel | Format | Placement | Frequency | Expected Impact |
|---|---|---|---|---|

## Moderation Policy
- Guidelines: [summary]
- Response protocol: [process]
- Escalation: [path]

## Measurement
| Metric | Baseline | Target | Tracking |
|---|---|---|---|
```

## Platform Implementation Steps

### Social Listening
1. Set up brand mention monitoring (Sprout Social, Mention, Brandwatch)
2. Create branded hashtag and track submissions
3. Set up alerts for product mentions on Instagram, TikTok, Twitter
4. Monitor review platforms (G2, Trustpilot, Google Reviews)

### UGC Platforms
1. Evaluate UGC platforms (Bazaarvoice, Yotpo, Stackla, TINT)
2. Set up rights management workflow within platform
3. Integrate UGC feed with website and e-commerce platform
4. Configure automated collection triggers (post-purchase emails)

### Legal Setup
1. Create UGC terms of use (add to website terms)
2. Draft rights request templates (DM, email)
3. Set up FTC-compliant disclosure for incentivized content
4. Create content creator agreement for ambassador programs

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| No UGC submitted | No incentive or prompt; customers don't know you want it | Add prompts to post-purchase emails; create hashtag campaign; seed with influencer content |
| Low-quality UGC | No guidance on what to create | Share examples of ideal UGC; provide creative prompts; product seeding with instructions |
| Rights issues | Using content without permission | Implement rights request workflow; audit current UGC usage; add terms to signup |
| Negative UGC goes viral | No monitoring or response plan | Set up alerts; create response templates; respond publicly and resolve privately |

## How to Get Your Data

- **Social mentions**: Social listening tool → brand mentions with media
- **Reviews**: Review platform → export reviews with ratings and content
- **Customer photos**: Instagram/TikTok → search branded hashtag
- **No data**: Describe your business and customers — Claude designs a UGC program from scratch

## Example

**Input**: "UGC strategy for a DTC skincare brand. 50K customers, 25K Instagram followers. Getting ~20 mentions/week on Instagram (mostly Stories). No formal UGC program. Want to use customer content on product pages and in ads."

**Output**: Current UGC: 20 mentions/week = ~80/month, but most are Stories (expire in 24 hours) and low-resolution. Target: 200+ reusable UGC pieces/month. Collection plan: (1) Post-purchase email with photo prompt (Day 14 after delivery — enough time to see results) — "Share your glow-up with #[BrandName]Results for a chance to be featured + 15% off next order." Expected: 5-8% response rate = 200+ submissions/month. (2) Instagram story prompt with "Add Yours" sticker monthly — theme-based (routine, before/after, morning ritual). (3) Ambassador program: 20 micro-customers (not influencers) who create monthly content for product credits. Rights: DM template requesting permission within 24 hours of mention. Add clause to checkout terms allowing review/photo usage on website. Amplification: Tier 1 (ad-quality photos/videos, ~10%) → paid social ads, product pages. Tier 2 (good social content, ~30%) → brand social feed, email campaigns. Tier 3 (reviews/text, ~60%) → product pages, review sections. Expected impact: 25-35% conversion lift on product pages with UGC, 3-4x higher ad CTR with UGC creative vs. studio creative.
