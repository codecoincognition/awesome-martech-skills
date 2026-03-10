---
name: Press Release Writer
description: "Write professional press releases in AP style format. Need a press release for a product launch? Announcing company news or funding? Crafting a crisis response statement? Writing event announcements? Promoting awards or recognition? Announcing partnerships or integrations? Need executive quotes formatted properly? Want media distribution recommendations? Creating press release for journalist outreach? Need media kit templates? This skill generates production-ready press releases following AP style, inverted pyramid structure, professional formatting, boilerplate sections, media contact details, and distribution strategy recommendations."
---

## User Intent Mapping

| User Says | Underlying Need |
|-----------|-----------------|
| "Write a press release" | Full AP-style press release from news angle |
| "Announce our product launch" | Feature-focused press release with launch date |
| "We just got funded — write PR" | Funding announcement with financial details |
| "Create press release for event" | Event announcement with date, location, registration |
| "Write an award announcement" | Recognition/award press release with achievement context |
| "Partnership press release" | Collaboration announcement with both parties' perspectives |
| "Format quotes properly" | Executive quote extraction and formatting |
| "Where should we send this?" | Media distribution list and journalist outreach strategy |
| "Crisis response statement" | Immediate/rapid-response press release template |
| "Media kit press release" | Press release + media kit guidance |

## Input Contract

**Required Fields (Form):**
| Field | Type | Description | Example |
|-------|------|-------------|---------|
| `news_angle` | text | Core story/hook (1-2 sentences) | "EcoBlend raises $3M Series A to scale sustainable beverage distribution" |
| `company_name` | text | Your organization name | "EcoBlend Inc." |
| `announcement_date` | date | When news goes public | "2026-04-15" |
| `announcement_type` | select | News category | Product Launch / Funding / Partnership / Award / Event / Other |
| `key_facts` | list | 3-5 critical data points | ["$3M funding", "Led by Sequoia", "Expansion to 15 states", "95% recycled packaging"] |
| `primary_quote` | text | Founder/CEO quote | "This funding validates our mission to make sustainability accessible to millions..." |
| `quote_attribution` | text | Who said it | "Jane Smith, Co-founder & CEO, EcoBlend" |
| `boilerplate` | text | Company description | "EcoBlend is a sustainable beverage company..." |
| `media_contact` | text | PR contact name & email | "John Doe, PR Manager, john@ecoblend.com, (555) 123-4567" |
| `embargo_date` | date (optional) | Release embargo time | "2026-04-15 9:00 AM ET" |

**Optional Fields:**
| Field | Type | Example |
|-------|------|---------|
| `secondary_quotes` | list | Additional executive/partner quotes |
| `supporting_facts` | list | Statistics, context, validation |
| `partner_company` | text | For partnerships, co-announcement partner |
| `call_to_action` | text | Investor link, sign-up, registration URL |
| `target_media` | list | Specific publications to reach | ["TechCrunch", "Forbes", "Sustainability Today"] |
| `visual_assets` | list | Available media assets | "Founder headshot, product photo, company logo" |

**Validation Rules:**
- News angle: >15 characters, compelling hook
- Company name: non-empty, <100 characters
- Announcement date: Valid date, ideally future or recent past
- Key facts: 3-5 items minimum
- Primary quote: >50 characters, attributed to real person
- Boilerplate: >100 characters, professional description
- Media contact: Valid email + phone format
- Embargo: If provided, must be future date/time

**Sample Input:**
```
News Angle: EcoBlend Secures $3M Series A Funding to Scale Sustainable Beverage Distribution Across North America

Company Name: EcoBlend Inc.

Announcement Type: Funding

Announcement Date: 2026-04-15

Key Facts:
  1. $3M Series A led by Sequoia Capital
  2. 95% recycled plastic bottles, 100% compostable materials
  3. Expanding from 5 to 15 states by EOY 2026
  4. Partnering with Whole Foods for national shelf space
  5. 45% YoY revenue growth since Series Seed

Primary Quote: "This funding validates our belief that consumers will choose sustainability when given access. We're not just building a beverage company—we're building a movement toward regenerative business." — Jane Smith, Co-founder & CEO, EcoBlend

Boilerplate: EcoBlend is a venture-backed sustainable beverage company founded in 2021. We craft plant-based drinks from ethically sourced ingredients and package everything in 95% recycled materials. Today, EcoBlend is available in 5 states, with plans to reach 50M consumers by 2028. Learn more at ecoblend.com.

Media Contact: John Doe, PR Manager, john@ecoblend.com, (555) 123-4567, mobile: (555) 987-6543

Embargo: 2026-04-15 9:00 AM ET

Secondary Quotes:
  - "Sustainability is no longer optional—it's table stakes. EcoBlend is leading the charge in beverage innovation." — Michael Chen, Partner, Sequoia Capital
  - "When we met Jane and the team, we saw the future of food. EcoBlend is already outperforming category benchmarks." — Regional Director, Whole Foods

Target Media: TechCrunch, Forbes, Sustainability Today, Fast Company
```

### If You Don't Have This Data

- **No media list?** Search "[your industry] journalists" on Twitter/X or use Google News to find reporters covering your space.
- **No event details?** Define: date, location, expected attendees, budget range, and primary goal. That's enough to start.
- **No press release history?** Describe your company, product, and the newsworthy event. This skill generates the release from scratch.
- **No attendee data?** Start with your CRM contacts tagged as "event interest" or your email list segments.

## Process

1. **Story Structure & Angle Validation**
   - Confirm news angle is compelling and specific (not generic)
   - Validate announcement type fits press release format
   - Identify unique/newsworthy hook
   - **Human Checkpoint:** Approve news angle and headline direction

2. **Headline & Dateline Drafting**
   - Create compelling headline (7-12 words, benefit-driven)
   - Draft subheading if needed (elaborates on headline)
   - Format dateline: CITY, STATE — DATE
   - **Human Checkpoint:** Approve headline and dateline

3. **Inverted Pyramid Body**
   - Paragraph 1 (Lede): Answer Who/What/When/Where/Why in 2-3 sentences
   - Paragraph 2: Elaborate on main news, add context
   - Paragraph 3: Supporting facts and statistics
   - Paragraph 4: Primary quote and attributed speaker
   - Paragraphs 5-6: Secondary context, partnership details, or expansion info
   - Paragraph 7: Secondary quotes (if available)
   - Paragraph 8: Call to action or next steps
   - **Human Checkpoint:** Review body flow and fact accuracy

4. **Quote Integration & Formatting**
   - Validate all quotes are properly attributed
   - Ensure quotes sound natural and authentic
   - Format: "Direct quote," said Full Name, Title, Company.
   - Integrate 1-2 quotes per 400 words of copy
   - **Human Checkpoint:** Approve quote authenticity and formatting

5. **Boilerplate & Media Info**
   - Add company boilerplate (3-4 sentences, "about company")
   - Format media contact with name, title, email, phone
   - Include company URL and social handles
   - Add embargo line if applicable
   - **Human Checkpoint:** Verify accuracy of boilerplate and contact details

6. **AP Style & Formatting Review**
   - Validate AP style conventions (numbers, punctuation, abbreviations)
   - Check formatting: All caps for DATELINE, proper spacing
   - Verify markdown or plain text format
   - Create "###" line separators between major sections
   - **Human Checkpoint:** Final QA for style and format

7. **Distribution & Outreach Guidance**
   - Generate media distribution list recommendations
   - Create journalist outreach email template
   - Suggest timing and follow-up strategy
   - **Human Checkpoint:** Approve distribution recommendations


> **Benchmark Context**: Average press release pickup rate is 1-3% of targeted journalists. Event email invitation open rates average 20-25%, with 2-5% registration conversion. Best press release send times: Tuesday-Thursday, 9-10 AM in the journalist's time zone.


### Confidence & Sample Size
> **Confidence Note**: Results are only as reliable as your input data. Small datasets (<50 records or <30 days of data) produce directional insights, not statistically significant conclusions. Always note your sample size when sharing results with stakeholders. Recommendations should be validated with A/B testing or additional data before making major strategic changes.

## Output Contract

**Markdown Press Release Document:**

```markdown
# [HEADLINE - ALL CAPS OPTIONAL IF DRAMATIC]

## [Subheading elaborating on headline]

---

**FOR IMMEDIATE RELEASE** [or **EMBARGOED UNTIL:** Date/Time]

---

CITY, STATE — Month Date, Year — [COMPANY NAME] today announced [core news]. [Supporting detail]. [Context/relevance].

[Paragraph 2: Elaborate on announcement, add strategic context]

[Paragraph 3: Supporting facts, statistics, timeline details]

"[Direct quote]," said [Full Name], [Title], [Company Name]. "[Continuation of quote if multi-sentence]"

[Paragraph 5: Additional context, partnership details, or technical depth]

[Optional Secondary Quote: "[Quote]," said [Full Name], [Title], [Company Name].]

[Paragraph 6-7: Call to action, availability, or next steps]

### About [Company Name]

[3-4 sentence boilerplate describing company, mission, key achievements]

### Media Contact

[Full Name]
[Title]
[Company Name]
[Email Address]
[Phone Number]

---

**###**
```

**XLSX Media Distribution Template:**

| Publication | Contact Name | Email | Phone | Relevance | Timing | Follow-up Notes |
|-------------|--------------|-------|-------|-----------|--------|-----------------|
| TechCrunch | Sarah Johnson | news@techcrunch.com | (415) 555-0100 | Funding, startup | Tier 1: Day 1 | Sent Apr 15, 9 AM |
| Forbes | Michael Chen | editorial@forbes.com | (212) 555-0200 | Leadership, funding | Tier 1: Day 1 | Follow up if no response |
| Sustainability Today | Lisa Garcia | editor@sustain.com | (415) 555-0300 | ESG, climate | Tier 2: Day 2 | Industry angle |

**Distribution Guidance Email Template:**

```
Subject: Press Release — [HEADLINE] [Embargo Release Time]

Hi [Journalist Name],

[Company Name] today announced [news angle]. This is an exclusive first look / This story is now live.

[2-3 sentence summary of news and relevance to their coverage area]

Key facts:
• [Fact 1]
• [Fact 2]
• [Fact 3]

[If applicable: Link to full press release, media kit, or assets]

Available for interview/comment: [Name, Title, Contact Info]

[Sign-off]
[Your Name]
[Title]
[Contact Info]
```

## AP Style Quick Reference

| Element | AP Style Rule |
|---------|---------------|
| Numbers | Spell out 1-9, use numerals 10+; except money ($5M), percentages (3%), time (2 p.m.) always numerals |
| Abbreviations | Use only standard abbreviations; spell out states first mention, then use postal code |
| Titles | Capitalize formal titles before names (CEO Jane Smith); lowercase after name (Jane Smith, chief executive officer) |
| Dates | Month Day, Year format (April 15, 2026); not April 15th |
| Companies | Use official legal name first mention, then acceptable short name; capitalize all formal names |
| URLs | Remove "https://www." — use "ecoblend.com" not "https://www.ecoblend.com" |
| Quotes | Use double quotes for direct quotes; single for quotes within quotes. Attribution after quote: "Quote," said Person. |
| Punctuation | No serial comma (Oxford comma avoided in AP); em dashes for clarity; semicolons sparingly |
| Hyphens | Use for compound adjectives before noun: "revenue-generating product" but "product generates revenue" |

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

| Scenario | Symptom | Resolution |
|----------|---------|------------|
| No real news | Announcement reads like puff piece | Flag: "This lacks newsworthy angle." Suggest: "What changed? What's the impact?" Reframe around customer benefit, market shift, or measurable outcome |
| Quote sounds fake | "This quote doesn't sound like real person." | Ask for original quote from executive; provide quote template/suggestions; option to generate natural-sounding quote based on talking points |
| Unclear key facts | Reader doesn't understand what's being announced | Ask to rank key facts by importance; reorder paragraphs; move critical context up |
| Embargo too soon | "Embargo time already passed when I see this" | Set embargo to future date (minimum 24 hours ahead); suggest coordinating with journalist outreach timing |
| No distribution list | "Where do I send this?" | Generate default list based on announcement type; ask for target publications; provide journalist contact research guidance |
| Company boilerplate missing | "We don't have official company description" | Provide template; ask for core facts (founding year, mission, key products, notable clients); draft generic version |

## How to Get Your Data

**Press Release Raw Materials:**

**News Angle (Required):**
- Answer: "What changed in the world because of this announcement?"
- If funding: How much? Who led? What's the use of proceeds?
- If product: What problem does it solve? What's unique?
- If partnership: Who are the partners? What's the mutual benefit?
- If award: What achievement is being recognized?

**Executive Quotes:**
- Email executives: "Please provide 1-2 sentences on [specific angle]"
- Use frameworks: "Why this matters to customers" / "What this enables" / "What success looks like"
- Examples:
  - Founder quote: Strategic vision, mission alignment
  - Partner quote: External validation, mutual benefit
  - Customer quote: Real-world impact (if possible)

**Key Facts:**
- From: Financial data, product specs, timeline, market positioning
- Checklist: Size of announcement (funding $ or user count), credibility markers (who's backing), customer impact, timeline
- Tip: List 8-10 facts, then rank top 5 by newsworthiness

**Target Media:**
- By type: Tech media (TechCrunch, VentureBeat), business (Forbes, Wall Street Journal), industry-specific (Cannabis Business Times, Fintech Magazine)
- By journalist beat: Search "reporter [topic]", check their recent bylines
- Tools: Muck Rack, Cision, PitchDB for contact research
- Alternative: Newswire services (PR Newswire, eWire) can handle distribution for fee

**Boilerplate:**
- Template: "[Company] is a [category] company founded in [year] by [founders]. [Company description]. [Key achievements/market position]. Learn more at [URL]."
- Keep to 3-4 sentences; update quarterly with latest milestones

## Full Example

**Scenario:** EcoBlend (sustainable beverage startup) closed $3M Series A funding. Wants press release for journalist outreach + Whole Foods partnership announcement coordination.

---

## OUTPUT: PRESS RELEASE

---

# ECOBLEND RAISES $3M SERIES A LED BY SEQUOIA CAPITAL TO SCALE SUSTAINABLE BEVERAGES ACROSS NORTH AMERICA

## Funding accelerates expansion to 15 states and enables Whole Foods partnership for national shelf space

---

**FOR IMMEDIATE RELEASE**

SAN FRANCISCO, CA — April 15, 2026 — EcoBlend, the venture-backed sustainable beverage company, today announced it has raised $3 million in Series A funding led by Sequoia Capital. The round will accelerate EcoBlend's expansion from 5 to 15 states by the end of 2026 and fund a strategic partnership with Whole Foods Market for national distribution.

EcoBlend crafts plant-based drinks from ethically sourced ingredients and packages everything in 95% recycled materials and 100% compostable components. Since launch in 2021, the company has achieved 45% year-over-year revenue growth and expanded to 50,000+ retail locations across the West Coast.

"This funding validates our belief that consumers will choose sustainability when given access," said Jane Smith, Co-founder and CEO of EcoBlend. "We're not just building a beverage company—we're building a movement toward regenerative business. With this capital, we can reach 50 million consumers within 24 months."

The Series A round comes as consumer demand for sustainable food and beverage options reaches an all-time high, with market research showing 73% of millennial and Gen Z consumers willing to pay a premium for eco-friendly products. EcoBlend's Series A valuation reflects investor confidence in the company's market fit, brand strength, and operational efficiency.

"Sustainability is no longer optional—it's table stakes," said Michael Chen, Partner at Sequoia Capital. "EcoBlend is leading the charge in beverage innovation. When we met Jane and the team, we saw the future of food. EcoBlend is already outperforming category benchmarks in customer retention and unit economics."

The funding will be allocated toward: 30% supply chain scaling, 25% marketing and brand expansion, 20% product development (2 new flavors launching Q3 2026), and 25% team expansion and operations.

Whole Foods Regional Director Tom Anderson noted, "EcoBlend represents the next generation of consumer brands. Their commitment to transparency, sustainability, and taste has earned a place in 150 of our stores, with national expansion beginning June 1, 2026."

"This partnership validates our product-market fit and gives us access to 10 million Whole Foods shoppers," Smith added. "We'll move from a West Coast regional brand to a national household name in under 12 months."

EcoBlend will host a live Q&A with investors and the media on April 22, 2026, at 2 p.m. PT. Registration available at ecoblend.com/press.

### About EcoBlend

EcoBlend is a venture-backed sustainable beverage company founded in 2021 by Jane Smith and Robert Chen. The company crafts plant-based drinks from ethically sourced ingredients—partnering directly with farmers in Peru, Colombia, and Vietnam—and packages everything in 95% recycled materials. EcoBlend is available in 5,000+ retail locations across California, Oregon, Washington, and Colorado, with expansion to 15 states underway. Learn more at ecoblend.com, or follow @EcoBlendbev on Instagram and TikTok.

### Media Contact

John Doe
VP of Communications
EcoBlend Inc.
john@ecoblend.com
(555) 123-4567
Mobile: (555) 987-6543

---

**###**

---

## DISTRIBUTION RECOMMENDATIONS

**Tier 1 (Day 1 — 9 AM PT Release):**
- TechCrunch (Sarah Johnson, sarah@techcrunch.com) — Funding angle
- Forbes (Michael Chen, michael@forbes.com) — Leadership, consumer trend
- WSJ (Jennifer Lee, jlee@wsj.com) — Business, funding
- Whole Foods Magazine (Editor) — Retail partnership angle

**Tier 2 (Day 2 — Journalist follow-up):**
- Fast Company (Sustainability beat reporter)
- Food & Wine (James Park, james@foodandwine.com) — Product, trend
- Sustainability Today (Lisa Garcia, lisa@sustain.com) — ESG angle

**Tier 3 (Day 3-5 — Regional media):**
- San Francisco Chronicle, LA Times, Seattle Times (Business sections)
- Bay Area business journals and podcasts

**Outreach Timing:**
- 9 AM PT: Release to Tier 1 journalists simultaneously
- 10 AM PT: Alert Sequoia Capital PR team (partner validation)
- 12 PM PT: Publish on EcoBlend website + social media
- Day 2, 9 AM: Follow-up emails to Tier 2 journalists
- Week 2: Pitch features and deep-dive stories

**Follow-up Strategy:**
- If no response within 48 hours: Send Slack message or call journalist
- If interested: Offer founder interview, offer images/video, provide embargoed data
- Track coverage and thank journalists who cover the story

---

**Next Steps:**
- Have Jane Smith available for interviews all day April 15-17
- Prepare media kit (1-page summary, founder photo, product photo, logo)
- Coordinate announcement timing with Whole Foods (they release their own PR simultaneously)
- Monitor social media for questions and engagement
- Share coverage on EcoBlend channels within 24 hours of publication
