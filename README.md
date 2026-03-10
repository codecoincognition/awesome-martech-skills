# awesome-martech-skills

The definitive open-source collection of Marketing Technology skills for Claude Code & Claude Cowork.

**148 skills** across **15 categories** — from UTM tracking to attribution modeling, from email sequences to ad copy generation.

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
| [SEO](skills/seo/) | 14 | Keyword research, technical audits, content briefs, SERP analysis |
| [Email](skills/email/) | 11 | Sequences, subject lines, deliverability, list management |
| [Social](skills/social/) | 12 | Content calendars, engagement analysis, short-form video, social commerce |
| [Ads](skills/ads/) | 12 | Google/Meta/LinkedIn ads, copy generation, budget optimization |
| [Analytics](skills/analytics/) | 10 | GA4 setup, dashboards, attribution, funnel analysis |
| [CRM](skills/crm/) | 9 | Lead scoring, data hygiene, enrichment prioritization, lifecycle management |
| [CRO](skills/cro/) | 9 | A/B testing, landing pages, form optimization, friction detection |
| [Content](skills/content/) | 12 | Blog outlines, content repurposing, editorial calendars, SEO writing |
| [PR & Events](skills/pr-events/) | 8 | Press releases, media lists, event planning, crisis comms |
| [MarTech Ops](skills/martech-ops/) | 9 | UTM tracking, compliance, contracts, vendor scoring, SLA docs |
| [Video & Podcast](skills/video-podcast/) | 10 | Scripts, YouTube SEO, show notes, short-form video |
| [Growth](skills/growth/) | 9 | Experiments, channel mix, personas, GTM planning, referral programs |
| [Insights](skills/insights/) | 11 | Voice of customer, win/loss analysis, competitive positioning, trend radar |
| [AI Marketing](skills/ai-marketing/) | 7 | AI image prompts, personalization, prompt libraries, content quality |
| [B2B & ABM](skills/b2b/) | 6 | Account research, buying committees, sales decks, RFP responses |

## Built Skills (57)

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

### Phase 4 — Video & Podcast (5 skills)

| Skill | Category | Description |
|---|---|---|
| [video-script-writer](skills/video-podcast/video-script-writer.md) | Video & Podcast | Write structured video scripts with hooks, segments, CTAs, and timing |
| [youtube-seo-optimizer](skills/video-podcast/youtube-seo-optimizer.md) | Video & Podcast | Optimize YouTube titles, descriptions, tags, and chapters for search |
| [podcast-show-notes-generator](skills/video-podcast/podcast-show-notes-generator.md) | Video & Podcast | Generate show notes with timestamps, takeaways, and SEO descriptions |
| [short-form-video-planner](skills/video-podcast/short-form-video-planner.md) | Video & Podcast | Plan TikTok, Reels, and Shorts content calendars with scripts |
| [video-thumbnail-concept-generator](skills/video-podcast/video-thumbnail-concept-generator.md) | Video & Podcast | Generate thumbnail design briefs with layout, text, and A/B variants |

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
