---
name: campaign-performance-benchmarker
description: >
  Benchmark marketing campaign performance against industry standards and historical data to identify gaps.
  Use this skill when the user says "campaign benchmarking", "how do our metrics compare", "industry
  benchmark comparison", "are our email metrics good", "ad performance benchmarks", "benchmark our
  conversion rate", "marketing KPI benchmarks", "is our CTR good", "compare our metrics to industry",
  "campaign performance assessment", or "marketing metrics scorecard". Also trigger for channel
  performance benchmarking, competitive metric comparison, or marketing health check.
---

# Campaign Performance Benchmarker

Benchmarks marketing campaign performance against industry standards, historical data, and best-in-class metrics to identify gaps, validate performance, and prioritize optimization efforts.

## Granularity Check

> **Time**: ~5 min data prep → ~10 min Claude session → ~30-60 min building in Google Sheets / Looker / GA4. No implementation required unless acting on optimization recommendations. Input is campaign metrics and industry context. Output is Markdown benchmark report with gap analysis and prioritized improvements.

## User Intent Mapping

- "Are our email metrics good?" (email)
- "How does our ad CTR compare?" (ads)
- "Is our conversion rate competitive?" (conversion)
- "Marketing performance health check" (health check)
- "Benchmark our social media metrics" (social)
- "Industry average for [metric]" (lookup)
- "Compare our metrics to competitors" (competitive)
- "Marketing scorecard for leadership" (reporting)
- "Which channels are underperforming?" (diagnosis)
- "Are we spending too much per lead?" (efficiency)

[Content truncated for space - core framework includes benchmarks for email, paid ads, social media, website/SEO with severity classification and optimization prioritization framework]

## Output Contract

### Deliverable: Markdown Benchmark Report with Gap Analysis and Recommendations

Includes summary health assessment, channel-by-channel benchmarks, gap analysis, and optimization roadmap.

## Related Skills

- **ab-test-result-analyzer** (./ab-test-result-analyzer.md) — Test improvements for underperforming metrics; use A/B testing to validate optimization hypotheses identified through benchmarking.
- **budget-variance-analyzer** (./budget-variance-analyzer.md) — Compare budget allocation to benchmark performance; reallocate from underperforming to outperforming channels.
- **ad-performance-analyzer** (../ads/ad-performance-analyzer.md) — Deep-dive analysis into specific ad campaign performance; use benchmarking to identify which campaigns need optimization.
- **marketing-roi-calculator** (./marketing-roi-calculator.md) — Calculate true ROI per channel against benchmarks; understand if spend is justified by performance.
