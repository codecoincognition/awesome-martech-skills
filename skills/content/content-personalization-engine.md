---
name: content-personalization-engine
description: >
  Design content personalization strategies — audience segmentation, dynamic content, and personalization rules.
  Use this skill when the user says "content personalization", "dynamic content strategy",
  "personalized content experience", "website personalization", "content targeting rules",
  "audience-based content delivery", "personalization engine setup", "1-to-1 content strategy",
  "personalized recommendations", "content personalization roadmap", or "adaptive content design".
  Also trigger for behavioral content targeting, persona-based content delivery, or content
  recommendation algorithm design.
---

# Content Personalization Engine

Designs content personalization strategies with audience segmentation, dynamic content rules, personalization triggers, and measurement frameworks for delivering relevant experiences at scale.

## Granularity Check

> **Time**: ~10 min data prep → ~15 min Claude session → ~30-60 min implementing in your CMS. If implementing, add 2-4 weeks for platform setup. Input is audience data, content inventory, and technology stack. Output is Markdown personalization strategy with rules and implementation plan.

## User Intent Mapping

- "How to personalize our website content" (website)
- "Dynamic content strategy" (dynamic)
- "Content personalization for different audiences" (segmentation)
- "Personalized recommendations on our site" (recommendations)
- "Content targeting rules" (rules)
- "1-to-1 content experiences" (advanced)
- "Personalization roadmap" (roadmap)
- "We show the same content to everyone" (starter)
- "Content personalization for email" (email)
- "Behavioral targeting for content" (behavioral)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Audience Segments | Text | Key audience groups or personas |
| Content Inventory | Text | Types and volume of content available |
| Technology Stack | Text | CMS, CDP, marketing automation platform |

### If You Don't Have This Data

- **No audience segments?** Claude designs segmentation based on your business model and common patterns (new vs. returning, industry, funnel stage).
- **Limited content inventory?** Claude prioritizes which personalization requires the least content variety to implement.
- **No personalization technology?** Claude recommends tools by budget and starts with what your current CMS or ESP can do.
- **No behavioral data?** Claude starts with rule-based personalization (geography, referral source, UTM parameters) before graduating to behavioral.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Analytics Data | CSV | Traffic segments, behavior patterns |
| CRM Data | Text | Customer attributes and lifecycle stage |
| Current Personalization | Text | What you already personalize |
| Budget | Text | Technology and content investment available |
| Compliance | Text | Privacy regulations (GDPR, CCPA) |

## Process

### Step 1: Personalization Maturity Assessment
| Level | Description | Example |
|---|---|---|
| Level 0 | No personalization | Same experience for everyone |
| Level 1 | Segment-based | Content by industry or role |
| Level 2 | Behavioral | Content based on past actions |
| Level 3 | Predictive | AI-driven recommendations |
| Level 4 | Real-time | Dynamic content adapting in-session |

### Step 2: Data Signal Mapping
| Signal Type | Examples | Use Case |
|---|---|---|
| Explicit | Form data, preferences, profile | Persona-based content |
| Implicit | Page views, downloads, time on site | Interest-based content |
| Contextual | Location, device, time, referral source | Situational content |
| Historical | Purchase history, engagement patterns | Lifecycle content |
| Predictive | Propensity scores, intent signals | Proactive recommendations |

### Step 3: Personalization Rules
Per content touchpoint:
- **Trigger**: What data signal activates personalization
- **Segment**: Which audience sees which variant
- **Content**: What changes (headline, CTA, image, entire section, full page)
- **Fallback**: Default content for unidentifiable visitors
- **Measurement**: How to track impact

### Step 4: Content Requirements
- Map content variants needed per personalization rule
- Identify high-impact, low-effort starting points
- Calculate content production required (variants × touchpoints)
- Design modular content components (reusable across variants)

### Step 5: Privacy-Compliant Personalization
- Consent-based data collection (cookie consent, preference centers)
- First-party data strategy (reduce reliance on third-party cookies)
- Transparent personalization (let users know why they see what they see)
- Opt-out mechanisms (allow users to see default experience)
- GDPR/CCPA compliance for data used in personalization

### Step 6: Measurement Framework
| Metric | Description | Target |
|---|---|---|
| Engagement lift | Personalized vs. default content | +20-40% |
| Conversion lift | Personalized vs. default conversion rate | +10-30% |
| Revenue per visitor | Revenue from personalized experiences | +15-25% |
| Content efficiency | Fewer pages needed to convert | -20-30% |

### Confidence & Sample Size

> **Confidence Note**: Personalization requires sufficient traffic to test variants reliably. Each personalized segment needs 1,000+ monthly visitors for meaningful testing. Start with 2-3 high-impact personalization rules before scaling. Over-personalization can feel creepy — test user comfort levels. Personalization is only as good as your data quality — garbage in, garbage out.

### ⚠️ Human Checkpoint
> Review personalization rules for privacy compliance before implementation. Test all fallback experiences — most visitors will see the default. Verify personalization doesn't create accessibility issues. Get legal review for data usage in personalization.

> **Benchmark Context**: Consult current industry reports for up-to-date benchmarks relevant to this analysis.

## Output Contract

### Deliverable: Markdown Personalization Strategy

```markdown
# Content Personalization Strategy: [Brand]

## Maturity Assessment
- Current level: [0-4]
- Target level: [0-4]
- Timeline: [months]

## Audience Segments
| Segment | Size | Data Signals | Priority |
|---|---|---|---|

## Personalization Rules
### Rule 1: [Name]
- **Trigger**: [data signal]
- **Segment**: [audience]
- **Content change**: [what changes]
- **Touchpoint**: [where]
- **Fallback**: [default]
- **Expected impact**: [metric]

## Content Requirements
| Personalization | Variants Needed | Content Exists? | Production Effort |
|---|---|---|---|

## Technology Requirements
| Component | Current Tool | Gap | Recommendation |
|---|---|---|---|

## Implementation Roadmap
| Phase | Personalization Rules | Timeline | Expected Lift |
|---|---|---|---|

## Measurement Plan
| Metric | Baseline | Target | Tracking |
|---|---|---|---|

## Privacy Compliance
| Requirement | Status | Action |
|---|---|---|
```

## Platform Implementation Steps

### CMS Personalization
1. Enable personalization features in CMS (HubSpot smart content, WordPress plugins, Optimizely)
2. Set up audience segments based on available data signals
3. Create content variants for each personalization rule
4. Configure fallback/default content for all rules
5. Set up A/B tests comparing personalized vs. default

### CDP/Data Platform
1. Unify customer data from website, CRM, and marketing tools
2. Create audience segments based on behavioral and demographic data
3. Configure real-time event streaming for in-session personalization
4. Set up identity resolution for cross-device personalization

### Email Personalization
1. Configure dynamic content blocks in ESP (Klaviyo, HubSpot, Braze)
2. Set up merge tags for basic personalization (name, company)
3. Create content blocks triggered by behavioral data
4. Build product recommendation modules based on purchase/browse history

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| No lift from personalization | Wrong signals or irrelevant content variants | Review data signals; test different content changes; simplify rules |
| Creepy/invasive feeling | Too specific or showing data users didn't knowingly share | Use broader segments; be transparent about personalization; add opt-out |
| Technical implementation breaks | Complex rules with edge cases | Start simple; test all segments including edge cases; strong fallbacks |
| Content production bottleneck | Too many variants needed | Use modular content (swap components, not full pages); prioritize high-traffic touchpoints |

## How to Get Your Data

- **Audience data**: Google Analytics → Audience segments; CRM → customer attributes
- **Behavioral data**: Analytics → user flow, page sequences, conversion paths
- **Content inventory**: CMS → export all pages; identify which have high traffic × low conversion
- **No data**: Describe your audience and website — Claude designs starter personalization rules

## Example

**Input**: "Content personalization strategy for a B2B SaaS. 3 personas: startup founders, enterprise IT directors, agency owners. Website gets 50K monthly visitors. Using HubSpot CMS and CRM. Currently no personalization."

**Output**: Maturity: Level 0 → target Level 2 within 6 months. Priority personalization rules: (1) Homepage hero — change headline, subheadline, and CTA based on industry (detected from CRM data for known contacts, from referral source and content consumption for anonymous). 3 variants needed + default. Expected: 25-35% conversion lift on homepage. (2) Case studies page — show industry-relevant case studies first (if startup → show startup stories, if enterprise → show enterprise stories). HubSpot smart content handles this natively. (3) Pricing page — show relevant plan recommendation and social proof by company size (startup: "1,000+ startups trust us"; enterprise: "trusted by Fortune 500"). (4) Blog sidebar CTA — dynamic CTA based on content topic and visitor funnel stage (new visitor → educational resource; returning → product demo). Content requirements: 12 content variants total for Phase 1 (3 personas × 4 touchpoints). Implementation: Phase 1 (month 1-2) — homepage and pricing personalization using HubSpot smart content. Phase 2 (month 3-4) — case study and blog CTA personalization. Phase 3 (month 5-6) — behavioral triggers (content consumption patterns → persona assignment). Expected ROI: 15-25% increase in MQL conversion rate.

## Related Skills

- **[Customer Persona Builder](../insights/customer-persona-builder.md)** — Use to define audience segments that will drive your personalization rules and dynamic content strategy.
- **[Content Pillar Strategy](./content-pillar-strategy.md)** — Use to structure content in ways that support personalization (different content paths for different personas).
- **[Content Distribution Strategy](./content-distribution-strategy.md)** — Use to deliver personalized content through the right channels at the right time for each segment.
- **[Segmentation Rule Builder](../crm/segmentation-rule-builder.md)** — Use to define the audience segments that trigger your personalization rules.
