<p align="center">
  <h1 align="center">awesome-martech-skills</h1>
  <p align="center"><strong>Turn Claude into your marketing team's secret weapon.</strong></p>
  <p align="center">156 ready-to-use skills that transform raw marketing data into strategies, audits, campaigns, and copy — in minutes, not days.</p>
  <p align="center">
    <a href="SKILL-PICKER.md">Find Your Skill →</a> · <a href="STARTER-PACKS.md">Industry Starter Packs →</a> · <a href="SHOWCASE.md">See It In Action →</a>
  </p>
</p>

---

## The Problem

You're sitting on a goldmine of marketing data — Google Analytics exports, email campaign reports, CRM dumps, ad platform CSVs — but turning that data into *decisions* takes hours of spreadsheet wrestling, agency fees, or expensive tools you'll use twice.

Meanwhile, your competitors ship campaigns faster, test more, and optimize relentlessly.

## The Solution

**awesome-martech-skills** is a free, open-source collection of 156 Claude AI skills that do the heavy lifting for you. Each skill is a battle-tested prompt template that takes your CSV data and produces actionable marketing output — keyword strategies, email sequences, ROI calculations, competitor analyses, content calendars, and more.

**No API keys. No vendor lock-in. No setup.** Just export a CSV from any tool you already use, paste it into Claude, and get results you'd normally pay an agency $5K+ to deliver.

> *"I built my entire Q2 content strategy in 90 minutes using 5 skills chained together. That used to take my team two weeks."* — [Read the full case study →](SHOWCASE.md#case-study-1-from-zero-to-content-pipeline-in-one-afternoon)

---

## How It Works

```
┌─────────────────┐      ┌──────────────────┐      ┌─────────────────────┐
│  Your Data       │      │  Claude + Skill   │      │  Actionable Output   │
│  (CSV export     │  →   │  (paste data +    │  →   │  (strategy, audit,   │
│  from any tool)  │      │  trigger skill)   │      │  copy, analysis)     │
└─────────────────┘      └──────────────────┘      └─────────────────────┘
```

1. **Export your data** from any marketing tool as CSV — each skill tells you exactly what to export and where to find it
2. **Tell Claude what you need** in plain language — each skill has 10+ trigger phrases so Claude knows what to do
3. **Get production-ready output** — scored analyses, prioritized recommendations, ready-to-implement strategies

Every skill includes honest time estimates, confidence levels, industry benchmarks with sources, and clear "what this can't do" disclaimers. No black boxes.

## Quick Start

```bash
# Clone the whole collection
git clone https://github.com/CodeCoinCognitionLLC/awesome-martech-skills.git

# Or install a single skill
claude install skill path/to/skill.md
```

**Not sure which skill to start with?** Just describe your problem — the [MarTech Skill Router](skills/router/SKILL.md) will recommend the right skills and the order to use them:

```
 You say:                                     You get:
 ────────                                     ────────
 "My email open rates                         Step 1: email-subject-line-tester
  dropped 20% this quarter"          →        Step 2: email-deliverability-auditor
                                              Step 3: email-list-segmentation
                                              + what data to export, time estimate

 "I need to launch a product                  Step 1: customer-persona-builder
  in 6 weeks"                        →        Step 2: gtm-launch-planner
                                              Step 3: campaign-brief-synthesizer
                                              Step 4: content-distribution-strategy

 "My boss wants a dashboard                   Step 1: dashboard-requirement-gatherer
  by Friday"                         →        Step 2: marketing-dashboard-builder
```

The router matches your *outcome* to skills — no need to know which category or channel to look in. Just say "help" to get started.

You can also browse skills manually: [Skill Picker](SKILL-PICKER.md) (channel × stage matrix) · [Industry Starter Packs](STARTER-PACKS.md) · [Maturity Model](MATURITY-MODEL.md)

---

## 🚀 Pick Your Path

Whether you're a solo founder or a 50-person marketing team, we've built entry points for every situation:

### By Industry

Pick a curated bundle of skills designed for your business model, with a recommended adoption sequence and expected outcomes.

| Starter Pack | Skills | Best For |
|---|---|---|
| [SaaS B2B](STARTER-PACKS.md#1-saas-b2b-starter-pack) | 15 | Product-led growth, lead gen, multi-touch attribution |
| [E-commerce & DTC](STARTER-PACKS.md#2-e-commerce--dtc-starter-pack) | 15 | Product pages, ad campaigns, checkout optimization |
| [Agency & Consultancy](STARTER-PACKS.md#3-agency--consultancy-starter-pack) | 20 | Client deliverables, reporting, multi-client management |
| [Enterprise Marketing](STARTER-PACKS.md#4-enterprise-marketing-starter-pack) | 18 | Governance, compliance, cross-functional alignment |
| [Media & Publishing](STARTER-PACKS.md#5-media--publishing-starter-pack) | 14 | Content production, audience growth, monetization |
| [Non-Profit & Education](STARTER-PACKS.md#6-non-profit--education-starter-pack) | 12 | Limited budgets, community building, donor engagement |

[Browse all Starter Packs →](STARTER-PACKS.md)

### By Team Maturity

Know where you are, know where to go. Our [Maturity Model](MATURITY-MODEL.md) maps all 156 skills to 5 organizational stages:

| Level | Stage | Skills to Adopt | You're Here If... |
|---|---|---|---|
| 1 | **Foundation** | 10 core skills | Just starting with AI-assisted marketing |
| 2 | **Growth** | +20 skills | Established channels, need optimization |
| 3 | **Scale** | +30 skills | Multi-channel, need efficiency + governance |
| 4 | **Enterprise** | +40 skills | Full stack, need advanced analytics + compliance |
| 5 | **Optimization** | All 156 | Running at peak, optimizing every edge |

[See the full Maturity Model →](MATURITY-MODEL.md)

### By Channel

Jump straight to the category you need:

| Category | Skills | What You'll Get |
|---|---|---|
| [SEO](skills/seo/) | 16 | Keyword clusters, technical audits, content briefs, competitor gaps, migration plans |
| [Email](skills/email/) | 12 | Sequences, subject line scoring, deliverability fixes, segmentation, compliance checks |
| [Social](skills/social/) | 13 | Content calendars, platform-specific optimization, influencer briefs, crisis plans |
| [Ads](skills/ads/) | 13 | Campaign builders (Google/Meta/LinkedIn), budget optimization, creative testing |
| [Analytics](skills/analytics/) | 11 | GA4 setup, dashboards, attribution models, funnel analysis, cohort tracking |
| [CRM](skills/crm/) | 9 | Lead scoring, data hygiene, lifecycle stages, churn prediction, automation |
| [CRO](skills/cro/) | 9 | A/B test design, landing page audits, form optimization, heatmap analysis |
| [Content](skills/content/) | 13 | Blog outlines, repurposing, editorial calendars, governance, localization |
| [PR & Events](skills/pr-events/) | 8 | Press releases, media pitches, event logistics, crisis comms, speaker proposals |
| [MarTech Ops](skills/martech-ops/) | 9 | UTM management, compliance, vendor scoring, SLA docs, approval workflows |
| [Video & Podcast](skills/video-podcast/) | 10 | Scripts, YouTube SEO, show notes, repurposing, webinar promotion |
| [Growth](skills/growth/) | 9 | Experiments, channel mix, personas, GTM plans, referral programs |
| [Insights](skills/insights/) | 11 | VoC mining, win/loss analysis, journey mapping, trend scanning, pricing research |
| [AI Marketing](skills/ai-marketing/) | 7 | Prompt libraries, chatbot design, predictive scoring, sentiment analysis |
| [B2B & ABM](skills/b2b/) | 6 | Account research, buying committees, sales decks, RFP responses |

---

## See It In Action

Don't take our word for it — see complete walkthroughs of marketers using these skills to solve real problems:

📖 **[Case Study 1: Content Pipeline in an Afternoon](SHOWCASE.md#case-study-1-from-zero-to-content-pipeline-in-one-afternoon)** — A SaaS founder chains 5 skills to build a complete Q2 content strategy in 90 minutes.

📖 **[Case Study 2: Agency Reporting at Scale](SHOWCASE.md#case-study-2-agency-reporting-at-scale)** — A digital agency uses 6 skills to deliver client deliverables in hours instead of days.

📖 **[Case Study 3: Retention Machine](SHOWCASE.md#case-study-3-building-a-retention-machine)** — A DTC brand chains 4 skills to reduce churn by identifying at-risk customers before they leave.

[Read all case studies →](SHOWCASE.md)

---

## Workflow Chains

Skills are designed to chain together — the output of one becomes the input for the next. Pre-built workflows connect skills into complete marketing processes:

| Workflow | Skills Chained | What It Builds |
|---|---|---|
| [SEO Content Flywheel](workflows/seo-content-flywheel.md) | 5 | keyword research → brief → outline → write → optimize |
| [Content Engine](workflows/content-engine.md) | 6 | keywords → gaps → brief → outline → expand → SEO audit |
| [Paid Acquisition](workflows/paid-acquisition.md) | 5 | personas → campaign → ad copy → landing page → A/B test |
| [Brand Positioning](workflows/brand-positioning.md) | 4 | VoC research → whitespace → narrative → campaign angles |

Every skill also includes a **Related Skills** section suggesting 2-4 natural next steps, so you always know what to chain next.

---

## Complete Skill Index

All 156 skills organized by category. Click any category to expand.

<details>
<summary><strong>SEO — 16 skills</strong></summary>

| Skill | Description |
|---|---|
| [keyword-cluster-analyzer](skills/seo/keyword-cluster-analyzer.md) | Cluster keywords by topic and search intent |
| [content-brief-generator](skills/seo/content-brief-generator.md) | Generate SEO content briefs from target keywords |
| [content-gap-analyzer](skills/seo/content-gap-analyzer.md) | Find content gaps vs. competitors |
| [on-page-seo-auditor](skills/seo/on-page-seo-auditor.md) | Audit on-page SEO elements with scored report |
| [content-refresh-prioritizer](skills/seo/content-refresh-prioritizer.md) | Prioritize which content to update first |
| [technical-seo-auditor](skills/seo/technical-seo-auditor.md) | Crawl-level technical SEO audits for indexation, speed, and structure |
| [backlink-analysis-report](skills/seo/backlink-analysis-report.md) | Analyze backlink profiles for authority, toxicity, and opportunities |
| [local-seo-optimizer](skills/seo/local-seo-optimizer.md) | Optimize Google Business Profiles and local search presence |
| [serp-feature-optimizer](skills/seo/serp-feature-optimizer.md) | Win featured snippets, PAA boxes, and rich results |
| [seo-competitor-analysis](skills/seo/seo-competitor-analysis.md) | Deep-dive SEO competitor benchmarking and gap analysis |
| [ecommerce-seo-optimizer](skills/seo/ecommerce-seo-optimizer.md) | Product page and category SEO for e-commerce sites |
| [international-seo-strategy](skills/seo/international-seo-strategy.md) | Multi-market hreflang, content, and domain strategy |
| [site-migration-seo-plan](skills/seo/site-migration-seo-plan.md) | SEO migration checklists for domain, platform, or redesign moves |
| [page-speed-optimizer](skills/seo/page-speed-optimizer.md) | Core Web Vitals diagnosis and page speed improvements |
| [seo-content-strategy](skills/seo/seo-content-strategy.md) | Build topic authority with pillar-cluster content architecture |
| [seo-reporting-dashboard](skills/seo/seo-reporting-dashboard.md) | Create SEO reporting dashboards from Search Console and GA4 data |

</details>

<details>
<summary><strong>Email — 12 skills</strong></summary>

| Skill | Description |
|---|---|
| [email-subject-line-tester](skills/email/email-subject-line-tester.md) | Score subject lines on 6 dimensions + generate variants |
| [email-sequence-builder](skills/email/email-sequence-builder.md) | Design multi-step email sequences with timing and logic |
| [welcome-series-creator](skills/email/welcome-series-creator.md) | Generate complete welcome email series |
| [email-deliverability-auditor](skills/email/email-deliverability-auditor.md) | Diagnose and fix email deliverability issues (SPF, DKIM, reputation) |
| [email-list-segmentation](skills/email/email-list-segmentation.md) | Build behavioral and demographic email segments |
| [email-template-designer](skills/email/email-template-designer.md) | Design responsive email templates with HTML/CSS best practices |
| [email-performance-analyzer](skills/email/email-performance-analyzer.md) | Analyze email campaign metrics and identify optimization opportunities |
| [email-copywriting-framework](skills/email/email-copywriting-framework.md) | Write high-converting email copy by type (promo, nurture, re-engage) |
| [email-ab-testing-framework](skills/email/email-ab-testing-framework.md) | Design and analyze email A/B tests with statistical rigor |
| [email-compliance-checker](skills/email/email-compliance-checker.md) | Audit emails for CAN-SPAM, GDPR, and CASL compliance |
| [email-automation-workflow](skills/email/email-automation-workflow.md) | Design triggered email automation workflows with branching logic |
| [transactional-email-optimizer](skills/email/transactional-email-optimizer.md) | Optimize transactional emails for engagement and brand consistency |

</details>

<details>
<summary><strong>Social — 13 skills</strong></summary>

| Skill | Description |
|---|---|
| [social-content-calendar](skills/social/social-content-calendar.md) | Plan monthly social media content calendars |
| [hashtag-strategy-builder](skills/social/hashtag-strategy-builder.md) | Research and optimize hashtag strategies per platform |
| [linkedin-post-optimizer](skills/social/linkedin-post-optimizer.md) | Optimize LinkedIn posts for algorithm reach and engagement |
| [twitter-thread-writer](skills/social/twitter-thread-writer.md) | Write compelling Twitter/X threads with hooks and formatting |
| [instagram-caption-writer](skills/social/instagram-caption-writer.md) | Write Instagram captions optimized for engagement and discovery |
| [tiktok-content-strategy](skills/social/tiktok-content-strategy.md) | Plan TikTok content strategy with trends and creator tactics |
| [social-listening-report](skills/social/social-listening-report.md) | Analyze social listening data for brand mentions and sentiment |
| [influencer-outreach-brief](skills/social/influencer-outreach-brief.md) | Create influencer collaboration briefs with deliverables and terms |
| [social-ad-creative-brief](skills/social/social-ad-creative-brief.md) | Write creative briefs for paid social ad campaigns |
| [community-management-playbook](skills/social/community-management-playbook.md) | Build community management playbooks with response frameworks |
| [social-commerce-optimizer](skills/social/social-commerce-optimizer.md) | Optimize social commerce storefronts and shoppable content |
| [social-crisis-response-plan](skills/social/social-crisis-response-plan.md) | Create social media crisis response plans with escalation protocols |
| [social-engagement-analyzer](skills/social/social-engagement-analyzer.md) | Analyze social engagement metrics to optimize content strategy |

</details>

<details>
<summary><strong>Ads — 13 skills</strong></summary>

| Skill | Description |
|---|---|
| [ad-copy-generator](skills/ads/ad-copy-generator.md) | Generate ad copy for Google/Meta/LinkedIn |
| [google-ads-campaign-builder](skills/ads/google-ads-campaign-builder.md) | Structure Google Ads campaigns end-to-end |
| [landing-page-ad-matcher](skills/ads/landing-page-ad-matcher.md) | Audit ad-to-landing-page message alignment |
| [meta-ads-campaign-builder](skills/ads/meta-ads-campaign-builder.md) | Build Meta/Facebook/Instagram ad campaigns end-to-end |
| [linkedin-ads-campaign-builder](skills/ads/linkedin-ads-campaign-builder.md) | Build LinkedIn advertising campaigns for B2B targeting |
| [ad-performance-analyzer](skills/ads/ad-performance-analyzer.md) | Analyze paid ad performance across platforms with optimization recs |
| [ad-budget-optimizer](skills/ads/ad-budget-optimizer.md) | Optimize ad budget allocation across campaigns and platforms |
| [retargeting-campaign-builder](skills/ads/retargeting-campaign-builder.md) | Design retargeting campaigns with audience segmentation |
| [ppc-keyword-strategy](skills/ads/ppc-keyword-strategy.md) | Build PPC keyword strategies with match types and bid recommendations |
| [ad-creative-testing-framework](skills/ads/ad-creative-testing-framework.md) | Design ad creative testing programs with statistical methodology |
| [display-ad-network-optimizer](skills/ads/display-ad-network-optimizer.md) | Optimize display and programmatic ad network campaigns |
| [audience-targeting-builder](skills/ads/audience-targeting-builder.md) | Build audience targeting strategies across ad platforms |
| [ad-compliance-checker](skills/ads/ad-compliance-checker.md) | Check ad copy and landing pages for platform policy compliance |

</details>

<details>
<summary><strong>Analytics — 11 skills</strong></summary>

| Skill | Description |
|---|---|
| [ga4-event-setup-guide](skills/analytics/ga4-event-setup-guide.md) | Create GA4 event tracking implementation guides |
| [marketing-roi-calculator](skills/analytics/marketing-roi-calculator.md) | Calculate ROI, ROAS, CAC, LTV across channels |
| [marketing-dashboard-builder](skills/analytics/marketing-dashboard-builder.md) | Build interactive HTML marketing dashboards |
| [attribution-model-builder](skills/analytics/attribution-model-builder.md) | Build and compare attribution models |
| [budget-variance-analyzer](skills/analytics/budget-variance-analyzer.md) | Compare planned vs. actual marketing spend with root cause analysis |
| [dashboard-requirement-gatherer](skills/analytics/dashboard-requirement-gatherer.md) | Gather KPI definitions and data sources for dashboard builds |
| [cohort-analysis-builder](skills/analytics/cohort-analysis-builder.md) | Build cohort analyses for retention, revenue, and LTV tracking |
| [marketing-mix-modeler](skills/analytics/marketing-mix-modeler.md) | Model marketing channel contributions and optimize budget allocation |
| [funnel-drop-off-analyzer](skills/analytics/funnel-drop-off-analyzer.md) | Diagnose conversion funnel drop-offs with root cause analysis |
| [ab-test-result-analyzer](skills/analytics/ab-test-result-analyzer.md) | Analyze A/B test results with statistical significance assessment |
| [campaign-performance-benchmarker](skills/analytics/campaign-performance-benchmarker.md) | Benchmark campaign performance against industry standards |

</details>

<details>
<summary><strong>CRM — 9 skills</strong></summary>

| Skill | Description |
|---|---|
| [lead-scoring-model-builder](skills/crm/lead-scoring-model-builder.md) | Build points-based lead scoring from CRM data |
| [crm-data-hygiene-auditor](skills/crm/crm-data-hygiene-auditor.md) | Audit CRM data for duplicates, stale records, and formatting issues |
| [data-enrichment-prioritizer](skills/crm/data-enrichment-prioritizer.md) | Prioritize which CRM records to enrich first |
| [lifecycle-stage-designer](skills/crm/lifecycle-stage-designer.md) | Design customer lifecycle stages with transition criteria |
| [segmentation-rule-builder](skills/crm/segmentation-rule-builder.md) | Build CRM segmentation rules for targeted marketing |
| [automation-workflow-designer](skills/crm/automation-workflow-designer.md) | Design CRM automation workflows with triggers and branching |
| [churn-prediction-framework](skills/crm/churn-prediction-framework.md) | Build churn prediction frameworks from CRM behavioral data |
| [customer-onboarding-optimizer](skills/crm/customer-onboarding-optimizer.md) | Optimize customer onboarding sequences for activation |
| [reporting-dashboard-designer](skills/crm/reporting-dashboard-designer.md) | Design CRM reporting dashboards with KPIs and drill-downs |

</details>

<details>
<summary><strong>CRO — 9 skills</strong></summary>

| Skill | Description |
|---|---|
| [landing-page-optimizer](skills/cro/landing-page-optimizer.md) | Audit landing page copy across conversion dimensions |
| [ab-test-designer](skills/cro/ab-test-designer.md) | Design statistically sound A/B tests |
| [form-optimization-toolkit](skills/cro/form-optimization-toolkit.md) | Optimize web forms for completion rate and lead quality |
| [checkout-funnel-optimizer](skills/cro/checkout-funnel-optimizer.md) | Diagnose and fix e-commerce checkout abandonment |
| [cta-optimization-framework](skills/cro/cta-optimization-framework.md) | Optimize CTAs for click-through rate and conversion |
| [pricing-page-optimizer](skills/cro/pricing-page-optimizer.md) | Optimize pricing page layout, tiers, and conversion elements |
| [heatmap-analysis-toolkit](skills/cro/heatmap-analysis-toolkit.md) | Interpret heatmap and scroll map data for UX improvements |
| [social-proof-optimizer](skills/cro/social-proof-optimizer.md) | Optimize social proof elements (testimonials, reviews, badges) |
| [mobile-conversion-optimizer](skills/cro/mobile-conversion-optimizer.md) | Optimize mobile web experiences for conversion |

</details>

<details>
<summary><strong>Content — 13 skills</strong></summary>

| Skill | Description |
|---|---|
| [blog-outline-generator](skills/content/blog-outline-generator.md) | Create structured blog outlines with word count targets |
| [content-repurposer](skills/content/content-repurposer.md) | Turn long-form content into multi-channel assets |
| [editorial-calendar-builder](skills/content/editorial-calendar-builder.md) | Build editorial calendars with topics and deadlines |
| [blog-section-expander](skills/content/blog-section-expander.md) | Expand outline sections into polished copy |
| [campaign-brief-synthesizer](skills/content/campaign-brief-synthesizer.md) | Synthesize multi-stakeholder inputs into unified campaign briefs |
| [content-brief-writer](skills/content/content-brief-writer.md) | Write comprehensive content briefs for writers and agencies |
| [content-pillar-strategy](skills/content/content-pillar-strategy.md) | Build content pillar architectures for topical authority |
| [content-distribution-strategy](skills/content/content-distribution-strategy.md) | Plan multi-channel content distribution for maximum reach |
| [content-performance-scorecard](skills/content/content-performance-scorecard.md) | Score and rank content pieces by performance metrics |
| [content-localization-planner](skills/content/content-localization-planner.md) | Plan content localization for multi-market expansion |
| [content-governance-framework](skills/content/content-governance-framework.md) | Build content governance policies, workflows, and quality standards |
| [ugc-curation-strategy](skills/content/ugc-curation-strategy.md) | Curate and leverage user-generated content at scale |
| [content-personalization-engine](skills/content/content-personalization-engine.md) | Design content personalization strategies by segment and journey stage |

</details>

<details>
<summary><strong>PR & Events — 8 skills</strong></summary>

| Skill | Description |
|---|---|
| [press-release-writer](skills/pr-events/press-release-writer.md) | Write AP-style press releases |
| [event-logistics-coordinator](skills/pr-events/event-logistics-coordinator.md) | Create comprehensive event logistics plans |
| [event-attendee-matcher](skills/pr-events/event-attendee-matcher.md) | Match attendees to sessions, networking groups, and sales reps |
| [webinar-technical-runbook](skills/pr-events/webinar-technical-runbook.md) | Generate complete webinar runbooks with troubleshooting guides |
| [media-pitch-builder](skills/pr-events/media-pitch-builder.md) | Craft personalized media pitches with newsworthiness scoring |
| [crisis-comms-playbook](skills/pr-events/crisis-comms-playbook.md) | Build crisis communications plans with response frameworks |
| [event-roi-calculator](skills/pr-events/event-roi-calculator.md) | Calculate and optimize event ROI across all cost and revenue factors |
| [speaker-proposal-writer](skills/pr-events/speaker-proposal-writer.md) | Write compelling conference CFP submissions and speaking proposals |

</details>

<details>
<summary><strong>MarTech Ops — 9 skills</strong></summary>

| Skill | Description |
|---|---|
| [utm-tracking-manager](skills/martech-ops/utm-tracking-manager.md) | Generate UTM-tagged URLs with naming conventions |
| [brand-asset-compliance-checker](skills/martech-ops/brand-asset-compliance-checker.md) | Audit marketing assets against brand guidelines |
| [digital-asset-audit-report](skills/martech-ops/digital-asset-audit-report.md) | Audit DAM inventory for naming issues, duplicates, metadata gaps |
| [content-changelog-generator](skills/martech-ops/content-changelog-generator.md) | Compare document versions and generate change logs |
| [marketing-compliance-pre-checker](skills/martech-ops/marketing-compliance-pre-checker.md) | Pre-screen marketing content for FTC/FDA/CAN-SPAM compliance |
| [contract-clause-extractor](skills/martech-ops/contract-clause-extractor.md) | Extract and analyze key clauses from vendor contracts |
| [vendor-performance-scorecard](skills/martech-ops/vendor-performance-scorecard.md) | Score vendors across delivery, cost, quality, and strategic value |
| [sla-document-generator](skills/martech-ops/sla-document-generator.md) | Generate marketing-sales SLA documents |
| [approval-bottleneck-analyzer](skills/martech-ops/approval-bottleneck-analyzer.md) | Analyze approval cycle times to find bottlenecks |

</details>

<details>
<summary><strong>Video & Podcast — 10 skills</strong></summary>

| Skill | Description |
|---|---|
| [podcast-guest-research-brief](skills/video-podcast/podcast-guest-research-brief.md) | Research and prepare briefs for podcast guest interviews |
| [video-repurposing-engine](skills/video-podcast/video-repurposing-engine.md) | Repurpose long-form video/podcast content into multi-platform assets |
| [webinar-promotion-playbook](skills/video-podcast/webinar-promotion-playbook.md) | Plan and execute webinar promotion campaigns for max registration |
| [live-stream-engagement-toolkit](skills/video-podcast/live-stream-engagement-toolkit.md) | Plan and optimize live stream events for audience engagement |
| [video-analytics-interpreter](skills/video-podcast/video-analytics-interpreter.md) | Interpret video and podcast analytics for content optimization |

> *5 additional Video & Podcast skills in the [skills/video-podcast/](skills/video-podcast/) directory.*

</details>

<details>
<summary><strong>Growth — 9 skills</strong></summary>

| Skill | Description |
|---|---|
| [customer-persona-builder](skills/growth/customer-persona-builder.md) | Create buyer personas from research data |
| [growth-experiment-designer](skills/growth/growth-experiment-designer.md) | Design growth experiments with hypotheses, metrics, and analysis plans |
| [channel-mix-optimizer](skills/growth/channel-mix-optimizer.md) | Optimize marketing channel mix based on performance data |
| [onboarding-flow-optimizer](skills/growth/onboarding-flow-optimizer.md) | Optimize user onboarding flows for activation and retention |
| [viral-loop-designer](skills/growth/viral-loop-designer.md) | Design viral and referral loop mechanics for product growth |
| [retention-analysis-framework](skills/growth/retention-analysis-framework.md) | Analyze and improve user retention with cohort and behavioral data |
| [pricing-page-optimizer](skills/growth/pricing-page-optimizer.md) | Optimize pricing pages for conversion and revenue |
| [referral-program-designer](skills/growth/referral-program-designer.md) | Design referral programs with incentive structures and tracking |
| [gtm-launch-planner](skills/growth/gtm-launch-planner.md) | Plan go-to-market launches with timeline, channels, and messaging |

</details>

<details>
<summary><strong>Insights — 11 skills</strong></summary>

| Skill | Description |
|---|---|
| [voice-of-customer-miner](skills/insights/voice-of-customer-miner.md) | Extract customer insights from Reddit |
| [positioning-whitespace-finder](skills/insights/positioning-whitespace-finder.md) | Find unclaimed positioning territory |
| [hook-stress-tester](skills/insights/hook-stress-tester.md) | Score headlines and generate improved variants |
| [campaign-angle-generator](skills/insights/campaign-angle-generator.md) | Generate campaign angles across persuasion lenses |
| [win-loss-interview-analyzer](skills/insights/win-loss-interview-analyzer.md) | Analyze win/loss interview transcripts for patterns and recommendations |
| [competitor-messaging-tracker](skills/insights/competitor-messaging-tracker.md) | Track and analyze competitor messaging changes over time |
| [customer-journey-mapper](skills/insights/customer-journey-mapper.md) | Map customer journeys with touchpoints, emotions, and opportunities |
| [market-trend-scanner](skills/insights/market-trend-scanner.md) | Scan and analyze emerging market trends for strategic planning |
| [audience-persona-builder](skills/insights/audience-persona-builder.md) | Build data-driven audience personas from analytics and research |
| [survey-design-analyzer](skills/insights/survey-design-analyzer.md) | Design surveys and analyze response data for insights |
| [pricing-research-framework](skills/insights/pricing-research-framework.md) | Conduct pricing research with conjoint analysis and willingness-to-pay |

</details>

<details>
<summary><strong>AI Marketing — 7 skills</strong></summary>

| Skill | Description |
|---|---|
| [ai-content-generator](skills/ai-marketing/ai-content-generator.md) | Generate marketing content with AI prompt engineering best practices |
| [chatbot-conversation-designer](skills/ai-marketing/chatbot-conversation-designer.md) | Design chatbot conversation flows for marketing and support |
| [predictive-lead-scoring](skills/ai-marketing/predictive-lead-scoring.md) | Build predictive lead scoring models from behavioral data |
| [sentiment-analysis-monitor](skills/ai-marketing/sentiment-analysis-monitor.md) | Monitor and analyze brand sentiment across channels |
| [personalization-recommendation-engine](skills/ai-marketing/personalization-recommendation-engine.md) | Design product and content recommendation engines |
| [customer-segmentation-engine](skills/ai-marketing/customer-segmentation-engine.md) | Build data-driven customer segmentation models |
| [marketing-attribution-modeler](skills/ai-marketing/marketing-attribution-modeler.md) | Build multi-touch attribution models with AI/ML approaches |

</details>

<details>
<summary><strong>B2B & ABM — 6 skills</strong></summary>

| Skill | Description |
|---|---|
| [account-research-synthesizer](skills/b2b/account-research-synthesizer.md) | Synthesize firmographic and intent signals into account briefs |
| [buying-committee-mapper](skills/b2b/buying-committee-mapper.md) | Map buying committee roles, decision criteria, and engagement strategy |
| [sales-deck-assembler](skills/b2b/sales-deck-assembler.md) | Assemble customized sales presentations for specific prospects |
| [rfp-response-builder](skills/b2b/rfp-response-builder.md) | Generate structured RFP/RFI responses from product knowledge |
| [sales-content-usage-analyzer](skills/b2b/sales-content-usage-analyzer.md) | Analyze which sales content gets used and wins deals |
| [partner-co-marketing-planner](skills/b2b/partner-co-marketing-planner.md) | Plan co-marketing campaigns with partners for shared lead generation |

</details>

---

## Behind the Scenes

| Document | What It Covers |
|---|---|
| [Methodology](METHODOLOGY.md) | Our design philosophy — CSV-in/results-out architecture, 5 quality dimensions, why we chose no-API-key design |
| [Evaluation](EVALUATION.md) | The 5-dimension rubric every skill is tested against before shipping |
| [Contributing](CONTRIBUTING.md) | How to add your own skills to the collection |
| [Skill Template](SKILL-TEMPLATE.md) | The standard format all skills follow |

## Contributing

We welcome contributions! See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines and the [SKILL-TEMPLATE.md](SKILL-TEMPLATE.md) for the required format.

The granularity rule: **"One skill, one decision."** Each skill should help you make one specific marketing decision in a single Claude session.

## License

MIT — Use these skills however you want. Attribution appreciated but not required.

---

<p align="center"><strong>Built by <a href="https://github.com/CodeCoinCognitionLLC">CodeCoinCognition LLC</a></strong> — Making MarTech accessible to everyone.</p>
<p align="center">⭐ Star this repo if you find it useful — it helps others discover it.</p>
