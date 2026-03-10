---
name: Social Content Calendar
description: "Plan your social media strategy month-by-month. Need a content calendar for Instagram, LinkedIn, Twitter, TikTok? Want to batch-create social posts with hashtags and CTAs? Planning seasonal campaigns and key date activations? Need platform-specific posting times? Looking for content pillar organization? Want visual direction for posts? Need brand voice consistency across platforms? Creating hashtag strategies? Planning engagement tactics? Building content calendar from brand guidelines? This skill generates a complete social media calendar with posting schedules, copy, hashtags, visual direction, and platform-specific optimization."
---

## User Intent Mapping

| User Says | Underlying Need |
|-----------|-----------------|
| "Create a social media calendar" | Full month/quarter planning with posts |
| "Plan Instagram content for March" | Platform-specific calendar with visual direction |
| "I need 60 LinkedIn posts" | Batch generation with professional messaging |
| "Build a content strategy" | Content pillars + posting schedule + themes |
| "What should we post about?" | Topic generation from brand + audience + key dates |
| "Schedule our seasonal campaign" | Time-specific posts aligned with calendar events |
| "Give me hashtag strategy" | Hashtag research + relevant tags per platform |
| "Plan TikTok content" | Short-form, trend-based, youth-oriented scheduling |
| "Multi-platform posting plan" | Different content per platform, coordinated calendar |
| "What time should we post?" | Platform-specific optimal posting times |

## Input Contract

**Required Fields (Form or CSV):**
| Field | Type | Description | Example |
|-------|------|-------------|---------|
| `brand_name` | text | Your company/brand name | "TechFlow" |
| `brand_voice` | text | Tone and personality | "Casual, empowering, slightly humorous" |
| `platforms` | list | Platforms to plan for | ["Instagram", "LinkedIn", "Twitter"] |
| `posting_frequency` | text | Posts per week/platform | "Instagram: 4x/week, LinkedIn: 3x/week" |
| `target_audience` | text | Who you're talking to | "SaaS marketers, ages 25-44, startup founders" |
| `content_pillars` | list | Main topics/themes (3-5) | ["Product tips", "Customer stories", "Industry insights", "Behind-the-scenes"] |
| `campaign_theme` | text | Month's primary theme | "Q1: Growth acceleration" |
| `key_dates` | list | Important dates/events | ["Q1 Product launch: Mar 15", "Earth Day: Apr 22"] |

**Optional Fields:**
| Field | Type | Example |
|-------|------|---------|
| `visual_style` | text | "Minimalist, bright colors, illustrated" |
| `hashtag_strategy` | text | "Mix trending + branded + niche hashtags" |
| `engagement_tactics` | list | ["Polls", "Q&A", "User-generated content"] |
| `industry_events` | list | Trade shows, webinars, conference dates |
| `competitor_keywords` | list | Keywords to monitor/incorporate |

**Validation Rules:**
- Brand name: non-empty, <100 chars
- Platforms: minimum 1, maximum 5
- Posting frequency: numeric values present
- Content pillars: 3-5 items minimum
- Key dates: Valid date format (YYYY-MM-DD) or descriptive text
- Target audience: >10 characters, specific enough

**Sample Input (Form):**
```
Brand Name: EcoBlend (sustainable beverage startup)
Brand Voice: Warm, educational, eco-conscious, conversational
Platforms: Instagram, LinkedIn, TikTok
Posting Frequency: Instagram 5x/week, LinkedIn 3x/week, TikTok 4x/week
Target Audience: Health-conscious millennials/Gen Z, ages 20-35, eco-focused, urban
Content Pillars:
  1. Sustainability impact
  2. Product tutorials & recipes
  3. Founder/team stories
  4. Community spotlights
  5. Ingredient sourcing
Campaign Theme: "Spring Refresh 2026"
Key Dates:
  - Earth Day (Apr 22)
  - Launch strawberry variant (Apr 15)
  - TikTok challenge launch (Apr 1)
Visual Style: Bright, natural photography, minimalist design, green/cream color palette
```

### If You Don't Have This Data

- **No social analytics?** Start by describing your audience and goals. This skill generates a content plan that you can then measure.
- **No content pillars?** List 3-5 topics you could talk about every week without running out of ideas. Those are your pillars.
- **No posting schedule?** Industry defaults: B2B LinkedIn 3-5x/week, Instagram 3-5x/week, X/Twitter 1-3x/day, TikTok 1-3x/day.
- **No past performance data?** Check your last 10 posts' engagement (likes, comments, shares) manually. Identify the top 3.

## Process

1. **Brand & Audience Analysis**
   - Confirm brand voice and messaging platform
   - Validate content pillars align with business goals
   - Map target audience to platform preferences
   - **Human Checkpoint:** Approve brand voice tone and pillars

2. **Content Calendar Framework**
   - Create month-long calendar structure (30-31 days)
   - Assign content pillars to days (balanced distribution)
   - Map key dates/campaigns to specific windows
   - Calculate post slots per platform
   - **Human Checkpoint:** Review calendar structure and pillar distribution

3. **Post Copy Generation**
   - Generate 4-5 draft posts per content pillar
   - Adapt voice to each platform (formal for LinkedIn, casual for TikTok)
   - Ensure copy length matches platform norms (280 chars Twitter, 2,200 chars Instagram caption)
   - Include micro-copy (CTA, engagement hooks)
   - **Human Checkpoint:** Approve tone and messaging samples

4. **Hashtag & Visual Strategy**
   - Research 5-10 relevant hashtags per platform
   - Mix: trending (10%) + niche (50%) + branded (40%)
   - Define visual direction per platform
   - Create guidelines for image/video specs
   - **Human Checkpoint:** Validate hashtag strategy

5. **Platform-Specific Optimization**
   - Instagram: Captions with emojis, hashtags (bottom), carousel/Reels strategy
   - LinkedIn: Professional tone, thought leadership angles, article links
   - Twitter: Conversational, reply-worthy, 240-char sweet spot
   - TikTok: Trend-forward, audio strategy, hashtag challenges
   - **Human Checkpoint:** Review platform-specific formats

6. **Scheduling & Timing**
   - Assign optimal posting times per platform/audience
   - Stagger posts to avoid overlap
   - Include engagement windows (e.g., monitor comments 30 min post-publish)
   - Add prep/approval checkpoints
   - **Human Checkpoint:** Approve posting schedule

7. **XLSX Calendar Export**
   - Compile all posts into calendar view
   - Generate accompanying strategy document


> **Benchmark Context**: Average LinkedIn engagement rate is 0.35-0.50%. Instagram average engagement rate is 0.60-0.80% (declining from 1.2% in 2022). Posting frequency sweet spot: LinkedIn 3-5x/week, Instagram 3-7x/week. Video content gets 2-3x more engagement than static images.


### Confidence & Sample Size
> **Confidence Note**: Results are only as reliable as your input data. Small datasets (<50 records or <30 days of data) produce directional insights, not statistically significant conclusions. Always note your sample size when sharing results with stakeholders. Recommendations should be validated with A/B testing or additional data before making major strategic changes.

## Output Contract

**XLSX Workbook:**

**Sheet 1: Calendar View (Month Grid)**
```
Week | Date | Day | Instagram Post | LinkedIn Post | Twitter Post | TikTok Post | Notes
1 | Apr 1 | Tue | Product Recipe #1 (Carousel) | Industry insight | Q&A reply thread | Trend dance video | TikTok challenge launch
1 | Apr 2 | Wed | Behind-the-scenes | - | Engagement poll | - |
1 | Apr 3 | Thu | - | Company culture story | News commentary | Duet challenge |
```

**Sheet 2: Detailed Posts**
```
Date | Platform | Content Pillar | Post Copy | CTA | Hashtags | Visual Direction | Posting Time | Engagement Tactics
Apr 1 | Instagram | Product Tips | "Meet your new spring ritual... [recipe details]" | "Tag a friend!" | #EcoBlend #Sustainable #HealthyLiving | Bright flat-lay, green tones | 9 AM | Ask which flavor variant |
Apr 1 | TikTok | Product Tips | [Script: 15s trend dance + product sip transition] | "Make your own!" | #EcoBlend #SpringRefresh #HealthyChoices | Trending audio, quick cuts | 6 PM | User duet/stitch challenge |
Apr 2 | Instagram | Behind-the-Scenes | "Meet our farmers in Peru... [story]" | "Learn more in bio" | #BehindTheScenes #Sustainability #EcoBlend | Candid farm photos | 10 AM | Story polling |
```

**Sheet 3: Hashtag Strategy**
```
Platform | Hashtag Category | Hashtags (Ranked by reach)
Instagram | Trending | #HealthyChoices, #SustainableLiving, #EcoFriendly
Instagram | Niche | #EcoBlend, #SustainableBeverage, #PlantBasedDrinks
Instagram | Branded | #EcoBlendRecipe, #EcoBlendCommunity
LinkedIn | Industry | #Sustainability, #GreenBusiness, #FoodTech
LinkedIn | Authority | #ThoughtLeadership, #StartupLife, #Entrepreneurship
Twitter | Trending | (Daily monitoring) #ClimateAction, #GreenTech
TikTok | Trend | (Audio-based - monitored weekly for trends)
```

**Sheet 4: Visual Direction & Assets**
```
Platform | Post Type | Image Specs | Photography Style | Color Palette | Key Elements
Instagram | Feed (Static) | 1080x1350px, square 1:1 also | Bright, natural, lifestyle | Green/cream/white | Product + lifestyle context
Instagram | Reels | 1080x1920px, 9:16 | Fast-paced, trend-based | Same palette | Product demo or trend participation
LinkedIn | Article thumbnail | 1200x627px | Professional, polished | Corporate colors | Graph, team, or key visual
TikTok | Video | 1080x1920px, 9:16 | Trendy, authentic, high-energy | Vibrant, on-trend | Creator/founder, product, trend audio
```

**Sheet 5: Posting Schedule & Times**
```
Platform | Optimal Posting Times | Rationale | Monitoring Window | Engagement SLA
Instagram | 9 AM & 6 PM (Mon-Fri) | Peak commute/evening leisure | 30 min post-publish | Like/comment within 1 hour
LinkedIn | 8 AM (Tue-Thu) | Weekday work browsing | 2 hours | Engage with early commenters
Twitter | 10 AM, 2 PM, 7 PM | Multiple engagement waves | 15 min per post | Reply to replies within 1 hour
TikTok | 6 PM & 9 PM (daily) | Evening scrolling peak | 1 hour | Duet/stitch with early responses
```

**Sheet 6: Content Pillar Distribution**
```
Pillar | Weekly Posts | Month Total | Themes | Sample Topics
Sustainability Impact | 2-3 | 8-12 | Carbon footprint, sourcing ethics, waste reduction | "How we offset 1 ton of CO2 monthly", "Meet our farmers"
Product Tips | 2-3 | 8-12 | Recipes, usage ideas, flavor features | "5 springtime recipes", "Hidden ingredient benefits"
Founder/Team Stories | 1-2 | 4-8 | Behind-the-scenes, culture, values | "Day in the life", "Why we started EcoBlend"
Community Spotlights | 1 | 4 | Customer stories, user-generated content, testimonials | "Customer of the month", "Your EcoBlend moment"
Industry Insights | 1 | 4 | Trends, thought leadership, news commentary | "Q1 sustainability report takeaways", "Plant-based market growth"
```

## Platform-Specific Best Practices

**Instagram:**
- Post at 9 AM (commute) and 6 PM (evening leisure) for highest engagement
- Reels get 2-3x more reach than static posts — allocate 30% of content to video
- Hashtags: Use 20-30 relevant hashtags (place in first comment, not caption)
- Captions: 100-150 words optimal; include CTA
- Engagement: Reply to all comments within 1 hour for boost; use emojis strategically
- Stories: Post 1-2 daily for visibility; use polls/questions for engagement

**LinkedIn:**
- Post Tuesday-Thursday at 8-9 AM for B2B engagement
- Focus on thought leadership, industry insights, culture/values
- Captions: 100-200 words; avoid aggressive selling
- Hashtags: 3-5 relevant industry tags (not trending, niche-focused)
- Engagement: Share from employees' personal profiles for amplification
- Format: Articles > Posts with personal narrative; video performs well

**Twitter/X:**
- Post at 10 AM, 2 PM, 7 PM for multi-wave engagement
- Keep under 240 characters for maximum retweets (leaves room for quote-tweets)
- Use threads (3-5 tweets) for deeper topics
- Engagement: Reply-focused; engage with other brands, influencers, news
- Hashtags: 1-2 max; focus on conversation, not reach
- Monitor replies within 15 minutes for real-time conversation

**TikTok:**
- Post 4-7x per week; algorithm favors consistent creators
- Post at 6 PM & 9 PM for evening leisure viewing
- Hook viewers in first 3 seconds; trend-based audio critical
- Captions: Keep under 150 characters; use CTAs ("duet this!", "stitch with us!")
- Hashtags: 4-7 relevant tags; #FYP does NOT increase reach (algorithm-based)
- Engagement: Participate in trends weekly; respond to comments with video replies
- Trends: Monitor every 3-4 days for relevant audio/trend alignment

## Platform Implementation Steps

### Buffer / Hootsuite / Later
1. Create a new post for each calendar entry
2. Paste the caption, hashtags, and media notes
3. Schedule according to the recommended posting times
4. Use the built-in analytics to track performance

### Native Platform Publishing
1. Open the platform (Instagram, LinkedIn, X, etc.)
2. Create a new post with the provided caption
3. Add hashtags and tag relevant accounts
4. Post at recommended times or save as draft

### Google Sheets (Calendar Tracking)
1. Create a content calendar spreadsheet
2. Add columns: date, platform, caption, media, status
3. Color-code by content pillar
4. Track engagement metrics post-publish

## Failure Modes

| Scenario | Symptom | Resolution |
|----------|---------|------------|
| No visual assets | Calendar created but no images identified | Note "ASSETS NEEDED"; recommend stock photo sources (Unsplash, Pexels) or note days requiring new photography |
| Platform mismatch | TikTok content ideas are too formal/corporate | Regenerate with appropriate tone; flag platform-tone misalignment |
| Thin content pillars | Only 2 pillar ideas; calendar becomes repetitive | Suggest additional pillars; recommend quarterly theme rotation |
| Key date overlap | Multiple campaigns fight for same week | Consolidate or stagger; ask user to prioritize |
| No engagement plan | Posts scheduled but no response strategy | Add engagement monitoring column; suggest team assignment for monitoring |
| Hashtag fatigue | Same hashtags every post | Rotate hashtag sets weekly; suggest seasonal variations |

## How to Get Your Data

**Brand Voice Reference:**
- Collect 3-5 competitor posts you admire (tone/format)
- Review your previous best-performing posts
- Write 2-3 sample posts to establish tone
- Share brand guidelines if they exist

**Content Pillar Ideas (By Industry):**
- **SaaS/B2B:** Product features, customer stories, industry insights, thought leadership, company culture
- **E-commerce:** Product showcases, tutorials, behind-the-scenes, user-generated content, seasonal campaigns
- **Creator/Personal Brand:** Daily life, expertise sharing, hot takes, Q&A, exclusive previews
- **Non-profit:** Mission impact, beneficiary stories, volunteer spotlights, awareness campaigns, donor appreciation
- **Health/Wellness:** Tips & tricks, expert interviews, user transformations, myth-busting, lifestyle content

**Key Dates by Industry:**
- **General:** Earth Day (4/22), Mental Health Awareness (5), Pride Month (6), International Day (various)
- **Retail:** Black Friday (11/28), Cyber Monday (12/1), Holidays (12), New Year (1)
- **B2B:** Conference season, webinar dates, product releases, industry reports
- **Creator:** YouTube Rewind, TikTok Awards, Hype House collaborations, trend emergence

**Optimal Posting Times (by platform & region):**
- **US Eastern:** Instagram 9AM/6PM, LinkedIn 8AM Tue-Thu, Twitter 10AM/2PM/7PM, TikTok 6PM/9PM
- **US Pacific:** Shift back 3 hours; adjust for timezone audience concentration
- **Global:** Test with own audience insights; use platform analytics

## Full Example

**Scenario:** EcoBlend (sustainable beverage startup) plans April content calendar for 3 platforms (Instagram, LinkedIn, TikTok). Focus: Spring refresh campaign + product launch (Apr 15) + Earth Day (Apr 22). Audience: Health-conscious millennials/Gen Z, urban, eco-focused.

**Output Calendar (Selected Posts):**

**April 1 (Tuesday) — Campaign Kickoff**
- **Instagram:**
  - Copy: "Spring is here 🌱 Ready to refresh your routine? We're dropping our new strawberry-mint blend THIS MONTH. Swipe for the recipe that started it all. #EcoBlend #SpringRefresh #HealthyLiving"
  - Visual: Bright flat-lay of strawberry, mint, glass of blend, natural sunlight
  - Hashtags: #EcoBlend #Sustainable #PlantBased #HealthyChoices #GreenLiving
  - Time: 9 AM
  - CTA: "Save this recipe!"

- **TikTok:**
  - Script: [Creator does trending spring aesthetic dance, transitions to sipping EcoBlend, text overlay: "Your new spring ritual"]
  - Audio: Trending spring-themed TikTok audio (current trending)
  - Hashtags: #EcoBlend #SpringRefresh #HealthyChoices
  - Time: 6 PM
  - CTA: "POV: You've found your new favorite drink"

**April 7 (Monday) — Sustainability Focus**
- **LinkedIn:**
  - Copy: "1 month in, and here's what we've learned: Building a sustainable beverage company means making hard choices. We source 100% of strawberries from fair-trade farms in Peru. It costs 2x more. We do it anyway. Why? Because the alternative—cheap at any cost—isn't actually cheap. It extracts from communities and ecosystems. Here's the math... [article link]"
  - Hashtags: #Sustainability #GreenBusiness #Startups
  - Time: 8 AM
  - CTA: "Read our sourcing impact report"

**April 15 (Tuesday) — Product Launch**
- **Instagram (Carousel - 5 slides):**
  - Slide 1: "We've been waiting for this moment 🍓 Meet the strawberry-mint blend"
  - Slides 2-4: Product features, user testimonial, recipe inspiration
  - Slide 5: "Swipe to order" (link in bio)
  - Hashtags: 25 tags
  - Time: 10 AM (peak engagement for launch)
  - CTA: "Tap to order now"

- **TikTok (Product Launch Video):**
  - 15-second unboxing + first sip reaction
  - Trending audio with product reveal
  - Time: 6 PM
  - CTA: "Link in bio to order before we sell out!"

**April 22 (Tuesday) — Earth Day**
- **Instagram Story Series (3 stories):**
  - Story 1: "Earth Day is every day for us" + Poll (carousel of impact metrics)
  - Story 2: "Our carbon offset" + Question sticker
  - Story 3: "How you can join" + Swipe-up link (if eligible)

- **LinkedIn Article:**
  - Title: "What We Learned Building a Carbon-Neutral Beverage Company"
  - Narrative: Behind-the-scenes sourcing, offset strategy, team perspectives
  - Time: 8 AM (Tue)

---

**Calendar Summary:**
- 35 total posts across 3 platforms
- 5 per week Instagram, 3 per week LinkedIn, 4 per week TikTok
- Pillar distribution: Product Tips (25%), Sustainability (25%), Behind-the-Scenes (20%), Community (15%), Industry Insights (15%)
- 3 major campaign pushes: Launch (Apr 15), Earth Day (Apr 22), User Challenge (Apr 1-30)
- Visual assets needed: 15 product photos, 8 behind-the-scenes photos, 20 TikTok videos

**Next Steps:**
- Source/create visual assets by April 5
- Schedule all posts in Buffer/Later by April 8
- Assign engagement monitoring owner
- Establish daily review cadence (10 min) for comments/DMs
- Monitor performance mid-month (Apr 15) for optimization
