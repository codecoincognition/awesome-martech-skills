---
name: market-trend-scanner
description: >
  Identify and analyze emerging market trends, consumer behavior shifts, and industry movements for strategic marketing decisions.
  Use this skill when the user says "market trend analysis", "emerging trends in our industry", "consumer behavior
  shifts", "market signal detection", "trend forecasting for marketing", "industry movement analysis",
  "what trends should we watch", "market opportunity scanning", "trend-based content strategy",
  "cultural trend mapping", or "trend impact assessment". Also trigger for macro trend analysis,
  micro trend detection, or trend-to-strategy translation.
---

# Market Trend Scanner

Identifies, analyzes, and translates emerging market trends into actionable marketing strategies through signal detection, impact assessment, and response planning.

## Granularity Check

> **Time**: ~10 min data prep → ~15 min Claude session → ~30-60 min synthesizing into your strategy deck. If implementing, add 2-4 hours for strategy development. Input is industry context and available trend data. Output is Markdown trend analysis with strategic recommendations.

## User Intent Mapping

- "What trends should we be watching?" (scanning)
- "How does [trend] affect our marketing?" (impact)
- "Consumer behavior changes in our market" (behavior)
- "Emerging trends for our industry" (industry)
- "Should we jump on this trend?" (evaluation)
- "Trend-based content opportunities" (content)
- "Market signals we're missing" (signals)
- "How to spot trends early" (detection)
- "Translate trends into marketing strategy" (strategy)
- "Cultural trends for our brand" (culture)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Industry/Market | Text | Your market, category, or vertical |
| Target Audience | Text | Who you serve (demographics, psychographics) |
| Business Context | Text | Your product/service and positioning |

### If You Don't Have This Data

- **Not sure which trends matter?** Claude scans for trends relevant to your industry and audience, then prioritizes by potential business impact.
- **No trend data sources?** Claude recommends free and paid sources for trend monitoring and helps set up a scanning routine.
- **Don't know how to act on trends?** Claude translates each identified trend into specific marketing actions (content, campaigns, positioning).
- **Too many trends, can't prioritize?** Claude scores trends by relevance, velocity, and business impact to identify the 3-5 that matter most.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Current Trends Watched | Text | Trends you're already tracking |
| Competitor Response | Text | How competitors are responding to trends |
| Historical Data | Text | Past trends that impacted your business |
| Data Sources | Text | Where you currently get trend information |
| Budget/Resources | Text | Capacity to respond to trends |

## Process

### Step 1: Trend Signal Sources
| Source Type | Examples | Signal Strength |
|---|---|---|
| Search data | Google Trends, keyword volume changes | Leading (3-6 months) |
| Social media | Hashtag velocity, conversation volume | Leading (1-3 months) |
| Industry reports | Gartner, Forrester, McKinsey | Confirming (0-6 months) |
| Patent filings | USPTO, Google Patents | Long-range (1-3 years) |
| VC funding | Crunchbase, PitchBook | Medium-range (6-18 months) |
| Job postings | LinkedIn, Indeed trend data | Medium-range (3-12 months) |
| Consumer surveys | Pew, Edelman, Statista | Confirming (0-3 months) |
| Academic research | Journals, conference papers | Long-range (2-5 years) |

### Step 2: Trend Classification
| Type | Timeframe | Examples |
|---|---|---|
| Micro-trend | 3-12 months | Specific product trends, social media formats |
| Macro-trend | 1-5 years | Technology adoption, consumer value shifts |
| Mega-trend | 5-20 years | Demographics, climate, urbanization |

### Step 3: Trend Evaluation Framework
| Criteria | Score 1-5 | Weight |
|---|---|---|
| Relevance to audience | How much does this affect your buyers? | 30% |
| Velocity | How fast is this trend growing? | 20% |
| Durability | Will this last or is it a fad? | 20% |
| Business alignment | Does this fit your brand and capabilities? | 20% |
| Competitive gap | Are competitors responding? | 10% |

### Step 4: Trend Impact Assessment
Per trend:
- **Opportunity**: What new marketing angles, content, or campaigns does this enable?
- **Threat**: What existing strategies does this make obsolete?
- **Audience impact**: How does this change buyer behavior, expectations, or decision criteria?
- **Channel impact**: Does this shift where or how to reach your audience?
- **Messaging impact**: Should your positioning or value proposition change?

### Step 5: Response Strategy
| Response Level | When | Example |
|---|---|---|
| Monitor only | Early signal, low relevance | Track in quarterly reviews |
| Content response | Confirmed trend, medium relevance | Blog posts, social content, thought leadership |
| Campaign response | Growing trend, high relevance | Trend-based campaign, new messaging angle |
| Strategic response | Macro trend, transforms market | Positioning shift, new product, new audience |
| First-mover play | Early trend, high alignment | Launch before competitors, own the narrative |

### Step 6: Ongoing Monitoring
- Set up Google Trends alerts for key terms
- Subscribe to industry trend reports (quarterly)
- Monitor social media conversation volume weekly
- Track competitor responses to trends monthly
- Quarterly trend review and strategy adjustment session

### Confidence & Sample Size

> **Confidence Note**: Trends are probabilistic, not certain. Most identified "trends" are actually noise — true trends show consistent growth across multiple signals and sources. The earlier you spot a trend, the less certain it is. Wait for 2-3 confirming signals before committing significant resources. Not every trend deserves a response — acting on too many trends dilutes your positioning and resources. The best trend strategy is being early on the 2-3 that matter most, not reacting to everything.

### ⚠️ Human Checkpoint
> Validate trend relevance with customer conversations before building campaigns around them. Quantitative signals (search volume, social mentions) should be confirmed with qualitative evidence (customer interviews, sales team insights). Be cautious of "trends" that are actually echo chambers within your professional bubble.

> **Benchmark Context**: See McKinsey 2024 State of AI Report for current industry benchmarks relevant to this analysis.
## Output Contract

### Deliverable: Markdown Trend Analysis

```markdown
# Market Trend Analysis: [Industry/Market]

## Trend Radar
| Trend | Type | Velocity | Relevance | Score | Response Level |
|---|---|---|---|---|---|

## Top Trends Deep Dive

### Trend 1: [Name]
- **Signal sources**: [where you see this]
- **Evidence**: [data points]
- **Audience impact**: [how it affects buyers]
- **Marketing opportunity**: [what to do]
- **Timeline**: [when to act]
- **Risk of inaction**: [what happens if you ignore it]

[Repeat for top 3-5 trends]

## Trend-to-Strategy Translation
| Trend | Content Play | Campaign Angle | Positioning Impact |
|---|---|---|---|

## Monitoring Plan
| Trend | Signal to Watch | Source | Review Cadence |
|---|---|---|---|

## Recommended Actions (Next 90 Days)
| Action | Trend | Owner | Timeline |
|---|---|---|---|
```

## Platform Implementation Steps

### Google Trends
1. Set up keyword alerts for your industry's core terms
2. Compare trend lines across related terms (identify emerging vs. declining)
3. Check geographic and seasonal patterns
4. Monitor "related queries" for emerging subtopics
5. Export data monthly for trend tracking spreadsheet

### Social Listening
1. Set up brand and industry keyword monitoring (Brandwatch, Sprout Social, or free: TweetDeck, Google Alerts)
2. Track conversation volume changes week-over-week
3. Monitor hashtag velocity and new hashtag emergence
4. Analyze sentiment shifts around key industry topics
5. Identify influential voices driving trend conversations

### Reporting
1. Create a quarterly trend report template
2. Include quantitative signals (search volume, social mentions) and qualitative evidence
3. Score each trend on the evaluation framework
4. Recommend response level and specific actions
5. Present to marketing team and leadership quarterly

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Chasing fads | Reacting to noise instead of trends | Require 2-3 confirming signals before acting |
| Missing real trends | Only monitoring familiar sources | Diversify signal sources; look outside your industry |
| Trend fatigue | Acting on too many trends at once | Prioritize ruthlessly; respond to max 2-3 per quarter |
| Late response | Identifying trend after competitors act | Improve monitoring cadence; set up automated alerts |

## How to Get Your Data

- **Search trends**: Google Trends → enter industry terms → export interest-over-time data
- **Social signals**: Social listening tool or manual hashtag tracking
- **Industry reports**: Subscribe to key analyst reports (many offer free summaries)
- **No data yet**: Describe your industry and audience — Claude identifies relevant trends from current knowledge

## Example

**Input**: "Market trend scan for a DTC skincare brand targeting millennial women. Currently sell through our website and Amazon. Main products: serums and moisturizers. Want to know what trends to act on in the next 6 months."

**Output**: Top 5 trends identified: (1) "Skin cycling" (micro-trend, high velocity): rotating active ingredients by night. Marketing play: educational content series on skin cycling with your products, position products as part of a skin cycling routine. Timeline: act now, trend peaking. (2) Ingredient transparency (macro-trend, growing): consumers demanding full ingredient disclosure and sourcing. Marketing play: ingredient storytelling content, "behind the formula" series, supply chain transparency page. Timeline: build over next quarter. (3) Microbiome skincare (macro-trend, early): gut-skin connection and probiotic skincare. Marketing play: thought leadership content now, product development exploration. Timeline: content in 60 days, product in 12-18 months. (4) "Skinimalism" (macro-trend, established): fewer products, simpler routines. Marketing play: position as quality-over-quantity; create "essentials only" bundles. Timeline: this quarter. (5) AI skin analysis (micro-trend, early): apps that recommend products from photos. Marketing play: consider AI quiz tool on website to recommend products. Timeline: Q3-Q4 evaluation. Recommended focus: (1) and (4) for immediate content and campaign response, (2) for ongoing brand strategy, (3) for long-term positioning.

## Related Skills

- **[Competitor Messaging Tracker](./competitor-messaging-tracker.md)** — Monitor how competitors are responding to identified trends.
- **[Campaign Angle Generator](./campaign-angle-generator.md)** — Generate trend-based campaign angles once trends are identified.
- **[Content Brief Writer](../content/content-brief-writer.md)** — Turn trend insights into content briefs for trend-based content strategy.
- **[Voice of Customer Miner](./voice-of-customer-miner.md)** — Validate market trends against actual customer discussions on Reddit.
