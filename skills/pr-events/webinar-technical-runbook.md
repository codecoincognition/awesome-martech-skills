---
name: webinar-technical-runbook
description: >
  Generate a complete pre/during/post webinar technical runbook with setup checklists,
  rehearsal scripts, troubleshooting guides, and follow-up workflows. Use this skill when
  the user says "webinar runbook", "webinar checklist", "webinar technical setup",
  "virtual event playbook", "webinar production guide", "prepare for webinar", "webinar
  rehearsal plan", "webinar troubleshooting guide", "live stream checklist", "webinar
  follow-up process", or "how to run a professional webinar". Also trigger when the user
  is planning any live virtual event and needs a production-quality checklist.
---

# Webinar Technical Runbook

Generates a complete production runbook for webinars and virtual events — covering technical setup, rehearsal protocols, live-day operations, troubleshooting procedures, and post-event follow-up workflows.

## Granularity Check

> Can this be completed in a single Claude session? **Yes — expect ~5 min data prep + ~10 min Claude session.** If implementing output in a platform, add 10-20 min for setup. Input is webinar details. Output is a Markdown runbook. No system access needed.

## User Intent Mapping

This skill should trigger when the user says things like:

- "Create a runbook for our webinar next week" (direct request)
- "What's the technical checklist for running a webinar?" (checklist)
- "How do we avoid technical issues during the webinar?" (prevention)
- "Rehearsal plan for our virtual event" (preparation)
- "What to do if the speaker's audio drops mid-webinar" (troubleshooting)
- "Post-webinar follow-up process" (after-event)
- "We've never run a webinar — give us the full playbook" (first-timer)
- "Webinar production guide for our team" (team documentation)
- "Zoom webinar setup checklist" (platform-specific)
- "On-demand replay setup after the live webinar" (post-production)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Webinar Topic | Text | Title and subject of the webinar |
| Date/Time | Text | Date, time, timezone, and duration |
| Platform | Text | Zoom, Webex, GoToWebinar, Teams, Livestorm, custom |
| Format | Text | Solo presenter, panel, interview, demo, workshop |

### If You Don't Have This Data

- **No media list?** Search "[your industry] journalists" on Twitter/X or use Google News to find reporters covering your space.
- **No event details?** Define: date, location, expected attendees, budget range, and primary goal. That's enough to start.
- **No press release history?** Describe your company, product, and the newsworthy event. This skill generates the release from scratch.
- **No attendee data?** Start with your CRM contacts tagged as "event interest" or your email list segments.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Speakers | Text | Names, roles, technical comfort level |
| Expected Attendance | Number | Registered count and expected show rate |
| Interactive Elements | Text | Q&A, polls, chat, breakout rooms, handouts |
| Recording Plan | Text | Record + on-demand, live only, no recording |
| Team Roles | Text | Who's producing, moderating, monitoring chat |
| Integration | Text | CRM, marketing automation for registration/follow-up |
| Previous Issues | Text | Problems from past webinars to prevent |

## Process

### Step 1: Pre-Event Setup (1-2 weeks before)

**Technical Setup Checklist:**
- Platform configuration (registration page, email confirmations, reminders)
- Presenter permissions and roles
- Branding (virtual background, waiting room, lower thirds)
- Registration form fields (for lead capture)
- CRM/marketing automation integration (registrant sync)
- Backup recording setup (platform recording + local backup)
- Test all interactive features (polls, Q&A, chat settings)

**Content Preparation:**
- Slides finalized and uploaded to platform
- Pre-built polls with answer options
- Q&A seed questions (in case audience is quiet)
- Handout/resource links ready
- Speaker bios and introduction scripts

### Step 2: Rehearsal Protocol (2-3 days before)

**Dry Run Checklist:**
- Full run-through with all speakers (45-60 min)
- Test each speaker's audio, video, and screen share
- Practice transitions between speakers
- Test polls, Q&A, and interactive elements
- Verify recording works (start/stop test)
- Review backup plans for each failure scenario
- Confirm roles: who introduces, moderates, monitors chat, handles tech

### Step 3: Day-of Run-of-Show

**Pre-Show (60 min before):**
- Producer opens platform, verifies settings
- Speakers join 30 min early for final sound/video check
- Load slides, open polls, prepare Q&A panel
- Start recording (both platform and local backup)
- Final comms check between producer and speakers

**During Show:**
- Opening: welcome slide with music, start 2 min after scheduled time
- Introduction: moderator introduces speakers (scripted, 2 min)
- Content: speakers present per rehearsed flow
- Engagement: launch polls at planned intervals
- Q&A: moderator filters and sequences questions
- Close: CTA, next steps, thank you

**Post-Show (immediately after):**
- Stop recording
- Export attendee list and engagement data
- Export Q&A log and chat transcript
- Speaker debrief (5 min)

### Step 4: Troubleshooting Guide

| Issue | Detection | Fix | Backup |
|---|---|---|---|
| Speaker audio drops | Moderator monitors | Speaker: reconnect, switch to phone dial-in | Co-host narrates slides while speaker reconnects |
| Screen share fails | Audience can't see slides | Switch presenter, reshare | Upload slides to chat, narrate verbally |
| Platform crashes | Complete outage | Switch to backup Zoom link (pre-configured) | Send email with new link + delay notice |
| Low attendance | <20% show rate | Continue — recording will reach more people | Promote replay aggressively |
| Troll/disruption | Inappropriate chat messages | Mute/remove participant, disable chat if needed | Pre-configure: attendees chat to panelists only |
| Recording fails | No recording indicator | Start backup recording immediately | Ask speakers to re-record key sections after |

### Step 5: Post-Event Follow-Up

**Within 24 hours:**
- Send thank-you email to attendees (with recording link, slides, resources)
- Send "sorry we missed you" email to registrants who didn't attend (with replay link)
- Sync attendee data to CRM with engagement scores
- Share Q&A log with sales team (for follow-up)

**Within 48 hours:**
- Publish recording as on-demand (gate with form for new viewers)
- Create social clips from key moments
- Update landing page from "register" to "watch replay"
- Sales follow-up on hot leads (engaged attendees, high-value questions)

**Within 1 week:**
- Publish performance report (registrations, attendance, engagement, pipeline generated)
- Team debrief and lessons learned
- Plan follow-up content based on top Q&A themes


### Confidence & Sample Size
> **Confidence Note**: Results are only as reliable as your input data. Small datasets (<50 records or <30 days of data) produce directional insights, not statistically significant conclusions. Always note your sample size when sharing results with stakeholders. Recommendations should be validated with A/B testing or additional data before making major strategic changes.

### ⚠️ Human Checkpoint
> Conduct the full rehearsal — never skip it. Most webinar failures are preventable with a proper dry run. Test the exact setup each speaker will use on webinar day.


> **Benchmark Context**: Average press release pickup rate is 1-3% of targeted journalists. Event email invitation open rates average 20-25%, with 2-5% registration conversion. Best press release send times: Tuesday-Thursday, 9-10 AM in the journalist's time zone.

## Output Contract

### Deliverable: Markdown Runbook

```markdown
# Webinar Runbook: [Title]

## Event Details
| Field | Value |
|---|---|
| Date/Time | [date + timezone] |
| Platform | [platform] |
| Format | [format] |
| Expected Attendance | [count] |

## Team Assignments
| Role | Person | Responsibilities |
|---|---|---|

## Pre-Event Checklist (1-2 weeks)
- [ ] [task with owner and due date]

## Rehearsal Plan
[Date, time, agenda, checklist]

## Day-of Run-of-Show
| Time | Activity | Owner | Notes |
|---|---|---|---|

## Troubleshooting Quick-Reference
| Problem | Solution |
|---|---|

## Post-Event Follow-Up
| Timeline | Task | Owner |
|---|---|---|

## Emergency Contacts
| Role | Name | Phone | Email |
|---|---|---|---|
```

## Platform Implementation Steps

### Google Docs (Collaboration)
1. Create a new Google Doc
2. Paste the output content
3. Use Suggesting Mode for stakeholder review
4. Share with PR team and executives for approval

### Notion / Confluence
1. Create a new page in your team workspace
2. Paste Markdown output directly
3. Add status trackers for action items
4. Link to related event pages or campaign briefs

### Email Distribution
1. Copy the finalized output
2. Format for email distribution to media contacts
3. Use your PR tool (Muck Rack, Cision) for targeted sends
4. Track opens and pickups

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Unknown platform | User hasn't chosen a platform yet | Provide platform-agnostic checklist, recommend based on needs |
| Solo operator | One person doing everything | Prioritize critical tasks, recommend recruiting one helper minimum |
| First webinar ever | Team has no experience | Provide extra detail, recommend a practice webinar (internal only) |
| Complex format | Multi-day event or hybrid | Focus on one day/format, note that full production needs more planning |

## How to Get Your Data

No data export needed. Bring:
- Webinar topic, date, and platform
- Speaker names and their technical comfort level
- Expected attendance
- Team members available to help produce
- Any interactive elements planned (polls, Q&A, demos)

## Example

**Input**: "Q1 Product Launch Webinar" on Zoom Webinars, March 20 at 1pm ET, 60 minutes. Panel format: CEO + VP Product + Customer guest. Expected 400 registrants, 150 live. Interactive: 3 polls, live Q&A, product demo. Team: 1 producer, 1 moderator, 1 chat monitor.

**Output**: Complete runbook with 32-item pre-event checklist (platform config, integration with HubSpot, slide prep, rehearsal scheduling). Rehearsal plan for March 18 (full dry run with all 3 panelists). Day-of run-of-show: 12:00pm producer opens room → 12:30pm speakers join → 12:55pm recording starts → 1:00pm welcome slide → 1:02pm CEO intro → 1:15pm VP Product demo → 1:35pm customer story → 1:45pm Q&A → 1:58pm CTA + close. Troubleshooting for 6 scenarios. Post-event: replay email within 4 hours, sales handoff within 24 hours, on-demand page live within 48 hours.
