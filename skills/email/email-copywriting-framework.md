---
name: email-copywriting-framework
description: >
  Write high-converting email copy — subject lines, body content, CTAs, and persuasion frameworks.
  Use this skill when the user says "email copywriting", "write email copy", "email copy
  framework", "persuasive email writing", "email CTA optimization", "email body copy",
  "email copywriting formulas", "sales email copy", "promotional email writing", "email
  copy best practices", or "email copy that converts". Also trigger for email tone of voice,
  email storytelling, or email persuasion techniques.
---

# Email Copywriting Framework

Creates high-converting email copy using proven frameworks, persuasion psychology, and data-backed best practices for subject lines, body content, CTAs, and complete email campaigns.

## Granularity Check

> **Time**: ~5 min data prep → ~10 min Claude session → ~20-30 min building in your ESP. Output is ready-to-use email copy or frameworks you can adapt. Input is campaign goals and audience context. Output is Markdown with copy drafts and framework recommendations.

## User Intent Mapping

- "Write email copy for our product launch" (campaign copy)
- "Subject line formulas that work" (subject lines)
- "Our email CTAs aren't getting clicks" (CTA optimization)
- "Email copywriting best practices" (best practices)
- "Write a sales email sequence" (sales emails)
- "Promotional email copy for our sale" (promotional)
- "Email storytelling techniques" (storytelling)
- "Persuasive email frameworks" (frameworks)
- "Tone of voice for our emails" (voice)
- "Email copy review — is this good?" (copy review)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Campaign Goal | Text | What you want the email to achieve |
| Audience | Text | Who you're writing for |
| Offer/Message | Text | What you're promoting or communicating |

### If You Don't Have This Data

- **No audience insights?** Describe your ideal customer. Claude writes copy tailored to that persona.
- **No brand voice guide?** Share 2-3 emails you've liked the tone of. Claude infers your voice.
- **No performance data?** Claude uses best-practice frameworks. Track performance on the first send to establish baselines.
- **First time writing emails?** Claude provides complete, ready-to-send copy with explanations of why each element works.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Brand Voice | Text | Tone descriptors (casual, professional, witty, etc.) |
| Product Details | Text | Features, benefits, pricing |
| Past Winners | Text | Subject lines or emails that performed well |
| Constraints | Text | Character limits, compliance requirements |
| Urgency | Text | Time-sensitive elements (deadlines, limited stock) |

## Process

### Step 1: Framework Selection
| Framework | Best For | Structure |
|---|---|---|
| PAS (Problem-Agitate-Solve) | Pain-point driven products | Problem → make it worse → your solution |
| AIDA (Attention-Interest-Desire-Action) | Broad promotions | Grab attention → build interest → create desire → CTA |
| BAB (Before-After-Bridge) | Transformation products | Current state → desired state → how to get there |
| 4 Ps (Promise-Picture-Proof-Push) | High-ticket offers | Bold claim → paint the outcome → evidence → CTA |
| Story-based | Brand building, loyalty | Character + conflict + resolution + lesson |

### Step 2: Subject Line Writing
Formulas that drive opens:
- **Curiosity gap**: "The [thing] most [audience] get wrong about [topic]"
- **Benefit-driven**: "Get [benefit] in [timeframe]"
- **Question**: "Are you making this [topic] mistake?"
- **Social proof**: "[Number] [audience] already [action]"
- **Urgency**: "[Time] left to [benefit/save]"
- **Personalization**: "[Name], your [personalized detail]"
- Rules: 30-50 characters for mobile, no ALL CAPS, avoid spam triggers, preview text complements (doesn't repeat) subject

### Step 3: Body Copy Structure
- **Opening line**: Hook that continues the subject line promise (no "Hi [Name], I hope you're well")
- **First paragraph**: Establish relevance — why should they care?
- **Middle**: Value delivery — benefits, proof, story
- **CTA section**: Clear, specific action with reason to act now
- **P.S. line**: Second chance at CTA or add urgency (45% of readers scan to P.S. first)

### Step 4: CTA Optimization
- Use action verbs: "Get", "Start", "Claim", "Download" (not "Click Here" or "Submit")
- Add value: "Start My Free Trial" vs. "Sign Up"
- Create urgency when genuine: "Claim Your Spot (12 left)"
- Button vs. text link: buttons get 28% more clicks
- Single primary CTA per email (repeat 2-3 times in long emails)
- Place first CTA above the fold

### Step 5: Persuasion Psychology
- **Scarcity**: Limited quantity or time ("Only 50 spots left")
- **Social proof**: Numbers, testimonials, logos ("Join 10,000+ marketers")
- **Reciprocity**: Give value before asking ("Free guide inside")
- **Authority**: Expert endorsements, credentials, data
- **Loss aversion**: Frame as what they'll miss, not what they'll gain
- **Specificity**: Specific numbers build credibility ("37% increase" vs. "big improvement")

### Step 6: Copy Review Checklist
- [ ] Subject line creates curiosity or promises clear benefit
- [ ] Opening line hooks immediately (no throat-clearing)
- [ ] One clear message per email
- [ ] Benefits > features
- [ ] CTA is specific and action-oriented
- [ ] Mobile-friendly length (under 200 words for promotional)
- [ ] Reads naturally when spoken aloud
- [ ] No jargon the reader wouldn't use

### Confidence & Sample Size
> **Confidence Note**: Email copy performance is highly audience-dependent — what works for one brand may not work for another. A/B test subject lines on every send. Copy frameworks are starting points, not formulas — adapt based on your brand voice and audience feedback. Short emails (under 125 words) generally outperform long emails for promotional sends; long emails work better for educational content.

### ⚠️ Human Checkpoint
> Review all email copy for factual accuracy, brand voice alignment, and legal compliance (especially claims, pricing, and deadlines). Ensure urgency and scarcity claims are genuine — false urgency damages trust.

> **Benchmark Context**: See HubSpot 2024 State of Marketing for current industry benchmarks relevant to this analysis.
## Output Contract

### Deliverable: Markdown Copy Package

```markdown
# Email Copy: [Campaign]

## Subject Line Options
1. [Subject line] — [framework used]
2. [Subject line] — [framework used]
3. [Subject line] — [framework used]
Preview text: [text]

## Email Body

### Version A: [Framework]
[Complete email copy]

### Version B: [Framework]
[Complete email copy]

## CTA Options
- Primary: [button text]
- Alternative: [button text]

## Copy Notes
- Tone: [description]
- Key persuasion elements: [list]
- Recommended A/B test: [suggestion]
```

## Platform Implementation Steps

### Copy Production
1. Use the framework to draft 2-3 versions per email
2. Write 5+ subject line options and select best 2 for A/B test
3. Read copy aloud to check natural flow
4. Preview on mobile device (60%+ of opens are mobile)
5. Get a second pair of eyes for review

### Testing & Iteration
1. A/B test subject lines on every send
2. Track which frameworks generate highest engagement per audience segment
3. Build a swipe file of winning copy elements
4. Review and update copy templates quarterly

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Low open rate | Subject line doesn't create curiosity or promise value | Test more subject line variations; try different frameworks |
| Opens but no clicks | Body copy doesn't deliver on subject line promise; weak CTA | Strengthen the connection between subject and body; make CTA more specific |
| Clicks but no conversion | Email copy promises more than the landing page delivers | Align email copy with landing page copy; manage expectations |
| High unsubscribe after send | Copy tone or offer mismatched to audience expectations | Review segmentation; adjust tone; ensure content matches signup promise |

## How to Get Your Data

- **Past winners**: ESP → sort campaigns by highest click rate → analyze those subject lines and copy
- **Audience insights**: Survey 20 subscribers on what they value from your emails
- **Competitor emails**: Subscribe to competitor emails → note subject lines and frameworks they use
- **No data**: Describe your product, audience, and campaign goal — Claude writes ready-to-send copy

## Example

**Input**: "Write email copy for a SaaS product's annual pricing promotion. 20% off annual plans for a week. Audience: existing monthly subscribers. Tone: friendly, direct, no hype."

**Output**: 3 subject lines: (1) "Your plan, but 20% less" (direct + benefit), (2) "We did the math so you don't have to" (curiosity), (3) "Quick question about your subscription" (curiosity + personal). Preview text: "Switch to annual and save $[amount] this year." Email body (PAS framework): "You're already getting value from [Product] every day. (acknowledge) But paying monthly means you're spending $[monthly×12] per year. (agitate) Switch to annual this week and pay $[annual price] instead — that's $[savings] back in your budget. (solve) [CTA: Switch to Annual — Save 20%] The math: Monthly = $X/year. Annual = $Y/year. You save $Z. That's [relatable comparison — 'enough for X months of coffee']. This offer expires [date]. After that, it's back to full price. — [Name], [Product] Team. P.S. It takes 30 seconds to switch, and your remaining monthly balance is credited automatically. [CTA: Save 20% Now]"

## Related Skills

- **[Email Subject Line Tester](./email-subject-line-tester.md)** — Use to optimize the subject lines that pair with your email copy.
- **[Email Sequence Builder](./email-sequence-builder.md)** — Use to structure the sequence before writing copy for each email in the flow.
- **[Email Template Designer](./email-template-designer.md)** — Use to design the visual layout that will showcase your copy effectively.
- **[Email CTA Optimization](./email-copywriting-framework.md)** — Use to craft high-converting CTAs that support your campaign goals.
