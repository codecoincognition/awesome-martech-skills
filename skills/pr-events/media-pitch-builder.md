---
name: media-pitch-builder
description: >
  Craft personalized media pitches that get journalist attention and secure press coverage.
  Use this skill when the user says "media pitch", "pitch to journalists", "press pitch template",
  "how to pitch media", "journalist outreach", "PR pitch optimization", "media relations pitch",
  "story angle for press", "pitch email to reporter", "press outreach strategy", or "get media
  coverage". Also trigger for media list building, pitch personalization, or press pitch follow-up strategy.
---

# Media Pitch Builder

Crafts personalized, newsworthy media pitches tailored to specific journalists, outlets, and story angles that maximize response rates and press coverage.

## Granularity Check

> **Time**: ~5 min data prep → ~10 min Claude session → ~20-45 min sending / implementing. If building a full media outreach campaign, add 1-2 weeks for research, pitching, and follow-up. Input is your news, target journalists/outlets, and story angle. Output is Markdown pitch strategy with personalized pitch templates, follow-up sequence, and media list guidance.

## User Intent Mapping

- "Write a pitch to get press coverage" (pitch)
- "How to pitch journalists" (strategy)
- "Media pitch for our product launch" (launch)
- "PR outreach email template" (template)
- "Personalize pitch for specific reporter" (personalization)
- "Story angles for media coverage" (angles)
- "Follow-up strategy after pitching media" (follow-up)
- "Build a media list for outreach" (media list)
- "Why aren't journalists responding to our pitches?" (diagnosis)
- "Pitch for thought leadership placement" (thought leadership)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| News/Story | Text | What you want covered (announcement, data, perspective) |
| Target Audience | Text | Which publications or journalists you want to reach |
| Company Context | Text | Who you are and why this matters |

### If You Don't Have This Data

- **No media contacts?** Claude helps you identify the right journalists and outlets based on your story, industry, and target audience — plus recommends tools for building media lists.
- **Not sure if your story is newsworthy?** Claude evaluates your angle against news value criteria and suggests stronger framing or alternative angles.
- **No PR experience?** Claude provides the full pitch framework — subject line, opening, body, CTA — with personalization templates.
- **No existing media relationships?** Claude designs a cold pitch strategy with specific personalization tactics that work without prior relationships.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Journalist Names | Text | Specific journalists you want to pitch |
| Past Coverage | Text | Previous media coverage of your company |
| Data/Research | Text | Unique data points or research findings |
| Competing Stories | Text | What competitors are getting covered for |
| Timing | Text | Relevant news hooks or timely angles |

## Process

### Step 1: Newsworthiness Assessment

| Criteria | Description | Score (1-5) |
|---|---|---|
| Timeliness | Is this connected to current events or trends? | |
| Impact | How many people does this affect? | |
| Novelty | Is this genuinely new or different? | |
| Conflict/Tension | Does this challenge conventional wisdom? | |
| Human interest | Is there an emotional or relatable story? | |
| Data | Do you have unique numbers or research? | |
| Prominence | Are notable people or brands involved? | |

Score 25+: Strong pitch. Score 15-24: Needs stronger angle. Below 15: Reconsider pitching.

### Step 2: Story Angle Development

| Angle Type | Best For | Example |
|---|---|---|
| Trend story | Positioning as industry expert | "3 shifts in [industry] that will define 2026" |
| Data/research | Unique findings or surveys | "[X]% of [audience] now [behavior] — here's why" |
| Counter-narrative | Challenging assumptions | "Everyone says [X], but our data shows [Y]" |
| Problem/solution | Product or service launch | "The hidden cost of [problem] and how to fix it" |
| Founder story | Company profiles, features | "From [origin] to [achievement]: how [founder] built [company]" |
| Customer success | Case study-driven coverage | "How [customer] achieved [result] in [timeframe]" |
| Expert commentary | Reactive/newsjacking | "What [breaking news] means for [your industry]" |

### Step 3: Pitch Structure

| Element | Length | Purpose | Example |
|---|---|---|---|
| Subject line | 6-10 words | Get the open | "[Data point]: [Implication]" |
| Opening line | 1 sentence | Show you know their work | Reference their recent article or beat |
| The hook | 2-3 sentences | Why this matters NOW | Connect to trend, data, or timely event |
| The story | 3-5 sentences | What you're offering | Concise story with key facts/data |
| The ask | 1-2 sentences | What you want | Interview, exclusive, comment opportunity |
| Sign-off | 1 sentence | Make it easy to say yes | Availability and contact method |

Total pitch length: 150-250 words maximum.

### Step 4: Personalization Framework

| Personalization Level | Tactic | Time Investment | Response Rate Lift |
|---|---|---|---|
| Level 1 (basic) | Use journalist's name, reference their outlet | 2 min | +20% |
| Level 2 (relevant) | Reference a specific recent article they wrote | 5 min | +40% |
| Level 3 (insightful) | Connect your story to a theme they've been covering | 10 min | +60% |
| Level 4 (relationship) | Reference a previous conversation or shared connection | 15 min | +80% |

Personalization rules:
- Never pitch a journalist who doesn't cover your topic
- Reference their most recent relevant article (not one from 2 years ago)
- Explain why YOUR story fits THEIR beat specifically
- Never use generic openings like "I'm reaching out because..."

### Step 5: Follow-Up Sequence

| Touchpoint | Timing | Channel | Content |
|---|---|---|---|
| Initial pitch | Day 0 | Email | Full pitch with story angle |
| Follow-up 1 | Day 3-4 | Email | Brief reminder + new data point or angle |
| Follow-up 2 | Day 7-8 | Email or Twitter/X | Short "still relevant" note + timely hook |
| Move on | Day 14 | — | Stop following up; pitch new angle later |

Follow-up rules:
- Maximum 2-3 follow-ups per pitch
- Each follow-up must add new value (not just "checking in")
- If no response after 3 touches, pitch is dead — move to new angle or outlet
- Never follow up same day or next business day

### Step 6: Pitch Performance Tracking

| Metric | Target | Action if Below |
|---|---|---|
| Open rate | 40-60% | Improve subject lines |
| Response rate | 10-20% | Better personalization and angle |
| Coverage rate | 5-10% of pitches | Improve targeting and newsworthiness |
| Positive coverage | 80%+ of coverage | Better story preparation and spokesperson training |

### Confidence & Sample Size

> **Confidence Note**: Average PR pitch response rate is 3-5% for mass pitches and 15-25% for personalized pitches — personalization is the single biggest factor in pitch success. Journalists receive 50-100+ pitches per day — your subject line has 2-3 seconds to earn an open. Pitches sent Tuesday-Thursday between 6-10am in the journalist's timezone get the highest response rates. Exclusive offers (giving one outlet the story first) increase coverage probability by 30-50% for major announcements. 85% of successful pitches are under 200 words.

### ⚠️ Human Checkpoint
> Have your spokesperson or company leadership review all pitches before sending — especially for sensitive topics, financial data, or competitive claims. Verify all data points and claims in the pitch are accurate and attributable. Ensure your story timing doesn't conflict with major industry events or competing news.

> **Benchmark Context**: 75% of journalists say they prefer pitches under 200 words (Cision 2024 State of the Media Report). 68% say personalization is the most important factor in whether they read a pitch. Only 3% of pitches result in coverage — the rest are ignored or declined. Journalists are most responsive to pitches with original data or research (28% response rate vs. 6% for product announcements. Morning pitches (6-10am) get 2x the response rate of afternoon pitches. (Cision 2024 State of the Media Report).
## Output Contract

### Deliverable: Markdown Pitch Strategy

```markdown
# Media Pitch Strategy: [Story/Announcement]

## Story Assessment
- Newsworthiness score: [X/35]
- Primary angle: [description]
- Alternative angles: [list]
- Timing hook: [why now]

## Target Media
| Outlet | Journalist | Beat | Why They'd Care | Priority |
|---|---|---|---|---|

## Pitch Template
### Subject Line Options
1. [option 1]
2. [option 2]
3. [option 3]

### Pitch Body
[Full pitch text — personalization placeholders marked]

## Follow-Up Sequence
| Day | Action | Content |
|---|---|---|

## Supporting Materials
- Data points: [key stats to offer]
- Visuals: [images, infographics available]
- Spokesperson: [who's available for interview]
- Exclusives: [what can be offered exclusively]

## Success Metrics
| Metric | Target |
|---|---|
```

## Platform Implementation Steps

### Media List Building
1. Identify 10-20 target outlets based on your audience and story type
2. Find specific journalists who cover your beat (use Muck Rack, Cision, or manual research)
3. Read their last 5-10 articles to understand their angle and interests
4. Find their preferred contact method (email, Twitter DM, LinkedIn)
5. Organize media list by priority tier (Tier 1: dream outlets, Tier 2: likely hits, Tier 3: long shots)

### Pitch Execution
1. Personalize each pitch using the framework (no mass emails)
2. Send pitches Tuesday-Thursday, 6-10am in journalist's timezone
3. Track opens and responses (use email tracking tool)
4. Follow up per the sequence (Day 3-4, Day 7-8)
5. Log all interactions in a PR CRM or spreadsheet

### Post-Coverage
1. Thank the journalist (brief, genuine email)
2. Share the coverage across your channels (social, email, website)
3. Add the outlet/journalist to your ongoing media relationships list
4. Send them relevant stories in the future (maintain the relationship)
5. Track coverage impact (traffic, leads, brand mentions)

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| No responses | Mass pitch, not personalized, weak angle | Research journalists, personalize, strengthen angle |
| Wrong journalist | Pitched someone who doesn't cover your beat | Verify journalist's beat before pitching; read their work |
| Coverage but wrong message | Didn't prepare spokesperson or talking points | Create key messages and talking points before any pitch |
| Burned journalist relationship | Followed up too aggressively or pitched non-story | Respect their time; only pitch genuinely newsworthy stories |

## How to Get Your Data

- **Media contacts**: Muck Rack, Cision, or manually research journalists on Twitter/LinkedIn
- **Journalist interests**: Read their last 5 articles to understand what they cover and how they frame stories
- **Pitch performance**: Email tracking tools (Mailtrack, HubSpot, Mixmax) to monitor opens and clicks
- **No contacts yet**: Describe your story — Claude identifies outlet types and beat descriptions to guide your research

## Example

**Input**: "Media pitch for our AI startup's new report: 'State of AI Adoption in Small Business 2026.' Surveyed 2,000 small business owners. Key finding: 62% now use AI tools daily, up from 18% in 2024. We want coverage in business and tech media."

**Output**: Newsworthiness: HIGH (original data, strong trend, broad impact). Primary angle: "Small businesses are adopting AI 3x faster than predicted — and it's changing how America works." Pitch targets: Tier 1: Forbes (SMB reporter), Business Insider (AI reporter), TechCrunch (AI section). Tier 2: Inc., Fast Company, VentureBeat, Axios. Tier 3: Industry-specific outlets (Entrepreneur, SmallBizTrends). Subject line options: (1) "62% of small businesses now use AI daily — new data" (2) "Small business AI adoption up 244% since 2024 [exclusive data]" (3) "2,000 SMBs surveyed: AI is no longer enterprise-only." Pitch (150 words): "[Name], I noticed your recent piece on [topic] — the data from our new report might add to your coverage. We surveyed 2,000 small business owners and found 62% now use AI tools daily, up from 18% in 2024 — a 244% increase in two years. The report reveals which tools they're using, what's driving adoption, and where they're seeing ROI (average: $12K/year in time savings). The full report includes industry breakdowns, regional data, and adoption barriers. I can offer you early access to the data before public release on [date] and make our CEO available for an interview. Would this be useful for an upcoming piece? Best, [Name]." Follow-up Day 3: share one additional data point not in the original pitch.

## Related Skills

- **[Press Release Writer](./press-release-writer.md)** — Use after successful pitch to draft formal press release with journalist.
- **[Campaign Angle Generator](../insights/campaign-angle-generator.md)** — Generate compelling story angles before pitching to media contacts.
- **[Market Trend Scanner](../insights/market-trend-scanner.md)** — Identify newsy market trends to pitch to journalists as story angles.
- **[Crisis Comms Playbook](./crisis-comms-playbook.md)** — Use media pitching to proactively shape narrative during reputation challenges.
