---
name: chatbot-conversation-designer
description: >
  Design conversational AI flows for marketing chatbots — lead qualification, support, and engagement.
  Use this skill when the user says "chatbot conversation design", "chatbot flow builder",
  "marketing chatbot strategy", "conversational AI for marketing", "lead qualification chatbot",
  "chatbot script design", "website chatbot setup", "chatbot conversation flow", "AI chatbot
  for lead gen", "chatbot personalization", or "chatbot ROI optimization". Also trigger for
  chatbot A/B testing, conversational marketing strategy, or chatbot analytics optimization.
---

# Chatbot Conversation Designer

Designs conversational AI flows for marketing chatbots — lead qualification paths, support routing, engagement scenarios, and personalization rules to convert website visitors into qualified leads.

## Granularity Check

> **Time**: ~5 min data prep → ~15 min Claude session → ~30-60 min configuring in your marketing platform. If implementing, add 1-2 weeks for platform setup and testing. Input is business goals, audience, and qualification criteria. Output is Markdown conversation flow with scripts and logic.

## User Intent Mapping

- "Design a chatbot for our website" (new chatbot)
- "Lead qualification chatbot flow" (lead qual)
- "Chatbot conversation scripts" (scripts)
- "Conversational marketing strategy" (strategy)
- "Our chatbot isn't converting" (optimization)
- "Chatbot for product recommendations" (e-commerce)
- "Support chatbot that escalates to sales" (hybrid)
- "Chatbot personalization by visitor type" (personalization)
- "Chatbot A/B testing plan" (testing)
- "Chatbot ROI — is it worth it?" (ROI analysis)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Business Goal | Text | Lead gen, support deflection, product discovery |
| Target Audience | Text | Who visits your site and their intent |
| Qualification Criteria | Text | What makes a lead qualified |

### If You Don't Have This Data

- **No qualification criteria?** Claude builds BANT-based qualification flow (Budget, Authority, Need, Timeline) adapted to your business.
- **No chatbot experience?** Claude designs a simple 3-5 step flow to start, with testing plan to iterate.
- **No conversion data?** Claude uses industry benchmarks and designs built-in tracking from day one.
- **Not sure which pages?** Claude recommends highest-impact pages for chatbot deployment based on typical visitor intent.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Current Website Flow | Text | How visitors currently convert |
| Common Questions | Text | FAQ from sales or support team |
| CRM Integration | Text | How leads should be passed to sales |
| Brand Voice | Text | Tone for chatbot conversations |
| Page-Level Intent | Text | What visitors want on different pages |

## Process

### Step 1: Conversation Architecture
| Page | Visitor Intent | Bot Goal | Trigger |
|---|---|---|---|
| Homepage | Exploring | Qualify and route | 10s delay or scroll |
| Pricing | Evaluating | Book demo or answer questions | Immediate |
| Product | Learning | Recommend features, offer trial | 15s delay |
| Blog | Researching | Capture email, suggest resources | Exit intent |
| Support | Needs help | Resolve or escalate | Immediate |

### Step 2: Conversation Flow Design
```
[Greeting] → [Intent Detection] → [Qualification Path]
     ↓                                    ↓
[Quick Answer]              [Qualified] → [Book Meeting]
     ↓                      [Not Ready] → [Nurture CTA]
[Follow-up CTA]            [Not Fit] → [Self-Serve Resource]
```

### Step 3: Qualification Flow
- Question 1: Intent identification ("What brings you here today?")
- Question 2: Company/role context ("What's your role?")
- Question 3: Need assessment ("What challenge are you trying to solve?")
- Question 4: Timeline/urgency ("When are you looking to get started?")
- Routing: qualified → calendar booking; nurture → resource offer; not fit → self-serve

### Step 4: Script Writing Guidelines
- Keep messages under 60 words each
- Use conversational, not corporate language
- Offer 2-3 button options (don't make users type)
- Include escape hatch at every step ("Talk to a human")
- Personalize based on known data (returning visitor, page context)
- End every flow with a clear next step

### Step 5: Personalization Rules
| Signal | Personalization | Example |
|---|---|---|
| Returning visitor | Acknowledge return | "Welcome back! Last time you were checking out [feature]" |
| Known company | Reference company | "I see you're from [Company] — here's what works for teams your size" |
| High-intent page | Skip intro | On pricing page, jump straight to "Want a custom quote?" |
| UTM source | Match messaging | From ad campaign → mirror ad copy in greeting |
| Time of day | Adjust availability | After hours → "Our team is offline but I can help with..." |

### Step 6: Escalation & Handoff
- Human handoff triggers: complex question, high-value lead, frustrated user
- Handoff protocol: transfer chat history to agent (no repeat questions)
- After-hours protocol: collect info, schedule callback, offer self-serve resources
- Fallback: if bot can't answer after 2 attempts, offer human or email follow-up

### Confidence & Sample Size

> **Confidence Note**: Chatbot conversion rates vary from 2-15% depending on industry, targeting, and conversation quality. Start with the highest-intent page (pricing) before deploying site-wide. Button responses get 3-5x more engagement than open text inputs. The first message is the most important — 40% of visitors who engage will continue past the first interaction. Test extensively before scaling.

### ⚠️ Human Checkpoint
> Test all conversation paths end-to-end before go-live. Review scripts for brand voice, accuracy, and edge cases. Verify CRM integration passes correct data. Monitor first 100 conversations for unexpected patterns.

> **Benchmark Context**: See McKinsey 2024 State of AI Report for current industry benchmarks relevant to this analysis.
## Output Contract

### Deliverable: Markdown Conversation Design

```markdown
# Chatbot Design: [Brand]

## Deployment Plan
| Page | Trigger | Goal | Priority |
|---|---|---|---|

## Conversation Flows

### Flow 1: [Name]
- Trigger: [condition]
- Steps:
  1. Bot: [message] → Buttons: [options]
  2. [Branch A]: Bot: [message]
  3. [Branch B]: Bot: [message]
- Outcome: [action — book meeting, capture email, etc.]

## Qualification Logic
| Question | Options | Score | Route |
|---|---|---|---|

## Scripts
### Greeting Scripts
- [Variant 1]
- [Variant 2]

### Qualification Scripts
- [Step-by-step]

## Personalization Rules
| Signal | Action | Script Change |
|---|---|---|

## Escalation Protocol
| Trigger | Action | SLA |
|---|---|---|

## A/B Test Plan
| Element | Variant A | Variant B | Metric |
|---|---|---|---|
```

## Platform Implementation Steps

### Drift / Intercom / HubSpot Chat
1. Create bot playbooks matching conversation flows
2. Configure page-level targeting rules
3. Set up CRM integration for lead data sync
4. Build routing rules for sales team assignment
5. Enable calendar booking integration

### Custom Implementation
1. Design conversation state machine (states, transitions, conditions)
2. Build NLP intent classification for open-ended responses
3. Implement context persistence (remember past interactions)
4. Set up analytics tracking (funnel, drop-off, conversion)

### Testing
1. Internal team testing of all conversation paths
2. Shadow mode (chatbot suggests, human reviews) for 1 week
3. Soft launch on one page before expanding
4. Monitor and adjust based on first 200 conversations

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Low engagement rate | Poor trigger timing or irrelevant greeting | Test different triggers; personalize greeting by page; reduce intrusiveness |
| Users drop off mid-flow | Too many questions or confusing flow | Shorten qualification; add progress indicators; use buttons not text |
| Wrong leads qualified | Qualification criteria too loose | Tighten scoring; add disqualification questions; calibrate with sales feedback |
| Users frustrated with bot | Can't find human option or bot loops | Add "Talk to human" at every step; improve fallback responses; detect frustration |

## How to Get Your Data

- **Common questions**: Sales and support teams — what do visitors ask most?
- **Visitor behavior**: Analytics → highest traffic pages, conversion rates, drop-off points
- **Qualification criteria**: Sales team — what makes a lead worth their time?
- **No data**: Describe your business and ideal customer — Claude designs a starter chatbot flow

## Example

**Input**: "Design chatbot for B2B SaaS website. Goal: qualify leads and book demos. ICP: 100+ employees, director+ in marketing. Currently have a demo form with 3% conversion. Want chatbot on homepage and pricing page. Using HubSpot."

**Output**: Two chatbot playbooks: (1) Homepage — trigger after 10 seconds. Greeting: "Hey! Looking for [product category]? I can help you find what you need." → 3 buttons: "See a demo", "Learn more", "Just browsing." Demo path: 3 qualification questions (company size, role, use case) → if qualified, inline calendar booking. Learn more path: "What's your biggest [pain point] challenge?" → route to relevant product page + offer resource download. (2) Pricing page — trigger immediately. "Thinking about [product]? Happy to help you find the right plan." → "Get a custom quote" (qualification flow) or "Compare plans" (self-serve). Qualification: company size (100+ = 10 pts), role (director+ = 10 pts), timeline (this quarter = 10 pts). Score 20+ = book demo immediately. Score 10-19 = offer resource + email capture. Score <10 = self-serve resources. Expected results: chatbot engages 15% of pricing page visitors (vs. 3% form), books 5-8% into demos directly. Net increase: 2-3x more qualified demos from same traffic.

## Related Skills

- **[Lead Scoring Model Builder](../crm/lead-scoring-model-builder.md)** — Integrate lead scoring rules into chatbot qualification flows to identify MQL-ready prospects.
- **[Automation Workflow Designer](../crm/automation-workflow-designer.md)** — Route chatbot-qualified leads into automated CRM workflows for follow-up.
- **[Customer Segmentation Engine](./customer-segmentation-engine.md)** — Use segments to show different chatbot paths to different visitor types.
- **[Personalization & Recommendation Engine](./personalization-recommendation-engine.md)** — Recommend products or content within the chatbot based on conversation context.
