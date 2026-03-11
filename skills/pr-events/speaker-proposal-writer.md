---
name: speaker-proposal-writer
description: >
  Write compelling conference speaking proposals and CFP (call for papers) submissions that get accepted.
  Use this skill when the user says "conference speaking proposal", "CFP submission", "call for papers
  response", "speaker proposal for conference", "speaking abstract", "conference talk submission",
  "session proposal writing", "keynote pitch", "panel proposal", "speaking opportunity application",
  or "how to get accepted as a conference speaker". Also trigger for speaker bio writing, talk title
  optimization, or speaking portfolio development.
---

# Speaker Proposal Writer

Writes compelling conference speaking proposals optimized for CFP (call for papers) review committees, with talk title development, abstract writing, and speaker positioning.

## Granularity Check

> **Time**: ~5 min data prep → ~10 min Claude session → ~20-45 min sending / implementing per proposal. If applying to multiple conferences, add 15-20 min per CFP customization. Input is talk topic, speaker background, and target conference. Output is Markdown speaking proposal with title options, abstract, learning objectives, and speaker bio.

## User Intent Mapping

- "Write a speaking proposal for a conference" (proposal)
- "CFP submission help" (CFP)
- "Compelling talk title ideas" (title)
- "Conference abstract writing" (abstract)
- "How to get accepted as a speaker" (strategy)
- "Panel discussion proposal" (panel)
- "Workshop proposal for conference" (workshop)
- "Speaker bio for conference" (bio)
- "Tailor my talk to this conference's theme" (customization)
- "Lightning talk proposal" (lightning)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Talk Topic | Text | What you want to speak about |
| Speaker Background | Text | Your expertise, role, and relevant experience |
| Target Conference | Text | Which conference or type of conference |

### If You Don't Have This Data

- **Not sure what to speak about?** Claude helps you identify talk topics based on your expertise, audience interest, and what conference committees look for.
- **No speaking experience?** Claude positions your proposal around unique practitioner experience, case studies, or data — committees value fresh perspectives.
- **Don't know which conferences?** Claude recommends conferences based on your industry, topic, and career level, plus provides typical CFP timelines.
- **No case studies or data?** Claude helps you frame your talk around frameworks, lessons learned, or industry analysis without requiring original research.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Conference Theme | Text | Specific conference theme or track |
| CFP Requirements | Text | Specific fields or requirements from the CFP |
| Past Talks | Text | Previous speaking experience and topics |
| Audience Level | Text | Beginner, intermediate, advanced, or mixed |
| Talk Format | Text | Keynote, breakout, workshop, lightning, panel |

## Process

### Step 1: Talk Angle Development

| Angle Type | When to Use | Example |
|---|---|---|
| Case study | You have specific results from a project | "How We Increased Retention 40% by Rethinking Onboarding" |
| Framework | You've developed a repeatable approach | "The 3-Layer Content Strategy That Scales From 1 to 100 Writers" |
| Lessons learned | You've made mistakes others can learn from | "5 Expensive Mistakes in Our Migration to Microservices" |
| Data/research | You have unique data or survey results | "What 500 SaaS Companies Taught Us About Pricing" |
| Trend analysis | You've identified an emerging pattern | "Why the Next Wave of AI Will Come From Non-Tech Industries" |
| Contrarian | You challenge conventional wisdom | "Stop A/B Testing Everything: When Data-Driven Goes Wrong" |
| How-to | You can teach a practical skill | "Building a Marketing Dashboard in 30 Minutes With GA4" |

### Step 2: Title Optimization

High-performing title formulas:
- **Number + outcome**: "5 Strategies That Doubled Our Conversion Rate"
- **How We + result**: "How We Reduced Churn 60% in 6 Months"
- **Question format**: "Is Your Content Strategy Actually Working?"
- **Contrarian**: "Stop Doing X: Why [Common Practice] Is Hurting Your [Metric]"
- **Framework**: "The [Name] Framework for [Outcome]"
- **Specific + universal**: "[Specific Tactic] for [Broad Audience]"

Title rules:
- Under 12 words (ideally 6-10)
- Include a concrete outcome or benefit
- Avoid jargon that limits audience appeal
- Make the value proposition immediately clear
- Test with someone outside your field — if they understand why they'd attend, it works

### Step 3: Abstract Structure

| Section | Length | Purpose | Content |
|---|---|---|---|
| Hook | 1-2 sentences | Grab attention | Provocative question, surprising stat, or bold claim |
| Problem | 2-3 sentences | Establish relevance | Why this matters to the audience right now |
| Promise | 2-3 sentences | What they'll learn | Specific takeaways (3-5 items) |
| Credibility | 1-2 sentences | Why you can teach this | Your relevant experience or data |
| Call to action | 1 sentence | Who should attend | Target audience description |

Total: 150-300 words (most CFPs require under 300).

### Step 4: Learning Objectives

Write 3-5 learning objectives that are:
- **Specific**: "Implement a lead scoring model using CRM data" (not "understand lead scoring")
- **Actionable**: Start with verbs: implement, build, evaluate, design, optimize
- **Measurable**: The audience should be able to do something concrete after the talk
- **Audience-relevant**: Match the conference's audience level and interests

Format: "After this session, attendees will be able to [action verb] + [specific outcome]."

### Step 5: Speaker Bio Optimization

| Element | Purpose | Length |
|---|---|---|
| Current role | Establish authority | 1 sentence |
| Relevant achievement | Prove expertise on this topic | 1-2 sentences |
| Unique angle | What makes your perspective different | 1 sentence |
| Human touch | Make you relatable and memorable | 1 sentence |

Bio length: 75-150 words. Write in third person. Focus on credibility for THIS talk, not your entire career.

### Step 6: CFP Review Committee Optimization

What review committees look for:
- **Relevance**: Does the topic fit the conference theme and audience?
- **Originality**: Is this a fresh perspective, not a vendor pitch?
- **Specificity**: Are there concrete takeaways, not vague promises?
- **Speaker credibility**: Can this person actually deliver on this topic?
- **Audience fit**: Is the level right for the expected audience?
- **No sales pitches**: Talks that promote a product get rejected immediately

### Confidence & Sample Size

> **Confidence Note**: Average CFP acceptance rate is 10-25% for major conferences. Proposals with specific case studies and data get accepted 2-3x more often than theoretical talks. First-time speakers have lower acceptance rates but can compensate with unique practitioner experience and strong abstracts. Submitting to 5-10 conferences per talk significantly increases your chances of getting at least one acceptance. Review committees read hundreds of proposals — your title and first 2 sentences determine whether they read the rest.

### ⚠️ Human Checkpoint
> Verify all data points and claims in your proposal are accurate and can be supported in the talk. Ensure you have permission to share case studies or company data publicly. Check that your talk doesn't overlap with your employer's confidentiality requirements.

> **Benchmark Context**: See Cision 2024 State of the Media Report, and they understand the audience. Workshop and hands-on session proposals have higher acceptance rates than standard talks due to lower submission volume. (Cision 2024 State of the Media Report for current industry benchmarks relevant to this analysis.
## Output Contract

### Deliverable: Markdown Speaking Proposal

```markdown
# Speaking Proposal: [Conference Name]

## Talk Options
### Option 1: [Title]
- Format: [keynote/breakout/workshop/lightning]
- Level: [beginner/intermediate/advanced]
- Duration: [minutes]

### Option 2: [Alternative Title]
- Format: [type]
- Level: [level]

## Selected Proposal
### Title
[Final title]

### Abstract
[150-300 word abstract]

### Learning Objectives
1. [Objective 1]
2. [Objective 2]
3. [Objective 3]

### Outline
1. [Section 1 — X minutes]
2. [Section 2 — X minutes]
3. [Section 3 — X minutes]

### Target Audience
[Who should attend and why]

### Speaker Bio
[75-150 word bio]

## CFP Submission Checklist
- [ ] Title under 12 words
- [ ] Abstract under 300 words
- [ ] 3-5 specific learning objectives
- [ ] No product pitches or sales language
- [ ] Speaker photo (high-res headshot)
- [ ] Social media links
```

## Platform Implementation Steps

### CFP Research
1. Identify target conferences 6-12 months in advance
2. Track CFP deadlines (most open 4-6 months before the event)
3. Read past year's accepted talks for topic and style guidance
4. Follow conference organizers on social media for theme announcements
5. Attend the conference before proposing (understand the audience)

### Proposal Development
1. Develop 2-3 talk angles based on your expertise
2. Write title options (3-5 per talk angle)
3. Draft abstract following the hook-problem-promise-credibility structure
4. Write learning objectives that are specific and actionable
5. Customize each submission to the specific conference theme

### Post-Acceptance
1. Confirm logistics (travel, AV requirements, session length)
2. Develop full presentation aligning with accepted abstract
3. Rehearse 3-5 times before the event
4. Prepare handout or resource page for attendees
5. Promote your session on social media before the event

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Proposal too vague | No specific outcomes or takeaways | Add concrete numbers, case studies, and actionable frameworks |
| Sounds like a sales pitch | Too much company/product focus | Remove brand mentions; focus on insights, not products |
| Wrong audience level | Talk too basic or too advanced for the conference | Research past attendee feedback; match level explicitly |
| Rejected everywhere | Topic is saturated or timing is wrong | Differentiate with unique angle; try emerging/smaller conferences |

## How to Get Your Data

- **Conference CFPs**: Sessionize.com, Papercall.io, conference websites, Twitter #CFP hashtag
- **Past talks**: Conference YouTube channels or Slideshare for accepted talk styles
- **Audience research**: Past attendee reviews, conference attendee surveys, social media conversations
- **No speaking experience**: Start with meetups, webinars, or podcast appearances to build a speaking resume

## Example

**Input**: "Speaking proposal for a B2B marketing conference. I'm VP of Growth at a SaaS startup. Topic: how we used product-led growth to reduce CAC by 55%. We went from $420 CAC to $189 over 12 months by changing our signup flow, pricing model, and onboarding. Conference is for marketing leaders at mid-market SaaS companies."

**Output**: Title options: (1) "From $420 to $189 CAC: The Product-Led Playbook We Wish We'd Known Earlier" (2) "The Anti-Marketing Growth Strategy That Cut Our CAC by 55%" (3) "Stop Spending More on Ads: How PLG Changed Our Unit Economics." Recommended: Option 1 (specific numbers + relatability). Abstract (195 words): "Every SaaS marketing leader faces the same problem: CAC keeps climbing while budgets don't. Twelve months ago, our CAC was $420 and rising. Today it's $189 — and we spend less on paid acquisition than ever. This isn't a story about finding a magical new channel. It's about rethinking what 'marketing' means when your product does the selling. In this session, I'll share the exact changes we made to our signup flow, pricing model, and onboarding experience that turned our product into our best acquisition channel. You'll learn: the 3 friction points we eliminated from signup that doubled our conversion rate, why we killed our sales-assisted onboarding (and what replaced it), how we restructured pricing to create a natural upgrade path, and the metrics we track instead of MQLs. This talk is for marketing leaders at SaaS companies doing $2M-$50M ARR who feel stuck on the paid acquisition treadmill and want a path to more efficient growth. No vendor pitches — just the playbook we built through 12 months of experimentation." Learning objectives: (1) Identify friction points in your signup flow using activation data. (2) Evaluate whether product-led pricing models apply to your business. (3) Design an onboarding sequence that drives activation without sales involvement.

## Related Skills

- **[Podcast Guest Research Brief](../video-podcast/podcast-guest-research-brief.md)** — Prepare guest positioning and talking points after speaking proposal is accepted.
- **[Video Script Writer](../video-podcast/video-script-writer.md)** — Script your presentation content after speaking proposal is accepted.
- **[Webinar Technical Runbook](./webinar-technical-runbook.md)** — Prepare technical setup for your presentation if it's a virtual speaking engagement.
- **[Webinar Promotion Playbook](../video-podcast/webinar-promotion-playbook.md)** — Promote your speaking opportunity to maximize attendance.
