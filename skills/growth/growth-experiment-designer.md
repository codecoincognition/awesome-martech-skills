---
name: growth-experiment-designer
description: >
  Design structured growth experiments with hypotheses, metrics, and prioritization frameworks.
  Use this skill when the user says "growth experiment", "growth hack ideas", "experiment backlog",
  "ICE scoring", "RICE framework", "growth sprint planning", "test ideas for growth", "experiment
  hypothesis", "growth experiment prioritization", "experiment design template", or "experiment
  velocity". Also trigger for north star metric definition, growth model design, or experiment
  results analysis.
---

# Growth Experiment Designer

Designs structured growth experiments with clear hypotheses, success metrics, ICE/RICE prioritization, and documentation templates for systematic growth testing.

## Granularity Check

> **Time**: ~5 min data prep → ~10 min Claude session → ~60-120 min implementing in your product / tools. If implementing experiments, add variable time per experiment. Input is growth goals and current metrics. Output is Markdown experiment backlog with prioritized experiments.

## User Intent Mapping

- "Help me design growth experiments" (methodology)
- "Prioritize our experiment backlog" (prioritization)
- "Growth sprint planning for next month" (planning)
- "What should we test to increase signups?" (ideation)
- "ICE score our experiment ideas" (scoring)
- "Set up a growth experiment framework" (framework)
- "We need more experiment velocity" (process improvement)
- "Analyze this experiment's results" (analysis)
- "Define our north star metric" (strategy)
- "Growth model for our funnel" (modeling)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Product/Business | Text | What you do, your business model |
| Growth Goal | Text | What metric you want to improve (signups, activation, revenue, retention) |
| Current Metrics | Text | Baseline numbers for key funnel metrics |

### If You Don't Have This Data

- **No experiment history?** Perfect — this skill creates your first experiment backlog from scratch.
- **No funnel metrics?** List your conversion steps and estimate rates. Set up tracking, then revisit with real data in 30 days.
- **No growth team?** This framework works for solo founders and small teams. Start with 1-2 experiments per sprint.
- **No analytics?** Set up basic event tracking (Google Analytics, Mixpanel, or even spreadsheet tracking) before running experiments.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Funnel Data | CSV or Text | Step-by-step conversion rates |
| Past Experiments | Text | Previous tests and results |
| Team Resources | Text | Engineers, designers, marketers available |
| Sprint Length | Text | 1-week, 2-week, or monthly sprints |
| Constraints | Text | Technical, budget, or time limitations |

## Process

### Step 1: Growth Model
Map the growth equation:
- **Acquisition**: How users find you (channels, virality, SEO)
- **Activation**: First value moment (aha moment, onboarding completion)
- **Retention**: Users coming back (daily/weekly/monthly active)
- **Revenue**: Monetization (conversion to paid, ARPU, expansion)
- **Referral**: Users bringing others (viral coefficient, NPS)

Identify the biggest lever: where is the funnel leaking most?

### Step 2: Experiment Ideation
Generate 10-20 experiment ideas per growth lever:
- Customer interviews and feedback themes
- Competitor feature analysis
- Industry best practices and benchmarks
- Data anomalies and drop-off points
- Cross-functional brainstorming prompts

### Step 3: Prioritization (ICE or RICE)

**ICE Score** (simpler):
| Factor | Score 1-10 | Description |
|---|---|---|
| Impact | 1-10 | How much will this move the metric? |
| Confidence | 1-10 | How sure are we this will work? |
| Ease | 1-10 | How easy is this to implement? |
| **ICE Score** | Average | (Impact + Confidence + Ease) / 3 |

**RICE Score** (more rigorous):
| Factor | Description |
|---|---|
| Reach | How many users affected per quarter? |
| Impact | Score 0.25-3 (minimal to massive) |
| Confidence | Percentage (100% = high data, 50% = gut feel) |
| Effort | Person-weeks to implement |
| **RICE Score** | (Reach × Impact × Confidence) / Effort |

### Step 4: Experiment Documentation
For each experiment, define:
- **Name**: Descriptive experiment name
- **Hypothesis**: "If we [change], then [metric] will [improve by X%] because [reasoning]"
- **Metric**: Primary metric + secondary metrics
- **Minimum Detectable Effect**: Smallest change worth detecting
- **Sample Size**: Users needed for statistical significance
- **Duration**: How long to run
- **Implementation**: What to build/change
- **Success Criteria**: What makes this a win/lose/learn

### Step 5: Sprint Planning
- Select top 2-5 experiments per sprint
- Balance quick wins with bigger bets
- Assign owners and deadlines
- Review and document results at sprint end

### Confidence & Sample Size
> **Confidence Note**: Most experiments fail (70-80% show no significant result). This is normal and expected. Run enough experiments to find the 20-30% that work. Small sample sizes (<1,000 users per variant) produce unreliable results — extend duration or simplify the test. Don't "peek" at results mid-experiment — set a duration and stick to it.

### ⚠️ Human Checkpoint
> Review experiment priorities with the team before committing engineering resources. Verify that success metrics are tracked correctly before launch. Ensure experiments don't negatively impact user experience in ways that outweigh potential gains.

> **Benchmark Context**: See ProfitWell 2024 SaaS Benchmarks for current industry benchmarks relevant to this analysis.
## Output Contract

### Deliverable: Markdown Experiment Backlog

```markdown
# Growth Experiment Backlog: [Product]

## Growth Model
- North Star Metric: [metric]
- Key Lever: [acquisition/activation/retention/revenue/referral]
- Current: [baseline metric]
- Target: [goal metric]

## Prioritized Experiments

### Experiment 1: [Name] — ICE Score: X.X
- **Hypothesis**: If we [change], then [metric] will [improve] because [reason]
- **Primary Metric**: [metric]
- **Effort**: [days/weeks]
- **Sample Size**: [users needed]
- **Duration**: [days]
- **Owner**: [role]

### Experiment 2: [Name] — ICE Score: X.X
...

## Sprint Plan: [Sprint Name]
| Experiment | Owner | Start | End | Status |
|---|---|---|---|---|

## Results Log
| Experiment | Hypothesis | Result | Metric Change | Learning |
|---|---|---|---|---|
```

## Platform Implementation Steps

### Experiment Tracking (Notion/Airtable)
1. Create an experiments database with fields: Name, Hypothesis, ICE Score, Status, Owner, Metric, Result
2. Set up views: Backlog (prioritized), Active, Completed
3. Create a sprint planning view filtered to current sprint
4. Add a results log view for historical analysis

### Analytics Setup
1. Define events for each experiment's success metric
2. Set up A/B testing tool (Google Optimize, VWO, LaunchDarkly, or Statsig)
3. Create dashboards for active experiments
4. Set up alerts for significant results

### Sprint Cadence
1. Sprint Planning (Day 1): Select experiments from backlog
2. Implementation (Days 2-3): Build and launch experiments
3. Monitoring (Days 4-12): Track metrics without interference
4. Review (Day 14): Analyze results, document learnings
5. Next Sprint Planning: reprioritize backlog based on learnings

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| No significant results | Too small a change or too little traffic | Test bolder changes; increase sample size; extend duration |
| Experiment polluted | Multiple changes running simultaneously | Ensure experiments don't overlap on the same user flow |
| Team lost interest | Lack of wins or slow velocity | Focus on quick wins (1-3 day experiments) to build momentum |
| Wrong metric | Vanity metric that doesn't correlate with growth | Align experiments to north star metric; validate metric-to-revenue link |

## How to Get Your Data

- **Funnel data**: Google Analytics → Funnels or custom event sequences
- **No data**: Describe your product and conversion steps — Claude builds the experiment backlog from best practices
- **Past experiments**: Describe what you tested and what happened

## Example

**Input**: "Growth experiments for a B2B SaaS. Current funnel: 10K monthly visitors → 500 signups (5%) → 100 activated (20%) → 20 paid (4%). North star: monthly activated users. Biggest drop: signup to activation (20%)."

**Output**: 12 experiments prioritized by ICE score. Top 5: (1) Onboarding checklist with progress bar (ICE 8.3) — hypothesis: gamified onboarding increases activation from 20% to 30%; (2) Time-to-value optimization — reduce steps to first aha moment from 8 to 3 (ICE 7.7); (3) Personalized onboarding flow by use case (ICE 7.3); (4) In-app welcome video replacing email drip (ICE 7.0); (5) Proactive chat trigger at activation drop-off point (ICE 6.7). Sprint 1 plan: experiments 1 and 2 (both targeting activation). Sprint 2: experiments 3 and 4. Testing framework: minimum 250 users per variant, 14-day test duration, 95% confidence threshold. Expected combined impact if top 3 succeed: activation rate from 20% to 28-32%.

## Related Skills

- **[retention-analysis-framework](./retention-analysis-framework.md)** — Use retention analysis to identify and prioritize experiments.
- **[onboarding-flow-optimizer](./onboarding-flow-optimizer.md)** — Design experiments to improve user activation and time-to-value.
- **[customer-persona-builder](./customer-persona-builder.md)** — Segment experiments by persona for persona-specific optimization.
- **[ab-test-result-analyzer](../analytics/ab-test-result-analyzer.md)** — Analyze experiment results with statistical rigor.
