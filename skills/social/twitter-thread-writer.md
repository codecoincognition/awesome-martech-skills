---
name: twitter-thread-writer
description: >
  Write engaging Twitter/X threads that build authority and drive engagement.
  Use this skill when the user says "write a Twitter thread", "X thread", "tweetstorm",
  "create a thread about", "Twitter content", "write tweets", "tweet thread strategy",
  "turn this into a thread", "thread hook", "Twitter engagement", or "viral thread format".
  Also trigger for single tweet optimization, Twitter content calendars, or tweet copy.
---

# Twitter/X Thread Writer

Writes structured Twitter/X threads with scroll-stopping hooks, clear value delivery, and engagement-optimized formatting. Supports single tweets, threads (3-15 tweets), and thread series.

## Granularity Check

> **Session time**: ~5 min data prep + ~10 min Claude session. If implementing output in a platform, add 5 min for posting. Input is topic or source content. Output is formatted thread with tweet-by-tweet copy.

## User Intent Mapping

- "Write a thread about [topic]" (direct creation)
- "Turn this article into a Twitter thread" (repurposing)
- "Create a tweetstorm about our product launch" (announcement)
- "My threads don't get engagement" (optimization)
- "Write viral-style Twitter content" (technique)
- "Tweet thread hooks that work" (hook-specific)
- "Create a 10-tweet thread about [topic]" (length-specific)
- "Twitter content strategy for B2B" (strategic)
- "Write a single tweet announcing [thing]" (single tweet)
- "X thread about lessons learned from [experience]" (personal)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Topic or Source Content | Text | What the thread is about, or source material to convert |

### If You Don't Have This Data

- **No topic ideas?** Share your area of expertise and 3 opinions you hold strongly. Each is a thread.
- **No source content?** Describe the key insight in 2-3 sentences. Claude structures it into a thread.
- **No audience info?** Describe who you want to attract to your profile.
- **No analytics?** Post and track impressions, likes, and retweets for 2 weeks to baseline.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Thread Length | Number | Preferred tweet count (default: 7-10) |
| Tone | Text | authoritative, casual, contrarian, educational, storytelling |
| Goal | Text | followers, engagement, clicks, brand awareness |
| Audience | Text | Who you're writing for |
| Include Visuals | Boolean | Whether to suggest image/graphic placement |

## Process

### Step 1: Thread Architecture
Choose the thread format:
- **Listicle**: "X [things/lessons/tools] for [outcome]" — highest save rate
- **Story arc**: "How I [achieved X]" — highest engagement rate
- **Contrarian**: "Unpopular opinion: [X]. Here's why." — highest reply rate
- **Breakdown**: "I analyzed [X]. Here's what I found." — highest retweet rate
- **How-to**: "Step-by-step guide to [X]" — highest bookmark rate

### Step 2: Hook Tweet (Tweet 1)
The hook tweet determines 90% of thread performance:
- Must be self-contained (valuable even if nobody clicks "Show this thread")
- Keep under 200 characters for maximum impressions
- Formats that work: bold claim, surprising stat, "I [did X]. Here's what happened."
- Never start with "Thread:" or "🧵" (reduces reach)
- End with a reason to keep reading

### Step 3: Body Tweets (Tweets 2-N)
- One idea per tweet — never split a thought across tweets
- Start each tweet with a transition or standalone hook
- Use the 1-2-1 rhythm: 1 short tweet, 2 medium, 1 short
- Include a "re-hook" at tweet 4-5 (reader drop-off point)
- Add specific numbers, names, or examples (not generic advice)

### Step 4: Closing Tweet
- Summarize the key takeaway in one sentence
- Add a CTA: "Follow me for more on [topic]" or "Retweet tweet 1 to share"
- Self-reference the thread ("If this thread helped you, RT the first tweet")

### Step 5: Formatting & Polish
- 280 characters max per tweet (strict limit)
- Use line breaks for readability
- Limit emojis to 0-1 per tweet
- No hashtags in thread body (add 1-2 in final tweet only)

### Confidence & Sample Size
> **Confidence Note**: Thread performance varies hugely by niche, following size, and timing. Test 3+ threads before drawing conclusions. Engagement rates are not predictable — focus on consistent value.

### ⚠️ Human Checkpoint
> Review for authenticity and accuracy. Add personal experiences, specific numbers from your own data, or named examples. Generic threads underperform personal ones by 3-5x.

> **Benchmark Context**: Average tweet impression rate is 2-5% of followers. Threads get 2-3x more engagement than single tweets. Top-performing threads have 7-12 tweets. Best posting times: Tuesday-Thursday, 8-10 AM and 5-7 PM in your audience's timezone. Bookmark rate is the strongest signal of value.

## Output Contract

### Deliverable: Markdown Thread

```markdown
## Thread: [Title]
**Format**: [listicle/story/contrarian/breakdown/how-to]
**Tweets**: [count]

### Tweet 1 (Hook)
[text]
[char count]

### Tweet 2
[text]
[char count]

...

### Tweet [N] (Close)
[text]
[char count]

## Posting Notes
- Best time: [recommendation]
- Add to first tweet reply: [link if applicable]
- Quote-tweet the hook after 2 hours with an additional insight
```

## Platform Implementation Steps

### Twitter/X (Direct)
1. Compose tweet 1 → click "+" to add subsequent tweets
2. Paste each tweet maintaining line breaks
3. Review character counts (strict 280 limit)
4. Post, then reply to the last tweet with any links
5. Quote-tweet the hook 2 hours later with bonus context

### Typefully / Hypefury / Buffer
1. Create new thread → paste all tweets
2. Review formatting in preview
3. Schedule for recommended time
4. Set up auto-retweet of tweet 1 at +6 hours and +24 hours

### Notion (Content Library)
1. Save thread in your content database
2. Tag by topic, format, and performance tier
3. Repurpose top threads into LinkedIn posts or newsletters

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Hook doesn't grab attention | Too generic or long | Test 3 hook variants; keep under 200 chars |
| Thread too long | Reader drop-off after tweet 5-7 | Cut to 7-10 tweets; move extras to a follow-up thread |
| Low retweets | No shareable standalone tweets | Make tweets 3 and 7 independently valuable (screenshot-worthy) |
| Character count exceeded | Tweet over 280 chars | Split into two tweets or tighten language |

## How to Get Your Data

- **Twitter/X Analytics**: Profile → More → Analytics (or analytics.twitter.com)
- **No analytics**: Describe your topic and audience — Claude generates from scratch
- **Source content**: Paste a blog post, newsletter, or talk transcript to convert

## Example

**Input**: "Thread about why most startups fail at content marketing. Tone: contrarian, B2B."

**Output**:

> **Tweet 1**: Most startups don't have a content problem. They have a distribution problem. They publish 3 blog posts/week that nobody reads. Here's the framework that actually works: (243 chars)
>
> **Tweet 2**: The mistake: treating content like a slot machine. Write → publish → pray for traffic. The fix: spend 20% of time creating, 80% distributing. (153 chars)
>
> **Tweet 3**: Distribution channels that work in 2026: → LinkedIn (repurpose every post) → Email list (your owned audience) → Communities (Reddit, Slack groups, Discord) → SEO (compounds over 6-12 months) (199 chars)
>
> ...
