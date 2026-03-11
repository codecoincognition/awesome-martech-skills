---
name: referral-program-designer
description: >
  Design referral and word-of-mouth programs with incentive structures and viral mechanics.
  Use this skill when the user says "referral program", "refer-a-friend program", "viral loop
  design", "word of mouth strategy", "referral incentive structure", "ambassador program",
  "customer referral campaign", "viral coefficient optimization", "referral tracking setup",
  "invite program design", or "growth loop builder". Also trigger for referral reward
  optimization, two-sided incentive design, or referral program audit.
---

# Referral Program Designer

Designs referral programs with incentive structures, viral mechanics, referral flow optimization, tracking setup, and fraud prevention for sustainable word-of-mouth growth.

## Granularity Check

> **Time**: ~5 min data prep → ~10 min Claude session → ~60-120 min implementing in your product / tools. If implementing the program, add 1-4 weeks for development and launch. Input is product info and growth goals. Output is Markdown referral program design.

## User Intent Mapping

- "Design a referral program for our app" (full design)
- "What incentive should we offer for referrals?" (incentive structure)
- "Our referral program isn't working — help" (optimization)
- "Viral loop for our marketplace" (viral mechanics)
- "Ambassador program for power users" (advocacy)
- "Two-sided referral incentive" (incentive design)
- "Referral program benchmarks" (benchmarking)
- "Reduce referral fraud" (fraud prevention)
- "Track referral performance" (measurement)
- "Referral program email templates" (communications)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Product/Service | Text | What you offer, pricing model |
| Current Users | Number | Approximate active user/customer count |
| Goal | Text | More signups, more purchases, market expansion |

### If You Don't Have This Data

- **No NPS or satisfaction data?** If users are actively using your product, referrals can work. Survey 20 users: "Would you recommend us to a colleague?" to gauge potential.
- **No referral history?** Start by asking top customers to refer manually. Track results for 30 days to estimate natural referral rate.
- **No budget for incentives?** Many successful programs use product-based incentives (free month, storage, credits) which cost less than cash.
- **No technical resources?** Start with a manual referral code system. Upgrade to automated tracking when volume justifies it.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Average Order Value / LTV | Number | For incentive sizing |
| Current Referral Rate | Number | % of customers who refer |
| NPS Score | Number | Net Promoter Score |
| Competitor Programs | Text | What competitors offer |
| Technical Constraints | Text | Platform limitations |

## Process

### Step 1: Program Type Selection
| Type | Best For | Example |
|---|---|---|
| Two-Sided (give-get) | Consumer apps, SaaS | "Give $20, get $20" |
| One-Sided (referrer reward) | B2B, high-LTV products | "Earn $100 per referral" |
| Tiered | Platforms wanting ambassadors | "Refer 5 → Silver, 10 → Gold" |
| Community-Based | Content platforms, marketplaces | "Unlock features as community grows" |
| Milestone | Gamification-friendly products | "Refer 3 friends, unlock premium features" |

### Step 2: Incentive Design
Rules for effective incentives:
- Incentive value should be 10-25% of customer LTV
- Product-based rewards have higher ROI than cash
- Two-sided incentives generate 2-3x more referrals than one-sided
- Time-limited bonuses create urgency
- Test multiple incentive levels to find optimal point

### Step 3: Referral Flow Design
Map the complete referral journey:
1. **Trigger**: When to prompt referral (post-purchase, milestone, NPS survey)
2. **Share**: How to refer (unique link, code, email invite, social share)
3. **Landing**: What the referred user sees (dedicated landing page with offer)
4. **Conversion**: Sign-up or purchase by referred user
5. **Reward**: Fulfillment of incentive for both parties
6. **Loop**: Prompt the newly referred user to refer others

### Step 4: Communication Templates
- In-app referral prompt
- Referral invitation email (from referrer to friend)
- Welcome email for referred user
- Reward confirmation for referrer
- Milestone celebration (nth referral)
- Re-engagement for lapsed referrers

### Step 5: Fraud Prevention
- Rate limiting (max 10 referrals per day)
- Self-referral detection (same IP, device, payment method)
- Minimum activity requirement before reward (prevent fake accounts)
- Clawback policy (reverse rewards for refunded or fraudulent signups)
- Monitor for referral rings (groups gaming the system)

### Confidence & Sample Size
> **Confidence Note**: Referral programs take 2-3 months to reach steady state. Initial participation rate will be lower as users discover the program. Expect 5-15% of active users to participate in a well-designed program. Viral coefficient >1.0 (organic viral growth) is rare — most successful programs achieve 0.3-0.7. Incentive optimization requires testing with minimum 500 referral-eligible users.

### ⚠️ Human Checkpoint
> Review incentive structure with finance team (cost modeling). Verify terms and conditions with legal (anti-spam compliance, tax implications of rewards). Test the complete referral flow as a user before launching. Ensure fraud prevention measures don't create false positives.

> **Benchmark Context**: See ProfitWell 2024 SaaS Benchmarks, and OpenView 2024 Product Benchmarks for current industry benchmarks relevant to this analysis.
## Output Contract

### Deliverable: Markdown Referral Program Design

```markdown
# Referral Program Design: [Product]

## Program Type
- Model: [Two-Sided / One-Sided / Tiered / etc.]
- Incentive: Referrer gets [X], Friend gets [Y]

## Referral Flow
1. Trigger: [when]
2. Share: [how]
3. Landing: [what friend sees]
4. Conversion: [required action]
5. Reward: [fulfillment]

## Incentive Structure
| Tier | Referrals | Referrer Reward | Friend Reward |
|---|---|---|---|

## Communication Templates
### Referral Prompt
"[text]"
### Invitation Email
Subject: [subject]
Body: [text]

## Fraud Prevention
| Rule | Implementation |
|---|---|

## KPIs
| Metric | Target | Tracking |
|---|---|---|

## Cost Model
| Scenario | Referrals/Month | Cost | CAC |
|---|---|---|---|
```

## Platform Implementation Steps

### Referral Tools (ReferralCandy / Viral Loops / GrowSurf)
1. Sign up and connect your platform (Shopify, WooCommerce, custom)
2. Configure incentive structure (reward type, amount, conditions)
3. Customize referral widget and sharing options
4. Set up email templates for referrer and referee
5. Launch and monitor from dashboard

### Custom Implementation
1. Generate unique referral codes per user
2. Build referral landing page with friend's offer
3. Track attribution: referral code → signup → conversion
4. Automate reward fulfillment via CRM/billing system
5. Build a referral dashboard for monitoring

### Manual / Low-Tech Start
1. Create unique promo codes per referrer (spreadsheet tracking)
2. Share via email template users can forward
3. Track redemptions in your billing system
4. Fulfill rewards manually (credit, gift card, etc.)
5. Graduate to automated system when volume exceeds 50 referrals/month

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Low participation | Users don't know program exists or incentive is weak | Increase visibility (in-app, email, post-purchase); test higher incentive |
| Low conversion of referrals | Poor landing page or unclear offer | Optimize landing page; test different friend incentives |
| Fraud abuse | Gaming referral system | Implement fraud rules; require qualifying actions before reward |
| High cost per acquisition | Incentive too generous relative to LTV | Reduce incentive; add minimum purchase requirements |

## How to Get Your Data

- **No data needed**: Describe your product and pricing — Claude designs the program from best practices
- **NPS data**: Survey tool (Delighted, Typeform) → export promoter list as referral program seed audience
- **Customer data**: Export from CRM → identify highest-LTV customers as initial referral program invitees

## Example

**Input**: "Referral program for a $29/mo project management SaaS. 5,000 active users. LTV: $600. Current organic referral rate: ~2% of users. Goal: double referral-driven signups."

**Output**: Two-sided program: Referrer gets 1 free month ($29 value), friend gets 20% off first 3 months ($17.40 savings). Trigger: prompt after user completes 5th project (activation milestone). Share: unique referral link + pre-written email/LinkedIn message. Landing page: "[Friend's name] invited you to [Product] — get 20% off your first 3 months." Fraud prevention: max 20 referrals/user, friend must remain active for 30 days before referrer reward, same IP/device detection. Cost model: at 10% participation (500 users referring), expecting 250 new signups at $29 effective CAC vs. current $85 paid CAC. Tiered bonus: 5 referrals → branded swag, 10 referrals → lifetime 20% discount, 25 referrals → annual user conference ticket. Communication: 3-email sequence (invite, reminder at 7 days, milestone celebration).

## Related Skills

- **[viral-loop-designer](./viral-loop-designer.md)** — Design viral mechanics to amplify referral program reach.
- **[customer-persona-builder](./customer-persona-builder.md)** — Tailor referral incentives to different persona segments.
- **[growth-experiment-designer](./growth-experiment-designer.md)** — Test different referral incentive structures and messaging.
- **[retention-analysis-framework](./retention-analysis-framework.md)** — Track retention of referred users vs. organic users.
