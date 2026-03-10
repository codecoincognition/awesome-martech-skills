# awesome-martech-skills

The definitive open-source collection of Marketing Technology skills for Claude Code & Claude Cowork.

**156 skills** across **15 categories** — from UTM tracking to attribution modeling, from email sequences to ad copy generation.

Built by [CodeCoinCognition LLC](https://github.com/CodeCoinCognitionLLC) and the community.

## Why This Exists

The MarTech landscape has 15,384+ tools (per Scott Brinker's 2025 Supergraphic), yet 75% of marketers cite disconnected data as their top pain point and nearly 50% of MarTech tools go unused. These skills bridge the gap — turning Claude into a marketing operations assistant that works with your existing tools via simple CSV exports.

## Quick Install

```bash
# Install a single skill
claude install skill path/to/skill.md

# Or clone the whole repo and point Claude at it
git clone https://github.com/CodeCoinCognitionLLC/awesome-martech-skills.git
```

## How It Works

1. **Export your data** from any marketing tool as CSV (each skill includes step-by-step export guides)
2. **Tell Claude what you need** in natural language (each skill has 10+ trigger phrases)
3. **Get actionable output** — HTML dashboards, XLSX reports, Markdown strategies, ready-to-use copy

No API keys. No MCP connectors. Just CSV in, results out.

## Skill Categories

| Category | Skills | Description |
|---|---|---|
| [SEO](skills/seo/) | 16 | Keyword research, technical audits, content briefs, SERP analysis |
| [Email](skills/email/) | 12 | Sequences, subject lines, deliverability, list management |
| [Social](skills/social/) | 13 | Content calendars, engagement analysis, short-form video, social commerce |
| [Ads](skills/ads/) | 13 | Google/Meta/LinkedIn ads, copy generation, budget optimization |
| [Analytics](skills/analytics/) | 11 | GA4 setup, dashboards, attribution, funnel analysis, cohort analysis |
| [CRM](skills/crm/) | 9 | Lead scoring, data hygiene, enrichment prioritization, lifecycle management |
| [CRO](skills/cro/) | 9 | A/B testing, landing pages, form optimization, friction detection |
| [Content](skills/content/) | 13 | Blog outlines, content repurposing, editorial calendars, SEO writing |
| [PR & Events](skills/pr-events/) | 8 | Press releases, media lists, event planning, crisis comms |
| [MarTech Ops](skills/martech-ops/) | 9 | UTM tracking, compliance, contracts, vendor scoring, SLA docs |
| [Video & Podcast](skills/video-podcast/) | 10 | Scripts, YouTube SEO, show notes, short-form video, webinar promotion |
| [Growth](skills/growth/) | 9 | Experiments, channel mix, personas, GTM planning, referral programs |
| [Insights](skills/insights/) | 11 | Voice of customer, win/loss analysis, competitive positioning, trend radar |
| [AI Marketing](skills/ai-marketing/) | 7 | AI image prompts, personalization, prompt libraries, content quality |
| [B2B & ABM](skills/b2b/) | 6 | Account research, buying committees, sales decks, RFP responses |

## Built Skills (156)

### Phase 1 — Foundation (15 skills)

| Skill | Category | Description |
|---|---|---|
| [keyword-cluster-analyzer](skills/seo/keyword-cluster-analyzer.md) | SEO | Cluster keywords by topic and search intent |
| [content-brief-generator](skills/seo/content-brief-generator.md) | SEO | Generate SEO content briefs from target keywords |
| [blog-outline-generator](skills/content/blog-outline-generator.md) | Content | Create structured blog outlines with word count targets |
| [utm-tracking-manager](skills/martech-ops/utm-tracking-manager.md) | MarTech Ops | Generate UTM-tagged URLs with naming conventions |
| [ga4-event-setup-guide](skills/analytics/ga4-event-setup-guide.md) | Analytics | Create GA4 event tracking implementation guides |
| [email-subject-line-tester](skills/email/email-subject-line-tester.md) | Email | Score subject lines on 6 dimensions + generate variants |
| [ad-copy-generator](skills/ads/ad-copy-generator.md) | Ads | Generate ad copy for Google/Meta/LinkedIn |
| [landing-page-optimizer](skills/cro/landing-page-optimizer.md) | CRO | Audit landing page copy across conversion dimensions |
| [ab-test-designer](skills/cro/ab-test-designer.md) | CRO | Design statistically sound A/B tests |
| [lead-scoring-model-builder](skills/crm/lead-scoring-model-builder.md) | CRM | Build points-based lead scoring from CRM data |
| [marketing-roi-calculator](skills/analytics/marketing-roi-calculator.md) | Analytics | Calculate ROI, ROAS, CAC, LTV across channels |
| [customer-persona-builder](skills/growth/customer-persona-builder.md) | Growth | Create buyer personas from research data |
| [social-content-calendar](skills/social/social-content-calendar.md) | Social | Plan monthly social media content calendars |
| [press-release-writer](skills/pr-events/press-release-writer.md) | PR & Events | Write AP-style press releases |
| [voice-of-customer-miner](skills/insights/voice-of-customer-miner.md) | Insights | Extract customer insights from Reddit |

### Phase 2 — Integration (15 skills)

| Skill | Category | Description |
|---|---|---|
| [content-gap-analyzer](skills/seo/content-gap-analyzer.md) | SEO | Find content gaps vs. competitors |
| [on-page-seo-auditor](skills/seo/on-page-seo-auditor.md) | SEO | Audit on-page SEO elements with scored report |
| [content-refresh-prioritizer](skills/seo/content-refresh-prioritizer.md) | SEO | Prioritize which content to update first |
| [content-repurposer](skills/content/content-repurposer.md) | Content | Turn long-form content into multi-channel assets |
| [editorial-calendar-builder](skills/content/editorial-calendar-builder.md) | Content | Build editorial calendars with topics and deadlines |
| [blog-section-expander](skills/content/blog-section-expander.md) | Content | Expand outline sections into polished copy |
| [email-sequence-builder](skills/email/email-sequence-builder.md) | Email | Design multi-step email sequences with timing and logic |
| [welcome-series-creator](skills/email/welcome-series-creator.md) | Email | Generate complete welcome email series |
| [google-ads-campaign-builder](skills/ads/google-ads-campaign-builder.md) | Ads | Structure Google Ads campaigns end-to-end |
| [landing-page-ad-matcher](skills/ads/landing-page-ad-matcher.md) | Ads | Audit ad-to-landing-page message alignment |
| [marketing-dashboard-builder](skills/analytics/marketing-dashboard-builder.md) | Analytics | Build interactive HTML marketing dashboards |
| [attribution-model-builder](skills/analytics/attribution-model-builder.md) | Analytics | Build and compare attribution models |
| [positioning-whitespace-finder](skills/insights/positioning-whitespace-finder.md) | Insights | Find unclaimed positioning territory |
| [hook-stress-tester](skills/insights/hook-stress-tester.md) | Insights | Score headlines and generate improved variants |
| [campaign-angle-generator](skills/insights/campaign-angle-generator.md) | Insights | Generate campaign angles across persuasion lenses |

### Phase 3 — Expansion (22 skills)

| Skill | Category | Description |
|---|---|---|
| [brand-asset-compliance-checker](skills/martech-ops/brand-asset-compliance-checker.md) | MarTech Ops | Audit marketing assets against brand guidelines |
| [digital-asset-audit-report](skills/martech-ops/digital-asset-audit-report.md) | MarTech Ops | Audit DAM inventory for naming issues, duplicates, metadata gaps |
| [content-changelog-generator](skills/martech-ops/content-changelog-generator.md) | MarTech Ops | Compare document versions and generate change logs |
| [marketing-compliance-pre-checker](skills/martech-ops/marketing-compliance-pre-checker.md) | MarTech Ops | Pre-screen marketing content for FTC/FDA/CAN-SPAM compliance |
| [contract-clause-extractor](skills/martech-ops/contract-clause-extractor.md) | MarTech Ops | Extract and analyze key clauses from vendor contracts |
| [vendor-performance-scorecard](skills/martech-ops/vendor-performance-scorecard.md) | MarTech Ops | Score vendors across delivery, cost, quality, and strategic value |
| [sla-document-generator](skills/martech-ops/sla-document-generator.md) | MarTech Ops | Generate marketing-sales SLA documents |
| [approval-bottleneck-analyzer](skills/martech-ops/approval-bottleneck-analyzer.md) | MarTech Ops | Analyze approval cycle times to find bottlenecks |
| [crm-data-hygiene-auditor](skills/crm/crm-data-hygiene-auditor.md) | CRM | Audit CRM data for duplicates, stale records, and formatting issues |
| [data-enrichment-prioritizer](skills/crm/data-enrichment-prioritizer.md) | CRM | Prioritize which CRM records to enrich first |
| [account-research-synthesizer](skills/b2b/account-research-synthesizer.md) | B2B & ABM | Synthesize firmographic and intent signals into account briefs |
| [buying-committee-mapper](skills/b2b/buying-committee-mapper.md) | B2B & ABM | Map buying committee roles, decision criteria, and engagement strategy |
| [sales-deck-assembler](skills/b2b/sales-deck-assembler.md) | B2B & ABM | Assemble customized sales presentations for specific prospects |
| [rfp-response-builder](skills/b2b/rfp-response-builder.md) | B2B & ABM | Generate structured RFP/RFI responses from product knowledge |
| [sales-content-usage-analyzer](skills/b2b/sales-content-usage-analyzer.md) | B2B & ABM | Analyze which sales content gets used and wins deals |
| [event-logistics-coordinator](skills/pr-events/event-logistics-coordinator.md) | PR & Events | Create comprehensive event logistics plans |
| [event-attendee-matcher](skills/pr-events/event-attendee-matcher.md) | PR & Events | Match attendees to sessions, networking groups, and sales reps |
| [webinar-technical-runbook](skills/pr-events/webinar-technical-runbook.md) | PR & Events | Generate complete webinar runbooks with troubleshooting guides |
| [budget-variance-analyzer](skills/analytics/budget-variance-analyzer.md) | Analytics | Compare planned vs. actual marketing spend with root cause analysis |
| [dashboard-requirement-gatherer](skills/analytics/dashboard-requirement-gatherer.md) | Analytics | Gather KPI definitions and data sources for dashboard builds |
| [campaign-brief-synthesizer](skills/content/campaign-brief-synthesizer.md) | Content | Synthesize multi-stakeholder inputs into unified campaign briefs |
| [win-loss-interview-analyzer](skills/insights/win-loss-interview-analyzer.md) | Insights | Analyze win/loss interview transcripts for patterns and recommendations |

### Phase 4 — Full Expansion (99 skills)

#### SEO (11 new)

| Skill | Description |
|---|---|
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

#### Email (6 new)

| Skill | Description |
|---|---|
| [email-deliverability-auditor](skills/email/email-deliverability-auditor.md) | Diagnose and fix email deliverability issues (SPF, DKIM, reputation) |
| [email-list-segmentation](skills/email/email-list-segmentation.md) | Build behavioral and demographic email segments |
| [email-template-designer](skills/email/email-template-designer.md) | Design responsive email templates with HTML/CSS best practices |
| [email-performance-analyzer](skills/email/email-performance-analyzer.md) | Analyze email campaign metrics and identify optimization opportunities |
| [email-copywriting-framework](skills/email/email-copywriting-framework.md) | Write high-converting email copy by type (promo, nurture, re-engage) |
| [email-ab-testing-framework](skills/email/email-ab-testing-framework.md) | Design and analyze email A/B tests with statistical rigor |
| [email-compliance-checker](skills/email/email-compliance-checker.md) | Audit emails for CAN-SPAM, GDPR, and CASL compliance |
| [email-automation-workflow](skills/email/email-automation-workflow.md) | Design triggered email automation workflows with branching logic |
| [transactional-email-optimizer](skills/email/transactional-email-optimizer.md) | Optimize transactional emails for engagement and brand consistency |

#### Social (9 new)

| Skill | Description |
|---|---|
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

#### Ads (10 new)

| Skill | Description |
|---|---|
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

#### Content (7 new)

| Skill | Description |
|---|---|
| [content-brief-writer](skills/content/content-brief-writer.md) | Write comprehensive content briefs for writers and agencies |
| [content-pillar-strategy](skills/content/content-pillar-strategy.md) | Build content pillar architectures for topical authority |
| [content-distribution-strategy](skills/content/content-distribution-strategy.md) | Plan multi-channel content distribution for maximum reach |
| [content-performance-scorecard](skills/content/content-performance-scorecard.md) | Score and rank content pieces by performance metrics |
| [content-localization-planner](skills/content/content-localization-planner.md) | Plan content localization for multi-market expansion |
| [content-governance-framework](skills/content/content-governance-framework.md) | Build content governance policies, workflows, and quality standards |
| [ugc-curation-strategy](skills/content/ugc-curation-strategy.md) | Curate and leverage user-generated content at scale |
| [content-personalization-engine](skills/content/content-personalization-engine.md) | Design content personalization strategies by segment and journey stage |

#### AI Marketing (7 new)

| Skill | Description |
|---|---|
| [ai-content-generator](skills/ai-marketing/ai-content-generator.md) | Generate marketing content with AI prompt engineering best practices |
| [chatbot-conversation-designer](skills/ai-marketing/chatbot-conversation-designer.md) | Design chatbot conversation flows for marketing and support |
| [predictive-lead-scoring](skills/ai-marketing/predictive-lead-scoring.md) | Build predictive lead scoring models from behavioral data |
| [sentiment-analysis-monitor](skills/ai-marketing/sentiment-analysis-monitor.md) | Monitor and analyze brand sentiment across channels |
| [personalization-recommendation-engine](skills/ai-marketing/personalization-recommendation-engine.md) | Design product and content recommendation engines |
| [customer-segmentation-engine](skills/ai-marketing/customer-segmentation-engine.md) | Build data-driven customer segmentation models |
| [marketing-attribution-modeler](skills/ai-marketing/marketing-attribution-modeler.md) | Build multi-touch attribution models with AI/ML approaches |

#### Growth (8 new)

| Skill | Description |
|---|---|
| [growth-experiment-designer](skills/growth/growth-experiment-designer.md) | Design growth experiments with hypotheses, metrics, and analysis plans |
| [channel-mix-optimizer](skills/growth/channel-mix-optimizer.md) | Optimize marketing channel mix based on performance data |
| [onboarding-flow-optimizer](skills/growth/onboarding-flow-optimizer.md) | Optimize user onboarding flows for activation and retention |
| [viral-loop-designer](skills/growth/viral-loop-designer.md) | Design viral and referral loop mechanics for product growth |
| [retention-analysis-framework](skills/growth/retention-analysis-framework.md) | Analyze and improve user retention with cohort and behavioral data |
| [pricing-page-optimizer](skills/growth/pricing-page-optimizer.md) | Optimize pricing pages for conversion and revenue |
| [referral-program-designer](skills/growth/referral-program-designer.md) | Design referral programs with incentive structures and tracking |
| [gtm-launch-planner](skills/growth/gtm-launch-planner.md) | Plan go-to-market launches with timeline, channels, and messaging |

#### CRO (7 new)

| Skill | Description |
|---|---|
| [form-optimization-toolkit](skills/cro/form-optimization-toolkit.md) | Optimize web forms for completion rate and lead quality |
| [checkout-funnel-optimizer](skills/cro/checkout-funnel-optimizer.md) | Diagnose and fix e-commerce checkout abandonment |
| [cta-optimization-framework](skills/cro/cta-optimization-framework.md) | Optimize CTAs for click-through rate and conversion |
| [pricing-page-optimizer](skills/cro/pricing-page-optimizer.md) | Optimize pricing page layout, tiers, and conversion elements |
| [heatmap-analysis-toolkit](skills/cro/heatmap-analysis-toolkit.md) | Interpret heatmap and scroll map data for UX improvements |
| [social-proof-optimizer](skills/cro/social-proof-optimizer.md) | Optimize social proof elements (testimonials, reviews, badges) |
| [mobile-conversion-optimizer](skills/cro/mobile-conversion-optimizer.md) | Optimize mobile web experiences for conversion |

#### Insights (6 new)

| Skill | Description |
|---|---|
| [competitor-messaging-tracker](skills/insights/competitor-messaging-tracker.md) | Track and analyze competitor messaging changes over time |
| [customer-journey-mapper](skills/insights/customer-journey-mapper.md) | Map customer journeys with touchpoints, emotions, and opportunities |
| [market-trend-scanner](skills/insights/market-trend-scanner.md) | Scan and analyze emerging market trends for strategic planning |
| [audience-persona-builder](skills/insights/audience-persona-builder.md) | Build data-driven audience personas from analytics and research |
| [survey-design-analyzer](skills/insights/survey-design-analyzer.md) | Design surveys and analyze response data for insights |
| [pricing-research-framework](skills/insights/pricing-research-framework.md) | Conduct pricing research with conjoint analysis and willingness-to-pay |

#### CRM (6 new)

| Skill | Description |
|---|---|
| [lifecycle-stage-designer](skills/crm/lifecycle-stage-designer.md) | Design customer lifecycle stages with transition criteria |
| [segmentation-rule-builder](skills/crm/segmentation-rule-builder.md) | Build CRM segmentation rules for targeted marketing |
| [automation-workflow-designer](skills/crm/automation-workflow-designer.md) | Design CRM automation workflows with triggers and branching |
| [churn-prediction-framework](skills/crm/churn-prediction-framework.md) | Build churn prediction frameworks from CRM behavioral data |
| [customer-onboarding-optimizer](skills/crm/customer-onboarding-optimizer.md) | Optimize customer onboarding sequences for activation |
| [reporting-dashboard-designer](skills/crm/reporting-dashboard-designer.md) | Design CRM reporting dashboards with KPIs and drill-downs |

#### Video & Podcast (5 new)

| Skill | Description |
|---|---|
| [podcast-guest-research-brief](skills/video-podcast/podcast-guest-research-brief.md) | Research and prepare briefs for podcast guest interviews |
| [video-repurposing-engine](skills/video-podcast/video-repurposing-engine.md) | Repurpose long-form video/podcast content into multi-platform assets |
| [webinar-promotion-playbook](skills/video-podcast/webinar-promotion-playbook.md) | Plan and execute webinar promotion campaigns for max registration |
| [live-stream-engagement-toolkit](skills/video-podcast/live-stream-engagement-toolkit.md) | Plan and optimize live stream events for audience engagement |
| [video-analytics-interpreter](skills/video-podcast/video-analytics-interpreter.md) | Interpret video and podcast analytics for content optimization |

#### Analytics (5 new)

| Skill | Description |
|---|---|
| [cohort-analysis-builder](skills/analytics/cohort-analysis-builder.md) | Build cohort analyses for retention, revenue, and LTV tracking |
| [marketing-mix-modeler](skills/analytics/marketing-mix-modeler.md) | Model marketing channel contributions and optimize budget allocation |
| [funnel-drop-off-analyzer](skills/analytics/funnel-drop-off-analyzer.md) | Diagnose conversion funnel drop-offs with root cause analysis |
| [ab-test-result-analyzer](skills/analytics/ab-test-result-analyzer.md) | Analyze A/B test results with statistical significance assessment |
| [campaign-performance-benchmarker](skills/analytics/campaign-performance-benchmarker.md) | Benchmark campaign performance against industry standards |

#### PR & Events (4 new)

| Skill | Description |
|---|---|
| [media-pitch-builder](skills/pr-events/media-pitch-builder.md) | Craft personalized media pitches with newsworthiness scoring |
| [crisis-comms-playbook](skills/pr-events/crisis-comms-playbook.md) | Build crisis communications plans with response frameworks |
| [event-roi-calculator](skills/pr-events/event-roi-calculator.md) | Calculate and optimize event ROI across all cost and revenue factors |
| [speaker-proposal-writer](skills/pr-events/speaker-proposal-writer.md) | Write compelling conference CFP submissions and speaking proposals |

#### B2B & ABM (1 new)

| Skill | Description |
|---|---|
| [partner-co-marketing-planner](skills/b2b/partner-co-marketing-planner.md) | Plan co-marketing campaigns with partners for shared lead generation |

### Quality Revision v1

All 57 skills received 5 universal quality improvements based on expert review:

1. **Honest time estimates** — Replaced "10-minute session" with realistic prep + session + implementation times
2. **Data fallbacks** — Added "If You Don't Have This Data" section with workarounds for every required input
3. **Confidence disclaimers** — Added sample size and statistical confidence notes
4. **Benchmark context** — Added quantitative industry benchmarks (CTR, conversion rates, etc.)
5. **Platform implementation steps** — Added step-by-step instructions for implementing outputs in real tools

## Workflow Chains

Skills are designed to chain together. Pre-built workflows in the [workflows/](workflows/) directory connect skills into complete marketing processes with decision gates at each step.

| Workflow | Skills Chained | Use Case |
|---|---|---|
| [SEO Content Flywheel](workflows/seo-content-flywheel.md) | 5 | keyword research → brief → outline → write → optimize |
| [Content Engine](workflows/content-engine.md) | 6 | keywords → gaps → brief → outline → expand → SEO audit |
| [Paid Acquisition](workflows/paid-acquisition.md) | 5 | personas → campaign → ad copy → landing page → A/B test |
| [Brand Positioning](workflows/brand-positioning.md) | 4 | VoC research → whitespace → narrative → campaign angles |

## Quality Standard

Every skill is evaluated on a 5-dimension rubric (see [EVALUATION.md](EVALUATION.md)):

- **Trigger Accuracy** — Does it activate on the right prompts?
- **Output Quality** — Is the output production-ready?
- **Input Validation** — Does it handle bad data gracefully?
- **Completeness** — Does it deliver everything promised?
- **Usability** — Can a non-technical marketer use it on first try?

Minimum bar: 3/5 on all dimensions before a skill ships.

## Contributing

We welcome contributions! See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines, the [SKILL-TEMPLATE.md](SKILL-TEMPLATE.md) for the required format, and the granularity check rule: **"Can this be completed in a single 10-minute Claude session?"**

## License

MIT — Use these skills however you want. Attribution appreciated but not required.

---

*Built by CodeCoinCognition LLC — Making MarTech accessible to everyone.*
