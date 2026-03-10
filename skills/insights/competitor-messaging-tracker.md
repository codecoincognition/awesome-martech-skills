---
name: competitor-messaging-tracker
description: >
  Track and analyze competitor messaging changes across websites, ads, emails, and social media over time.
  Use this skill when the user says "competitor messaging analysis", "competitive messaging tracker",
  "what are competitors saying", "competitor positioning changes", "competitive messaging audit",
  "track competitor messaging", "competitor value proposition analysis", "competitive narrative monitoring",
  "competitor tagline analysis", "how competitors position themselves", or "competitive messaging intelligence".
  Also trigger for competitor homepage analysis, competitive ad copy tracking, or messaging differentiation.
---

# Competitor Messaging Tracker

Tracks and analyzes competitor messaging across channels to identify positioning shifts, messaging gaps, and differentiation opportunities.

## Granularity Check

> **Session time**: ~10 min data collection + ~10 min Claude session. If ongoing, add 1 hour/month for monitoring. Input is competitor URLs, ad copies, and messaging samples. Output is Markdown competitive messaging analysis with differentiation strategy.

## User Intent Mapping

- "What are our competitors saying now?" (current state)
- "How has competitor X changed their messaging?" (tracking)
- "Competitor positioning analysis" (positioning)
- "How do we differentiate our messaging?" (differentiation)
- "Competitive messaging audit" (audit)
- "What messaging angles are competitors using?" (angles)
- "Track competitor ad copy changes" (ads)
- "Competitor email messaging analysis" (email)
- "What claims are competitors making?" (claims)
- "Messaging gaps vs. competitors" (gaps)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Competitors | Text | 3-5 competitor names/URLs |
| Your Messaging | Text | Your current positioning and key messages |
| Channels | Text | Where to track (website, ads, email, social) |

### If You Don't Have This Data

- **Not sure who competitors are?** Claude identifies direct and indirect competitors based on your product description and target market.
- **No historical messaging data?** Claude captures current state as baseline and designs a tracking framework for ongoing monitoring.
- **No ad copies to share?** Claude recommends free tools (Meta Ad Library, Google Ads Transparency Center) to find competitor ads.
- **Don't have competitor emails?** Claude suggests signing up for competitor newsletters and provides a tracking template.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Historical Snapshots | Text/Screenshots | Previous competitor messaging |
| Ad Library Data | Text | Competitor ads from Meta/Google transparency tools |
| Competitor Emails | Text | Marketing emails from competitors |
| Industry Context | Text | Market trends affecting messaging |
| Win/Loss Data | Text | Why customers chose competitors |

## Process

### Step 1: Messaging Capture Matrix
Per competitor, capture:
| Element | Source | What to Track |
|---|---|---|
| Headline/tagline | Homepage | Primary value proposition |
| Subheadline | Homepage | Supporting message |
| Feature framing | Product pages | How they describe capabilities |
| Proof points | Throughout | Stats, testimonials, logos used |
| CTAs | Key pages | Action language and offers |
| Ad headlines | Ad libraries | Paid messaging angles |
| Email subject lines | Newsletter | Email positioning and hooks |
| Social bio | Social profiles | How they describe themselves |

### Step 2: Messaging Framework Analysis
| Dimension | What to Analyze |
|---|---|
| Positioning | Category, target buyer, primary differentiator |
| Value proposition | Core promise (speed, cost, quality, ease) |
| Proof strategy | Data, testimonials, logos, awards, case studies |
| Emotional appeal | Fear, aspiration, belonging, authority |
| Competitive framing | Direct comparison, category creation, alternative positioning |
| Language register | Technical vs. casual, enterprise vs. startup |

### Step 3: Messaging Comparison Grid
| Dimension | Your Brand | Competitor A | Competitor B | Competitor C |
|---|---|---|---|---|
| Primary promise | [message] | [message] | [message] | [message] |
| Target buyer | [buyer] | [buyer] | [buyer] | [buyer] |
| Key differentiator | [diff] | [diff] | [diff] | [diff] |
| Proof type | [proof] | [proof] | [proof] | [proof] |
| Tone | [tone] | [tone] | [tone] | [tone] |

### Step 4: Gap & Opportunity Analysis
- **Unoccupied positions**: Messages no competitor is using
- **Overcrowded angles**: Messages everyone uses (hard to differentiate)
- **Emerging themes**: New messaging trends in the market
- **Vulnerability windows**: Competitor messaging weaknesses to exploit
- **Claim gaps**: True advantages you're not messaging

### Step 5: Differentiation Strategy
- Identify your unique messaging territory
- Develop counter-positioning for top competitor claims
- Create messaging that fills identified gaps
- Design proof points that support unique claims
- Test differentiated messaging with target audience

### Step 6: Ongoing Monitoring
| Cadence | Action |
|---|---|
| Weekly | Scan competitor homepages for headline changes |
| Monthly | Review competitor ad libraries and email campaigns |
| Quarterly | Full messaging audit across all competitors and channels |
| Event-driven | Monitor after competitor funding, product launches, or rebrand |

### Confidence & Sample Size

> **Confidence Note**: Competitor messaging analysis is inherently qualitative — you're interpreting intent and strategy from observed outputs. Don't over-index on a single ad or homepage variation; competitors A/B test too. Look for consistent themes across channels before concluding a positioning shift. Win/loss interviews provide the most reliable competitive intelligence — messaging analysis alone shows what competitors say, not what resonates with buyers.

### ⚠️ Human Checkpoint
> Verify competitive intelligence with sales team and customer feedback. Messaging on a website doesn't always reflect what sales reps say in conversations. Cross-reference with win/loss data for accuracy.

> **Benchmark Context**: 74% of buyers choose the vendor that first helps them understand the problem. Companies that differentiate messaging see 36% higher win rates. Competitor messaging changes correlate with product launches or strategy shifts 80% of the time. 65% of B2B companies struggle to articulate clear differentiation.

## Output Contract

### Deliverable: Markdown Competitive Messaging Analysis

```markdown
# Competitive Messaging Analysis: [Market/Category]

## Messaging Comparison Grid
| Dimension | [Your Brand] | [Comp A] | [Comp B] | [Comp C] |
|---|---|---|---|---|

## Key Findings
1. [Finding with evidence]
2. [Finding with evidence]
3. [Finding with evidence]

## Messaging Gaps & Opportunities
| Gap | Competitors Missing It | Your Advantage | Recommended Message |
|---|---|---|---|

## Differentiation Strategy
- Primary differentiator: [message]
- Supporting proof: [evidence]
- Counter-positioning: [against which competitor, how]

## Monitoring Plan
| Channel | Frequency | What to Track | Tool |
|---|---|---|---|

## Recommended Messaging Updates
| Element | Current | Proposed | Rationale |
|---|---|---|---|
```

## Platform Implementation Steps

### Data Collection
1. Capture competitor homepages using Wayback Machine or screenshot tools
2. Set up Google Alerts for competitor brand names and product launches
3. Subscribe to all competitor newsletters (use a dedicated email)
4. Bookmark Meta Ad Library and Google Ads Transparency Center
5. Follow competitors on social media and enable notifications

### Analysis Tools
1. Use a spreadsheet to track messaging changes over time (date, channel, old message, new message)
2. Set up Visualping or ChangeTower for automated webpage change alerts
3. Create a Notion or Google Doc as a living competitive messaging database
4. Schedule quarterly deep-dive analysis sessions

### Internal Distribution
1. Share competitive messaging updates with sales team monthly
2. Include messaging intelligence in marketing team standups
3. Update battlecards when competitor messaging shifts
4. Brief leadership on major positioning changes

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Analysis too surface-level | Only looking at homepage headlines | Go deeper: product pages, ads, emails, social, case studies |
| Overreacting to one change | Treating an A/B test as a strategy shift | Wait for consistency across channels before calling it a shift |
| Analysis doesn't drive action | Interesting but not actionable | Focus output on "so what" — what should we change in our messaging |
| Stale intelligence | Analysis done once, never updated | Set up automated monitoring and quarterly refresh cadence |

## How to Get Your Data

- **Competitor websites**: Visit and screenshot key pages; use Wayback Machine for historical
- **Competitor ads**: Meta Ad Library (facebook.com/ads/library), Google Ads Transparency Center
- **Competitor emails**: Subscribe to newsletters; use MailCharts or Owletter for archives
- **No data yet**: Share 3-5 competitor names — Claude analyzes current messaging from publicly available sources

## Example

**Input**: "Competitor messaging analysis for our project management tool. 3 competitors: Monday.com, Asana, ClickUp. We position as 'the simplest project management tool for small teams.' Need to understand how to differentiate."

**Output**: Messaging comparison: Monday.com leads with "Work OS" (platform/flexibility positioning), Asana leads with "manage work across teams" (enterprise collaboration), ClickUp leads with "one app to replace them all" (consolidation/value). Gaps found: (1) None lead with "simplicity" — all three trend toward complexity and feature lists. Your "simplest" position is defensible and differentiated. (2) "Small teams" is underserved — all three target enterprise/mid-market. (3) No competitor leads with speed-to-value ("set up in 5 minutes"). Recommendations: (1) Double down on simplicity as primary differentiator — competitors can't credibly claim this. (2) Add proof: "Set up in 5 minutes" (speed), "No training needed" (ease), "Loved by 2,000+ small teams" (social proof). (3) Counter-position: "No workflows to configure. No certifications needed. Just get work done." (4) Risk: competitors may copy simplicity messaging — protect the position with product decisions that keep the product genuinely simpler.
