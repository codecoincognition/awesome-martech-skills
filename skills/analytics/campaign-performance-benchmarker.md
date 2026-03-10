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

> **Session time**: ~5 min data gathering + ~10 min Claude session. No implementation required unless acting on optimization recommendations. Input is campaign metrics and industry context. Output is Markdown benchmark report with gap analysis and prioritized improvements.

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

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Campaign Metrics | Text/CSV | Current performance data (CTR, conversion rate, CPC, etc.) |
| Industry/Category | Text | Your industry or business type for benchmark comparison |
| Channels | Text | Which marketing channels to benchmark |

### If You Don't Have This Data

- **No campaign data?** Claude provides industry benchmarks for your sector and a measurement checklist to start tracking the right metrics.
- **Not sure which metrics matter?** Claude identifies the 5-7 key metrics for your business model and channel mix — not everything needs benchmarking.
- **Don't know your industry category?** Claude helps you identify the right benchmark category based on your product, audience, and sales model.
- **Only partial data?** Claude benchmarks what you have and recommends tracking for the metrics you're missing.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Historical Performance | CSV | Past campaign data for trend analysis |
| Competitor Data | Text | Known competitor metrics or industry reports |
| Budget | Text | Marketing spend for efficiency benchmarks |
| Goals | Text | Business targets for context |
| Segment Data | Text | Performance by audience, geography, or product |

## Process

### Step 1: Email Marketing Benchmarks

| Metric | All Industries | B2B | B2C | E-commerce | SaaS |
|---|---|---|---|---|---|
| Open rate | 20-25% | 22-28% | 18-22% | 15-20% | 25-30% |
| Click rate | 2.5-3.5% | 3-4% | 2-3% | 2-3% | 3-5% |
| Click-to-open rate | 10-15% | 12-16% | 10-14% | 10-13% | 13-18% |
| Unsubscribe rate | 0.1-0.3% | 0.1-0.2% | 0.2-0.4% | 0.2-0.3% | 0.1-0.2% |
| Bounce rate | 0.5-1.5% | 0.5-1.0% | 0.8-1.5% | 0.5-1.0% | 0.3-0.8% |
| List growth rate | 2-5%/mo | 3-5%/mo | 2-4%/mo | 2-3%/mo | 3-6%/mo |

### Step 2: Paid Advertising Benchmarks

| Metric | Google Search | Google Display | Facebook | LinkedIn | Instagram |
|---|---|---|---|---|---|
| CTR | 3-6% | 0.4-0.8% | 0.9-1.5% | 0.4-0.7% | 0.5-1.0% |
| CPC | $1-3 | $0.30-0.80 | $0.50-1.50 | $3-8 | $0.50-2.00 |
| Conversion rate | 3-6% | 0.5-1.5% | 1-3% | 2-5% | 0.5-2% |
| CPL (B2B) | $30-80 | $40-100 | $30-75 | $50-150 | $40-90 |
| CPL (B2C) | $15-40 | $10-30 | $10-30 | N/A | $15-35 |
| ROAS (e-commerce) | 4-8x | 1.5-3x | 2-5x | N/A | 2-4x |

### Step 3: Social Media Benchmarks

| Metric | LinkedIn | Instagram | Twitter/X | Facebook | TikTok |
|---|---|---|---|---|---|
| Engagement rate | 2-4% | 1-3% | 0.5-1.5% | 0.5-1.5% | 3-8% |
| Follower growth | 2-5%/mo | 1-3%/mo | 1-2%/mo | 0.5-1%/mo | 3-10%/mo |
| Post reach (organic) | 5-10% | 10-20% | 2-5% | 2-5% | 15-30% |
| Video view rate | 15-30% | 20-40% | 10-20% | 15-25% | 30-60% |
| Click rate | 1-3% | 0.5-1.5% | 0.5-1.5% | 0.5-1.0% | 1-2% |
| Best post frequency | 3-5x/week | 3-7x/week | 1-3x/day | 3-5x/week | 3-7x/week |

### Step 4: Website & SEO Benchmarks

| Metric | All Industries | B2B | B2C | E-commerce | SaaS |
|---|---|---|---|---|---|
| Organic traffic growth | 5-10%/yr | 8-15%/yr | 5-10%/yr | 5-8%/yr | 10-20%/yr |
| Bounce rate | 40-60% | 35-55% | 45-65% | 35-50% | 30-50% |
| Pages per session | 2-3 | 2-4 | 2-3 | 3-5 | 3-5 |
| Session duration | 2-3 min | 2-4 min | 1.5-3 min | 3-5 min | 3-6 min |
| Mobile traffic share | 55-70% | 40-55% | 65-80% | 60-75% | 35-50% |
| Page load time | < 3s | < 3s | < 2.5s | < 2s | < 3s |

### Step 5: Gap Analysis Framework

| Metric | Your Value | Benchmark | Gap | Severity | Priority |
|---|---|---|---|---|---|
| Email open rate | 15% | 22% | -32% | High | P1 |
| Google Ads CTR | 5.2% | 4.5% | +16% | Outperforming | Maintain |
| Social engagement | 0.8% | 2.5% | -68% | Critical | P0 |
| Website bounce | 62% | 45% | +38% | High | P1 |
| CPL | $120 | $65 | +85% | Critical | P0 |

Severity levels:
- **Outperforming**: Above benchmark — document what works, maintain
- **On track**: Within 10% of benchmark — minor optimizations
- **Below benchmark**: 10-30% gap — focused improvement needed
- **Critical gap**: 30%+ below benchmark — urgent attention required

### Step 6: Optimization Prioritization

| Priority | Criteria | Action |
|---|---|---|
| P0 — Fix immediately | Critical gap on high-spend or high-volume channel | Stop spending until fixed; reallocate budget |
| P1 — This quarter | Significant gap on important channel | Develop optimization plan; test improvements |
| P2 — Next quarter | Below benchmark on secondary channel | Add to backlog; address after P0/P1 |
| Maintain | Outperforming benchmarks | Document best practices; monitor for decline |
| Investigate | Metric seems wrong or lacks context | Verify data quality; gather more context |

### Confidence & Sample Size

> **Confidence Note**: Industry benchmarks are averages — top performers are typically 2-3x the average. Your benchmarks should evolve over time: once you beat industry average, benchmark against your own best performance and top-quartile peers. Benchmarks vary significantly by sub-industry, company size, audience maturity, and geographic market. Use benchmarks as directional guides, not absolute targets. A metric 20% below benchmark in a highly competitive niche may actually be strong performance.

### ⚠️ Human Checkpoint
> Validate that benchmark comparisons use the same metric definitions (e.g., "conversion" might mean different things). Ensure your data is clean — one tracking error can make all metrics look wrong. Context matters: a high CPL might be acceptable if deal sizes are also high.

> **Benchmark Context**: Companies that benchmark regularly and optimize based on gaps grow 15-20% faster than those that don't. The gap between average and top-quartile performers is typically 2-4x across most marketing metrics. Benchmarks shift over time — email open rates changed significantly after Apple Mail Privacy Protection (2021). Paid media benchmarks vary by season, with Q4 being 20-40% more expensive due to holiday competition.

## Output Contract

### Deliverable: Markdown Benchmark Report

```markdown
# Marketing Performance Benchmark: [Company]

## Summary
- Overall health: [strong/average/needs work]
- Top-performing channels: [list]
- Channels needing attention: [list]

## Channel Benchmarks
### Email
| Metric | Your Value | Benchmark | Gap | Status |
|---|---|---|---|---|

### Paid Advertising
| Metric | Your Value | Benchmark | Gap | Status |
|---|---|---|---|---|

### Social Media
| Metric | Your Value | Benchmark | Gap | Status |
|---|---|---|---|---|

### Website / SEO
| Metric | Your Value | Benchmark | Gap | Status |
|---|---|---|---|---|

## Gap Analysis
| Priority | Channel | Metric | Gap | Recommended Fix |
|---|---|---|---|---|

## Optimization Roadmap
| Timeline | Action | Channel | Expected Impact |
|---|---|---|---|

## Benchmarks Used
- Industry: [category]
- Source: [benchmark source]
- Date: [when benchmarks were published]
```

## Platform Implementation Steps

### Data Collection
1. Export email metrics from ESP (Mailchimp, HubSpot, Klaviyo)
2. Export ad metrics from Google Ads, Meta Ads Manager, LinkedIn Campaign Manager
3. Export social metrics from platform analytics or social management tool
4. Export website metrics from GA4
5. Compile all metrics into a single comparison spreadsheet

### Benchmark Sourcing
1. Use industry reports (HubSpot, Mailchimp, WordStream annual benchmarks)
2. Check platform-specific benchmarks (Google Ads Benchmark Tool, Meta Ads benchmarks)
3. Reference analyst reports for your specific industry
4. Track your own historical performance as internal benchmarks
5. Update benchmark references annually (benchmarks shift over time)

### Ongoing Monitoring
1. Create a monthly benchmark scorecard with automated data pulls
2. Highlight metrics that have moved significantly vs. benchmarks
3. Review with marketing team monthly to identify emerging issues
4. Update internal benchmarks quarterly based on your own performance
5. Share performance-vs-benchmark reports with leadership quarterly

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Wrong benchmarks used | Industry mismatch or outdated benchmarks | Verify benchmark source matches your business model and recency |
| Vanity metric focus | Benchmarking metrics that don't drive business outcomes | Focus on metrics that connect to revenue (CPL, ROAS, pipeline) |
| Benchmark obsession | Over-indexing on beating benchmarks vs. business goals | Use benchmarks for context, not as targets — business outcomes are the real goal |
| Apples-to-oranges | Comparing metrics with different definitions | Align metric definitions before comparing |

## How to Get Your Data

- **Email**: ESP → reports → campaign performance summary
- **Ads**: Google/Meta/LinkedIn → campaign reports → export key metrics
- **Social**: Platform analytics → export engagement and reach data
- **Website**: GA4 → reports → acquisition, engagement, conversion
- **All-in-one**: HubSpot or similar → marketing analytics → export performance dashboard
- **No data**: Tell Claude your industry and channels — get benchmark targets to work toward

## Example

**Input**: "Benchmark our B2B SaaS marketing. Email: 18% open rate, 2.1% click rate. Google Ads: 4.8% CTR, $65 CPC, 3.5% conversion rate. LinkedIn: 0.5% CTR, $12 CPC. Website: 48% bounce rate, 3.2 pages/session. Social: 1.2% LinkedIn engagement rate. Monthly spend: $45K across channels."

**Output**: Overall health: AVERAGE — two channels outperforming, two underperforming. Scorecard: (1) Email: BELOW BENCHMARK. Open rate 18% vs. 25-30% SaaS benchmark (-28%). Click rate 2.1% vs. 3-5% (-42%). Diagnosis: likely deliverability or subject line issues. Fix: audit deliverability (sender reputation, list hygiene), A/B test subject lines, segment sends. (2) Google Ads: OUTPERFORMING. CTR 4.8% (benchmark: 3-6%), conversion 3.5% (benchmark: 3-6%). CPC $65 is reasonable for B2B SaaS. Status: maintain; test new ad copy to push CTR higher. (3) LinkedIn Ads: ON TRACK. CTR 0.5% (benchmark: 0.4-0.7%). CPC $12 (benchmark: $3-8 — somewhat high). Fix: improve ad creative and targeting to reduce CPC while maintaining CTR. (4) Website: STRONG. Bounce rate 48% (benchmark: 30-50% SaaS). Pages/session 3.2 (benchmark: 3-5). Status: healthy; minor improvements possible. (5) Social engagement: BELOW BENCHMARK. LinkedIn 1.2% (benchmark: 2-4%). Fix: increase posting frequency, add polls and carousels, engage in comments. Priority: P0 — fix email (highest volume channel, biggest gap). P1 — improve LinkedIn ad CPC. P1 — boost social engagement. P2 — maintain Google Ads and website performance.
