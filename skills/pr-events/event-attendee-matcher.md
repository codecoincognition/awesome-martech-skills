---
name: event-attendee-matcher
description: >
  Match event attendees to sessions, networking opportunities, and sales reps based on their
  profiles, interests, and account data. Use this skill when the user says "match attendees
  to sessions", "networking recommendations", "attendee session assignment", "who should
  meet whom at the event", "match prospects to reps", "event networking optimizer",
  "attendee interest matching", "personalized event agenda", "route attendees to breakouts",
  or "sales rep attendee assignments". Also trigger when the user has a registration list
  and wants to maximize event value through smart matching.
---

# Event Attendee Matcher

Matches event attendees to relevant sessions, networking groups, and sales rep assignments based on registration data, interests, industry, role, and account value. Maximizes event ROI by ensuring the right people are in the right rooms.

## Granularity Check

> Can this be completed in a single 10-minute Claude session? **Yes.** Input is attendee CSV + session list. Output is XLSX with matching assignments. No system access needed.

## User Intent Mapping

This skill should trigger when the user says things like:

- "Match our attendees to the right breakout sessions" (session assignment)
- "Which prospects should each sales rep prioritize at the event?" (rep routing)
- "Create networking groups based on attendee profiles" (networking)
- "Personalized agenda recommendations for each attendee" (personalization)
- "Who are the VIP attendees we should focus on?" (prioritization)
- "Assign attendees to roundtable discussions" (group formation)
- "Which attendees should meet each other?" (networking facilitation)
- "Route high-value prospects to senior reps" (sales routing)
- "Create seating arrangements based on interests" (logistics)
- "Build an attendee intelligence brief for the sales team" (sales prep)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Attendee List | CSV | Columns: name, email, company, title, industry |
| Sessions/Tracks | Text | Available sessions with descriptions and capacity |

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Registration Interests | CSV column | Topics selected during registration |
| Account Value | CSV column | Deal value, customer tier, or lead score |
| Sales Rep Roster | Text/CSV | Available reps with territory/industry assignments |
| CRM Data | CSV | Existing relationship data (customer, prospect, lead stage) |
| Networking Preferences | CSV column | "looking to meet" or "interests" from registration form |
| Dietary/Accessibility | CSV columns | For meal/seating logistics |

### Sample Input CSV

```csv
name,email,company,title,industry,interests,account_value,relationship
Sarah Chen,sarah@techcorp.com,TechCorp,VP Marketing,SaaS,analytics;automation,150000,prospect
Mike Johnson,mike@retailco.com,RetailCo,CMO,Retail,content;personalization,0,customer
Lisa Park,lisa@healthinc.com,HealthInc,Dir Digital,Healthcare,compliance;analytics,75000,mql
```

## Process

### Step 1: Attendee Profiling
For each attendee, build a profile:
- **Role cluster**: Executive, Director, Manager, Individual Contributor
- **Industry vertical**: Map to available session tracks
- **Interest tags**: From registration + inferred from title/industry
- **Value tier**: VIP (high-value prospect/customer), Standard, General
- **Relationship status**: Customer, prospect, lead, unknown

### Step 2: Session Matching
Score each attendee-session pair (0-100) based on:
- Interest alignment (registration topics vs. session content)
- Role relevance (executive sessions for executives)
- Industry match (industry-specific sessions)
- Capacity constraints (don't over-assign popular sessions)

Generate a recommended agenda per attendee with top 2-3 sessions.

### Step 3: Sales Rep Assignment
Match attendees to reps based on:
- Territory/industry alignment
- Existing relationship (same rep who owns the account)
- Value-based routing (senior reps get VIP attendees)
- Load balancing (no rep gets 20 attendees while another gets 2)

### Step 4: Networking Groups
Create networking clusters (for roundtables, dinners, breaks):
- **By interest**: Group attendees who want to discuss similar topics
- **Cross-pollination**: Mix industries for diverse perspectives
- **Strategic**: Place high-value prospects with happy customers (social proof)
- **Size**: Keep groups at 6-8 for meaningful conversation

### Step 5: VIP Treatment Plan
For top-tier attendees:
- Assign executive sponsor from your team
- Pre-event outreach (personal invitation to exclusive sessions)
- Reserved seating at keynote
- Priority networking introductions
- Post-event follow-up assignment

### ⚠️ Human Checkpoint
> Review VIP assignments and rep routing before the event. Sales reps should review their assigned attendees and prepare talking points. Don't auto-assign without rep input.

## Output Contract

### Deliverable: XLSX (4 sheets)

**Sheet 1: Attendee Session Assignments**
Columns: `name | company | title | tier | session_1 | session_2 | session_3 | personalized_note`

**Sheet 2: Sales Rep Routing**
Columns: `rep_name | attendee_name | company | title | value | relationship | talking_points | priority`

**Sheet 3: Networking Groups**
Columns: `group_id | theme | attendee_name | company | industry | discussion_starter`

**Sheet 4: VIP Plan**
Columns: `attendee | company | value | exec_sponsor | pre_event_action | day_of_action | post_event_followup`

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Sparse registration data | Only name + email, no interests | Match by title/industry inference, note limited personalization |
| Too few sessions | 1-2 sessions, not enough to differentiate | Focus on networking groups and rep routing instead |
| No sales data | No account values or CRM data | Assign tiers by title seniority, treat all as equal priority |
| Large event (500+) | Too many attendees for manual matching | Group into clusters, do individual matching for top 50 VIPs only |

## How to Get Your Data

- **Eventbrite**: Attendees → Export
- **Cvent**: Reports → Registration Summary → Export
- **Splash**: Guest List → Download CSV
- **HubSpot Events**: Form submissions → Export
- **Google Forms**: Responses → Download as CSV
- **CRM**: Cross-reference attendee emails with account data

## Example

**Input**: 120 attendees, 3 breakout tracks (Analytics, Content Strategy, ABM), 4 sales reps, 15 VIP prospects.

**Output**: Session assignments: 45 attendees → Analytics, 40 → Content Strategy, 35 → ABM (based on registration interests + role inference). Rep routing: Rep 1 gets 8 VIPs in SaaS vertical, Rep 2 gets 7 VIPs in healthcare. 15 networking groups of 8 formed (3 by-interest, 2 cross-industry, 1 customer-prospect mix). VIP plan: 15 prospects each assigned an executive sponsor, pre-event LinkedIn message drafted, reserved keynote seating in rows 2-3.
