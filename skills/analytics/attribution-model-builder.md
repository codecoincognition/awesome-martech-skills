---
name: attribution-model-builder
description: >
  Build and compare marketing attribution models from conversion path data. Use this skill whenever
  the user mentions attribution modeling, marketing attribution, multi-touch attribution, MTA,
  first-touch attribution, last-touch attribution, linear attribution, time-decay attribution,
  position-based attribution, U-shaped attribution, "which channels are driving conversions",
  "how should I attribute revenue to marketing channels", conversion path analysis, channel credit
  allocation, "understand my customer journey touchpoints", attribution comparison, or any request
  to determine which marketing touchpoints deserve credit for conversions. Also trigger on "my
  attribution is wrong" or "which channels should I invest in based on conversion data".
---

> **How this skill works:** You export your conversion path data from your analytics platform (GA4, Mixpanel, etc.) as a CSV, and Claude builds attribution models. Claude cannot connect to live analytics platforms or pull data directly — you bring the data, Claude brings the models.

# Attribution Model Builder

Build and compare multiple attribution models (first-touch, last-touch, linear, time-decay, position-based) from conversion path data. Visualize how credit shifts between models and recommend the best fit for your business.

## Granularity Check

> Can this be completed in a single Claude session? **Yes — expect ~5 min data prep → ~10 min Claude session → ~30-60 min building in Google Sheets / Looker / GA4.** If implementing output in a platform, add 10-20 min for setup. Input is conversion path data (CSV). Output is an XLSX model comparison + HTML visualization. Requires ≥50 conversions for statistical significance.

## User Intent Mapping

Trigger when the user says:

- "Build an attribution model for my marketing channels" (direct request)
- "Which channels are actually driving conversions?" (diagnostic)
- "Compare first-touch vs last-touch attribution" (model comparison)
- "I need multi-touch attribution" (MTA request)
- "How should I credit revenue across channels?" (allocation question)
- "My attribution data looks wrong" (validation)
- "Which marketing touchpoints matter most?" (touchpoint analysis)
- "Should I invest more in [channel] based on attribution?" (budget decision)
- "Build a data-driven attribution model" (advanced)
- "Show me how credit changes across attribution models" (comparison)

## Input Contract

### Option A: Conversion Path Data (Best)

| Column | Type | Required | Description |
|---|---|---|---|
| `conversion_id` or `user_id` | string | Yes | Unique identifier per conversion |
| `touchpoint_channel` | string | Yes | Channel at each touchpoint |
| `touchpoint_date` or `touchpoint_order` | date/integer | Yes | When or in what order |
| `conversion_value` | float | No | Revenue or value of conversion |

### Option B: Aggregated Channel Data (Simpler)

| Column | Type | Required | Description |
|---|---|---|---|
| `channel` | string | Yes | Marketing channel |
| `first_touch_conversions` | integer | No | Conversions attributed to first touch |
| `last_touch_conversions` | integer | No | Conversions attributed to last touch |
| `assisted_conversions` | integer | No | Conversions where channel assisted |
| `total_spend` | float | No | Spend per channel |
| `total_revenue` | float | No | Revenue per channel |

### Sample Input (Option A)

```csv
conversion_id,touchpoint_channel,touchpoint_order,conversion_value
C001,Organic Search,1,500
C001,Email,2,500
C001,Paid Search,3,500
C002,Social,1,250
C002,Social,2,250
C002,Paid Search,3,250
C003,Organic Search,1,1000
C003,Content,2,1000
C003,Email,3,1000
C003,Direct,4,1000
```

### Input Validation Rules

1. Minimum 50 conversions recommended (warn if fewer — models won't be reliable)
2. At least 2 touchpoints per conversion for multi-touch to be meaningful
3. If only single-touch data, first-touch = last-touch (note this limitation)
4. Conversion value optional but greatly improves analysis
5. Flag conversions with >10 touchpoints (unusual — possible tracking error)

### If You Don't Have This Data

- **No analytics access?** Ask your web developer for a GA4 export, or use Google Sheets to manually track key metrics for 2 weeks.
- **No historical data?** Start with the current month. Even 2 weeks of data can reveal patterns.
- **No attribution setup?** Use UTM parameters on all campaign links going forward. This skill can help you design the taxonomy.
- **No BI tool?** Google Sheets with pivot tables covers 80% of dashboard needs for teams under 50 people.

## Process

1. **Validate and summarize data:**
   - Total conversions, total revenue
   - Average touchpoints per conversion
   - Unique channels in the dataset
   - Time span of data

2. **Build 5 attribution models:**

   **a. First-Touch (100% to first interaction)**
   - Full credit to the channel that introduced the prospect
   - Best for: understanding awareness generation

   **b. Last-Touch (100% to last interaction)**
   - Full credit to the channel before conversion
   - Best for: understanding closing channels

   **c. Linear (equal split)**
   - Credit divided equally among all touchpoints
   - Formula: credit = conversion_value / number_of_touchpoints
   - Best for: balanced view when all touches matter equally

   **d. Time-Decay (more credit to recent touches)**
   - Half-life decay: touches closer to conversion get more credit
   - Formula: weight = 2^(-(days_before_conversion / half_life))
   - Default half-life: 7 days (adjustable)
   - Best for: shorter sales cycles

   **e. Position-Based / U-Shaped (40-20-40)**
   - 40% to first touch, 40% to last touch, 20% split among middle
   - Best for: valuing both awareness and closing

3. **Compare models** — For each channel, show credited conversions and revenue under each model. Calculate the shift: which channels gain/lose credit as you move between models.

4. **Identify insights:**
   - Channels that are **undervalued** by last-touch (high first-touch, low last-touch)
   - Channels that are **overvalued** by last-touch (low first-touch, high last-touch)
   - **Assist-heavy** channels (rarely first or last, but frequently in the middle)
   - **Standalone** channels (high single-touch conversion rate)

5. **Recommend best-fit model** based on:
   - Average sales cycle length
   - Number of touchpoints
   - Business model (awareness-focused vs conversion-focused)

6. **Human checkpoint** — Present model comparison table. Ask: "Which model aligns best with how you think about marketing's role? Should I adjust the time-decay half-life or position-based weights?"

7. **Generate outputs** — Markdown tables with data ready for spreadsheet pasting + charting instructions.

## Output Contract

### Deliverable: Markdown Model Comparison Tables

Provides data ready to paste into Google Sheets, Excel, or any BI tool, plus interpretation guide.

## Related Skills

- **ad-performance-analyzer** (../ads/ad-performance-analyzer.md) — Analyze individual ad campaign performance; use attribution models to understand contribution to overall conversions.
- **campaign-performance-benchmarker** (./campaign-performance-benchmarker.md) — Compare attribution results against industry benchmarks; understand if your channel mix is optimal.
- **marketing-roi-calculator** (./marketing-roi-calculator.md) — Calculate ROI by channel using attribution-informed spend allocation; maximize return on marketing investment.
- **budget-variance-analyzer** (./budget-variance-analyzer.md) — Reallocate budget based on attribution insights; move spending from undervalued to overvalued channels.
