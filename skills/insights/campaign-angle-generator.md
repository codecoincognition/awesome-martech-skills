---
name: campaign-angle-generator
description: >
  Generate 10-20 fresh campaign angles by reframing value through contrarian, emotional,
  data-driven, aspirational, and fear-based lenses. Use this skill whenever the user mentions
  campaign angles, campaign ideas, creative angles, messaging angles, ad angles, campaign concepts,
  marketing angles, "give me fresh angles", "I need campaign ideas", content angles, "how should
  I frame this", value proposition framing, persuasion angles, "I'm stuck on messaging", "same old
  messaging isn't working", creative brief ideation, or any request to generate multiple ways to
  frame or angle a marketing message. Also trigger on "brainstorm campaign concepts" or "help me
  think about this differently". Chains with hook-stress-tester to evaluate generated angles.
---

# Campaign Angle Generator

Generate 10-20 campaign angles that reframe your product's value through different persuasion lenses. Each angle includes a hook, core argument, supporting evidence type, and suggested format — ready to hand off to copywriters or feed into ad-copy-generator.

## Granularity Check

> Can this be completed in a single Claude session? **Yes — expect ~5 min data prep → ~10 min Claude session → ~30-60 min synthesizing into your strategy deck.** If implementing output in a platform, add 10-20 min for setup. Input is product/service context + audience. Output is an angle library document. No external data needed.

## User Intent Mapping

Trigger when the user says:

- "Give me 10 campaign angles for my product" (direct request)
- "I need fresh ways to message our product" (staleness problem)
- "Brainstorm campaign concepts" (ideation)
- "How should I frame our Q2 campaign?" (strategic)
- "Our current messaging isn't resonating" (performance problem)
- "Generate ad angles for our launch" (launch-specific)
- "I need different ways to talk about [feature]" (reframing)
- "Help me think about our value proposition differently" (VP exploration)
- "What angles would work for [audience]?" (audience-specific)
- "Create a messaging angle library" (asset creation)

## Input Contract

### Required Input

| Field | Type | Description |
|---|---|---|
| `product_or_service` | text | What you're marketing |
| `target_audience` | string | Who you're trying to reach |
| `key_benefit` | string | Primary value proposition |

### If You Don't Have This Data

- **No customer interviews?** Use support tickets, sales call notes, or online reviews as proxy customer voice data.
- **No survey data?** Send a 5-question NPS-style survey to your customer base. 30+ responses is enough for initial patterns.
- **No competitor content?** Search your primary keywords and screenshot the top 10 results. That's your competitive landscape.
- **No win/loss data?** Ask your sales team to recall their last 5 won and 5 lost deals. Verbal notes work fine as input.

### Optional Input

| Field | Type | Description |
|---|---|---|
| `current_messaging` | text | What you're saying now (to differentiate from) |
| `competitor_messaging` | text | What competitors say (to avoid overlap) |
| `campaign_goal` | string | Awareness / Leads / Conversions / Retention |
| `customer_pain_points` | list | Known frustrations (from VoC data) |
| `proof_points` | list | Stats, testimonials, case studies available |
| `constraints` | list | Brand guidelines, compliance rules, tone restrictions |
| `channels` | list | Where angles will be used (ads, email, social, landing pages) |
| `industry` | string | Vertical for context |

### Sample Input

```
Product: ProjectFlow — project management SaaS for creative agencies
Target audience: Creative directors and agency owners (25-100 person agencies)
Key benefit: Eliminates project chaos so agencies deliver work on time and on budget
Current messaging: "Project management for creative teams"
Pain points: missed deadlines, scope creep, client communication gaps, team burnout
Proof points: 34% reduction in missed deadlines, 500+ agencies, NPS 72
```

### Input Validation Rules

1. Product description and audience are essential — ask if missing
2. Key benefit should be specific (not just "better" or "easier")
3. Current messaging helps Claude differentiate new angles from status quo
4. More context = more relevant angles

## Process

1. **Analyze the value landscape** — Identify all the ways the product creates value:
   - Functional value (what it does)
   - Emotional value (how it makes people feel)
   - Social value (how it makes people look)
   - Financial value (money saved/made)
   - Time value (time saved/recovered)

2. **Generate angles through 7 persuasion lenses:**

   **a. Contrarian (2-3 angles)**
   Challenge conventional wisdom. "What everyone believes about X is wrong."
   - Flip assumptions: "You don't need more tools. You need fewer."
   - Challenge the category: "Project management software is the problem."
   - Redefine the problem: "The issue isn't productivity. It's clarity."

   **b. Data-Driven (2-3 angles)**
   Lead with numbers that shock, validate, or benchmark.
   - Customer results: "Agencies using ProjectFlow miss 34% fewer deadlines."
   - Industry stats: "The average agency loses $X per year to project chaos."
   - Benchmark: "How does your agency's on-time delivery compare to the top 10%?"

   **c. Emotional / Story (2-3 angles)**
   Connect through feeling, narrative, or identity.
   - Pain: "That 3am email from a client asking 'where are we on this?'"
   - Aspiration: "Run the kind of agency people brag about working at."
   - Identity: "For creative directors who refuse to let admin kill the craft."

   **d. Fear / Risk (2-3 angles)**
   Highlight what happens if they don't act.
   - Loss aversion: "Every week without a system costs you 8 hours of status meetings."
   - Competitive fear: "Your competitors already solved this problem."
   - Consequence: "Scope creep doesn't just kill margins. It kills morale."

   **e. Aspirational / Vision (2-3 angles)**
   Paint the future state or ideal outcome.
   - Transformation: "From chaotic agency to well-oiled creative machine."
   - Unlocked potential: "What could your team create with 10 more hours per week?"
   - Status: "Join the 500+ agencies that eliminated project chaos."

   **f. Social Proof / Authority (2-3 angles)**
   Leverage credibility and belonging.
   - Peer pressure: "500+ agencies already switched. Here's why."
   - Expert endorsement: "[Expert Name] calls it 'the missing piece for creative teams.'"
   - Momentum: "The fastest-growing PM tool in the creative industry."

   **g. Simplicity / Clarity (1-2 angles)**
   Cut through complexity with clear, direct messaging.
   - Reductive: "One tool. One source of truth. Zero excuses for missed deadlines."
   - Before/after: "Before ProjectFlow: 5 tools and confusion. After: 1 dashboard and clarity."

3. **For each angle, provide:**
   - **Hook** — The headline or opening line (1 sentence)
   - **Core argument** — The logical structure behind the angle (2-3 sentences)
   - **Evidence needed** — What proof point best supports this angle
   - **Best format** — Where this angle works best (ad, landing page, email, social post, video)
   - **Audience resonance** — Which audience segment this angle appeals to most

4. **Score and rank angles** by:
   - Differentiation from current messaging (1-10)
   - Audience relevance (1-10)
   - Proof point availability (1-10)
   - Versatility across channels (1-10)

5. **Human checkpoint** — Present top 5 angles. Ask: "Which angles resonate most with your brand? Any lenses to explore more deeply?"

6. **Generate output** — Complete angle library.


> **Benchmark Context**: Win/loss analysis requires minimum 20 interviews per segment for reliable patterns. Survey response rates average 10-15% for email surveys, 30-50% for in-app (McKinsey 2024 State of AI Report). Qualitative research saturation typically occurs at 12-15 interviews (McKinsey 2024 State of AI Report). ### Confidence & Sample Size.
> **Confidence Note**: Results are only as reliable as your input data. Small datasets (<50 records or <30 days of data) produce directional insights, not statistically significant conclusions. Always note your sample size when sharing results with stakeholders. Recommendations should be validated with A/B testing or additional data before making major strategic changes.

## Output Contract

### Output Format

| Output | Format | Contents |
|---|---|---|
| Angle library | Markdown | 15-20 angles organized by lens |
| Top 5 summary | Markdown | Best angles with full development |

### Angle Library Structure

```markdown
# Campaign Angle Library
Product: [name]
Audience: [target]
Generated: [date]
Total angles: [N]

## Top 5 Angles (Recommended)

### #1: [Angle Name] — [Lens: Contrarian]
**Hook:** "[headline]"
**Core argument:** [2-3 sentences]
**Evidence:** [proof point]
**Best format:** [channel/format]
**Audience fit:** [which segment]
**Differentiation score:** 9/10
**Example execution:**
- Ad headline: "[text]"
- Email subject: "[text]"
- Social post opening: "[text]"

[Repeat for top 5]

## Full Angle Library

### Contrarian Angles
1. **[Name]:** [hook] | Argument: [brief] | Format: [channel]
2. **[Name]:** [hook] | Argument: [brief] | Format: [channel]
3. **[Name]:** [hook] | Argument: [brief] | Format: [channel]

### Data-Driven Angles
[...]

### Emotional Angles
[...]

[Continue for all lenses]

## Angle Comparison Matrix
| # | Angle | Lens | Differentiation | Relevance | Proof Available | Versatility | Total |
|---|---|---|---|---|---|---|---|
| 1 | [name] | Contrarian | 9 | 8 | 7 | 9 | 33 |
| 2 | [name] | Emotional | 7 | 9 | 8 | 8 | 32 |
...

## Next Steps
- Feed top angles into **hook-stress-tester** for headline variants
- Use top angles in **ad-copy-generator** for platform-specific copy
- Test 2-3 angles in parallel campaigns to identify winner
```

## Platform Implementation Steps

### Google Sheets / Excel
1. Create a new spreadsheet
2. Paste output tables directly (Markdown tables → Sheets)
3. Add conditional formatting for scores/ratings
4. Create charts for visual summaries
5. Share with stakeholders

### Notion
1. Create a new page
2. Paste the Markdown output directly
3. Convert tables to Notion databases for filtering/sorting
4. Add to your team's research hub

### Presentation (for Stakeholders)
1. Copy key findings into a slide deck
2. Use the output scores/rankings as data slides
3. Include the recommended actions as a closing slide
4. Present to marketing/product leadership

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Too generic product description | Vague input | Ask for specific features, audience, and competitive differences |
| No proof points | Early-stage product | Generate angles that work without data; flag which need validation |
| Highly regulated industry | Healthcare, finance constraints | Generate compliant angles; flag any that need legal review |
| Very niche audience | Small market | Go deeper into identity and community angles; fewer fear-based |
| Competitor messaging unknown | No competitive context | Generate broader angles; recommend running positioning-whitespace-finder first |

## How to Get Your Data

### Starting Fresh (Most Common)

1. Describe your product, audience, and key benefit
2. Share any existing messaging, customer pain points, or proof points
3. Claude generates the full angle library

### From Voice of Customer Data (Best Path)

1. Run voice-of-customer-miner to extract real customer language
2. Feed pain points and desires into campaign-angle-generator
3. Angles will be grounded in actual customer language

### From Competitor Analysis

1. Run positioning-whitespace-finder to map competitor messaging
2. Feed whitespace opportunities into campaign-angle-generator
3. Angles will differentiate from competitor messaging

## Example

**User prompt:** "Generate campaign angles for our project management SaaS targeting creative agency owners. Our current messaging is generic and not resonating."

**Claude responds:**

> Here are the top 5 angles from 18 total generated:
>
> **#1: "The Admin Tax" (Contrarian)**
> Hook: "Your best designers spend 30% of their time on admin. That's not a productivity problem — it's a talent waste."
> Best for: LinkedIn ads, landing page hero
>
> **#2: "The 3am Client Email" (Emotional/Pain)**
> Hook: "That sinking feeling when a client asks 'where are we on this?' and you don't have an answer."
> Best for: Email nurture, social storytelling
>
> **#3: "The 34% Number" (Data-Driven)**
> Hook: "Agencies using ProjectFlow miss 34% fewer deadlines. What would that mean for your client retention?"
> Best for: Google Ads, case study landing page
>
> **#4: "The Creative Machine" (Aspirational)**
> Hook: "From chaotic agency to creative machine — without adding a single headcount."
> Best for: Brand campaign, video
>
> **#5: "The Tool Graveyard" (Contrarian/Fear)**
> Hook: "You don't need another PM tool. You need the only one your team will actually use."
> Best for: Competitive landing page, retargeting
>
> Full library includes 18 angles across 7 lenses. Feed top picks into hook-stress-tester for headline optimization or ad-copy-generator for platform-ready copy.

## Related Skills

- **[Hook Stress Tester](./hook-stress-tester.md)** — Evaluate and improve the headlines and hooks from generated campaign angles.
- **[Positioning Whitespace Finder](./positioning-whitespace-finder.md)** — Identify unclaimed positioning territory before generating angles to focus on unique angles.
- **[Ad Copy Generator](../ads/ad-copy-generator.md)** — Turn validated campaign angles into ad copy variations.
- **[Voice of Customer Miner](./voice-of-customer-miner.md)** — Ground campaign angles in actual customer language and pain points from Reddit discussions.
