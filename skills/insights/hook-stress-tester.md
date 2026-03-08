---
name: hook-stress-tester
description: >
  Evaluate marketing headlines and hooks across curiosity, specificity, novelty, and emotional
  impact — then generate improved alternatives. Use this skill whenever the user mentions headline
  testing, hook analysis, headline scoring, "is this headline good", "rate my headline", headline
  optimization, subject line testing, hook evaluation, "stress test my headlines", ad headline
  review, landing page headline analysis, "which headline is better", headline A/B test ideas,
  "improve my headline", "make this hook stronger", or any request to evaluate or improve a
  marketing headline, hook, or attention-grabbing first line. Also trigger on "write me better
  headlines" or "score these headlines".
---

# Hook Stress Tester

Evaluate marketing headlines and hooks on a 10-point scale across 6 dimensions. For each input headline, provide a scored analysis and generate 10 improved alternatives with rationale.

## Granularity Check

> Can this be completed in a single 10-minute Claude session? **Yes.** Input is 1-10 headlines. Output is scored analysis + 10 improved variants per headline.

## User Intent Mapping

Trigger when the user says:

- "Rate this headline" (scoring request)
- "Stress test these hooks" (evaluation)
- "Which of these headlines is strongest?" (comparison)
- "Improve my landing page headline" (optimization)
- "Score my ad headlines" (ad copy review)
- "Is this subject line compelling enough?" (email)
- "Generate better headline alternatives" (improvement)
- "My click-through rate is low — is it the headline?" (diagnostic)
- "Write me 10 headline options for this topic" (generation)
- "Evaluate these hooks for a LinkedIn post" (social media)

## Input Contract

### Required Input

| Field | Type | Description |
|---|---|---|
| `headlines` | list of strings | 1-10 headlines to evaluate |
| `context` | string | What the headline is for (ad, blog, email, landing page, social) |

### Optional Input

| Field | Type | Description |
|---|---|---|
| `target_audience` | string | Who should click/read |
| `product_or_topic` | string | What's being promoted |
| `platform` | string | Where it will appear (Google Ads, LinkedIn, email, blog) |
| `character_limit` | integer | Max characters (e.g., 30 for Google Ads headlines) |
| `tone` | string | Desired voice (professional, edgy, playful, authoritative) |
| `competitors` | list | Competitor headlines to differentiate from |

### Sample Input

```
Headlines to test:
1. "The Ultimate Guide to Project Management"
2. "Why 67% of Projects Fail (And How to Fix Yours)"
3. "Project Management Software for Modern Teams"

Context: Blog post titles for a project management SaaS
Target audience: Team leads and project managers
```

### Input Validation Rules

1. At least 1 headline required
2. Maximum 10 headlines per batch (more than that = diminishing analysis quality)
3. Context helps calibrate scoring (ad headline vs blog title have different standards)
4. If platform specified, apply platform-specific constraints

## Process

1. **Score each headline across 6 dimensions (1-10 each):**

   **a. Curiosity Gap (weight: 20%)**
   - Does it create a question in the reader's mind?
   - Does it tease information without giving everything away?
   - 10 = irresistible urge to click; 1 = no curiosity generated

   **b. Specificity (weight: 20%)**
   - Does it use concrete numbers, names, or details?
   - "67% of projects" > "many projects" > "projects"
   - 10 = precise, data-driven claims; 1 = vague generalities

   **c. Emotional Resonance (weight: 20%)**
   - Does it trigger an emotional response (fear, desire, frustration, hope)?
   - Does it connect to a felt pain or aspiration?
   - 10 = strong emotional pull; 1 = emotionally flat

   **d. Novelty (weight: 15%)**
   - Does it feel fresh and unexpected?
   - Would this stand out in a feed of similar content?
   - 10 = never seen anything like it; 1 = cliché/overused format

   **e. Clarity (weight: 15%)**
   - Is the value proposition immediately clear?
   - Can the reader understand what they'll get in <2 seconds?
   - 10 = crystal clear benefit; 1 = confusing or ambiguous

   **f. Urgency/Relevance (weight: 10%)**
   - Does it feel timely or personally relevant?
   - Is there a reason to click NOW vs. later?
   - 10 = must read immediately; 1 = can read anytime/never

2. **Calculate overall score** — Weighted average (1-10 scale).

3. **Rank all submitted headlines** from strongest to weakest.

4. **For each headline, identify:**
   - Strongest dimension (what's working)
   - Weakest dimension (what's holding it back)
   - Specific fix for the weakest dimension

5. **Generate 10 improved alternatives** per headline:
   - 2 curiosity-optimized variants
   - 2 specificity-optimized variants
   - 2 emotional variants
   - 2 novelty/contrarian variants
   - 1 clarity-optimized variant
   - 1 urgency-optimized variant
   - Each with a brief rationale explaining the technique used

6. **Apply platform constraints** if specified:
   - Google Ads: ≤30 characters per headline
   - Email subject: ≤50 characters optimal
   - LinkedIn: ≤150 characters for preview
   - Blog: ≤60 characters for SERP display

7. **Human checkpoint** — Present the scores. Ask: "Do the scores feel right? Want me to go deeper on any specific headline?"

## Output Contract

### Output Format

| Output | Format | Contents |
|---|---|---|
| Scored analysis | Markdown | Dimension scores + ranking |
| Improved variants | Markdown | 10 alternatives per headline with rationale |

### Output Structure

```markdown
# Hook Stress Test Results
Headlines tested: [N]
Context: [platform/use case]

## Ranking
| Rank | Headline | Overall Score |
|---|---|---|
| 1 | "Why 67% of Projects Fail (And How to Fix Yours)" | 7.8/10 |
| 2 | "Project Management Software for Modern Teams" | 4.2/10 |
| 3 | "The Ultimate Guide to Project Management" | 3.5/10 |

## Detailed Analysis

### Headline 1: "Why 67% of Projects Fail (And How to Fix Yours)"
**Overall: 7.8/10**

| Dimension | Score | Notes |
|---|---|---|
| Curiosity | 8/10 | "Why" + parenthetical creates double curiosity |
| Specificity | 9/10 | "67%" is concrete and credible |
| Emotion | 7/10 | "Fail" triggers fear; "fix yours" offers hope |
| Novelty | 6/10 | "Why X% fail" is a proven but common format |
| Clarity | 8/10 | Clear promise: diagnosis + solution |
| Urgency | 7/10 | "Yours" makes it personal and immediate |

**Strongest:** Specificity (the 67% stat anchors credibility)
**Weakest:** Novelty (format is familiar — could feel predictable)
**Quick fix:** Make the format less expected while keeping the data

### Improved Variants:
1. **Curiosity:** "The Invisible Mistake Behind 67% of Failed Projects" (what mistake? must click)
2. **Curiosity:** "67% of Projects Fail for the Same Reason. Here's What No One Tells You." (insider knowledge tease)
3. **Specificity:** "67% of Projects Fail Before Week 3. Here's the Fix That Takes 10 Minutes." (more numbers)
4. **Specificity:** "We Analyzed 1,000 Failed Projects. 67% Share This One Mistake." (adds methodology)
5. **Emotional:** "That Sinking Feeling When Your Project Is Off Track? 67% of Teams Know It." (visceral)
6. **Emotional:** "Stop Watching Your Projects Slowly Fail. 67% Do — You Don't Have To." (empowerment)
7. **Novelty:** "67% of Projects Fail. The Other 33% Do This Differently." (flip the frame)
8. **Novelty:** "Project Failure Is a $1M Problem. Most Teams Treat It as a $0 One." (money frame)
9. **Clarity:** "How to Be in the 33% of Projects That Succeed (3-Step Framework)" (clear promise)
10. **Urgency:** "Your Current Project Has a 67% Chance of Failing. Fix It This Week." (immediate threat)

[Repeat for each headline]
```

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Only 1 headline | No comparison possible | Still score and generate alternatives; note comparison is more useful |
| No context | Don't know the platform/audience | Score generically; note that platform-specific analysis would be better |
| Headlines are for different topics | Can't compare fairly | Score each independently; don't rank against each other |
| Character limit too restrictive | Google Ads 30-char headlines | Focus variants on brevity techniques; some dimensions less relevant |
| Headlines are already excellent (>8/10) | High-quality input | Focus improvements on incremental gains; suggest A/B test pairings |

## How to Get Your Data

### From Your Existing Content

1. Gather your current headlines: blog titles, email subjects, ad headlines, landing page H1s
2. Paste them into Claude with the platform context
3. Get scores + improvements

### From Competitors

1. Collect competitor blog titles, ad headlines, or email subjects
2. Provide alongside yours for comparative analysis
3. Claude scores all and identifies differentiation opportunities

### Fresh Creation

1. Tell Claude your topic, audience, and platform
2. Claude generates 10-20 headlines scored by default
3. Iterate on the highest-scoring options

## Example

**User prompt:** "Score these 3 blog titles and give me better alternatives."

**Claude responds with the full scored analysis and 10 variants per headline as shown in the output structure above.**
