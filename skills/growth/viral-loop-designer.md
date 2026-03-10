---
name: viral-loop-designer
description: >
  Design viral loops and product-led growth mechanics that drive organic acquisition.
  Use this skill when the user says "viral loop design", "product-led growth mechanics",
  "viral coefficient optimization", "network effects strategy", "organic growth engine",
  "invite flow optimization", "viral sharing mechanics", "k-factor improvement",
  "word of mouth strategy", "growth loop design", or "self-serve acquisition funnel".
  Also trigger for referral loop analysis, sharing trigger identification, or
  viral content mechanics.
---

# Viral Loop Designer

Designs viral loops and product-led growth mechanics — identifying sharing triggers, optimizing invite flows, calculating viral coefficients, and building self-reinforcing growth engines.

## Granularity Check

> **Session time**: ~5 min data prep + ~10 min Claude session. If implementing output, add 4-8 hours for engineering and design. Input is product details and current sharing data. Output is Markdown viral loop blueprint with implementation plan.

## User Intent Mapping

- "Design a viral loop for our product" (full design)
- "How do we increase our viral coefficient?" (optimization)
- "Our invite flow has low conversion" (funnel fix)
- "Product-led growth strategy" (PLG mechanics)
- "How do we build network effects?" (network strategy)
- "What should trigger users to share?" (trigger identification)
- "Calculate our k-factor" (measurement)
- "Viral loop for a marketplace" (model-specific)
- "Embed sharing into the product experience" (integration)
- "Why aren't users inviting others?" (diagnosis)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Product/Service | Text | What your product does and core value proposition |
| User Journey | Text | Key steps from signup to active usage |
| Current Sharing | Text | How users currently share or invite others (if at all) |

### If You Don't Have This Data

- **No sharing mechanics yet?** Describe your product and user journey. Claude designs viral loops from scratch based on your product type.
- **No viral coefficient data?** Claude estimates based on your invite flow. Start tracking: invites sent per user, invite acceptance rate, and time-to-invite.
- **No user research on sharing?** Claude uses product-type benchmarks. Survey 10 active users: "Have you told anyone about us? Why or why not?"
- **No technical resources?** Claude prioritizes low-engineering viral mechanics (shareable outputs, social proof, referral links) over complex integrations.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Current K-Factor | Number | Viral coefficient (invites × conversion rate) |
| Invite Funnel Data | CSV | Invites sent, opened, accepted, activated |
| User Segments | Text | Power users vs. casual — who shares most? |
| Product Type | Text | SaaS, marketplace, social, tool, content platform |
| Competitors | Text | How competitors drive organic growth |

## Process

### Step 1: Viral Loop Type Selection
Match product to optimal loop type:

| Loop Type | Best For | Mechanism | Example |
|---|---|---|---|
| Invite Loop | Social products, tools | User invites → new user → invites more | Dropbox, Slack |
| Content Loop | Creator tools, platforms | User creates → shares output → viewer signs up | Canva, Loom |
| Network Effect Loop | Marketplaces, social | More users = more value → attracts more users | LinkedIn, Airbnb |
| Embed Loop | Widgets, tools | Product appears on other sites → drives signups | Typeform, Calendly |
| Social Proof Loop | Reviews, communities | Visible usage → credibility → new users | Yelp, Product Hunt |

### Step 2: Sharing Trigger Identification
Identify natural moments users want to share:
- **Achievement moments**: User hits a milestone or completes something valuable
- **Output moments**: User creates something worth showing others
- **Collaboration moments**: User needs others to get value (inherent virality)
- **Delight moments**: User experiences something surprisingly good
- **Status moments**: Using the product signals something positive about the user

### Step 3: K-Factor Calculation & Optimization
- **K-Factor** = (avg invites per user) × (invite conversion rate)
- K > 1 = viral growth (each user brings in more than one new user)
- K = 0.5-1.0 = viral assist (amplifies paid/organic acquisition)
- K < 0.5 = low virality (needs fundamental loop redesign)
- Optimize both sides: increase invites sent AND improve invite conversion

### Step 4: Invite Flow Design
- Minimize friction in the invite process (pre-filled messages, one-click sharing)
- Personalize invite messages (from the inviter, not the brand)
- Show the inviter's content or activity in the invite
- Create urgency or exclusivity when appropriate
- Multi-channel: email, SMS, social share, direct link
- Follow-up sequence for unopened invites

### Step 5: Viral Cycle Time Optimization
- Measure time from signup → first share → new user signup
- Shorter cycles compound faster (daily loops > weekly loops)
- Identify and remove delays in the loop
- Create multiple loop opportunities per session

### Step 6: Network Effects Analysis (if applicable)
- **Direct network effects**: Product gets better with more users (messaging, social)
- **Indirect network effects**: More users attract complementary users (marketplace)
- **Data network effects**: More usage improves the product (AI, recommendations)
- **Critical mass**: Minimum users needed for value threshold
- **Cold start strategy**: How to deliver value before network effects kick in

### Confidence & Sample Size
> **Confidence Note**: Viral loops take 3-6 months to validate properly. K-factor calculations need minimum 1,000 invite events for reliable measurement. Viral mechanics are highly product-specific — what works for social apps rarely works for B2B SaaS. Test one loop at a time and measure full-cycle conversion, not just invite sends.

### ⚠️ Human Checkpoint
> Review sharing mechanics for user experience impact — aggressive invite prompts can damage retention. Ensure sharing doesn't expose private user data. Legal review for incentivized referrals in regulated industries.

> **Benchmark Context**: Average SaaS k-factor is 0.2-0.4. Top viral products achieve k-factor of 0.7-1.5. Personalized invite messages convert 3x better than generic ones. Users who arrive via referral have 25% higher LTV. The best viral loops feel like product features, not marketing — Calendly's scheduling link is both the product and the acquisition channel. Optimal invite prompt timing is at the "aha moment," not at signup.

## Output Contract

### Deliverable: Markdown Viral Loop Blueprint

```markdown
# Viral Loop Blueprint: [Product]

## Loop Architecture
- Primary loop type: [type]
- Secondary loops: [types]
- Estimated k-factor potential: [range]

## Sharing Triggers
| Trigger Moment | User Emotion | Share Mechanic | Channel |
|---|---|---|---|

## Invite Flow Design
- Step 1: [trigger] → Step 2: [compose] → Step 3: [send] → Step 4: [receive] → Step 5: [convert]

## K-Factor Model
- Current: [estimate]
- Target: [goal]
- Levers: [list]

## Implementation Roadmap
| Phase | Mechanic | Engineering Effort | Expected Impact |
|---|---|---|---|

## Measurement Plan
| Metric | Definition | Target |
|---|---|---|

## Cold Start Strategy
- [How to bootstrap the loop before scale]
```

## Platform Implementation Steps

### Product / Engineering
1. Instrument sharing triggers at identified moments in the user journey
2. Build invite flow with pre-filled messages and one-click sharing
3. Create unique referral tracking links per user
4. Implement invite funnel analytics (sent → opened → clicked → signed up → activated)
5. A/B test invite prompts, messaging, and timing

### Analytics Setup
1. Track k-factor weekly: (total invites / active users) × (accepted invites / total invites)
2. Measure viral cycle time: average days from signup to first successful referral
3. Segment by channel: which sharing channels convert best
4. Cohort analysis: do referred users share more than non-referred users?
5. Attribution: connect referral source to LTV for ROI calculation

### Growth Tools
1. Use referral platforms (ReferralCandy, Viral Loops, GrowSurf) for tracking
2. Implement deep linking (Branch, Firebase Dynamic Links) for mobile
3. Set up sharing SDKs for social platforms
4. Create shareable assets (images, badges, certificates) users can post

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Users don't share | No natural sharing trigger or wrong timing | Map user journey for genuine delight moments; test different triggers |
| High invite send, low conversion | Poor invite experience or weak value prop for receiver | Personalize invite content; show inviter's activity; improve landing page |
| K-factor stalls below 0.3 | Product lacks inherent virality | Shift to content loops or embed loops; add collaboration features |
| Sharing damages retention | Too aggressive invite prompts | Reduce prompt frequency; make sharing feel like a feature, not a request |

## How to Get Your Data

- **Invite funnel**: Product analytics → sharing/invite events → conversion rates
- **No data**: Describe your product and user journey — Claude designs the loop from first principles
- **Competitor analysis**: Sign up for competitor products, note every sharing prompt and mechanic you encounter
- **User interviews**: Ask 10 users: "When do you talk about our product to others?" and "What would make you invite a colleague?"

## Example

**Input**: "Design viral loops for a project management tool. Current state: 2,000 users, no sharing mechanics, users collaborate in teams of 3-8. Product type: B2B SaaS. Main value: visual project boards with AI task suggestions."

**Output**: Primary loop: Collaboration Loop (inherent virality — users need teammates to get full value). Secondary loop: Content Loop (shareable project board views). Sharing triggers: (1) When user creates a project → prompt to invite team (collaboration need), (2) When AI suggests tasks → "Share this board with your team" (delight moment), (3) Weekly progress reports → shareable summary link (output moment). K-factor model: Current ~0.1 (no mechanics), target 0.5 in 6 months. Invite flow: user creates project → one-click "Add team" with email import → personalized invite showing the board → recipient sees the board as read-only → signs up to collaborate. Cold start: Free tier for teams ≤5, so the loop works before payment. Quick win: add "Powered by [Product]" watermark on shared board links (embed loop, zero engineering for v1). Implementation roadmap: Phase 1 (2 weeks) — team invite flow at project creation; Phase 2 (4 weeks) — shareable board links with watermark; Phase 3 (6 weeks) — AI-generated progress reports with share buttons.
