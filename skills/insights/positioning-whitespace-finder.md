---
name: positioning-whitespace-finder
description: >
  Analyze your product messaging against 5+ competitors to find positioning whitespace and
  saturated messaging areas. Use this skill whenever the user mentions positioning analysis,
  competitive positioning, messaging whitespace, positioning map, differentiation analysis,
  "how do I differentiate", "what positioning is available", messaging gap analysis, competitive
  messaging comparison, "where is the white space", brand positioning map, "how are competitors
  positioned", value proposition differentiation, perceptual mapping, or any request to find
  unclaimed positioning territory. Also trigger on "help me find my unique angle" or "what
  messaging isn't being used by competitors". Chains with voice-of-customer-miner for
  data-driven positioning.
---

# Positioning Whitespace Finder

Map your competitors' messaging across key positioning dimensions to find unclaimed territory. Produces a positioning map showing saturated zones and whitespace opportunities with specific messaging recommendations.

## Granularity Check

> Can this be completed in a single 10-minute Claude session? **Yes.** Input is competitor descriptions or URLs (Claude analyzes provided content). Output is an HTML positioning map + gap analysis document.

## User Intent Mapping

Trigger when the user says:

- "Find positioning whitespace in my market" (direct request)
- "How are my competitors positioned?" (competitive landscape)
- "What messaging is nobody using?" (whitespace discovery)
- "Help me differentiate my product" (differentiation)
- "Map the competitive positioning landscape" (visualization)
- "Where can I position my brand uniquely?" (strategy)
- "Analyze competitor messaging for gaps" (gap analysis)
- "Everyone in my market sounds the same — help me stand out" (sameness problem)
- "Build a positioning map for my category" (perceptual map)
- "What value proposition would be unique?" (VP development)

## Input Contract

### Required Input

| Field | Type | Description |
|---|---|---|
| `your_product` | text | Your product description, key features, target audience |
| `competitors` | list | 3-7 competitor names with descriptions or website content |

### Optional Input

| Field | Type | Description |
|---|---|---|
| `competitor_content` | text | Copy-pasted competitor homepage/positioning text |
| `category` | string | Market category (e.g., "project management software") |
| `customer_insights` | text | VoC data or customer feedback (chains from voice-of-customer-miner) |
| `positioning_dimensions` | list | Specific axes to map (e.g., price, complexity, audience) |
| `current_positioning` | text | Your current tagline/messaging |

### Sample Input

```
Your product: ProjectFlow — project management SaaS for creative agencies.
Features: visual workflows, client portals, time tracking, resource allocation.

Competitors:
1. Monday.com — work management platform for any team
2. Asana — team collaboration and project tracking
3. Basecamp — simple project management and team communication
4. ClickUp — all-in-one productivity platform
5. Teamwork — project management for client work
```

### Input Validation Rules

1. Minimum 3 competitors for meaningful positioning analysis (5+ ideal)
2. The more competitor detail provided, the better the analysis
3. If only names provided, Claude works with publicly known positioning
4. Flag if all competitors are in different sub-categories (positioning map will be broad)

## Process

1. **Extract messaging dimensions** — Analyze competitor content to identify the 4-6 key positioning axes in this market:
   - Common dimensions: price (affordable ↔ premium), audience (SMB ↔ enterprise), complexity (simple ↔ powerful), approach (specialist ↔ generalist), value (efficiency ↔ creativity), support (self-serve ↔ high-touch)
   - Category-specific dimensions emerge from competitor language

2. **Map each competitor** — For each competitor, score on each dimension (1-10) based on their messaging emphasis:
   - Analyze headlines, taglines, feature emphasis, pricing language, customer testimonials
   - Note: this maps *messaging*, not actual product capabilities

3. **Identify patterns:**
   - **Saturated zones** — Where 3+ competitors cluster (everyone claims "easy to use")
   - **Contested zones** — Where 2 competitors compete head-to-head
   - **Whitespace** — Positioning combinations nobody claims
   - **Contradictions** — Dimensions rarely combined (e.g., "enterprise-grade + incredibly simple")

4. **Score whitespace opportunities** — For each gap:
   - Market demand signal (do customers want this combination?)
   - Credibility fit (can your product credibly claim this?)
   - Defensibility (is this hard for competitors to copy?)
   - Distinctiveness (how different is this from current market?)

5. **Generate positioning recommendations:**
   - Top 3 whitespace opportunities with specific messaging language
   - "Don't go here" warnings for saturated positioning
   - Tagline options for each whitespace opportunity
   - Message hierarchy: primary position → supporting messages

6. **Human checkpoint** — Present the positioning map. Ask: "Do these competitor placements look accurate? Are there ≥2 clear whitespace opportunities?"

7. **Generate output** — HTML positioning map + Markdown strategy document.

## Output Contract

### Output Format

| Output | Format | Contents |
|---|---|---|
| Positioning map | HTML | Interactive 2D map with competitor plots |
| Gap analysis | Markdown | Whitespace opportunities + recommendations |

### Positioning Map Structure

The HTML output includes:
- 2D scatter plot with competitor logos/names plotted on primary axes
- Color-coded zones (green = whitespace, red = saturated, yellow = contested)
- Your product plotted (current position + recommended position)
- Toggle between different axis pairs

### Gap Analysis Structure

```markdown
# Positioning Whitespace Analysis
Category: [market category]
Competitors analyzed: [N]

## Positioning Dimensions Identified
1. [Dimension A]: [low end] ←→ [high end]
2. [Dimension B]: [low end] ←→ [high end]
...

## Competitor Map
| Competitor | Dim A | Dim B | Dim C | Dim D | Core Message |
|---|---|---|---|---|---|
| Monday.com | 7 | 8 | 6 | 5 | "Where teams get work done" |
...

## Saturated Zones (Avoid)
### "Easy + Affordable" (4 competitors here)
[Why this is crowded. Which competitors. Why it's hard to win here.]

## Whitespace Opportunities
### Opportunity 1: [Name] (Score: 8.5/10)
**Position:** [dimension combination]
**Why it's open:** [analysis]
**Credibility for you:** [fit assessment]
**Recommended messaging:**
- Tagline option A: "[tagline]"
- Tagline option B: "[tagline]"
- Supporting messages: [list]

[Repeat for top 3 opportunities]

## Recommended Positioning Strategy
**Primary position:** [recommended whitespace]
**Message hierarchy:**
1. [Primary claim]
2. [Supporting proof point]
3. [Differentiator]
**Avoid saying:** [saturated claims to stay away from]
```

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Too few competitors (<3) | Niche market | Proceed but note limited map; suggest adding adjacent competitors |
| All competitors same positioning | Commoditized market | Every position is whitespace — focus on most credible for your product |
| No clear whitespace | Crowded, mature market | Look for positioning *combinations* or niche audience positioning |
| Competitors in different categories | Apples-to-oranges comparison | Define a shared category; compare on relevant dimensions only |
| No product details for your company | User hasn't shared | Ask for product description — needed to assess credibility fit |

## How to Get Your Data

### From Competitor Websites

1. Visit each competitor's homepage and product page
2. Copy their headline, subheadline, key benefit statements, and pricing page header
3. Paste all competitor content into Claude with labels

### From Review Sites

1. Check G2, Capterra, or TrustRadius for your category
2. Note how each competitor is described in their profile and top reviews
3. Share summaries with Claude

### From Voice of Customer Miner (Best Path)

1. Run voice-of-customer-miner first to understand what customers actually want
2. Combine customer language with competitor positioning
3. Find whitespace that aligns with real customer demand

### From Sales Experience

1. Describe how you win deals vs. each competitor
2. Share objection patterns ("they went with X because...")
3. Claude maps this intelligence to positioning dimensions

## Example

**User prompt:** "I run a project management tool for creative agencies. Compare my positioning against Monday.com, Asana, Basecamp, ClickUp, and Teamwork."

**Claude responds:**

> Analyzed 5 competitors across 4 positioning dimensions:
>
> **Dimensions identified:**
> 1. Audience: Generalist ←→ Specialist
> 2. Complexity: Simple ←→ Feature-rich
> 3. Brand: Corporate ←→ Creative
> 4. Pricing: Affordable ←→ Premium
>
> **Saturated zone (avoid):** "Easy team collaboration for any team" — Monday, Asana, and ClickUp all compete here.
>
> **Whitespace opportunities:**
>
> 1. **"Creative Specialist + Premium" (Score: 9/10)**
>    No competitor specifically positions for creative agencies with premium positioning. Teamwork is close but generic.
>    → Tagline: "Project management built for creative teams that deliver exceptional work"
>
> 2. **"Simple + Specialist" (Score: 7/10)**
>    Basecamp is simple but general. Nobody combines simplicity with creative-agency specialization.
>    → Tagline: "The refreshingly simple PM tool for agencies"
>
> 3. **"Feature-rich + Creative Brand" (Score: 6/10)**
>    ClickUp is feature-rich but corporate. There's space for a feature-rich tool with a creative personality.
>
> **Recommendation:** Go with Opportunity 1. Your client portals and resource allocation features support a premium, specialist position that none of the 5 competitors can credibly claim.
