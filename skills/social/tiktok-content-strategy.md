---
name: tiktok-content-strategy
description: >
  Build a TikTok content strategy with trending formats, posting cadence, and growth tactics.
  Use this skill when the user says "TikTok content strategy", "TikTok growth plan", "TikTok
  for business", "how to grow on TikTok", "TikTok content ideas", "TikTok posting strategy",
  "TikTok algorithm tips", "TikTok content calendar", "TikTok trends for brands", "TikTok
  marketing strategy", or "should our brand be on TikTok". Also trigger for TikTok format
  recommendations, TikTok hook formulas, duet/stitch strategies, or TikTok SEO optimization.
---

# TikTok Content Strategy

Creates a comprehensive TikTok content strategy with format recommendations, content pillars, posting cadence, growth tactics, and trend leveraging playbook tailored to brand goals.

## Granularity Check

> **Session time**: ~5 min data prep + ~10 min Claude session. If implementing output in a platform, add 15-20 min for content calendar setup. Input is brand info and goals. Output is Markdown strategy document with 4-week content plan.

## User Intent Mapping

- "Should our brand be on TikTok?" (platform evaluation)
- "Create a TikTok content strategy for our product" (full strategy)
- "What TikTok formats work for B2B?" (format guidance)
- "How do we grow our TikTok from 0?" (growth plan)
- "TikTok content ideas for a SaaS company" (content ideation)
- "How often should we post on TikTok?" (cadence)
- "What trends should we jump on?" (trend strategy)
- "TikTok vs. Reels — where should we focus?" (platform comparison)
- "How to use TikTok for lead generation" (objective-specific)
- "TikTok SEO — how do we get discovered?" (discoverability)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Brand/Product | Text | What you do, your value proposition |
| Goal | Text | Brand awareness, traffic, leads, sales, community |
| Target Audience | Text | Age, interests, pain points on TikTok |

### If You Don't Have This Data

- **No TikTok account yet?** That's fine — this skill creates your launch strategy from scratch.
- **No video production capability?** Claude recommends low-production formats (talking head, screen recordings, text-on-screen) that require only a phone.
- **No trend awareness?** Claude includes evergreen content pillars that work regardless of trends. Check TikTok Creative Center for current trends.
- **No performance data?** Post 10-15 videos over 3 weeks. Track views, watch time, and follows to establish your baseline.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Current Account | Text | Handle, follower count, top-performing content |
| Competitor Accounts | Text list | 3-5 competitor or aspirational TikTok accounts |
| Resources | Text | Team size, video equipment, talent availability |
| Industry | Text | Vertical for tailored format recommendations |
| Budget | Text | Paid promotion budget, if any |

## Process

### Step 1: Platform Fit Assessment
Evaluate whether TikTok aligns with goals:

| Goal | TikTok Fit | Why |
|---|---|---|
| Brand Awareness | Excellent | Algorithm rewards content quality over follower count |
| Traffic/Clicks | Good | Link in bio, TikTok Shop, paid traffic |
| Lead Generation | Moderate | Requires strong CTA + landing page strategy |
| Direct Sales | Excellent | TikTok Shop, affiliate program, live shopping |
| B2B Thought Leadership | Growing | "Corporate TikTok" and educational content trending |

### Step 2: Content Pillar Development
Define 3-5 content pillars:
- **Educational** (how-to, tips, myths busted) — builds authority
- **Behind-the-scenes** (team, process, day-in-the-life) — builds authenticity
- **Trend participation** (sounds, formats, challenges) — drives discovery
- **Product/Service showcase** (demos, transformations, results) — drives consideration
- **Community/UGC** (reactions, duets, stitches, customer stories) — drives engagement

### Step 3: Format Selection
Match formats to goals and resources:

| Format | Production Level | Best For | Avg. Watch Time |
|---|---|---|---|
| Talking head | Low (phone only) | Education, opinions | 15-45s |
| Text-on-screen | Low (CapCut) | Tips, listicles | 10-30s |
| Screen recording | Low | Software demos, tutorials | 30-60s |
| Voiceover + B-roll | Medium | Storytelling, product | 15-45s |
| Skit/scenario | Medium-High | Entertainment, relatability | 15-60s |
| Polished production | High | Brand campaigns | 30-90s |

### Step 4: Hook & Structure Formulas
- **Hook formulas** (first 1-3 seconds): "Stop scrolling if...", "Nobody talks about...", "POV:", "The reason your X isn't working..."
- **Video structure**: Hook (1-3s) → Context (3-5s) → Value (10-30s) → CTA (3-5s)
- **Retention tactics**: Pattern interrupts, text overlays, fast cuts, open loops
- **CTA types**: Follow for more, link in bio, comment [keyword], save this

### Step 5: Posting Strategy
- Recommended frequency: 3-5x/week minimum for growth phase
- Best posting times: Test between 7-9 AM, 12-2 PM, 7-10 PM in your audience's timezone
- Batch creation: Film 5-10 videos in one session, edit and schedule
- Trend response window: Jump on trends within 24-48 hours of spotting them

### Step 6: Growth Tactics
- TikTok SEO: Keywords in captions, on-screen text, and spoken words
- Hashtag strategy: 3-5 hashtags mixing niche + broad
- Engagement loop: Reply to comments with video responses
- Cross-promotion: Repurpose top TikToks to Reels and Shorts
- Collaboration: Duets/Stitches with complementary creators

### Confidence & Sample Size
> **Confidence Note**: TikTok's algorithm is opaque and changes frequently. What works for one account may not work for another. Post minimum 20-30 videos before evaluating strategy effectiveness. Individual video performance is highly variable — judge by 30-day averages, not single posts.

### ⚠️ Human Checkpoint
> Review content for platform guidelines compliance (music licensing, claims, disclosures for sponsored content). Verify all product claims and disclaimers before posting.

> **Benchmark Context**: Average TikTok engagement rate is 4-6% (highest of any social platform). Videos under 30 seconds have 2x the completion rate. TikTok's algorithm can surface content from accounts with 0 followers. 67% of TikTok users say the platform inspires them to shop. Posting 3-5x/week correlates with 2x faster follower growth vs. 1-2x/week.

## Output Contract

### Deliverable: Markdown Strategy Document

```markdown
# TikTok Content Strategy: [Brand]

## Platform Fit Assessment
- Goal alignment: [score]
- Audience match: [analysis]
- Resource requirements: [assessment]

## Content Pillars
1. [Pillar]: [description] — [% of content]

## Format Recommendations
| Format | Frequency | Example Topics |
|---|---|---|

## Hook Library
1. [Hook formula]: [example]

## 4-Week Content Calendar
| Week | Mon | Wed | Fri | Sat |
|---|---|---|---|---|

## Growth Playbook
- Month 1 target: [followers/views]
- Key tactics: [list]

## Measurement Plan
| Metric | Target | Review Cadence |
|---|---|---|
```

## Platform Implementation Steps

### TikTok Business Account Setup
1. Switch to Business Account in Settings → Manage Account
2. Complete profile: keyword-rich bio, link, profile image
3. Claim your website URL for attribution tracking
4. Set up TikTok Pixel on your website for conversion tracking

### Content Production Workflow
1. Batch film 5-10 videos in one session
2. Edit in CapCut (free, TikTok-integrated) with captions and effects
3. Write captions with keywords and hashtags per the strategy
4. Schedule using TikTok's built-in scheduler or Later/Hootsuite
5. Monitor comments and respond within 2 hours of posting

### TikTok Creative Center
1. Visit ads.tiktok.com/business/creativecenter
2. Browse trending hashtags, sounds, and creators in your region
3. Analyze top-performing ads in your industry for inspiration
4. Use Keyword Insights for TikTok SEO research

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Zero views on videos | Poor hooks or wrong posting times | Test 5 different hook formulas; experiment with posting times |
| Views but no follows | Content isn't building expectation for more | Add series content; use consistent intro/outro branding |
| Following competitors' strategy doesn't work | Different audience, authority, or resources | Find your unique angle; test lower-production authentic formats |
| Content feels forced | Trying to be something you're not | Lean into authenticity; show real people and real processes |

## How to Get Your Data

- **No data needed**: Describe your brand, audience, and goals — Claude generates the full strategy
- **TikTok Analytics**: Profile → Creator Tools → Analytics (requires 100+ followers)
- **Competitor research**: Browse competitor profiles, note top-performing content (sort by Most Popular)
- **TikTok Creative Center**: ads.tiktok.com/business/creativecenter for trending formats

## Example

**Input**: "TikTok content strategy for a B2B project management tool. Goal: brand awareness + lead gen. Audience: startup founders and team leads, 25-40. Small team, no video production experience."

**Output**: Platform fit: Strong — "Corporate TikTok" and productivity content trending heavily. 4 content pillars: Productivity Tips (40%), Behind-the-Scenes of building a SaaS (25%), Trend Participation with work-humor angle (20%), Product Demos as screen recordings (15%). Format: primarily talking head + screen recordings (zero production equipment needed). Hook library: 10 hooks including "The project management mistake killing your startup...", "POV: You're a founder and your team just missed another deadline", "Nobody talks about why standups don't work." 4-week content plan: 4 posts/week, batch-filmed on Mondays. Growth target: 1,000 followers in 60 days. Lead gen mechanic: free template in bio link, CTA "Comment TEMPLATE for the link."
