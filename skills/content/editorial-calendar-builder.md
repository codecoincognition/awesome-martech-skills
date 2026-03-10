---
name: editorial-calendar-builder
description: >
  Build a content editorial calendar with topics, keywords, formats, authors, and deadlines.
  Use this skill whenever the user mentions editorial calendar, content calendar, content plan,
  publishing schedule, content roadmap, blog calendar, content pipeline, "plan my content for
  the quarter", "what should I publish next month", content planning, topic calendar, content
  scheduling, or asks "how should I organize my content production". Also trigger on requests
  for content strategy planning, quarterly content plans, or building a content backlog. This
  is different from social-content-calendar which focuses on social media posts — this skill
  plans long-form content production (blog posts, guides, whitepapers, videos).
---

# Editorial Calendar Builder

Plan a multi-week or quarterly editorial calendar for long-form content: blog posts, guides, case studies, videos, and podcasts. Aligns topics with business goals, SEO opportunities, and seasonal trends.

## Granularity Check

> Can this be completed in a single Claude session? **Yes — expect ~5 min data prep → ~10 min Claude session → ~30-60 min implementing in your CMS.** If implementing output in a platform, add 10-20 min for setup. Input is strategy context + optional keyword data. Output is an XLSX calendar. No external tools needed.

## User Intent Mapping

Trigger when the user says:

- "Plan my blog content for Q2" (quarterly planning)
- "Build me an editorial calendar" (direct request)
- "What should I publish next month?" (topic ideation)
- "I need a content roadmap" (strategic planning)
- "Help me organize content production across my team" (operations)
- "Create a publishing schedule with deadlines" (scheduling)
- "I have keyword clusters — now plan the content" (chaining from keyword-cluster-analyzer)
- "Align my content with our product launches" (business alignment)
- "I need to publish 3 posts per week, help me plan" (cadence-based)
- "Build a content pipeline for our marketing team" (team planning)

## Input Contract

### Required Input

| Field | Type | Description |
|---|---|---|
| `business_description` | text | What the company does, target audience |
| `time_period` | string | Month, quarter, or custom date range |
| `publishing_frequency` | string | Posts per week/month |

### If You Don't Have This Data

- **No content strategy?** Describe your product and your top 3 customer pain points. That's enough to generate an outline.
- **No keyword research?** List 5 questions your customers frequently ask. These become your topics.
- **No brand voice guide?** Provide 2-3 examples of content you like the tone of. Claude can infer the voice from examples.
- **No performance data?** Start fresh. After publishing, track views, time-on-page, and conversions for 30 days.

### Optional Input (Improves Quality)

| Field | Type | Description |
|---|---|---|
| `keyword_clusters` | CSV | Output from keyword-cluster-analyzer |
| `content_pillars` | list | 3-5 core themes/topics |
| `upcoming_events` | list | Product launches, conferences, seasonal events |
| `team_members` | list | Writers with specialties |
| `existing_content` | list | Already-published topics (avoid duplication) |
| `content_formats` | list | Blog / Guide / Case study / Video / Podcast |
| `buyer_journey_focus` | string | Awareness / Consideration / Decision / All |
| `competitors` | list | Competitor blogs for differentiation |

### Input Validation Rules

1. Business description required — ask if not provided
2. Frequency must be feasible: flag if >5 posts/week for small teams
3. If keyword clusters provided, map them to calendar slots
4. If events provided, plan content around them (pre/post event)

## Process

1. **Gather context** — Confirm business description, audience, frequency, time period. If content pillars not provided, suggest 4-5 based on business description.

2. **Define content pillars** — Establish 3-5 thematic buckets. Each calendar slot maps to a pillar. Aim for balanced coverage:
   - Pillar A: 30%
   - Pillar B: 25%
   - Pillar C: 25%
   - Pillar D: 20%

3. **Generate topic ideas** — For each publishing slot, create:
   - Working title
   - Target keyword (from clusters or generated)
   - Content format (blog, guide, video, etc.)
   - Buyer journey stage
   - Content pillar
   - Brief description (1-2 sentences)

4. **Apply calendar logic:**
   - Alternate pillars (don't stack same topic 3 weeks in a row)
   - Place event-related content 1-2 weeks before events
   - Front-load evergreen content; place timely pieces near relevant dates
   - Mix formats (not all blog posts — include guides, videos, case studies)
   - Balance journey stages across the period

5. **Add production details:**
   - Draft deadline (publish date minus 5 business days)
   - Review deadline (publish date minus 2 business days)
   - Assigned author (if team provided)
   - Status: Planned / In Progress / In Review / Published
   - Promotion channels (email, social, paid)

6. **Human checkpoint** — Present the calendar overview. Ask: "Does this topic mix look right? Any topics to swap, add, or remove?"

7. **Generate structured output** with calendar view + topic detail tables in Markdown (ready to paste into Google Sheets or Excel).


> **Benchmark Context**: Blog posts averaging 1,500-2,500 words tend to rank highest in search (Content Marketing Institute 2024 B2B Research). Content marketing generates 3x more leads than outbound at 62% less cost (Semrush 2024 State of Content Marketing). Average time to write a 1,500-word blog post is 4-6 hours (research + writing + editing. (Semrush 2024 State of Content Marketing)


### Confidence & Sample Size.
> **Confidence Note**: Results are only as reliable as your input data. Small datasets (<50 records or <30 days of data) produce directional insights, not statistically significant conclusions. Always note your sample size when sharing results with stakeholders. Recommendations should be validated with A/B testing or additional data before making major strategic changes.

## Output Contract

### Output Format

| Output | Format | Contents |
|---|---|---|
| Editorial calendar | Markdown tables + CSV-ready data | Two sections: calendar view + topic briefs — paste into Google Sheets or Excel |
| Calendar summary | Markdown | Monthly overview with pillar balance |

### Sheet 1: Calendar View

| Column | Type | Description |
|---|---|---|
| `publish_date` | date | Planned publication date |
| `day_of_week` | string | Monday, Tuesday, etc. |
| `working_title` | string | Article/content title |
| `content_pillar` | string | Theme category |
| `content_format` | string | Blog / Guide / Case study / Video |
| `target_keyword` | string | Primary SEO keyword |
| `buyer_stage` | string | Awareness / Consideration / Decision |
| `author` | string | Assigned writer |
| `draft_deadline` | date | When draft is due |
| `review_deadline` | date | When review is due |
| `status` | string | Planned |
| `promotion` | string | Channels for distribution |
| `notes` | string | Special instructions |

### Sheet 2: Topic Briefs

| Column | Type | Description |
|---|---|---|
| `working_title` | string | Same as calendar |
| `brief_description` | string | 2-3 sentence content description |
| `target_audience` | string | Who this is for |
| `key_points` | string | 3-5 main points to cover |
| `internal_links` | string | Existing content to link to |
| `competitor_reference` | string | Competitor content to differentiate from |
| `estimated_word_count` | integer | Target length |
| `cta` | string | Call-to-action for this piece |

## Platform Implementation Steps

### WordPress
1. Log in to wp-admin → Posts → Add New
2. Paste the content outline into the editor
3. Use the Heading blocks (H2, H3) for structure
4. Add Featured Image and set Category/Tags before publishing

### Google Docs (Collaboration)
1. Create a new Google Doc
2. Paste the output and use Suggesting Mode for team review
3. Use Insert → Table of Contents for navigation
4. Share with stakeholders for feedback

### CMS-Agnostic
1. Copy Markdown output as-is into any CMS that supports Markdown
2. For HTML-based CMS platforms, convert Markdown to HTML using any converter
3. Adapt headings and formatting to match your site's style guide

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| No content pillars | User hasn't defined strategy | Suggest pillars based on business description and common patterns |
| Too high frequency | Unrealistic for team size | Recommend sustainable pace; suggest repurposing to fill gaps |
| No keyword data | Skipped keyword research | Generate topic ideas from business context; recommend running keyword-cluster-analyzer |
| Overlapping with existing content | User has large content library | Ask for existing content list to avoid duplication |
| Seasonal mismatch | Calendar period doesn't match business seasonality | Research industry seasonal trends; adjust topic timing |

## How to Get Your Data

### From Keyword Cluster Analyzer (Best Path)

1. Run keyword-cluster-analyzer first with your target keywords
2. Take the cluster output (XLSX)
3. Provide it alongside your editorial calendar request
4. Claude maps clusters to calendar slots

### From Google Analytics (Identify What Works)

1. GA4 → Reports → Engagement → Pages
2. Sort by most-viewed content
3. Export top 20 pages → provides input for "existing content" field
4. Helps avoid duplicating winners and identifies underserved topics

### Manual Input

1. Tell Claude your business, audience, and publishing frequency
2. Optionally list 3-5 content pillars
3. Mention any upcoming events or launches
4. Claude generates the calendar from context

## Example

**User prompt:** "I run a B2B SaaS for project management. Plan 3 blog posts per week for April. Our pillars are: product tutorials, industry insights, and customer success stories."

**Claude responds:**

> Here's your April editorial calendar overview:
>
> **Publishing cadence:** Mon/Wed/Fri, 13 posts total
> **Pillar balance:** Tutorials (5), Insights (4), Customer Stories (4)
>
> | Week | Mon | Wed | Fri |
> |---|---|---|---|
> | Apr 6 | Tutorial: Getting Started with Sprint Planning | Insight: PM Trends to Watch in 2026 | Story: How Acme Cut PM Overhead by 40% |
> | Apr 13 | Tutorial: Custom Dashboards Setup | Insight: Remote vs. Hybrid Team Management | Story: StartupCo's Journey to Agile |
> | Apr 20 | Tutorial: Automation Rules for Tasks | Insight: AI in Project Management | Story: Enterprise Co's Migration from Legacy PM |
> | Apr 27 | Tutorial: Integration with Slack/Teams | Insight: The Hidden Cost of PM Tool Sprawl | Story: Agency Team's Workflow Transformation |
>
> Each topic includes a target keyword, brief description, draft deadline (previous Wednesday), and author assignment.
>
> Want me to generate the full XLSX with topic briefs and deadlines?

## Related Skills

- **[Content Pillar Strategy](./content-pillar-strategy.md)** — Use to define the pillar-cluster structure before building your editorial calendar.
- **[Campaign Brief Synthesizer](./campaign-brief-synthesizer.md)** — Use to gather campaign briefs that inform your calendar and align content with campaigns.
- **[Content Distribution Strategy](./content-distribution-strategy.md)** — Use to embed distribution timelines and channel requirements into your editorial calendar.
- **[Social Content Calendar](../social/social-content-calendar.md)** — Use to align social content creation with your broader editorial calendar.
