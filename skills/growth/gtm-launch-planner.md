---
name: gtm-launch-planner
description: >
  Plan go-to-market launches for products, features, or market expansions.
  Use this skill when the user says "go-to-market plan", "GTM strategy", "product launch plan",
  "feature launch playbook", "market entry strategy", "launch timeline", "launch checklist",
  "GTM motion", "product launch campaign", "launch readiness assessment", or "new market launch".
  Also trigger for beta launch planning, waitlist strategy, or launch announcement planning.
---

# GTM Launch Planner

Creates comprehensive go-to-market launch plans with positioning, channel strategy, timeline, launch day playbook, and success metrics for product launches, feature releases, or market expansions.

## Granularity Check

> **Time**: ~5 min data prep → ~15 min Claude session → ~60-120 min implementing in your product / tools. If implementing the full launch plan, add weeks of execution time. Input is product/feature info and launch goals. Output is Markdown GTM plan with timeline and checklist.

## User Intent Mapping

- "Plan a go-to-market strategy for our new product" (full GTM)
- "Feature launch playbook" (feature release)
- "How to launch in a new market" (market expansion)
- "Launch timeline for Q2" (timeline)
- "Launch readiness checklist" (pre-launch)
- "Beta launch strategy" (early-stage)
- "Waitlist and pre-launch buzz strategy" (pre-launch marketing)
- "Launch day playbook" (day-of execution)
- "Post-launch measurement plan" (post-launch)
- "Compare launch strategies: big bang vs. soft launch" (strategic)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Product/Feature | Text | What you're launching and its key value proposition |
| Target Market | Text | Who it's for, market size estimate |
| Launch Date | Text | Target launch date or timeframe |

### If You Don't Have This Data

- **No positioning yet?** Describe the problem you solve and for whom. Claude will draft positioning as part of the plan.
- **No launch date?** Claude builds a "time-to-launch" plan with recommended milestones. Work backward from when you want to be in market.
- **No marketing budget?** Claude includes zero-cost tactics (PR, community, partnerships) alongside paid options. Specify budget constraints.
- **No competitive analysis?** Describe your top 3 competitors at a high level. Claude positions against them.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Budget | Number | Marketing budget for launch |
| Competitive Landscape | Text | Key competitors and their positioning |
| Existing Audience | Text | Email list size, social following, community |
| Sales Team | Text | Direct sales vs. self-serve vs. hybrid |
| Previous Launches | Text | What worked/didn't in past launches |

## Process

### Step 1: Launch Strategy Selection
| Strategy | When to Use | Risk Level |
|---|---|---|
| Big Bang | Major product launch, strong brand, large audience | High (all-or-nothing) |
| Phased Rollout | New market, complex product, limited resources | Medium |
| Soft Launch | Beta testing, MVP validation, regulated industry | Low |
| Waitlist/Pre-Launch | Building anticipation, supply-constrained, viral potential | Medium |

### Step 2: Positioning & Messaging
- One-liner positioning statement
- 3 key messages (benefit-driven)
- Competitive differentiation (why you vs. alternatives)
- Proof points (data, testimonials, case studies)

### Step 3: Channel Plan
Map channels to launch phases:
- **Pre-Launch (4-8 weeks)**: Email tease, social hints, PR outreach, influencer seeding
- **Launch Week**: Press release, blog post, social blitz, email blast, paid ads
- **Post-Launch (2-4 weeks)**: Content marketing, case studies, retargeting, community engagement

### Step 4: Timeline & Milestones
Build a week-by-week timeline:
- T-8 weeks: Finalize positioning and messaging
- T-6 weeks: Create launch assets (landing page, email, social, press kit)
- T-4 weeks: Begin pre-launch marketing
- T-2 weeks: Media outreach, influencer activation
- T-1 week: Final testing, team briefing, launch day playbook
- Launch Day: Execute playbook
- T+1-4 weeks: Monitor, optimize, follow-up content

### Step 5: Launch Day Playbook
Hour-by-hour execution plan:
- Pre-market: Final checks, team standup
- Launch hour: Publish blog, send emails, post social, activate PR
- Mid-day: Monitor metrics, respond to coverage, engage comments
- End-of-day: First metrics report, team debrief

### Step 6: Success Metrics
| Metric | Target | Measurement |
|---|---|---|
| Awareness | PR mentions, social impressions, website traffic spike |
| Acquisition | Signups, downloads, trials, purchases in first 7/30 days |
| Activation | Users reaching aha moment in first 7 days |
| Revenue | Revenue in first 30/60/90 days |
| Sentiment | Social sentiment, NPS, support ticket volume |

### Confidence & Sample Size
> **Confidence Note**: Launch success is hard to predict. Even well-planned launches can underperform if market timing is off or if the product doesn't resonate. Plan for scenarios: what if launch exceeds expectations (scaling plan) AND what if it underperforms (pivot plan). Set realistic expectations — most launches see a spike followed by a dip before finding steady state.

### ⚠️ Human Checkpoint
> Review positioning with actual customers before launch. Verify all legal/compliance requirements (regulatory approvals, terms of service, privacy policy updates). Ensure customer support is staffed for launch-day volume. Test all links, tracking, and landing pages before go-live.

> **Benchmark Context**: 70% of product launches miss their initial targets. Companies that do pre-launch marketing see 2-3x higher launch-day results. Email is the #1 launch channel by conversion rate. Press coverage has a 24-48 hour impact window. The most successful launches combine 3+ channels simultaneously. Post-launch content (case studies, tutorials) drives 40% of first-year revenue (ProfitWell 2024 SaaS Benchmarks).
## Output Contract

### Deliverable: Markdown GTM Plan

```markdown
# Go-to-Market Plan: [Product/Feature]

## Launch Strategy
- Type: [Big Bang / Phased / Soft / Waitlist]
- Date: [target]
- Budget: $X

## Positioning
- One-liner: [statement]
- Key Messages: 1. [msg] 2. [msg] 3. [msg]
- Differentiator: [vs. competitors]

## Channel Plan
### Pre-Launch
| Week | Channel | Activity | Owner |
|---|---|---|---|
### Launch Week
...
### Post-Launch
...

## Launch Day Playbook
| Time | Action | Owner | Channel |
|---|---|---|---|

## Success Metrics
| Metric | 7-Day Target | 30-Day Target | 90-Day Target |
|---|---|---|---|

## Risk Mitigation
| Risk | Likelihood | Mitigation |
|---|---|---|

## Launch Readiness Checklist
- [ ] Positioning approved
- [ ] Landing page live
- [ ] Email sequences ready
- [ ] PR kit distributed
- [ ] Support team briefed
- [ ] Tracking verified
```

## Platform Implementation Steps

### Project Management (Asana/Notion/Linear)
1. Create a launch project with milestones matching the timeline
2. Break each milestone into tasks with owners and due dates
3. Create a launch day checklist as a separate task list
4. Set up daily standup meetings for the 2 weeks before launch

### Email (Mailchimp/HubSpot/ConvertKit)
1. Build pre-launch teaser sequence (3-5 emails)
2. Create launch day announcement email
3. Design post-launch follow-up sequence
4. Segment audience for personalized messaging

### Social Media (Buffer/Hootsuite/Native)
1. Schedule pre-launch countdown posts
2. Prepare launch day content (10+ posts across platforms)
3. Create a social monitoring dashboard for launch mentions
4. Brief team on real-time response protocol

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Low launch-day traffic | Insufficient pre-launch marketing | Extend launch window; increase paid promotion post-launch |
| Media didn't cover it | Weak pitch or bad timing | Follow up with exclusive angles; pivot to community-driven buzz |
| High signups but low activation | Product-market misalignment or bad onboarding | Focus on activation experiments; gather user feedback immediately |
| Launch overshadowed by competitor | Bad timing | Double down on differentiation messaging; consider a "response" campaign |

## How to Get Your Data

- **No data needed**: Describe your product, audience, and timeline — Claude builds the full GTM plan
- **Market research**: Share any customer interviews, survey results, or competitive analysis
- **Past launches**: Describe what worked and what didn't

## Example

**Input**: "GTM plan for launching an AI-powered email assistant. Target: SMB sales teams. Launch date: April 15. Budget: $15,000. Have a waitlist of 2,000 emails and beta group of 50 users."

**Output**: Phased launch strategy: Beta expansion (April 1-14) → Public launch (April 15) → Sustained campaign (April 16-May 15). Positioning: "Write personalized follow-ups in 10 seconds — not 10 minutes." Pre-launch: waitlist email sequence (5 emails over 2 weeks, featuring beta testimonials), social teaser campaign (LinkedIn focus, 3 posts/week), press outreach to 20 SaaS/sales publications with early access offer. Launch day playbook: 6 AM — publish blog + Product Hunt launch; 8 AM — send waitlist email; 9 AM — LinkedIn post (CEO personal account); 10 AM — paid social activation ($2K daily for launch week). Post-launch: case study from beta users (week 2), comparison content vs. alternatives (week 3), webinar "How AI is Changing Sales Outreach" (week 4). Budget: $5K pre-launch (content + PR), $7K launch week (paid), $3K post-launch (content + retargeting). Targets: 500 signups day 1, 2,000 signups month 1, 200 activated users month 1.

## Related Skills

- **[customer-persona-builder](./customer-persona-builder.md)** — Segment launch messaging by buyer persona before launch.
- **[pricing-page-optimizer](./pricing-page-optimizer.md)** — Optimize pricing page as part of launch planning.
- **[growth-experiment-designer](./growth-experiment-designer.md)** — Design post-launch optimization experiments.
- **[channel-mix-optimizer](./channel-mix-optimizer.md)** — Plan channel strategy for maximum launch impact.
