---
name: podcast-guest-research-brief
description: >
  Research podcast guests and prepare interview briefs with talking points, questions, and audience context.
  Use this skill when the user says "podcast guest research", "interview prep for podcast", "guest brief
  for podcast", "podcast interview questions", "research podcast guest", "prepare for podcast interview",
  "guest talking points", "podcast guest background", "pre-interview research", "podcast guest bio",
  or "interview brief template". Also trigger for podcast booking research, guest outreach, or
  co-host prep material.
---

# Podcast Guest Research Brief

Researches podcast guests and creates comprehensive interview briefs with background, talking points, questions, and audience-relevant angles.

## Granularity Check

> **Time**: ~5 min data prep → ~10 min Claude session → ~30-60 min producing / uploading. Input is guest name/company and podcast context. Output is Markdown interview brief with research, questions, and talking points.

## User Intent Mapping

- "Research this podcast guest" (research)
- "Prepare interview questions" (questions)
- "Guest brief for our next episode" (brief)
- "Talking points for podcast interview" (talking points)
- "Background on our guest" (background)
- "What should I ask this guest?" (questions)
- "Pre-interview prep for podcast" (prep)
- "Make our guest shine on the podcast" (quality)
- "Podcast guest outreach research" (outreach)
- "Interview angle for this guest" (angle)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Guest Name | Text | Who you're interviewing |
| Guest Company/Role | Text | Their current position |
| Podcast Topic | Text | What your podcast covers |

### If You Don't Have This Data

- **Don't know much about the guest?** Claude researches their background, recent work, and public speaking topics to build a comprehensive brief.
- **Not sure what angle to take?** Claude identifies the most interesting intersection between the guest's expertise and your audience's interests.
- **No previous episodes for context?** Describe your audience and podcast format — Claude adapts questions accordingly.
- **Guest is not well-known?** Claude focuses on their work, company, and expertise rather than public profile.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Audience Profile | Text | Who listens to your podcast |
| Episode Theme | Text | Specific topic for this episode |
| Previous Episodes | Text | Past episodes for context |
| Guest's Content | Text | Articles, talks, or interviews by the guest |
| Interview Format | Text | Length, style (conversational, deep-dive, rapid-fire) |

## Process

### Step 1: Guest Background Research
- Current role, company, and responsibilities
- Career trajectory and notable achievements
- Published content (articles, books, talks)
- Recent interviews and media appearances
- Social media presence and recent posts
- Unique perspectives or contrarian views

### Step 2: Angle Identification
- What's the most interesting intersection between guest expertise and audience needs?
- What can this guest say that no one else can?
- What's timely or relevant about this guest right now?
- What would make the audience share this episode?

### Step 3: Question Framework
| Question Type | Purpose | Example |
|---|---|---|
| Ice-breaker | Build rapport, ease in | "What's the most surprising thing about your role?" |
| Origin story | Context and credibility | "How did you get into [field]?" |
| Expertise deep-dive | Core value content | "Walk us through how you approach [topic]" |
| Contrarian/hot take | Engagement and shareability | "What do most people get wrong about [topic]?" |
| Tactical/actionable | Audience takeaway | "What's one thing listeners can do tomorrow?" |
| Future-looking | Thought leadership | "Where do you see [topic] heading in 2-3 years?" |
| Rapid-fire (optional) | Fun, personality | "Favorite tool/book/podcast?" |

### Step 4: Talking Points for Host
- 3-5 key themes to explore
- Transition phrases between topics
- Follow-up questions for deeper exploration
- Topics to avoid (if any)
- Time allocation per section

### Step 5: Episode Promotion Prep
- Suggested episode title options (3-5)
- Key quotes to pull for social media
- Audience hook for episode description
- Guest's social handles for tagging

### Confidence & Sample Size

> **Confidence Note**: Research is only as good as publicly available information. For less well-known guests, supplement with a pre-interview questionnaire (5-10 questions sent before recording). The best podcast interviews feel like conversations, not interrogations — prepare 15-20 questions but expect to use 8-10. Let the guest's answers guide follow-ups rather than sticking rigidly to the script.

### ⚠️ Human Checkpoint
> Review guest's recent public statements for any sensitive topics to navigate. Confirm pronunciation of guest's name and company. Share a brief topic outline with the guest before recording for their comfort.

> **Benchmark Context**: See Edison Research 2024 Podcast Consumer Report, and Wistia 2024 State of Video for current industry benchmarks relevant to this analysis.
## Output Contract

### Deliverable: Markdown Guest Brief

```markdown
# Guest Brief: [Guest Name]

## Guest Profile
- Name: [full name]
- Title: [current role]
- Company: [company]
- Bio: [2-3 sentence bio]
- Social: [handles]

## Background & Key Achievements
[Relevant background for host prep]

## Episode Angle
- Theme: [what this episode is about]
- Unique value: [what only this guest can provide]
- Audience hook: [why listeners should care]

## Interview Questions
### Opening (5 min)
1. [Question]
2. [Question]

### Core Discussion (20-30 min)
3. [Question] — Follow-up: [probe]
4. [Question] — Follow-up: [probe]
5. [Question]
6. [Question]
7. [Question]

### Tactical / Actionable (5-10 min)
8. [Question]
9. [Question]

### Closing (5 min)
10. [Question]
11. Where can listeners find you? [guest plugs]

## Episode Promotion
- Title options: [3-5 suggestions]
- Description: [episode summary]
- Pull quotes: [quotable moments to watch for]
```

## Platform Implementation Steps

### Pre-Interview
1. Send guest a brief questionnaire (5 questions about their expertise and what they'd like to discuss)
2. Review their recent content (last 3 months of posts, articles, interviews)
3. Share episode outline with guest 48 hours before recording
4. Prepare backup questions in case conversation goes off-track

### Recording
1. Brief intro with guest bio (keep to 30 seconds)
2. Start with rapport-building question
3. Follow natural conversation flow, use prepared questions as guide
4. Watch for "pull quote" moments — ask guest to elaborate
5. Leave 2-3 minutes for guest to plug their work

### Post-Recording
1. Pull 3-5 key quotes for social media clips
2. Write episode description using angle and key takeaways
3. Tag guest in all promotion posts
4. Send guest a thank-you with episode release date

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Interview feels like interrogation | Too many questions, no follow-ups | Reduce to 8-10 questions; let conversation flow |
| Guest goes off-topic | No structure or redirection | Use transitions: "That's great — I'd love to connect that to..." |
| Low audience interest | Wrong angle for your audience | Pre-validate angle with 2-3 audience members |
| Guest gives short answers | Questions too narrow or yes/no | Use open-ended questions: "Walk us through..." "Tell me about..." |

## How to Get Your Data

- **Guest research**: LinkedIn profile, personal website, recent articles/interviews
- **Audience context**: Podcast analytics → listener demographics and popular episodes
- **Previous interviews**: Search guest name + "podcast" or "interview" for past appearances
- **No public info**: Send pre-interview questionnaire with 5-10 background questions

## Example

**Input**: "Guest brief for our marketing podcast. Guest: Sarah Chen, VP of Growth at a Series B fintech startup. Episode theme: growth marketing on a limited budget. Our audience: startup marketers and founders."

**Output**: Brief includes: background on Sarah's growth trajectory (took company from $0 to $2M ARR with $50K marketing budget), her published framework on "high-leverage growth channels," and recent LinkedIn posts about PLG. Questions: (1) "What's the first growth channel you'd invest in with under $5K/month?" (2) "Walk us through how you took [company] from zero to $2M ARR — what worked that surprised you?" (3) "What's the biggest growth marketing mistake you see startups make?" (4) "You've written about 'high-leverage channels' — what does that mean practically?" (5) "How do you decide when to stop experimenting and double down on a channel?" (6) "What's one growth tactic that works right now that most people aren't doing?" (7) "If you had to start over tomorrow with $1K and a new product, what would you do first?" Episode titles: "From $0 to $2M ARR on a $50K Budget" / "Growth Marketing When You Can't Outspend Competitors" / "The High-Leverage Growth Playbook for Startups."

## Related Skills

- **[Podcast Show Notes Generator](./podcast-show-notes-generator.md)** — Use guest research to create comprehensive show notes after recording.
- **[Video Script Writer](./video-script-writer.md)** — Script interview questions and talking points based on guest research.
- **[Audience Persona Builder](../insights/audience-persona-builder.md)** — Research guest audience and personas to tailor interview content.
- **[Win-Loss Interview Analyzer](../insights/win-loss-interview-analyzer.md)** — Apply interview analysis methodology to extract insights from podcast guest interviews.
