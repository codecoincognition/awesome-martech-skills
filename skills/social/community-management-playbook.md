---
name: community-management-playbook
description: >
  Build a community management playbook with response templates, escalation paths, and engagement strategies.
  Use this skill when the user says "community management playbook", "social media response guide",
  "community engagement strategy", "how to manage our online community", "social media moderation plan",
  "community guidelines", "response templates for social", "brand voice for community", "social customer
  service playbook", "comment moderation strategy", or "engagement playbook". Also trigger for community
  health metrics, troll management, or building social response SOPs.
---

# Community Management Playbook

Creates a comprehensive community management playbook with response templates, escalation workflows, engagement tactics, and moderation guidelines for social media communities.

## Granularity Check

> **Session time**: ~5 min data prep + ~10 min Claude session. If implementing output in a platform, add 20-30 min for team training. Input is brand info and community context. Output is a Markdown playbook with templates and workflows.

## User Intent Mapping

- "Build a community management playbook" (full playbook)
- "I need response templates for social media" (templates)
- "How should we handle negative comments?" (crisis/moderation)
- "Create community guidelines for our Facebook group" (guidelines)
- "Social media customer service SOP" (process)
- "How do we engage our community better?" (engagement)
- "Troll management strategy" (moderation)
- "Build an escalation path for social issues" (workflow)
- "Community health metrics — what should we track?" (measurement)
- "Brand voice guide for community managers" (voice)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Brand/Product | Text | What your brand does and its personality |
| Platforms | Text | Where your community lives (Facebook, Discord, Reddit, Twitter, LinkedIn, etc.) |
| Community Size | Text | Approximate size and activity level |

### If You Don't Have This Data

- **No community yet?** Describe your target audience and which platform you're considering. Claude will generate a launch playbook.
- **No brand voice guide?** Share 3-5 example responses you've given that felt "right." Claude will infer tone guidelines.
- **No historical issues?** Claude uses common community management scenarios (complaints, spam, trolls, crises) to build your playbook.
- **No metrics baseline?** Start tracking response time, sentiment, and engagement rate. After 30 days, you'll have a baseline.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Brand Voice | Text | Tone descriptors (friendly, professional, witty, etc.) |
| Common Issues | Text list | Top 5 questions/complaints you receive |
| Team Size | Number | How many community managers |
| Industry | Text | For compliance-specific templates (healthcare, finance, etc.) |
| Existing Guidelines | Text | Current community rules, if any |

## Process

### Step 1: Community Audit
- Map all community touchpoints (platforms, groups, forums)
- Identify community types: support, engagement, advocacy, learning
- Assess current response time and coverage gaps
- Flag high-risk scenarios specific to the industry

### Step 2: Response Framework
Build tiered response templates:

| Tier | Type | Response Time | Owner |
|---|---|---|---|
| 1 | Positive mentions, simple questions | < 1 hour | Community manager |
| 2 | Complaints, feature requests | < 4 hours | Community manager |
| 3 | Escalations, legal/PR risks | < 30 min | Manager + PR |
| 4 | Crisis (viral negative, data breach) | < 15 min | Leadership + Legal |

### Step 3: Template Library
Generate templates for:
- Positive engagement (thank you, reshare, amplification)
- FAQ responses (pricing, features, availability)
- Complaint handling (acknowledge, investigate, resolve)
- Negative review responses (empathy, action, follow-up)
- Troll/spam management (warning, mute, ban criteria)
- Crisis holding statements
- Community milestone celebrations

### Step 4: Engagement Playbook
- Daily engagement routines (proactive commenting, UGC spotlighting)
- Weekly community activations (polls, AMAs, challenges)
- Monthly community health reviews
- Advocacy program mechanics (identifying and nurturing superfans)

### Step 5: Moderation Guidelines
- Acceptable use policy
- Warning → mute → ban escalation ladder
- Content removal criteria (hate speech, spam, off-topic, misinformation)
- Appeals process

### Confidence & Sample Size
> **Confidence Note**: Response templates should be customized to your brand voice over time. Track which templates get positive reactions and iterate. Community management is more art than science — use these as starting frameworks, not rigid scripts.

### ⚠️ Human Checkpoint
> Review all templates for brand voice alignment, legal compliance (especially in regulated industries), and cultural sensitivity before distributing to your team.

> **Benchmark Context**: Average brand response time on social is 5 hours; top brands respond in under 1 hour. Responding to complaints publicly increases brand favorability by 25%. Communities with active moderation retain 40% more members. 71% of consumers who have a positive social media experience recommend the brand.

## Output Contract

### Deliverable: Markdown Playbook

```markdown
# Community Management Playbook: [Brand]

## Brand Voice for Community
- Tone: [descriptors]
- Do: [examples]
- Don't: [examples]

## Response Templates

### Tier 1: Positive Engagement
**Template: Thank You**
"[response text]"
Use when: [scenario]

### Tier 2: Complaint Handling
**Template: Acknowledge + Investigate**
"[response text]"
Use when: [scenario]
Escalate if: [criteria]

### Tier 3: Escalation
**Template: Holding Statement**
"[response text]"
Notify: [who]

## Engagement Calendar
| Day | Activity | Platform | Owner |
|---|---|---|---|

## Moderation Guidelines
1. [Rule]: [enforcement action]

## Escalation Workflow
[Flowchart description]

## Metrics Dashboard
| Metric | Target | Frequency |
|---|---|---|
```

## Platform Implementation Steps

### Sprout Social / Hootsuite
1. Import response templates into Saved Replies / Quick Responses
2. Set up auto-assignment rules matching the escalation tiers
3. Configure response time SLA alerts
4. Create team-specific inboxes for different issue types

### Discord
1. Set up channels matching your community structure (#welcome, #support, #general)
2. Configure AutoMod with your moderation keywords
3. Create role-based permissions matching escalation tiers
4. Pin community guidelines in #rules channel

### Facebook Groups
1. Post community guidelines as a pinned announcement
2. Set up membership questions aligned with your guidelines
3. Enable Admin Assist for keyword-based auto-moderation
4. Create Saved Replies for common questions

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Templates sound robotic | Over-reliance on scripts | Add personalization fields; train team on adapting tone |
| Escalation bottleneck | Too many Tier 3 issues | Review tier criteria; empower Tier 1 to handle more |
| Community feels ignored | Slow response times | Set platform-specific response SLAs; hire more moderators |
| Troll takeover | No moderation framework | Implement proactive moderation; use platform tools |

## How to Get Your Data

- **No data needed**: Describe your brand, platforms, and community size — Claude generates the full playbook
- **Existing templates**: Paste your current response templates for Claude to organize and improve
- **Community feedback**: Export community survey results or complaint logs for tailored templates

## Example

**Input**: "Community management playbook for a B2B SaaS company. Platforms: LinkedIn, Twitter, Slack community (500 members). Brand tone: helpful, knowledgeable, slightly informal. Common issues: billing questions, feature requests, integration bugs."

**Output**: Full playbook with 15+ response templates across 4 tiers. Engagement calendar with weekly LinkedIn polls, monthly Slack AMAs, and quarterly community spotlights. Moderation guidelines for Slack (spam, self-promotion limits, off-topic rules). Escalation path: Community Manager → Support Lead → Product Manager → VP of Customer Success. Metrics: response time target <2 hours, community NPS quarterly, engagement rate >15%.
