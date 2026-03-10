---
name: segmentation-rule-builder
description: >
  Design CRM segmentation rules for targeted marketing, sales prioritization, and personalized customer experiences.
  Use this skill when the user says "CRM segmentation rules", "contact segmentation strategy", "list segmentation",
  "audience segmentation in CRM", "dynamic list building", "behavioral segmentation rules", "RFM segmentation",
  "customer segment definitions", "segmentation for email targeting", "CRM list management strategy",
  or "smart list design". Also trigger for segment hygiene, suppression list rules, or segment overlap analysis.
---

# Segmentation Rule Builder

Designs CRM segmentation rules and dynamic lists for targeted marketing campaigns, sales prioritization, and personalized customer experiences.

## Granularity Check

> **Time**: ~5 min data prep → ~10 min Claude session → ~30-60 min configuring in Salesforce / HubSpot. If implementing, add 2-4 hours for CRM configuration. Input is CRM data fields and marketing goals. Output is Markdown segmentation architecture with rule definitions and implementation steps.

## User Intent Mapping

- "How to segment our CRM contacts" (strategy)
- "Build dynamic lists in HubSpot/Salesforce" (implementation)
- "Segmentation rules for email campaigns" (email)
- "RFM segmentation for our customers" (RFM)
- "Our CRM has 50K contacts — how to organize?" (organization)
- "Behavioral segmentation rules" (behavioral)
- "Segment by engagement level" (engagement)
- "Suppression list strategy" (suppression)
- "List hygiene rules" (hygiene)
- "Segment overlap — contacts in too many lists" (overlap)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| CRM Platform | Text | HubSpot, Salesforce, Pipedrive, etc. |
| Contact Volume | Text | Total contacts in CRM |
| Marketing Goals | Text | What you want segmentation to enable |

### If You Don't Have This Data

- **Don't know what fields to segment by?** Claude audits your CRM's available fields and recommends the highest-impact segmentation dimensions.
- **Messy CRM data?** Claude designs a data cleanup strategy alongside segmentation — clean data first, segment second.
- **No behavioral data?** Claude starts with demographic/firmographic segmentation and recommends behavioral tracking setup.
- **Not sure how granular to go?** Claude recommends segment sizes (minimum 500 contacts per segment for email) and warns against over-segmentation.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| CRM Fields | Text | Available data fields for segmentation |
| Current Segments | Text | Existing lists or segments |
| Email Performance | CSV | Open/click rates by segment |
| Customer Data | CSV | Purchase history, engagement data |
| Compliance | Text | Opt-in requirements (GDPR, CAN-SPAM) |

## Process

### Step 1: Segmentation Dimension Hierarchy
| Dimension | Data Source | Example Segments |
|---|---|---|
| Lifecycle stage | CRM field | Subscriber, MQL, SQL, Customer, Churned |
| Engagement level | Behavioral tracking | Active (30 days), Warm (90 days), Cold (90+ days), Dead |
| Industry/Vertical | CRM field | SaaS, E-commerce, Healthcare, Finance |
| Company size | CRM field | SMB (<50), Mid-market (50-500), Enterprise (500+) |
| Product interest | Behavioral/form | Product A, Product B, Multiple |
| Geography | CRM field | Americas, EMEA, APAC |
| Purchase history | Transaction data | New, Repeat, High-value, At-risk |
| Content topic | Engagement data | Topic A readers, Topic B readers |

### Step 2: Engagement Scoring Rules
| Level | Criteria | Action |
|---|---|---|
| Highly engaged | 5+ email opens AND 2+ clicks in 30 days | Priority nurture, sales alert |
| Engaged | 2+ email opens OR 1+ click in 30 days | Regular nurture cadence |
| Warm | 1+ email open in 90 days, no clicks | Re-engagement campaign |
| Cold | No opens in 90 days | Sunset warning sequence |
| Dead | No opens in 180 days, no website visits | Suppress from sends or remove |

### Step 3: Dynamic List Architecture
| List Type | Purpose | Rules | Update |
|---|---|---|---|
| Active list | Contacts meeting criteria right now | Dynamic (auto-updates) | Real-time |
| Static list | Point-in-time snapshot (event attendees) | Manual or import | One-time |
| Suppression list | Contacts to exclude from sends | Dynamic | Real-time |
| Enrollment list | Campaign-specific targeting | Dynamic with date logic | Campaign-based |

### Step 4: Suppression Rules
Always suppress:
- Unsubscribed contacts (legal requirement)
- Hard bounced emails (deliverability)
- Competitors and internal employees (data quality)
- Contacts who purchased in last 7 days (experience)
- Contacts currently in a sales conversation (alignment)
- Contacts who received 3+ emails this week (fatigue)

### Step 5: Segment Overlap Management
- Primary segment assignment: each contact has ONE primary segment
- Multi-segment eligibility: contacts can qualify for multiple campaigns
- Priority rules: if contact qualifies for 2 campaigns, which takes priority?
- Frequency caps: maximum emails per contact per week (typically 2-3)
- Exclusion rules: don't email about Product A if they already own Product A

### Step 6: Segment Health Monitoring
| Metric | Healthy | Warning | Action |
|---|---|---|---|
| Segment growth rate | Positive month-over-month | Flat or declining | Review acquisition for that segment |
| Segment engagement | >20% open rate | <10% open rate | Review content relevance or sunset |
| Segment size | 500+ contacts | <100 contacts | Merge with similar segment or broaden criteria |
| Overlap rate | <20% with other segments | >50% overlap | Refine criteria to reduce overlap |

### Confidence & Sample Size

> **Confidence Note**: Segments smaller than 500 contacts produce unreliable email performance data — you can't tell if 30% open rate is meaningful or noise. Aim for 500-5,000 contacts per segment for reliable A/B testing. Over-segmentation is as dangerous as no segmentation — 20 tiny segments mean 20 separate campaigns to manage. Start with 5-8 core segments and add granularity only when data shows it improves performance. Behavioral segmentation outperforms demographic segmentation for email targeting — what people do matters more than who they are.

### ⚠️ Human Checkpoint
> Review all segmentation rules for GDPR/CAN-SPAM compliance before activating. Verify suppression lists are working correctly (test with known contacts). Check segment overlap to ensure contacts aren't receiving duplicate communications.

> **Benchmark Context**: Segmented email campaigns see 14.3% higher open rates and 100.9% higher click rates than non-segmented (Salesforce 2024 State of Marketing). Companies using 3+ data points for segmentation see 2x conversion improvement (Salesforce 2024 State of Marketing). 77% of marketing ROI comes from targeted, segmented campaigns (Salesforce 2024 State of Marketing). Behavioral segments outperform demographic segments by 3x for email engagement (Salesforce 2024 State of Marketing). List decay rate averages 22.5% per year — regular hygiene is essential. (Salesforce 2024 State of Marketing).
## Output Contract

### Deliverable: Markdown Segmentation Architecture

```markdown
# CRM Segmentation Architecture: [Company]

## Segmentation Strategy
- Primary dimension: [lifecycle/engagement/industry]
- Secondary dimension: [engagement/product/geography]
- Total segments: [number]

## Segment Definitions
| Segment | Criteria | Size (est.) | Primary Use | Owner |
|---|---|---|---|---|

## Dynamic List Rules
### [Segment Name]
- Include: [criteria]
- Exclude: [criteria]
- Update: [real-time/daily/manual]
- Use case: [campaigns, automation, reporting]

[Repeat for each segment]

## Suppression Rules
| Rule | Criteria | Applied To |
|---|---|---|

## Overlap Management
| Primary Segment | Can Also Receive | Cannot Receive |
|---|---|---|

## Hygiene Schedule
| Task | Frequency | Criteria |
|---|---|---|

## Implementation Steps
| Step | CRM Action | Timeline |
|---|---|---|
```

## Platform Implementation Steps

### HubSpot
1. Create active lists for each segment (Contacts → Lists → Create List)
2. Use AND/OR logic for multi-criteria segments
3. Set up engagement tracking properties (last email open, last website visit)
4. Create suppression lists for each campaign type
5. Build reporting dashboard by segment performance

### Salesforce
1. Create Report filters matching segment criteria
2. Build Campaign Member segments for email targeting
3. Use Pardot/Marketing Cloud dynamic lists for behavioral segments
4. Configure Einstein Engagement Scoring for engagement-based segments
5. Set up scheduled reports for segment health monitoring

### General CRM/ESP
1. Map available data fields to segmentation dimensions
2. Create core segments (5-8) based on highest-impact dimensions
3. Set up behavioral tracking for engagement-based segmentation
4. Configure suppression rules and frequency caps
5. Schedule monthly segment health review

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Over-segmentation | Too many tiny segments, can't maintain | Merge segments under 500 contacts; simplify to core dimensions |
| Stale segments | Rules not updated as business changes | Quarterly segment review; dynamic lists over static |
| Missing contacts | Segmentation rules have gaps (no default) | Add "catch-all" segment for uncategorized contacts |
| Deliverability drops | Sending to unengaged segments | Implement engagement-based suppression; sunset cold contacts |

## How to Get Your Data

- **CRM fields**: CRM → Settings → Properties/Fields → export available fields
- **Contact volume**: CRM → Contacts → total count and breakdown by key fields
- **Email metrics**: ESP → Campaign reports → aggregate by segment or list
- **No segmentation yet**: Share your CRM platform and contact volume — Claude designs starter segments

## Example

**Input**: "Segmentation rules for HubSpot CRM. 35K contacts. Mix of leads and customers. Send weekly newsletter and monthly product updates. No current segmentation — same email goes to everyone. B2B SaaS with 3 products."

**Output**: Problem: 35K contacts receiving the same email = low engagement, high unsubscribe risk, wasted sends. Core segments (7): (1) Active Customers — purchased in last 12 months (engagement, retention). (2) New Leads — created in last 30 days, not yet customers (nurture). (3) Engaged Prospects — 2+ email opens in 30 days, not customers (sales-ready). (4) Product A Interest — engaged with Product A content (targeted promotion). (5) Product B Interest — engaged with Product B content. (6) Product C Interest — engaged with Product C content. (7) Cold/Unengaged — no email opens in 90+ days (sunset sequence). Suppression lists: unsubscribed, hard bounced, competitors (identified by domain), internal team. Implementation: Phase 1 (week 1) — create engagement-based segments (active/engaged/cold). Phase 2 (week 2) — create product interest segments from content engagement data. Phase 3 (week 3) — segment newsletter by engagement level, product updates by product interest. Expected results: open rates increase from typical 18% unsegmented to 25-35% segmented. Unsubscribe rate drops 40-50%. Newsletter engagement increases 2x.

## Related Skills

- **[Customer Segmentation Engine](../ai-marketing/customer-segmentation-engine.md)** — Define data-driven segments at the strategic level before operationalizing in CRM rules.
- **[Audience Persona Builder](../insights/audience-persona-builder.md)** — Validate CRM segments map to personas for consistent targeting across channels.
- **[Lead Scoring Model Builder](./lead-scoring-model-builder.md)** — Use segments as criteria and gates within your scoring model logic.
- **[Automation Workflow Designer](./automation-workflow-designer.md)** — Trigger different workflows based on segment membership for targeted nurture.
