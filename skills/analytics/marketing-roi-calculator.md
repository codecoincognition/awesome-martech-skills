---
name: Marketing ROI Calculator
description: "Calculate your marketing performance metrics instantly. Need to understand ROI across channels? Want to find your true customer acquisition cost? Curious about ROAS by platform? Struggling to justify marketing spend? Need budget reallocation recommendations? Analyze your CAC vs LTV? Looking for break-even analysis? Calculate blended metrics across campaigns? Find underperforming channels? Need competitive channel benchmarking? This skill calculates ROI, ROAS, CAC, LTV, break-even points, and generates budget optimization recommendations from your ad spend and revenue data."
---

## User Intent Mapping

| User Says | Underlying Need |
|-----------|-----------------|
| "How's my marketing performing?" | Calculate ROI, ROAS, and channel comparison |
| "Which channels waste my budget?" | Identify underperforming channels, break-even analysis |
| "What's my real customer cost?" | Calculate CAC and CAC payback period |
| "Should I spend more here?" | Budget reallocation recommendations |
| "Give me a metrics dashboard" | Comprehensive multi-channel analysis |
| "How much should I scale?" | ROI-based growth projections |
| "Compare my channels" | Side-by-side channel performance |
| "Where's my profit margin?" | ROAS vs spend analysis, profit calculations |
| "Break down my ad efficiency" | Cost per conversion, conversion rate analysis |
| "Show me my marketing health" | KPI dashboard with trend analysis |

## Input Contract

**Required Columns (CSV):**
| Column Name | Type | Description | Example |
|------------|------|-------------|---------|
| `channel` | text | Marketing channel name | "Google Ads", "Meta Ads", "LinkedIn" |
| `spend` | number | Total spend in period (USD) | 2500.00 |
| `revenue` | number | Revenue attributed to channel (USD) | 8500.00 |
| `conversions` | integer | Number of conversions | 12 |

**Optional Columns (CSV):**
| Column Name | Type | Description |
|------------|------|-------------|
| `period` | text | Date range or month | "Jan 2026" |
| `platform_specific_metric` | number | CPC, CPM, AOV, etc. | 1.25 |
| `customer_lifetime_value` | number | LTV for CAC payback (USD) | 500 |

**Validation Rules:**
- Spend > 0 for all rows
- Revenue >= 0 (can be 0 for testing phases)
- Conversions >= 0
- Channel name is non-empty
- Revenue >= Spend for profitable channels

**Sample CSV Input:**
```csv
channel,spend,revenue,conversions,period,customer_lifetime_value
Google Ads,2500,8500,12,Jan 2026,450
Meta Ads,1800,5400,15,Jan 2026,360
LinkedIn Ads,3200,6400,8,Jan 2026,800
Email Campaign,200,3500,45,Jan 2026,77.78
Organic,0,1200,20,Jan 2026,60
```

### If You Don't Have This Data

- **No analytics access?** Ask your web developer for a GA4 export, or use Google Sheets to manually track key metrics for 2 weeks.
- **No historical data?** Start with the current month. Even 2 weeks of data can reveal patterns.
- **No attribution setup?** Use UTM parameters on all campaign links going forward. This skill can help you design the taxonomy.
- **No BI tool?** Google Sheets with pivot tables covers 80% of dashboard needs for teams under 50 people.

## Process

1. **Data Ingestion & Validation**
   - Accept CSV upload or manual data entry via form
   - Validate all required columns present
   - Check for negative values or invalid data
   - **Human Checkpoint:** Confirm data looks correct before proceeding

2. **Core Metric Calculation**
   - ROI = ((Revenue - Spend) / Spend) × 100 for each channel
   - ROAS = Revenue / Spend
   - CAC = Spend / Conversions
   - Blended ROI = (Total Revenue - Total Spend) / Total Spend × 100
   - **Human Checkpoint:** Review preliminary metrics

3. **Advanced Analysis**
   - Calculate CAC Payback Period = CAC / (AOV × Margin %) if data provided
   - Break-even Point = Spend / ROAS
   - Conversion Rate = Conversions / Impressions (if impressions available)
   - Efficiency Score (0-100) based on ROAS quartiles
   - **Human Checkpoint:** Validate calculations match expectations

4. **Comparative & Predictive Analysis**
   - Rank channels by ROI, ROAS, CAC
   - Identify underperformers (ROI < 50% threshold)
   - Calculate optimal budget allocation using Pareto principle
   - Generate reallocation scenarios (+10%, +20%, -10%)
   - **Human Checkpoint:** Approve budget reallocation recommendations

5. **Output Generation**
   - Compile metrics into Markdown tables (ready to paste into Google Sheets or Excel)
   - Provide step-by-step charting instructions for visualizations
   - Add actionable recommendations
   - Generate summary narrative


> **Benchmark Context**: Marketing teams typically allocate 5-15% of budget to analytics tools (Google 2024 Marketing Measurement Guide). A well-built dashboard should answer 80% of weekly reporting questions without manual queries (Google 2024 Marketing Measurement Guide). GA4 reports average 24-48 hour data lag for standard processing. ### Confidence & Sample Size.
> **Confidence Note**: Results are only as reliable as your input data. Small datasets (<50 records or <30 days of data) produce directional insights, not statistically significant conclusions. Always note your sample size when sharing results with stakeholders. Recommendations should be validated with A/B testing or additional data before making major strategic changes.

## Output Contract

**Markdown Tables + CSV-Ready Data Structure:**

**Table 1: Channel Summary**
```
Channel | Spend | Revenue | Conversions | ROI % | ROAS | CAC | Efficiency Score
Google Ads | 2500 | 8500 | 12 | 240% | 3.40 | $208.33 | 92
Meta Ads | 1800 | 5400 | 15 | 200% | 3.00 | $120.00 | 85
LinkedIn | 3200 | 6400 | 8 | 100% | 2.00 | $400.00 | 65
Email | 200 | 3500 | 45 | 1650% | 17.50 | $4.44 | 98
Organic | 0 | 1200 | 20 | ∞ | ∞ | $0 | 100
TOTAL | 7700 | 25000 | 100 | 224% | 3.25 | $77 | 88
```

**Table 2: Break-even & Profitability**
```
Channel | Break-even Revenue | Current Revenue | Days to Break-even | Profit Margin %
Google Ads | 2500 | 8500 | 8 (of 30) | 71%
...
```

**Table 3: Budget Reallocation**
```
Current Channel | Current Budget | ROI Ranking | Rec. Budget (+10%) | Projected Revenue | Notes
Email | 200 | 1st | 350 | 5250 | Scale proven winner
Google | 2500 | 2nd | 3000 | 10200 | Solid performer
LinkedIn | 3200 | 4th | 2450 | 4900 | Reduce underperformer
```

All tables are provided in Markdown format and can be pasted directly into Google Sheets or Excel. Step-by-step instructions included for formatting and chart creation.

**Recommendations Summary**
- Text-based action items
- Quick wins
- Channel-specific insights

## Platform Implementation Steps

### Google Analytics 4
1. Navigate to GA4 → Admin → Data Streams → your stream
2. Under Events, use "Create Event" for custom events
3. For dimensions/metrics: Admin → Custom Definitions → Create
4. Import any CSV data via Data Import: Admin → Data Import → Create

### Looker Studio / Google Data Studio
1. Open Looker Studio → Create → Report
2. Add data source (GA4, Google Sheets, BigQuery, etc.)
3. Paste calculated metric formulas into custom fields
4. Use the "Blend Data" feature for multi-source reports

### Spreadsheet (Fallback)
If no BI tool available, create analysis in Google Sheets or Excel:
1. Import CSV data using File → Import
2. Use PIVOT tables for aggregation
3. Create charts using Insert → Chart

## Failure Modes

| Scenario | Symptom | Resolution |
|----------|---------|------------|
| Missing attribution | Revenue appears 0 for all channels | Ask user: Is this attributed revenue? Suggest using UTM params or platform tracking |
| Incomplete data (no conversions) | ROAS calculated but CAC shows #DIV/0! | Handle gracefully; show ROAS only, note "conversions not tracked" |
| Seasonal variance | Single month shows negative ROI | Recommend multi-month analysis; ask about seasonality |
| Currency mismatch | Data in different currencies | Standardize to single currency; ask user for conversion rates |
| No baseline LTV | Can't calculate CAC payback | Show CAC only; recommend gathering LTV data |
| Organic/free channels | Division by zero for organic metrics | Show only applicable metrics; flag as reference/control |

## How to Get Your Data

**Google Ads:**
- Log in to Google Ads > Campaigns > Columns > Modify columns
- Select: Spend, Conversions, Conversion value
- Download as CSV (Tools > Bulk actions > Download)
- Filter by date range needed

**Meta Ads Manager:**
- Ads > Campaigns
- Select date range
- Add columns: Spend, Purchases, Purchase value (or your conversion event)
- Export as CSV or copy/paste

**HubSpot:**
- Analytics > Marketing > Campaigns
- Select date range
- View "Revenue" and "Conversions"
- Export report as CSV

**Generic:**
- Aggregate from invoice data + payment processor (Stripe, Shopify)
- Match revenue to marketing channel via UTM parameters
- Cross-reference with ad platform data

## Example

**Scenario:** TaskFlow (project management SaaS) runs 5 paid marketing channels and wants to evaluate Q1 performance. Budget allocation decision: scale winners or pause underperformers?

**Input CSV (March 2026 data):**
```csv
channel,spend,revenue,conversions,period,customer_lifetime_value
Google Ads,5000,18500,25,March 2026,740
Meta Ads,4200,8400,28,March 2026,300
LinkedIn Ads,8500,10200,17,March 2026,600
Email Newsletter,800,8500,85,March 2026,100
Organic Search,0,2400,48,March 2026,50
```

**Output Analysis:**

| Channel | Spend | Revenue | ROI % | ROAS | CAC | Payback | Efficiency |
|---------|-------|---------|-------|------|-----|---------|------------|
| Google Ads | $5,000 | $18,500 | 270% | 3.70 | $200 | 12 days | 94 |
| Meta Ads | $4,200 | $8,400 | 100% | 2.00 | $150 | 18 days | 68 |
| LinkedIn Ads | $8,500 | $10,200 | 20% | 1.20 | $500 | 50 days | 42 |
| Email Newsletter | $800 | $8,500 | 962% | 10.63 | $9.41 | 2.8 days | 98 |
| **TOTAL** | **$18,500** | **$48,000** | **159%** | **2.59** | **$91** | **14 days** | **80** |

**Key Findings & Recommendations:**

**Scale Immediately (Cash Cows):**
- Email: 962% ROI + $9.41 CAC. Increase $800 → $2,000/month.
- Google Ads: 270% ROI + $200 CAC. Increase $5,000 → $7,000/month.

**Restructure (Problem Children):**
- LinkedIn: Only 20% ROI with $500 CAC. Reduce to $3,000/month; test ABM.
- Meta: 100% ROI is breakeven. Test new segments or pause.

**Proposed Q2 Budget Reallocation (+$10K increase):**
Expected monthly revenue impact: $48K → $62K (+29%), blended ROI 159% → 205%.

---

## Full Example (e-commerce benchmark)

**Scenario:** An e-commerce brand runs 4 paid channels + email + organic. Wants to understand true efficiency and how to allocate next month's $10,000 budget.

**Input CSV:**
```
channel,spend,revenue,conversions,period,customer_lifetime_value
Google Shopping,3500,12000,48,Feb 2026,250
Facebook Ads,2800,7200,36,Feb 2026,200
LinkedIn B2B,2200,3300,11,Feb 2026,300
Twitter Ads,500,400,4,Feb 2026,100
Email Newsletter,400,2800,70,Feb 2026,40
Organic Search,0,1500,30,Feb 2026,50
```

**Output Analysis:**

"Your marketing mix shows strong performance, but significant opportunity exists:

**Best Performers:**
1. Email Newsletter: 600% ROI, $5.71 CAC — This is your cash cow. Scale immediately.
2. Google Shopping: 243% ROI, $72.92 CAC — Strong efficiency. Increase budget 15%.

**Problem Children:**
- Twitter: -20% ROI. Consider pausing to test other channels.
- LinkedIn: 50% ROI, $200 CAC — Only viable if CAC payback < 60 days (currently 120 days). Restructure targeting.

**Recommended Budget Allocation (next $10,000):**
- Email: +$200 → $600 (scale winner)
- Google Shopping: +$700 → $4,200 (proven reliable)
- Facebook: +$300 → $3,100 (solid performer)
- LinkedIn: -$500 → $1,700 (test reduced spend)
- Twitter: -$500 → $0 (pause and reallocate)

**Expected Impact:** Revenue lift from $27,200 → $31,500 monthly (+16%) while improving blended ROI from 244% to 268%."

---

**Next Steps:**
- Review recommendations in alignment with strategic goals
- A/B test budget shifts gradually (don't move all at once)
- Re-run analysis monthly to track channel drift
- Establish attribution model if not already in place

## Related Skills

- **[marketing-mix-modeler](./marketing-mix-modeler.md)** — Use ROI metrics from this skill to optimize budget allocation.
- **[marketing-dashboard-builder](./marketing-dashboard-builder.md)** — Visualize ROI and ROAS metrics in a dashboard for ongoing monitoring.
- **[channel-mix-optimizer](../growth/channel-mix-optimizer.md)** — Inform channel strategy decisions with ROI data calculated here.
- **[funnel-drop-off-analyzer](./funnel-drop-off-analyzer.md)** — Combine ROI analysis with funnel diagnostics to improve conversion rates.
