---
name: linkedin-ads-campaign-builder
description: >
  Structure LinkedIn ad campaigns for B2B lead generation — targeting, formats, and budget optimization.
  Use this skill when the user says "LinkedIn ads campaign", "LinkedIn advertising strategy",
  "LinkedIn lead gen ads", "LinkedIn Sponsored Content", "LinkedIn InMail campaign", "LinkedIn
  ad targeting", "LinkedIn ads for B2B", "LinkedIn campaign structure", "LinkedIn audience
  targeting", "LinkedIn ads budget", or "LinkedIn conversion tracking". Also trigger for LinkedIn
  Document Ads, Thought Leader Ads, or LinkedIn retargeting setup.
---

# LinkedIn Ads Campaign Builder

Structures complete LinkedIn advertising campaigns with targeting, format selection, budget allocation, bidding strategy, and lead gen form optimization for B2B marketing.

## Granularity Check

> **Time**: ~5 min data prep → ~10 min Claude session → ~30-60 min building in Google Ads / Meta Ads Manager. If implementing output in LinkedIn Campaign Manager, add 30-45 min for setup. Input is business goals and ICP. Output is Markdown campaign blueprint.

## User Intent Mapping

- "Set up LinkedIn ads for our SaaS product" (full campaign)
- "LinkedIn targeting for C-suite decision makers" (targeting)
- "Best LinkedIn ad format for lead generation" (format selection)
- "LinkedIn ads budget for a B2B startup" (budget)
- "Our LinkedIn ads have high CPL — what's wrong?" (optimization)
- "LinkedIn retargeting campaign" (funnel stage)
- "Thought Leader Ads strategy" (specific format)
- "LinkedIn Lead Gen Forms vs. website landing page" (conversion strategy)
- "LinkedIn ABM campaign for enterprise accounts" (ABM)
- "How to reduce LinkedIn ad costs" (cost optimization)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Product/Service | Text | What you're advertising |
| Target Audience (ICP) | Text | Job titles, industries, company sizes |
| Objective | Text | Lead gen, brand awareness, website traffic, engagement |

### If You Don't Have This Data

- **No LinkedIn Insight Tag?** Install it first — Campaign Manager → Account Assets → Insight Tag. Required for conversion tracking and retargeting.
- **No ICP defined?** List your best 5 customers: their titles, company sizes, and industries. That's your starting ICP.
- **No budget benchmark?** LinkedIn is premium — expect $5-15 CPL for gated content, $50-150 CPL for demo requests. Budget minimum $3,000/month for meaningful data.
- **No creative?** Start with single image ads and Document Ads (PDF carousels) — they require no video production.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Monthly Budget | Number | Total LinkedIn ad spend |
| Current Performance | CSV | Campaign, spend, impressions, clicks, leads, CPL |
| Content Assets | Text | Whitepapers, case studies, webinar recordings available |
| Target Account List | CSV | Company names for ABM campaigns |
| Sales Cycle Length | Text | Average days from lead to close |

## Process

### Step 1: Campaign Structure
| Campaign Group | Objective | Funnel Stage |
|---|---|---|
| Awareness | Brand Awareness | Top of funnel |
| Consideration | Engagement / Video Views | Middle of funnel |
| Conversion | Lead Gen / Website Conversions | Bottom of funnel |
| Retargeting | Lead Gen / Website Conversions | Re-engagement |

### Step 2: Audience Targeting
LinkedIn targeting layers:
- **Job Title**: Target specific titles (VP Marketing, CTO, etc.)
- **Job Function + Seniority**: Broader reach (Marketing + Director+)
- **Industry + Company Size**: Vertical targeting
- **Skills**: Target by listed skills (alternative to job title)
- **Company List**: Upload ABM target list (minimum 300 companies)
- **Lookalike Audiences**: Based on customer list or website visitors
- **Matched Audiences**: Website retargeting, contact list, engagement retargeting

Audience size guidelines:
- Sponsored Content: 50,000-500,000
- Message Ads: 15,000-50,000
- ABM campaigns: 1,000-30,000

### Step 3: Format Selection
| Format | Best For | Avg. CTR | Notes |
|---|---|---|---|
| Single Image | Lead gen, traffic | 0.4-0.6% | Most versatile, easiest to produce |
| Carousel | Storytelling, multi-benefit | 0.5-0.8% | 2-10 cards, each clickable |
| Document Ad | Thought leadership, gated content | 0.6-1.0% | PDF carousel, native engagement |
| Video | Awareness, product demos | 0.3-0.5% | 15-30s optimal, captions required |
| Thought Leader Ad | Trust, authenticity | 0.8-1.5% | Boost employee posts as ads |
| Message Ad | Event invites, high-intent offers | 30-50% open rate | Use sparingly (1x/45 days per person) |
| Lead Gen Form | Frictionless conversion | Varies | Pre-filled forms, 2-3x higher conversion vs. landing page |

### Step 4: Budget & Bidding
- Minimum viable budget: $50/day per campaign ($1,500/month)
- Recommended: $100-200/day ($3,000-6,000/month) for statistical significance
- Bidding: Start with Maximum Delivery, switch to Manual CPC after 2 weeks
- Budget split: 60% conversion, 25% awareness, 15% retargeting

### Step 5: Lead Gen Form Optimization
- Use 3-4 fields maximum (more fields = higher quality but lower volume)
- Pre-filled fields: name, email, company, job title (LinkedIn auto-fills)
- Custom questions: 1-2 qualifying questions max
- Thank you page: include CTA to book a demo or access content
- Hidden fields: UTM parameters for CRM attribution

### Confidence & Sample Size
> **Confidence Note**: LinkedIn ads are expensive — $8-12 average CPC. Small budgets need longer to reach statistical significance. Don't judge campaign performance before 2,000+ impressions and 7+ days. CPL benchmarks vary 5-10x by industry, offer type, and audience seniority. Always compare CPL to customer LTV, not in isolation.

### ⚠️ Human Checkpoint
> Review audience targeting for relevance (avoid targeting too broad or too narrow), verify Lead Gen Form fields for GDPR/CCPA compliance, and ensure content offers match the audience's funnel stage.

> **Benchmark Context**: See LinkedIn 2024 B2B Marketing Benchmark for current industry benchmarks relevant to this analysis.
## Output Contract

### Deliverable: Markdown Campaign Blueprint

```markdown
# LinkedIn Ads Campaign Blueprint: [Business]

## Account Structure
| Campaign Group | Campaign | Objective | Budget |
|---|---|---|---|

## Audience Targeting
### Primary Audience
- Job Titles: [list]
- Industries: [list]
- Company Size: [range]
- Estimated Audience Size: [number]

### Retargeting Audiences
- [segment]: [criteria]

## Ad Format & Creative Recommendations
| Campaign | Format | Creative Direction |
|---|---|---|

## Lead Gen Form Design
- Fields: [list]
- Custom Questions: [list]
- Thank You CTA: [action]

## Budget & Bidding
| Campaign | Daily Budget | Bid Strategy | Target CPC/CPL |
|---|---|---|---|

## Launch Checklist
- [ ] Insight Tag verified
- [ ] Conversion tracking configured
- [ ] Lead Gen Form tested
- [ ] UTM parameters set
- [ ] CRM integration connected
```

## Platform Implementation Steps

### LinkedIn Campaign Manager
1. Go to linkedin.com/campaignmanager → Create Campaign Group
2. Set budget and schedule at the group level
3. Create campaigns per the blueprint (1 per objective)
4. Build audiences using the targeting specifications
5. Upload creative and set ad copy
6. Create Lead Gen Forms with specified fields
7. Set up conversion tracking events
8. Review and launch

### CRM Integration
1. Connect LinkedIn Lead Gen Forms to your CRM (HubSpot, Salesforce, etc.)
2. Map form fields to CRM contact properties
3. Set up lead routing rules based on form responses
4. Create automated follow-up sequences (respond within 5 minutes for best results)

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Very low impressions | Audience too narrow (<10K) | Broaden targeting; use Job Function + Seniority instead of exact titles |
| High CPL | Wrong offer for audience stage | Test lighter offers (guide, checklist) before demos |
| Leads but no pipeline | Low-quality leads or slow follow-up | Add qualifying questions to Lead Gen Form; automate <5 min follow-up |
| Ad fatigue | Same creative for 30+ days | Refresh creative every 3-4 weeks; rotate 3-5 ad variations |

## How to Get Your Data

- **LinkedIn Campaign Manager**: Campaigns → Export (CSV with all metrics)
- **No data**: Describe your ICP and budget — Claude builds from benchmarks
- **Customer list**: Export from CRM for Matched Audience upload (minimum 300 contacts, email match rate ~30-70%)

## Example

**Input**: "LinkedIn ads for a cybersecurity SaaS. Target: CISOs and VP Security at mid-market companies (500-5000 employees). Objective: lead gen for demo requests. Budget: $6,000/month. Have a threat assessment whitepaper and product demo video."

**Output**: 3-campaign structure: (1) Awareness — Video ad (product demo, 30s cut) to CISO + VP Security audience, $1,500/mo; (2) Lead Gen — Document Ad (whitepaper as carousel) with Lead Gen Form (4 fields: name, email, company size, biggest security concern), $3,000/mo; (3) Retargeting — Single image ad with demo CTA to whitepaper downloaders + website visitors, $1,500/mo. Audience: Job Titles (CISO, VP Security, Director Information Security) + Company Size (500-5000) + Industries (Technology, Financial Services, Healthcare). Estimated audience: 45,000. Lead Gen Form fields: Name (pre-filled), Work Email (pre-filled), Company Size (dropdown), "What's your biggest security challenge in 2026?" (open text). Expected CPL: $75-120 for whitepaper, $150-250 for demo. 4-week optimization plan included.

## Related Skills

- **[ad-copy-generator](./ad-copy-generator.md)** — Generate LinkedIn-specific ad copy and testimonial variations that convert B2B audiences.
- **[audience-targeting-builder](./audience-targeting-builder.md)** — Build and refine LinkedIn audience segments with layered targeting criteria.
- **[ad-performance-analyzer](./ad-performance-analyzer.md)** — Analyze LinkedIn campaign performance to optimize targeting and creative.
- **[account-research-synthesizer](../b2b/account-research-synthesizer.md)** — Research target accounts to inform LinkedIn ABM campaign strategy and messaging.
