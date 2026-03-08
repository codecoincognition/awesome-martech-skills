---
name: Voice of Customer Miner
description: "Extract real customer insights from Reddit discussions. Want to know what customers actually think about your product category? Need to find customer pain points and frustrations? Looking for buying triggers and decision-making language? Want to understand emotional drivers in your market? Analyzing competitor sentiment on Reddit? Need to identify messaging opportunities from customer language? Searching for product feature requests? Want to discover underserved customer segments? Finding authenticity in customer needs discussion? Mining Reddit for content inspiration? This skill analyzes target subreddit discussions over 90 days to extract customer insights, pain points, buying triggers, emotional language patterns, objection themes, and messaging opportunities with verbatim quotes and trend analysis."
---

## User Intent Mapping

| User Says | Underlying Need |
|-----------|-----------------|
| "What do customers really say?" | Mining authentic voice-of-customer from Reddit |
| "Find pain points in our market" | Identify frustration themes and problem statements |
| "What makes people buy?" | Extract buying triggers and decision drivers |
| "How do customers talk about this?" | Emotional language and authenticity of customer language |
| "Competitor sentiment on Reddit?" | Monitor how people discuss competing solutions |
| "What objections do they raise?" | Identify barriers and concerns in decision process |
| "Message inspiration from customers?" | Extract resonant language and metaphors from customer posts |
| "Find underserved segments?" | Identify customer needs not being addressed |
| "Product feature requests?" | Discover requested features and functionality gaps |
| "Content ideas from Reddit?" | Identify FAQ topics and discussion themes for content |

## Input Contract

**Required Fields (Form):**
| Field | Type | Description | Example |
|-------|------|-------------|---------|
| `target_subreddits` | list | 2-5 subreddit communities to analyze | r/startups, r/marketing, r/SaaS |
| `keywords` | list | 3-7 product/industry keywords to search | "marketing automation", "lead generation", "CRM" |
| `industry` | text | Industry/category | "SaaS MarTech" |
| `time_period` | select | Data window | "Last 90 days" (fixed) |
| `product_or_category` | text | Are you researching your product or category? | "Category: Marketing automation platforms" or "Product: HubSpot" |

**Optional Fields:**
| Field | Type | Example |
|-------|------|---------|
| `competitor_names` | list | Specific competitors to monitor | "HubSpot, Pipedrive, Salesforce" |
| `reddit_urls` | list | Specific Reddit threads to dive deep on | "reddit.com/r/startups/comments/..." |
| `user_segments` | list | Specific audience segments to focus on | "Bootstrapped founders", "Freelance marketers" |
| `emotional_tone_analysis` | checkbox | Include sentiment/emotional language tracking? | true/false |

**Validation Rules:**
- Target subreddits: 2-5 communities minimum
- Keywords: 3-7 terms, relevant to industry
- Industry: non-empty text, <100 chars
- Time period: Fixed to "Last 90 days" (Reddit API/web limitations)
- Product or category: Clear scope (specific product vs. broader category)
- Subreddit names: Valid subreddit format (r/[name])

**Sample Input:**
```
Target Subreddits:
  - r/marketing
  - r/SaaS
  - r/startups
  - r/smallbusiness

Keywords:
  - Marketing automation
  - Lead generation
  - Email campaigns
  - Customer relationship management

Industry: MarTech SaaS

Time Period: Last 90 days (2026-01-15 to 2026-04-15)

Product or Category: Category (Marketing Automation Solutions)

Competitor Names:
  - HubSpot
  - Pipedrive
  - Mailchimp
  - ActiveCampaign

Emotional Tone Analysis: Yes

User Segments:
  - Bootstrapped founders
  - Freelance marketers
  - Small business owners (1-50 employees)
```

## Process

1. **Subreddit Selection & Validation**
   - Confirm 2-5 target subreddits are active and relevant
   - Validate subreddit has healthy discussion (1000+ members, regular posts)
   - Check subreddit rules allow product discussion (not banned)
   - Assess audience demographic fit with target customer
   - **Human Checkpoint:** Approve target subreddits and rationale

2. **Keyword & Query Strategy**
   - Create search queries combining keywords (e.g., "marketing automation" OR "email campaigns")
   - Set time filter: Last 90 days
   - Plan competitor-specific searches (optional)
   - Identify emotion-focused searches ("frustrated with X", "love Y")
   - **Human Checkpoint:** Review keyword search strategy

3. **Reddit Web Search & Thread Collection**
   - Conduct web searches for each subreddit + keyword combination
   - Collect 40-60 relevant Reddit threads/discussions
   - Prioritize threads with 50+ comments (signal of active discussion)
   - Filter for human discussion (exclude bots, promotions)
   - **Human Checkpoint:** Confirm thread sample size and relevance

4. **Content Analysis & Extraction**
   - Extract verbatim quotes (10-15 per insight category)
   - Identify pain points: frustrations, complaints, blockers mentioned
   - Identify buying triggers: moments of intent, decision drivers
   - Extract emotional language: metaphors, intensity, authentic phrasing
   - Flag objections: concerns, hesitations, deal-breakers
   - **Human Checkpoint:** Validate quote accuracy and categorization

5. **Theme Identification & Clustering**
   - Group pain points into 4-6 dominant themes
   - Rank themes by frequency and intensity
   - Identify buying triggers associated with each pain point
   - Map objections to buying journey stage (awareness/consideration/decision)
   - Note underserved needs (mentioned but no solution discussed)
   - **Human Checkpoint:** Review theme clustering and accuracy

6. **Sentiment & Language Pattern Analysis**
   - Analyze emotional tone: frustration, enthusiasm, skepticism
   - Identify resonant language and metaphors used by customers
   - Extract decision-making language ("We chose X because...")
   - Map sentiment across competitor mentions (if applicable)
   - **Human Checkpoint:** Validate emotional analysis authenticity

7. **Messaging Opportunity Mapping**
   - Connect each pain point to potential value prop
   - Extract messaging angles from customer language
   - Identify objection rebuttals from threads where solved
   - Suggest content topics based on FAQ themes
   - Note content format preferences (threads, guides, comparisons)
   - **Human Checkpoint:** Review messaging recommendations

8. **XLSX Report Generation**
   - Compile insights into sortable matrix
   - Create theme summary sheet
   - Generate verbatim quote library
   - Output actionable recommendations

## Output Contract

**Markdown Insight Report Structure:**

```markdown
# Voice of Customer Report: [Industry/Category]
**Data Source:** [Subreddit names], 90 days (Jan 15 - Apr 15, 2026)
**Threads Analyzed:** 52 | **Quotes Extracted:** 127 | **Themes Identified:** 6

---

## Executive Summary

[2-3 paragraph overview of customer landscape, dominant pain points, buying drivers, and messaging opportunities]

---

## Pain Point Themes (Ranked by Frequency)

### Theme 1: [Pain Point Name] — 28% of discussions

**Definition:** [What problem customers describe]

**Verbatim Quotes:**
- "I'm spending 20 hours/week manually importing data into our CRM." — u/StartupFounder92 (r/startups, 47 upvotes)
- "The data entry alone is killing our productivity." — u/FrazzledMarketer (r/marketing, 62 upvotes)
- "We have no idea which campaigns actually convert because attribution is impossible." — u/DemandGenLead (r/SaaS, 38 upvotes)

**Context:** This pain point emerges early in customer journey (awareness), usually triggers search for automation solutions.

**Buying Trigger:** When manual process becomes >15 hours/week, customers actively seek solutions.

**Emotional Intensity:** Frustration (evident in language: "killing", "impossible", "wasting time")

**Messaging Angle:** "Reclaim 20 hours/week with automated data sync"

---

### Theme 2: [Pain Point Name] — 22% of discussions

[Repeat structure above]

---

## Buying Triggers & Decision Drivers

| Trigger | Evidence | Recommended Messaging |
|---------|----------|----------------------|
| Manual data entry becomes 15+ hrs/week | "I'm drowning in spreadsheets" (frequent quote) | "Automate the busywork, focus on strategy" |
| Scaling to 50+ customers | "We hired 2 salespeople and everything broke" | "Built for scale from day one" |
| Lost deal due to poor follow-up | "We forgot about half our leads in the pipeline" | "Never lose track of a prospect again" |

---

## Objections & Concerns (By Decision Stage)

### Awareness Stage
- **Objection:** "Is this even necessary? Can't I just use Mailchimp?" (11 mentions)
  - **Rebuttal insight:** Customers later mention Mailchimp limitations; frame as "Mailchimp starter, [your product] for scale"
  - **Quote:** "We outgrew Mailchimp's automation after 6 months." — u/GrowthHacker (r/SaaS, 73 upvotes)

### Consideration Stage
- **Objection:** "It's too complicated for my small team." (8 mentions)
  - **Rebuttal insight:** Customers praise ease-of-use and onboarding support
  - **Quote:** "I was worried about implementation but their support made it painless." — u/SmallBizOwner (r/smallbusiness, 41 upvotes)
- **Objection:** "We can't afford another SaaS subscription." (14 mentions)
  - **Rebuttal insight:** ROI language ("saves me $500/month in developer time") resonates
  - **Quote:** "It paid for itself in Week 2." — u/BootstrapFounder (r/startups, 156 upvotes)

### Decision Stage
- **Objection:** "Does it integrate with our stack?" (19 mentions, highest concern)
  - **Rebuttal insight:** Integration roadmap and native API access key
  - **Quote:** "We needed Zapier, which added cost and complexity." — u/IntegrationHeadache (r/SaaS, 29 upvotes)

---

## Emotional Language & Authenticity Patterns

**Frustration Language (Indicator of Pain Intensity):**
- "Drowning in", "killing our productivity", "impossible", "nightmare"
- Presence of capitalization and exclamation marks: "This is KILLING us!"
- Use of extreme comparisons: "like herding cats", "Sisyphean task"

**Enthusiasm Language (Indicator of Solution Success):**
- "Game-changer", "best decision we made", "literally saved us"
- Specific ROI language: "Paid for itself in 2 weeks", "saved 15 hours/week"
- Recommendation language: "Highly recommend", "wish we'd done this sooner"

**Skepticism Language (Indicator of Valid Objections):**
- "Seems like", "if it actually works", "too good to be true"
- Budget-focused: "Can't justify the cost", "too expensive for what we get"
- Adoption-focused: "Our team refuses to learn another tool"

---

## Competitor Mentions & Sentiment Analysis

| Competitor | Mention Count | Sentiment | Context |
|------------|---------------|-----------|---------|
| HubSpot | 47 | Mixed-Positive | Praised for all-in-one, criticized for complexity + pricing |
| Pipedrive | 23 | Positive | Loved for ease, criticized for limited automation |
| Mailchimp | 31 | Mixed | Good for email, limited for sales automation |
| Zapier | 18 | Positive | Loved for flexibility, criticized for setup complexity |

**Key Insight:** Customers choosing between "full-featured but complex" (HubSpot) vs. "simple but limited" (Pipedrive). Gap: easy + powerful.

---

## Messaging Opportunities

### Primary Value Prop (from "buying trigger" language)
"Eliminate manual data work. Scale your team without scaling chaos."
- **Resonance Metric:** This phrasing appears in 12+ customer quotes organically
- **Test:** A/B vs. "Unified CRM and marketing automation platform"

### Secondary Messages

#### For Consideration Stage (Objection: "Is it easy to use?")
"90% of users productive within 3 days"
- Source: Actual quote: "The onboarding was surprisingly smooth." (41 upvotes)
- Supports: Overcomes complexity objection

#### For Comparison Stage (vs. HubSpot)
"All the power, none of the learning curve"
- Source: "HubSpot is like drinking from a firehose." vs. "This was intuitive from day one."
- Supports: Ease vs. feature depth comparison

#### For Cost-Conscious (Objection: "Too expensive")
"Pays for itself in 2-3 weeks through time savings"
- Source: "Saved us $500/month in developer time" (multiple mentions)
- Supports: ROI reframing

### Content Topic Opportunities (from FAQ themes)
- **"HubSpot vs. [Your Product]: Which should startups choose?"** — 14 threads comparing
- **"How to migrate 10,000 contacts without losing data"** — 8 implementation questions
- **"Best CRM for bootstrapped startups (< $3k/month spend)"** — 11 budget-focused discussions
- **"Does [your product] integrate with Zapier/Slack/etc?"** — 19 integration questions
- **"Onboarding timeline and learning curve"** — 7 adoption concern threads

---

## Underserved Needs (Not Yet Discussed Solutions)

- **AI-powered lead scoring** (mentioned as pain, no solution suggested) — 6 mentions
- **API-first approach for developers** (implied need from integration requests) — 12 mentions
- **ROI dashboard/reporting** (mentioned as missing feature in competitors) — 8 mentions
- **Mobile-first sales tools** (referenced as gap compared to desktop solutions) — 5 mentions

---

## Actionable Recommendations

1. **Messaging Priority:** Lead with "eliminate manual data work" before feature parity. Customers repeat this pain 3x more than feature comparisons.

2. **Content Gap:** Create "HubSpot vs. [Your Product]" comparison guide targeting Pipedrive + Mailchimp customers. High search intent.

3. **Objection Prep:** Sales should emphasize 3-day productivity timeline and specific ROI ($500+ developer time savings). Data points appear in 8 successful conversion stories.

4. **Positioning:** Own the "simple + powerful" space vs. HubSpot (complex) and Pipedrive (limited). This gap mentioned in 11 independent threads.

5. **Feature Roadmap:** Prioritize AI-powered lead scoring and mobile sales tools. Underserved needs mentioned in 17 combined threads.

---
```

**XLSX Theme Matrix:**

| Theme Name | Pain Point | Buying Trigger | Objection | Messaging Angle | Content Opportunity | Mention Count | Sentiment |
|-----------|-----------|-----------------|-----------|-----------------|---------------------|---------------|-----------|
| Manual Data Overload | 20 hrs/week spreadsheets | > 15 hrs/week work | "Is it easy?" | "Eliminate busywork" | "Time savings ROI guide" | 28 | Frustration |
| Attribution Chaos | Can't track conversions | Losing deals | "Too expensive" | "Know what works" | "Attribution 101 for startups" | 22 | Skepticism |
| Integration Headaches | Manual API integrations | Need Zapier layers | "Does it integrate?" | "Native integrations out of box" | "Integration roadmap" | 19 | Mixed |

**XLSX Quote Library:**

| Theme | Quote | Source | Upvotes | Emotional Tone | Use Case |
|-------|-------|--------|---------|---------------|---------|
| Manual Data | "I'm drowning in spreadsheets, literally 20 hrs/week" | u/StartupFounder92, r/startups | 47 | High frustration | Awareness messaging |
| Manual Data | "Paid for itself in 2 weeks" | u/BootstrapFounder, r/startups | 156 | High enthusiasm | Cost objection rebuttal |
| Integration | "We needed Zapier which cost extra and broke constantly" | u/IntegrationHeadache, r/SaaS | 29 | Frustration | Competitive positioning |

## Failure Modes

| Scenario | Symptom | Resolution |
|----------|---------|------------|
| Insufficient data | <20 threads found after searching | Expand keywords; broaden subreddits (add r/business, r/EntrepreneurRidiculousness); note limitation in report; offer 60-day analysis |
| Subreddit too niche | Subreddit has <500 members or <1 post/day | Replace with related subreddit; ask user for alternative communities; note audience limitation |
| No relevant discussions | Keywords return zero results in target subreddits | Suggest alternative keywords; check subreddit rules (may ban product discussion); recommend 1-2 new subreddits |
| Quotes seem inauthentic | Extracted quotes sound promotional or fake | Flag for manual review; remove bot-detected posts; re-verify quote accuracy via Reddit URL |
| Competitor visibility | Target competitor not mentioned in subreddits | Note as "competitor not discussed in Reddit" — may indicate low awareness; suggest indirect comparison messaging |
| Trend too recent | Data shows emerging trend but insufficient evidence | Flag as "emerging insight" with lower confidence; recommend 30-day re-analysis; note sample size limitation |

## How to Get Your Data

**Subreddit Discovery (By Industry):**

**SaaS/B2B:**
- r/SaaS, r/startups, r/Entrepreneur, r/marketing, r/webdev, r/smallbusiness

**E-commerce:**
- r/ecommerce, r/shopify, r/Entrepreneur, r/smallbusiness, r/businessideas

**Freelance/Agency:**
- r/freelance, r/marketing, r/web_design, r/BusinessIntelligence, r/digital_marketing

**Health & Wellness:**
- r/Health, r/fitness, r/loseit, r/nutrition, r/running, r/bodyweightfitness

**Finance:**
- r/personalfinance, r/investing, r/stocks, r/CryptoCurrency, r/financialcareers

**Real Estate:**
- r/RealEstate, r/investing, r/Entrepreneur, r/HomeImprovement

**Manual Search Tips:**
1. Visit subreddit URL: reddit.com/r/[subreddit_name]
2. Use search bar: [keyword] (filters to that subreddit)
3. Sort by: "Top past 90 days" or "New" + "past 3 months"
4. Open threads with 50+ comments (signal of active discussion)
5. Copy/paste discussion and key quotes into XLSX

**Web Search Optimization:**
- Reddit: `"[keyword]" site:reddit.com/r/[subreddit] 2026`
- Google: `[keyword] reddit [subreddit] last 3 months`
- Example: `"marketing automation" site:reddit.com/r/SaaS 2026`

**Reddit Thread Collection Template (Save URLs):**
- r/SaaS — "What's the best marketing automation for small teams?" (52 comments)
- r/startups — "CRM tools for bootstrapped founders?" (147 comments)
- r/marketing — "I'm spending too much time on email campaigns" (83 comments)

## Full Example

**Scenario:** Sustainable beverage brand (EcoBlend) wants voice-of-customer insights from their market. Research goal: understand customer attitudes toward eco-friendly products, purchase barriers, and messaging opportunities.

**Input:**
```
Target Subreddits: r/sustainability, r/health, r/environment, r/StartupStories, r/smallbusiness

Keywords: Sustainable beverage, eco-friendly drinks, plant-based, organic, zero-waste packaging

Industry: Sustainable Consumer Products (Beverage)

Time Period: Last 90 days

Product: Category (Sustainable Beverage Market)

Competitor Names: Liquid IV, Olipop, MOJU Drinks, Essence Water

Emotional Tone Analysis: Yes
```

**OUTPUT HIGHLIGHTS:**

### Pain Point Theme 1: "Sustainability Guilt + Convenience Conflict" (26% of discussions)

**Verbatim Quotes:**
- "I want to buy eco-friendly but most 'sustainable' drinks taste like dirt." — u/HealthyLiving92 (r/health, 84 upvotes)
- "Every drink I love comes in plastic. It's guilt-inducing." — u/EcoMom42 (r/sustainability, 112 upvotes)
- "I'd pay more but I don't have 30 minutes to find a sustainable option at my local store." — u/BusyParent (r/smallbusiness, 67 upvotes)

**Buying Trigger:** Finding product that solves "taste + sustainability + convenience" simultaneously.

**Messaging Angle:** "Delicious. Sustainable. Available where you shop."

---

### Pain Point Theme 2: "Skepticism About Greenwashing" (18% of discussions)

**Verbatim Quotes:**
- "So many brands claim to be 'sustainable' but they're just doing the bare minimum." — u/SkepticalConsumer (r/sustainability, 156 upvotes)
- "I want to know the REAL impact. Where's the carbon footprint number?" — u/DataDrivenDecision (r/environment, 92 upvotes)

**Objection:** "Is this actually sustainable or just marketing?"

**Messaging Opportunity:** Show transparent metrics (carbon offset numbers, recycled % materials) upfront.

---

### Buying Trigger Mapping:

| Trigger | Evidence | Strength |
|---------|----------|----------|
| Taste + health benefits alignment | "Finally, healthy AND tasty" (38 mentions) | 38 |
| Visible sustainability proof | "Love seeing recycled % on label" (22 mentions) | 22 |
| Ease of access | "Available at Whole Foods near me" (16 mentions) | 16 |
| Peer recommendation | "My friend won't stop raving about it" (29 mentions) | 29 |

---

### Primary Messaging (Derived from Customer Language):

**Headline:** "Sustainable drinks that actually taste good."
- **Resonance:** This exact phrasing appeared in 14 independent comments
- **Validates:** Addresses core tension between taste + sustainability

**Sub-message:** "95% recycled. 100% delicious. Available where you shop."
- **Resonance:** Specificity (95% stat) and transparency appear in conversion stories

---

### Content Opportunities:

1. **"Is This Product Actually Sustainable? How We Audit Green Claims"** — 19 threads questioning greenwashing
2. **"Best Eco-Friendly Drinks for Athletes/Health Goals"** — 14 threads comparing options
3. **"Where to Buy Sustainable Drinks Near You (Store Locator)"** — 12 convenience/access questions
4. **"Our Carbon Footprint: Full Transparency Report"** — 22 requests for sustainability proof
5. **"Plant-Based vs. Conventional: Taste Blind Taste Test"** — 7 threads comparing taste perception

---

**Next Steps:**
- Create "product taste comparison" content addressing skepticism
- Build transparent sustainability dashboard (carbon offset, recycled %)
- Emphasize Whole Foods distribution in marketing (addresses convenience pain)
- Use "delicious AND sustainable" messaging in all campaigns
- Develop "greenwashing audit" blog to build trust vs. competitors
