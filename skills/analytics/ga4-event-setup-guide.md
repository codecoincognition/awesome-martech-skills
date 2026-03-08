---
name: ga4-event-setup-guide
description: >
  Create a GA4 event tracking implementation guide for a website or app.
  Use this skill whenever the user mentions GA4 event tracking, Google Analytics setup,
  event implementation, custom events, conversion tracking, GTM configuration, data layer
  setup, or says things like "help me set up tracking" or "what events should I track"
  or "I need to configure GA4 for my site." Also trigger for Google Tag Manager setup,
  custom dimensions, enhanced measurement, or e-commerce tracking configuration.
---

# GA4 Event Setup Guide

Creates a complete GA4 event tracking implementation guide tailored to a specific business type. Includes recommended events, parameter definitions, GTM tag configuration, data layer code snippets, and a QA checklist.

## Granularity Check

> Completable in one 10-minute session. Input is business type + key actions. Output is a Markdown implementation guide with code snippets.

## User Intent Mapping

- "Set up GA4 event tracking for my SaaS app" (direct command)
- "What events should I track on my e-commerce site?" (guidance)
- "Help me configure Google Tag Manager for GA4" (tool-specific)
- "I need custom events for signup tracking" (specific need)
- "Create a data layer spec for my website" (technical)
- "What GA4 events do I need for a B2B lead gen site?" (industry-specific)
- "Help me track conversions in GA4" (conversion focus)
- "Set up enhanced measurement plus custom events" (comprehensive)
- "I need a tracking plan for our new product launch" (planning)
- "What parameters should my GA4 events have?" (detail-oriented)

## Input Contract

### Required Input

| Field | Type | Description | Example |
|---|---|---|---|
| `business_type` | string | Type of website/app | `"SaaS"`, `"e-commerce"`, `"B2B lead gen"`, `"media/blog"` |
| `key_actions` | list of strings | Top 3-10 user actions to track | `["signup", "pricing_page_view", "demo_request", "feature_usage"]` |

### Optional Input

| Field | Type | Default | Description |
|---|---|---|---|
| `existing_ga4_export` | CSV | `null` | Current GA4 event export for gap analysis |
| `tech_stack` | string | `"standard website"` | Framework/platform (React, WordPress, Shopify, etc.) |
| `gtm_available` | boolean | `true` | Whether Google Tag Manager is set up |
| `current_events` | list | `[]` | Events already implemented |

### Input Validation Rules

1. `business_type` must not be empty
2. `key_actions` should have 3-10 items
3. If `existing_ga4_export` provided, must have `event_name` column

**If validation fails:** Ask user to describe their business and top 3 things they want to measure.

## Process

1. **Assess business type** — Map business type to recommended event categories:
   - SaaS: signup funnel, feature usage, subscription events
   - E-commerce: product views, cart, checkout, purchase
   - B2B Lead Gen: form submissions, content downloads, demo requests
   - Media/Blog: article reads, scroll depth, newsletter signups

2. **Build event taxonomy** — Create a structured list of events:
   - Enhanced Measurement events (auto-tracked, just enable)
   - Recommended events (GA4 standard names: `sign_up`, `purchase`, `generate_lead`)
   - Custom events (business-specific actions)

3. **Define parameters** — For each event, specify:
   - Required parameters (event-specific data)
   - User properties (session-level context)
   - Custom dimensions (for reporting)

4. **Human checkpoint** — Present the event list. Ask: "Does this cover your key measurement needs? Any events to add or remove?"

5. **Generate implementation guide** — Create:
   - Data layer push code for each event
   - GTM tag/trigger/variable configuration
   - Testing and validation steps

6. **Create QA checklist** — Build a testing checklist to verify each event fires correctly.

## Output Contract

### Output Format

| Output | Format | Contents |
|---|---|---|
| Implementation guide | Markdown | Complete tracking spec |

### Guide Structure

```markdown
# GA4 Event Tracking Guide: [Business Type]

## Event Taxonomy
| Event Name | Type | Trigger | Parameters |
|---|---|---|---|

## Data Layer Specifications
[Code snippets for each event]

## GTM Configuration
[Tag, trigger, variable setup for each event]

## Custom Dimensions
[Dimension mapping for reporting]

## QA Checklist
[Validation steps for each event]
```

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Unknown business type | Unusual or niche business | Ask user to describe their key revenue actions |
| Too many events | User wants to track everything | Recommend top 10-15 events; explain event limits |
| No GTM | User can't use Tag Manager | Provide gtag.js code snippets instead |
| Existing events conflict | Current naming doesn't match GA4 standards | Create migration plan from old → new event names |
| Tech stack limitations | Platform restricts data layer access | Provide platform-specific workarounds (e.g., Shopify's built-in tracking) |

## How to Get Your Data

### From GA4 Admin

1. Go to GA4 → Admin → Events
2. Review existing events list
3. Note which events are auto-collected vs. custom
4. Export to CSV via the API or screenshot the list

### From Google Tag Manager

1. Go to GTM → Tags
2. Note existing GA4 event tags
3. Check triggers and variables configured

## Example

**User prompt:** "I need to set up GA4 tracking for our SaaS app. Key actions: signup, trial start, feature usage, upgrade to paid, and support ticket submission."

**Claude output:**

> # GA4 Event Tracking Guide: SaaS Application
>
> ## Event Taxonomy
>
> | Event Name | Type | Trigger | Key Parameters |
> |---|---|---|---|
> | `page_view` | Enhanced | Auto | `page_title`, `page_location` |
> | `scroll` | Enhanced | Auto | `percent_scrolled` |
> | `sign_up` | Recommended | Form submit | `method` (email/google/github) |
> | `trial_start` | Custom | Trial activation | `plan_type`, `trial_duration` |
> | `feature_use` | Custom | Feature interaction | `feature_name`, `feature_category` |
> | `purchase` | Recommended | Upgrade complete | `value`, `currency`, `plan_name` |
> | `support_ticket` | Custom | Ticket submit | `ticket_category`, `priority` |
>
> ## Data Layer: Sign Up Event
> ```javascript
> window.dataLayer.push({
>   event: 'sign_up',
>   method: 'email',
>   user_id: 'usr_12345'
> });
> ```
>
> ## GTM Configuration: Sign Up Tag
> - **Tag type:** GA4 Event
> - **Event name:** sign_up
> - **Trigger:** Custom Event — event equals "sign_up"
> - **Parameters:** method = {{DLV - method}}
>
> [... continues for each event ...]
>
> ## QA Checklist
> - [ ] Enable GA4 DebugView
> - [ ] Trigger each event manually
> - [ ] Verify parameters appear in DebugView
> - [ ] Check real-time reports in GA4
> - [ ] Confirm conversions are marked in GA4 admin
