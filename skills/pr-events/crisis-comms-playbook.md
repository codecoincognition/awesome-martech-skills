---
name: crisis-comms-playbook
description: >
  Manage crisis communications with structured response plans, messaging frameworks, and stakeholder management.
  Use this skill when the user says "crisis communications", "PR crisis management", "crisis response plan",
  "negative press response", "brand reputation crisis", "social media crisis", "data breach communications",
  "product recall messaging", "crisis messaging framework", "reputation management strategy", or "how to
  respond to bad press". Also trigger for crisis preparedness planning, stakeholder communication during
  crisis, or post-crisis reputation recovery.
---

# Crisis Communications Playbook

Manages crisis communications with structured response frameworks, stakeholder messaging, channel strategy, and post-crisis recovery planning.

## Granularity Check

> **Session time**: During active crisis: ~5 min briefing + ~15 min Claude session for initial response. For preparedness planning: ~15 min context + ~20 min session. Input is crisis details, stakeholders, and communication channels. Output is Markdown crisis response plan with messaging templates, stakeholder matrix, and timeline.

## User Intent Mapping

- "We have a PR crisis — help us respond" (active crisis)
- "Write a crisis response statement" (statement)
- "Social media backlash — what do we do?" (social)
- "Negative press article — how to respond" (press)
- "Crisis communications plan for our company" (preparedness)
- "Data breach notification messaging" (data breach)
- "Customer communication during outage" (service)
- "How to manage bad reviews going viral" (reputation)
- "Internal communication during crisis" (internal)
- "Post-crisis reputation recovery" (recovery)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Crisis Description | Text | What happened, when, who's affected |
| Stakeholders | Text | Who needs to be communicated with |
| Current Status | Text | What's been done, what's known, what's unknown |

### If You Don't Have This Data

- **Crisis is unfolding?** Claude provides an immediate response framework — what to say in the first 60 minutes while you gather more information.
- **Not sure who to communicate with?** Claude maps all stakeholder groups and prioritizes communication order for your specific crisis type.
- **No crisis plan exists?** Claude creates a crisis response plan and preparedness checklist you can adapt for future events.
- **First time handling crisis comms?** Claude provides step-by-step guidance including what NOT to say, common mistakes to avoid, and escalation criteria.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Company Values | Text | Brand values and communication tone |
| Legal Guidance | Text | Any legal constraints on what can be said |
| Media Inquiries | Text | Specific journalist questions to address |
| Social Sentiment | Text | What people are saying online |
| Timeline | Text | Sequence of events leading to crisis |

## Process

### Step 1: Crisis Severity Assessment

| Level | Description | Response Time | Who's Involved |
|---|---|---|---|
| Level 1 — Low | Negative review, minor complaint | 4-24 hours | Marketing/PR team |
| Level 2 — Medium | Viral social post, negative article | 2-4 hours | PR + leadership |
| Level 3 — High | Major incident, data breach, product failure | 1-2 hours | C-suite + legal + PR |
| Level 4 — Critical | Existential threat, regulatory action, public safety | Immediate | Full leadership + external counsel |

### Step 2: First Response Framework (Golden Hour)

| Timing | Action | Content |
|---|---|---|
| 0-30 min | Acknowledge the situation | "We're aware of [issue] and are investigating" |
| 30-60 min | Internal alignment | Brief leadership, legal review, assign spokesperson |
| 1-2 hours | First public statement | Facts known, actions being taken, empathy |
| 2-4 hours | Stakeholder-specific messages | Tailored messages for each stakeholder group |
| 4-24 hours | Detailed response | Full statement with context, next steps, accountability |

Golden rules:
- Speed beats perfection — acknowledge fast, update often
- Never say "no comment" — say "we're looking into it and will share updates"
- Lead with empathy, then facts, then actions
- Only state what you know for certain

### Step 3: Messaging Framework

| Element | Purpose | Example |
|---|---|---|
| Acknowledge | Show you know and care | "We're aware of [issue] and take it seriously" |
| Empathize | Show you understand impact | "We understand this is [frustrating/concerning] for [stakeholders]" |
| Explain | Share what you know | "Here's what happened: [facts only]" |
| Act | What you're doing about it | "We've [actions taken] and are [next steps]" |
| Commit | What happens next | "We'll provide updates [when/how] as we learn more" |

What NOT to say:
- "We take this very seriously" (overused, sounds scripted)
- "This is an isolated incident" (may not be true)
- "It was a mistake" (admits fault before knowing details — check with legal)
- Blame others (even if accurate, comes across as deflecting)
- Minimize the impact (even if actual impact is small)

### Step 4: Stakeholder Communication Matrix

| Stakeholder | Priority | Channel | Key Message | Timing |
|---|---|---|---|---|
| Affected customers | P0 | Direct email + in-app | What happened, what we're doing, what you should do | First |
| All customers | P1 | Email + website banner | Awareness, reassurance, transparency | Within 2-4 hours |
| Employees | P1 | Internal email + Slack | Full context, talking points, what not to say externally | Before/alongside public |
| Media | P2 | Press statement + spokesperson | Official position, key messages, interview offer | After customers |
| Partners/vendors | P2 | Direct email or call | Impact assessment, joint action plan | After customers |
| Investors/board | P1 | Direct call or email | Full transparency, business impact, remediation plan | Within hours |
| Regulators | P0-P1 | Formal notice per requirements | Compliance-focused, factual | Per regulatory timeline |
| Social media public | P1 | Social posts | Brief statement + link to full response | After official statement |

### Step 5: Channel-Specific Response

| Channel | Format | Tone | Length |
|---|---|---|---|
| Website/blog | Full statement | Professional, thorough | 300-500 words |
| Email to customers | Direct, personal | Empathetic, actionable | 200-300 words |
| Social media | Brief statement + link | Human, transparent | 280 characters + link |
| Press/media | Official statement + Q&A | Factual, measured | Statement: 200 words |
| Internal (employees) | Full context + talking points | Honest, supportive | As needed |
| Customer support | FAQ + scripts | Empathetic, helpful | Per question |

### Step 6: Post-Crisis Recovery

| Phase | Timeline | Actions |
|---|---|---|
| Immediate aftermath | Week 1 | Continue updates, monitor sentiment, support affected stakeholders |
| Analysis | Weeks 2-3 | Root cause analysis, process review, identify systemic issues |
| Communication | Week 3-4 | Share findings and improvements with stakeholders |
| Rebuilding | Months 1-3 | Implement changes, demonstrate improvement, rebuild trust |
| Prevention | Ongoing | Update crisis plan, conduct drills, monitor for early warning signs |

### Confidence & Sample Size

> **Confidence Note**: The first 60 minutes of a crisis define the narrative — responding within an hour reduces negative coverage by 40-50% compared to waiting 24 hours. Companies that acknowledge mistakes and take swift action recover brand sentiment 2-3x faster than those that deflect or stay silent. Internal communication before external communication prevents employee leaks that can escalate the crisis. Social media crises have a typical lifecycle of 24-72 hours — most pass quickly if handled well and drag on for weeks if handled poorly.

### ⚠️ Human Checkpoint
> All crisis communications MUST be reviewed by legal counsel before publication — especially for data breaches, product safety issues, or regulatory matters. Never speculate about cause, blame, or impact without confirmed facts. Ensure your spokesperson is media-trained and aligned on key messages before any interviews.

> **Benchmark Context**: 53% of consumers expect brands to respond to a crisis within 1 hour on social media. Companies with a crisis plan respond 2x faster and recover reputation 3x faster. 70% of consumers say a brand's crisis response affects their purchase decisions. Post-crisis transparency (sharing what went wrong and how you fixed it) increases trust by 15-20%. Companies that handle crises well can end up with higher brand trust than before the crisis.

## Output Contract

### Deliverable: Markdown Crisis Response Plan

```markdown
# Crisis Response: [Situation]

## Situation Assessment
- Crisis level: [1-4]
- Description: [what happened]
- Impact: [who's affected and how]
- Status: [current state]

## Key Messages
- Acknowledge: [statement]
- Empathize: [statement]
- Explain: [facts known]
- Act: [what we're doing]
- Commit: [next steps]

## Stakeholder Communications
| Stakeholder | Channel | Message | Timing | Owner |
|---|---|---|---|---|

## Public Statement
[Draft statement — 200-300 words]

## Social Media Response
[Draft social post — brief + link to full statement]

## Customer Email
[Draft email — empathetic, actionable, 200-300 words]

## Internal Communication
[Draft employee message — full context + talking points]

## FAQ / Anticipated Questions
| Question | Approved Response |
|---|---|

## Timeline
| Time | Action | Owner | Status |
|---|---|---|---|

## Recovery Plan
| Phase | Actions | Timeline |
|---|---|---|
```

## Platform Implementation Steps

### Crisis Preparedness (Before a Crisis)
1. Identify potential crisis scenarios for your business
2. Create response templates for each scenario type
3. Define spokesperson(s) and ensure media training
4. Establish an internal escalation chain and contact list
5. Conduct a tabletop crisis exercise quarterly

### Active Crisis Response
1. Activate crisis team and establish communication channel
2. Gather facts and assess severity level
3. Draft and approve initial holding statement
4. Communicate to stakeholders in priority order
5. Monitor social media and news for real-time sentiment

### Post-Crisis
1. Conduct post-mortem within 1 week
2. Document lessons learned and update crisis plan
3. Communicate improvements to affected stakeholders
4. Monitor brand sentiment for 30-90 days
5. Update crisis response templates based on learnings

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Slow response makes it worse | No plan, analysis paralysis, approval bottlenecks | Pre-approve holding statements; empower PR to act in first hour |
| Tone-deaf response | Focused on brand, not on affected people | Lead with empathy; have someone outside the team review tone |
| Internal leak escalates crisis | Employees not briefed before public statement | Always communicate internally before going public |
| Conflicting messages | Multiple spokespeople saying different things | Designate single spokesperson; distribute approved talking points |

## How to Get Your Data

- **Social sentiment**: Social listening tools (Mention, Brandwatch) or manual monitoring of brand mentions
- **Media coverage**: Google Alerts, Meltwater, or manual news search
- **Customer impact**: Support ticket volume, NPS score changes, churn data
- **No monitoring tools**: Set up Google Alerts for your brand name + key terms (free, 2-minute setup)

## Example

**Input**: "Crisis response: a customer posted a viral tweet (45K retweets) showing a bug in our software that exposed other users' email addresses. It's been 2 hours. We've confirmed the bug and fixed it. ~200 users were affected. No passwords or payment data was exposed. We haven't said anything publicly yet."

**Output**: Crisis level: 3 (High) — data exposure + viral social attention. You're 2 hours in and haven't responded — this is urgent. Immediate actions (next 30 minutes): (1) Post on Twitter/X: "We're aware of a data display issue reported earlier today. We identified and fixed the bug within [X] hours. We're reaching out directly to affected users now. More details: [link to blog post]." (2) Publish blog post (300 words): acknowledge the bug, explain scope (email addresses only, no passwords/payment data, ~200 users), explain the fix, outline steps to prevent recurrence. (3) Email the ~200 affected users directly: what happened, that it's fixed, what data was exposed (email only), what to watch for, and a direct contact for questions. (4) Internal Slack: brief all employees with key messages and explicit instruction to not comment publicly — direct all inquiries to PR. Key messages: factual, empathetic, action-oriented. Lead with: "We take our users' privacy seriously. Earlier today, a software bug briefly exposed email addresses for approximately 200 users. We identified and fixed the issue within [X] hours." Avoid: calling it "minor" (the viral tweet means public perception is already amplified). Recovery (next 7 days): publish a technical post-mortem explaining the root cause and new safeguards. Offer affected users a direct line to your security team.
