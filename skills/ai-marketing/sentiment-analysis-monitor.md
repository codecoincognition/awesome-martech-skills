---
name: sentiment-analysis-monitor
description: >
  Monitor and analyze brand sentiment across social media, reviews, and customer feedback channels.
  Use this skill when the user says "sentiment analysis", "brand sentiment monitoring", "social
  listening analysis", "customer sentiment report", "review sentiment analysis", "brand perception
  tracking", "NPS sentiment analysis", "voice of customer analysis", "sentiment trend report",
  "reputation monitoring", or "what are customers saying about us". Also trigger for competitive
  sentiment comparison, crisis sentiment tracking, or product launch sentiment analysis.
---

# Sentiment Analysis Monitor

Monitors and analyzes brand sentiment across social media, reviews, support tickets, and customer feedback to identify trends, detect issues early, and inform marketing strategy.

## Granularity Check

> **Session time**: ~5 min data prep + ~10 min Claude session. If implementing monitoring, add 1-2 days for tool setup. Input is customer feedback data from any channel. Output is Markdown sentiment analysis with trends and recommendations.

## User Intent Mapping

- "What's customer sentiment about our brand?" (brand health)
- "Analyze our reviews for sentiment patterns" (review analysis)
- "Social media sentiment report" (social)
- "Customer feedback sentiment analysis" (feedback)
- "Sentiment trends over time" (trends)
- "Compare our sentiment to competitors" (competitive)
- "Product launch sentiment monitoring" (launch)
- "Negative sentiment is increasing — why?" (diagnosis)
- "Voice of customer analysis" (VoC)
- "Brand reputation monitoring setup" (monitoring)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Feedback Data | CSV/Text | Reviews, social mentions, survey responses, support tickets |
| Analysis Scope | Text | Brand-wide, product-specific, campaign-specific |
| Time Period | Text | Reporting period and comparison period |

### If You Don't Have This Data

- **No aggregated data?** Paste in reviews from G2, Trustpilot, App Store, or social media posts. Claude analyzes whatever you have.
- **No monitoring tool?** Claude recommends setup and provides manual analysis of pasted data.
- **No historical baseline?** This analysis becomes your baseline. Claude sets up tracking recommendations for trend comparison.
- **Limited feedback volume?** Claude works with as few as 20-30 feedback items. More data = more reliable themes.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Competitor Reviews | CSV/Text | Competitor feedback for comparison |
| NPS Data | CSV | NPS scores with verbatim comments |
| Support Tickets | CSV | Customer support interactions |
| Product Changes | Text | Recent launches, updates, or issues |
| Marketing Campaigns | Text | Active campaigns that may drive sentiment |

## Process

### Step 1: Sentiment Classification
| Category | Definition | Indicators |
|---|---|---|
| Positive | Expressing satisfaction, recommendation | "Love", "great", "recommend", high ratings |
| Neutral | Factual, no strong emotion | Descriptions, questions, neutral statements |
| Negative | Expressing dissatisfaction, complaints | "Disappointed", "terrible", "frustrating", low ratings |
| Mixed | Both positive and negative elements | "Love the product but hate the price" |

### Step 2: Theme Extraction
- Identify recurring topics (product quality, customer service, pricing, UX, etc.)
- Map sentiment by theme (users might love the product but hate support)
- Quantify theme frequency (how many mentions per theme)
- Track theme sentiment trends (improving, declining, stable)
- Identify emerging themes (new topics gaining mentions)

### Step 3: Trend Analysis
- Overall sentiment score over time (positive %)
- Sentiment by channel (social vs. reviews vs. support)
- Sentiment by product/feature/campaign
- Correlation with business events (launches, outages, price changes)
- Competitor sentiment comparison

### Step 4: Insight Generation
- Most praised aspects (double down on these in marketing)
- Most criticized aspects (fix or address proactively)
- Sentiment drivers (what moves sentiment most)
- Audience-specific sentiment (power users vs. new users)
- Competitive sentiment gaps (where competitors are praised/criticized)

### Step 5: Action Recommendations
| Finding | Impact | Action | Owner |
|---|---|---|---|
| Product feature frequently praised | Marketing opportunity | Feature in campaigns and website | Marketing |
| Support response time criticized | Retention risk | Improve SLA, add self-serve options | Support |
| Competitor weakness identified | Competitive advantage | Create comparison content | Content |
| Pricing concerns emerging | Revenue risk | Review pricing communication | Product/Marketing |

### Step 6: Monitoring Setup
- Real-time alerts for sentiment spikes (positive or negative)
- Daily digest of key mentions and sentiment summary
- Weekly sentiment scorecard (trends, themes, actions)
- Monthly deep-dive sentiment report with strategic recommendations
- Crisis detection: alert when negative sentiment exceeds threshold

### Confidence & Sample Size

> **Confidence Note**: Sentiment analysis accuracy depends on volume and context. Sarcasm and industry jargon can confuse automated tools. For reliable trend analysis, you need 50+ feedback items per period. Single reviews or social posts don't represent overall sentiment — look for patterns. Sentiment varies naturally by channel — support channels skew negative, social can skew positive (survivorship bias of engaged users).

### ⚠️ Human Checkpoint
> Review sentiment classification for accuracy — automated tools misclassify 15-25% of complex sentiment. Verify that negative themes are escalated appropriately. Check that competitor analysis uses comparable data sources.

> **Benchmark Context**: Companies that actively monitor sentiment reduce churn by 15-25%. Negative reviews cost businesses 22% of potential customers when 1 negative article is found. 4+ stars is the minimum threshold for most consumers. Responding to negative reviews increases customer advocacy by 25%. 95% of unhappy customers will return if their issue is resolved quickly. Brand sentiment impacts stock price by up to 30% for publicly traded companies.

## Output Contract

### Deliverable: Markdown Sentiment Report

```markdown
# Sentiment Analysis: [Brand/Product] — [Period]

## Executive Summary
- Overall sentiment: [positive/neutral/negative] ([score])
- Trend: [improving/stable/declining] vs. previous period
- Key highlight: [most positive finding]
- Key concern: [most negative finding]

## Sentiment Distribution
| Sentiment | Count | Percentage | Change |
|---|---|---|---|

## Theme Analysis
| Theme | Mentions | Sentiment | Trend | Action |
|---|---|---|---|---|

## Top Positive Themes
1. [Theme]: [insight with example quotes]

## Top Negative Themes
1. [Theme]: [insight with example quotes]

## Channel Comparison
| Channel | Volume | Positive % | Negative % | Key Theme |
|---|---|---|---|---|

## Competitive Sentiment
| Brand | Overall | Strengths | Weaknesses |
|---|---|---|---|

## Recommendations
| Priority | Action | Expected Impact | Owner |
|---|---|---|---|

## Monitoring Alerts
| Alert | Trigger | Escalation |
|---|---|---|
```

## Platform Implementation Steps

### Social Listening Tools
1. Set up brand monitoring in Sprout Social, Brandwatch, or Mention
2. Configure sentiment classification rules and keyword tracking
3. Create alerts for sentiment volume spikes (>2x normal volume)
4. Build automated sentiment dashboards and email reports

### Review Monitoring
1. Claim and monitor profiles on G2, Trustpilot, App Store, Google Reviews
2. Set up review notifications for new reviews across platforms
3. Create response templates for positive, neutral, and negative reviews
4. Track review sentiment trends monthly

### Customer Feedback
1. Aggregate NPS/CSAT verbatims with scores for sentiment correlation
2. Tag support tickets by topic and sentiment
3. Analyze survey open-ended responses for themes
4. Build quarterly Voice of Customer report combining all sources

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Inaccurate sentiment classification | Sarcasm, context misread by tools | Add human review layer; train custom classification for your domain |
| Alert fatigue | Too many alerts, threshold too low | Raise alert thresholds; prioritize by volume and severity |
| No action on insights | Reports generated but not acted upon | Assign action owners; track resolution in sprint/project tools |
| Biased sample | Only monitoring one channel | Aggregate across social, reviews, support, surveys for full picture |

## How to Get Your Data

- **Reviews**: Export from G2, Trustpilot, App Store, Google Reviews (most platforms have export or API)
- **Social mentions**: Social listening tool → export mentions with sentiment tags
- **NPS/Survey**: Survey platform → export responses with scores
- **Support tickets**: Help desk → export tickets with tags and resolution status
- **No tools**: Manually collect 30-50 recent reviews or social mentions — Claude analyzes themes and sentiment

## Example

**Input**: "Sentiment analysis for our SaaS project management tool. Have 200 G2 reviews (avg 4.2 stars), 50 App Store reviews (avg 3.8 stars), and last quarter's NPS verbatims (NPS score: 42). Want to understand what drives positive and negative sentiment."

**Output**: Overall sentiment: 68% positive, 22% neutral, 10% negative. Positive themes: (1) "Easy to use" (mentioned in 45% of positive reviews) — users consistently praise onboarding and UI simplicity. (2) "Great collaboration features" (30%) — real-time collaboration cited as competitive advantage. (3) "Responsive support" (20%) — support team NPS significantly higher than product NPS. Negative themes: (1) "Mobile app limitations" (40% of negative reviews) — G2 4.2 vs. App Store 3.8 gap explained by mobile-specific frustrations: slow load, missing features, sync issues. (2) "Reporting is basic" (25% of negative) — power users need advanced custom reports, currently switching to BI tools. (3) "Pricing concerns" (15% of negative) — mid-tier plan perceived as expensive vs. competitors for small teams. Recommendations: (1) URGENT — mobile app investment (driving 40% of negative sentiment; fixing would lift App Store to 4.3+). (2) HIGH — add 3-5 most-requested report templates (addresses #2 negative theme with moderate effort). (3) MEDIUM — promote "easy to use" in marketing (biggest positive theme underused in positioning). Competitive insight: competitors are praised for reporting but criticized for complexity — your simplicity is a genuine differentiator. Monitoring setup: weekly sentiment digest, alert when negative reviews exceed 3/week (crisis threshold).
