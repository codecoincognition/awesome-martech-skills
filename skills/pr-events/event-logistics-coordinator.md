---
name: event-logistics-coordinator
description: >
  Build comprehensive event logistics plans — timelines, checklists, vendor coordination,
  run-of-show, and contingency plans. Use this skill when the user says "plan event logistics",
  "event checklist", "conference planning", "event coordination plan", "run of show document",
  "event timeline", "trade show logistics", "vendor coordination for event", "event day
  runbook", "contingency plan for event", or "event planning checklist". Also trigger when
  the user is organizing a conference, trade show, workshop, user group, or corporate event.
---

# Event Logistics Coordinator

Builds a comprehensive event logistics plan including timeline with milestones, vendor coordination checklist, day-of run-of-show, staffing assignments, and contingency plans. Covers pre-event, day-of, and post-event operations.

## Granularity Check

> Can this be completed in a single 10-minute Claude session? **Yes.** Input is event details. Output is a Markdown logistics plan. No external tool access needed.

## User Intent Mapping

This skill should trigger when the user says things like:

- "Help me plan the logistics for our user conference" (direct request)
- "Create an event day run-of-show" (specific deliverable)
- "What's the checklist for a trade show booth?" (event type specific)
- "Build a timeline for our product launch event" (milestone planning)
- "Coordinate vendors for the annual summit" (vendor management)
- "What could go wrong at this event?" (contingency planning)
- "Staff assignments for the conference" (resource allocation)
- "Pre-event checklist — what am I forgetting?" (completeness check)
- "Post-event follow-up plan" (after-event operations)
- "Plan a 200-person workshop from scratch" (end-to-end planning)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Event Type | Text | Conference, trade show, workshop, webinar, product launch, user group, dinner |
| Event Date | Text | Date(s) of the event |
| Expected Attendance | Number | Approximate headcount |
| Event Goals | Text | Lead generation, brand awareness, customer engagement, product launch |

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Venue | Text | Venue name/type or "virtual" |
| Budget | Number | Total event budget |
| Staff Available | Number | Team members available for event duties |
| Speakers/Sessions | Text | Agenda outline if known |
| Vendors Confirmed | Text | Caterers, AV, printers, etc. already booked |
| Previous Event Notes | Text | Learnings from past events |

## Process

### Step 1: Master Timeline
Build a countdown timeline:
- **12-8 weeks out**: Venue, budget, vendor RFPs, speaker invitations
- **8-4 weeks out**: Registration launch, content creation, vendor confirmations
- **4-2 weeks out**: Attendee communications, print materials, rehearsals
- **2-1 weeks out**: Final confirmations, packing lists, staff briefing
- **Week of**: Setup, tech checks, dry runs
- **Day of**: Run-of-show execution
- **Post-event**: Follow-up, debrief, reporting

### Step 2: Vendor Coordination
For each vendor category:
- Contact and contract status
- Deliverable due dates
- Day-of requirements (setup time, power, space)
- Payment schedule
- Backup vendor identified

### Step 3: Run-of-Show
Minute-by-minute day-of schedule:
- Setup and load-in timeline
- Registration/doors open
- Session start/end times with buffer
- Meal/break timing
- Speaker transitions and AV cues
- Teardown and load-out

### Step 4: Staff Assignments
Role-based assignment matrix:
- Registration desk
- Speaker/VIP liaison
- AV/tech support
- Social media/photography
- Attendee support
- Vendor coordination
- Emergency contact

### Step 5: Contingency Planning
For each critical risk:
- Speaker cancels (backup speaker, recorded content)
- AV failure (backup equipment, alternate format)
- Low attendance (right-size rooms, adjust catering)
- Weather/venue issue (indoor backup, virtual pivot)
- Wi-Fi failure (mobile hotspot, offline materials)

### ⚠️ Human Checkpoint
> Review the run-of-show with all key stakeholders (venue, AV, speakers) at least 1 week before the event. Walk the venue if possible.

## Output Contract

### Deliverable: Markdown Logistics Plan

```markdown
# Event Logistics Plan: [Event Name]

## Event Overview
| Detail | Value |
|---|---|
| Date | [date] |
| Venue | [venue] |
| Attendance | [expected] |
| Budget | [budget] |
| Goals | [goals] |

## Master Timeline
| Weeks Out | Task | Owner | Status |
|---|---|---|---|
| 12 | Book venue | [name] | ☐ |

## Vendor Tracker
| Vendor | Category | Status | Due Date | Cost | Contact |
|---|---|---|---|---|---|

## Run-of-Show
| Time | Activity | Owner | AV Needs | Notes |
|---|---|---|---|---|

## Staff Assignments
| Role | Person | Shift | Location | Radio Channel |
|---|---|---|---|---|

## Contingency Plans
| Risk | Probability | Impact | Mitigation | Owner |
|---|---|---|---|---|

## Post-Event Checklist
- [ ] Send thank-you emails (within 24 hours)
- [ ] Share attendee list with sales (within 48 hours)
- [ ] Collect staff debrief notes
- [ ] Process vendor invoices
- [ ] Publish event recap content
```

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Vague event details | User hasn't decided on format/venue | Build flexible plan with decision points flagged |
| Virtual vs. in-person ambiguity | User says "event" without specifying | Ask — logistics differ dramatically |
| First-time event planner | User doesn't know what they don't know | Use comprehensive checklist, flag items they likely haven't considered |
| Very large event (1000+) | Complexity exceeds single-session scope | Focus on critical-path items, recommend professional event management |

## How to Get Your Data

No data export needed. Bring:
- Event date, type, and expected attendance
- Venue details (or whether you need help selecting)
- Budget (even approximate)
- Any vendors already booked
- Agenda outline (even rough)
- Team member count available for event duties

## Example

**Input**: Product launch event, March 15, 2026, 150 attendees, hotel conference room, $25K budget, 6 staff available. Sessions: keynote, 3 breakout sessions, networking reception. Goal: generate pipeline from prospect attendees.

**Output**: 12-week countdown timeline with 47 tasks. Vendor tracker for catering, AV, signage, photographer. Run-of-show: 8am setup → 9am registration → 9:30 keynote (45 min) → 10:30 breakouts (3 parallel, 40 min each) → 12pm lunch → 1pm demo stations → 2:30pm closing → 3pm networking reception → 5pm teardown. 6 staff assigned across registration (2), speaker liaison (1), AV (1), demo stations (1), photography/social (1). Top 5 contingency plans. Post-event: lead capture sync to CRM within 24 hours, follow-up email sequence within 48 hours.
