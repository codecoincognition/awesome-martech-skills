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

> Can this be completed in a single Claude session? **Yes — expect ~5 min data prep + ~10 min Claude session.** If implementing output in a platform, add 10-20 min for setup. Input is conversion path data (CSV). Output is an XLSX model comparison + HTML visualization. Requires ≥50 conversions for statistical significance.

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


> **Benchmark Context**: Marketing teams typically allocate 5-15% of budget to analytics tools. A well-built dashboard should answer 80% of weekly reporting questions without manual queries. GA4 reports average 24-48 hour data lag for standard processing.


### Confidence & Sample Size
> **Confidence Note**: Results are only as reliable as your input data. Small datasets (<50 records or <30 days of data) produce directional insights, not statistically significant conclusions. Always note your sample size when sharing results with stakeholders. Recommendations should be validated with A/B testing or additional data before making major strategic changes.

## Output Contract

### Output Format

| Output | Format | Contents |
|---|---|---|
| Model comparison | Markdown tables + CSV-ready data | Three data sections: comparison, per-channel detail, paths — paste into Google Sheets or Excel |
| Visualization | Markdown tables + step-by-step charting instructions | Structured data + guidance for creating charts in Google Sheets |
| Summary | Markdown | Key insights and model recommendation |

### Sheet 1: Model Comparison

| Column | Type | Description |
|---|---|---|
| `channel` | string | Marketing channel |
| `first_touch_revenue` | float | Revenue under first-touch model |
| `last_touch_revenue` | float | Revenue under last-touch model |
| `linear_revenue` | float | Revenue under linear model |
| `time_decay_revenue` | float | Revenue under time-decay model |
| `position_based_revenue` | float | Revenue under position-based model |
| `first_vs_last_shift` | float | % change first-touch vs last-touch |
| `total_spend` | float | Channel spend (if provided) |
| `linear_roas` | float | ROAS under linear model |

### Sheet 2: Per-Channel Detail

| Column | Type | Description |
|---|---|---|
| `channel` | string | Marketing channel |
| `total_touchpoints` | integer | How often this channel appears |
| `as_first_touch` | integer | Times appearing first |
| `as_last_touch` | integer | Times appearing last |
| `as_assist` | integer | Times appearing in middle |
| `avg_position_in_path` | float | Average position (1=first) |
| `conversion_rate` | float | Conversions / touchpoints |

### Sheet 3: Top Conversion Paths

| Column | Type | Description |
|---|---|---|
| `path` | string | Channel sequence (e.g., "Organic → Email → Paid") |
| `conversions` | integer | How many times this path occurred |
| `avg_value` | float | Average conversion value |
| `avg_touchpoints` | integer | Average path length |

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

| Failure | Cause | Recovery |
|---|---|---|
| Too few conversions (<50) | Small dataset | Proceed with caveat; recommend collecting more data |
| All single-touch conversions | No multi-touch paths | First=last for all; recommend better cross-channel tracking |
| One dominant channel (>80%) | Channel concentration | Note the dominance; compare models for remaining 20% |
| No conversion values | Leads only, no revenue | Use conversion count instead of revenue; note limitation |
| Missing timestamps | Can't calculate time-decay | Skip time-decay model; use position-based instead |
| Aggregated data (Option B) | No path-level data | Build first/last/assisted comparison only; can't do linear or time-decay |

## How to Get Your Data

### From Google Analytics 4

1. GA4 → Advertising → Conversion paths
2. Set date range and conversion event
3. Export → CSV (note: GA4 provides path-level data)

### From HubSpot

1. Reports → Attribution Reports
2. Select "Revenue attribution" or "Contact create attribution"
3. Export raw data → CSV

### From Google Ads

1. Tools → Attribution → Conversion paths
2. Export path data → CSV

### Manual Collection

1. Export conversion data from your CRM (conversion ID, date, value)
2. Export marketing touchpoint data (which channels each contact interacted with, in order)
3. Merge by contact/conversion ID
4. Provide to Claude

## Example

**User prompt:** "I have 200 conversions with touchpoint data across 5 channels. Build attribution models and tell me which channels I'm over/under-investing in."

**Claude responds:**

> Analyzed 200 conversions across 5 channels. Average path: 2.8 touchpoints.
>
> **Credit shift across models:**
>
> | Channel | First-Touch | Last-Touch | Linear | Position-Based | Shift |
> |---|---|---|---|---|---|
> | Organic Search | $82,000 | $41,000 | $58,000 | $62,000 | **Undervalued by last-touch** |
> | Paid Search | $31,000 | $68,000 | $48,000 | $46,000 | Overvalued by last-touch |
> | Email | $12,000 | $35,000 | $28,000 | $22,000 | Closing channel |
> | Social | $45,000 | $18,000 | $26,000 | $32,000 | **Undervalued by last-touch** |
> | Content | $30,000 | $38,000 | $40,000 | $38,000 | Consistent assist role |
>
> **Key insight:** Organic Search and Social are generating far more awareness than last-touch shows. If you're using last-touch to allocate budget, you're likely under-investing in these channels by ~35%.
>
> **Recommended model:** Position-based (40/20/40) — your average path has 2.8 touches, making both awareness and closing important.
>
> Want me to generate the full XLSX with all models + the interactive visualization?
