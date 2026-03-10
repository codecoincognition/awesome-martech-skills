# METHODOLOGY: The Design Philosophy Behind Awesome MarTech Skills

This document explains the *why* behind the design of awesome-martech-skills — a collection of 156 marketing skills for Claude. It's written for practitioners, researchers, and anyone curious about how we approach AI-assisted marketing intelligence.

---

## 1. Design Philosophy

### The CSV-In, Results-Out Architecture

The cornerstone of this collection is a deliberately simple architecture: **CSV data in, actionable results out**. No API keys, no vendor lock-in, no infrastructure.

**Why this matters:**

The MarTech landscape is fragmented. You use Ahrefs for keyword research, HubSpot for CRM, Google Ads for paid campaigns, Mailchimp for email, and GA4 for analytics. Each tool locks your data in its own silo. We designed these skills to work *across* tools via the universal language they all speak: CSV exports.

A marketer can:
1. Export keyword data from Ahrefs (CSV)
2. Paste it into Claude with the keyword-cluster-analyzer skill
3. Get a semantically coherent topic map in 10 minutes
4. Implement it in their CMS without re-entering data

**What this solves:**
- No dependency on API availability or quota limits
- No monthly API costs accumulating in the shadows
- No authentication headaches or token refresh issues
- Works with legacy tools and niche platforms equally
- Your data never leaves your computer (except what you share with Claude)

**The tradeoff:** These skills require human judgment and iteration. They're not "set it and forget it" automation. They're opinionated thinking partners that require you to review, edit, and decide. That's intentional.

### The Zero Infrastructure Principle

Every skill works in any Claude conversation. No setup. No configuration files. No server to maintain.

**Why this matters:**

The barrier to entry for most AI tools is too high. You need API keys, environment variables, a dev environment, documentation reading. We removed that entirely. A marketer opens Claude, pastes their CSV, asks a question, and gets analysis. No gatekeeping.

This democratizes marketing intelligence. A solo founder can use the same analytical rigor as a Fortune 500 marketing team.

### The Honest AI Principle

Every skill includes confidence levels, caveats, and explicit statements about what it *can't* do.

**Why this matters:**

AI outputs can sound authoritative even when they're directional. A lead scoring model built from 30 records feels similar to one built from 30,000 — but the uncertainty bands are wildly different. We made it mandatory for every skill to state:

- Sample size and statistical confidence
- What assumptions are being made
- Where benchmarks come from and when they're current
- What the skill *doesn't* handle well
- When to trust the output and when to validate further

This isn't a limitation. It's what separates thinking tools from hallucination machines.

---

## 2. Five Quality Dimensions

Every skill in this collection is evaluated against five dimensions. Think of these as the universal quality rubric:

### Actionability

**Question:** Does the output give you something you can immediately use?

A skill output succeeds if a marketer can take it and do something concrete in the next 30 minutes:
- Implement in a tool (copy and paste templates)
- Share with stakeholders (decision-ready format)
- Act on recommendations (specific next steps, not vague advice)
- Refine further (iterative, not final-answer)

**Failure mode:** "That's interesting but I don't know what to do with it."

### Honesty

**Question:** Does it clearly state confidence levels, limitations, and assumptions?

Honest outputs:
- Flag when sample size is small
- Name the benchmark source and its publication year
- Explain what triggers high error rates
- Distinguish between "we know this" and "we're assuming this"
- Suggest validation steps before major decisions

**Failure mode:** "This model is 95% accurate" (without context on which 5% fail).

### Context-Awareness

**Question:** Does it ask for the right inputs and adapt to your specific situation?

A skill that asks for "email performance" differently depending on whether you're:
- A B2B SaaS product (focus on CAC, LTV, email sequences)
- An e-commerce store (focus on AOV, repeat purchase rate, seasonal patterns)
- A nonprofit (focus on donor retention, cost per dollar raised)

**Failure mode:** Generic templates that ignore your business model.

### Benchmarking

**Question:** Does it ground recommendations in industry data with cited sources?

Every metric recommendation includes:
- Where the benchmark comes from (industry report, academic paper, survey data)
- What year the data is from
- What population it represents (e.g., "B2B SaaS companies $1M-$10M ARR")
- The caveat if the benchmark is dated

**Failure mode:** "Best practice is..." with no evidence.

### Connectivity

**Question:** Does it suggest logical next skills to chain together?

Each skill includes a "Related Skills" section recommending:
- What skill should come before this one (upstream dependencies)
- What skill should come after (natural next step)
- What skills can feed data into each other

This enables users to chain skills into complete workflows instead of one-off analyses.

---

## 3. Skill Anatomy

Each skill in the collection follows a consistent structure. Understanding this anatomy helps you understand how we think about marketing problems.

### YAML Frontmatter

```yaml
---
name: keyword-cluster-analyzer
description: >
  Cluster a list of keywords into topical groups based on search intent...
  Use this skill whenever the user mentions keyword research, keyword grouping,
  topic clusters, SEO content strategy...
---
```

The description is *extremely important*. It's not a summary — it's a list of trigger phrases. We spent time documenting:
- What the user might say when they need this skill
- Different ways to describe the same underlying problem
- Even vague requests ("I have a bunch of keywords")

This ensures the skill activates for the right use cases.

### Granularity Check

```
> **Time**: ~5 min data prep → ~10 min Claude session → ~30-60 min setup in CMS.
```

We document:
- How long data preparation takes (realistic, not optimistic)
- How long the Claude session itself takes
- How long implementation in a real tool takes
- Whether infrastructure setup is required

This is where the "one skill, one decision" rule lives. If a skill requires more than ~45 minutes total, we split it into multiple, smaller skills.

### User Intent Mapping

We list 10-15 different ways a user might describe their need. Not for keyword matching — for clarity. When a marketer reads "I need to organize these keywords," we want them to recognize that this is what the keyword-cluster-analyzer does.

### Input Contract

Explicit specification of:
- **Required columns** — What CSV columns must exist
- **Optional columns** — What would make the analysis richer (but isn't required)
- **Validation rules** — What makes data valid vs. invalid
- **Sample input** — Copy-paste-ready CSV example
- **"If you don't have this data"** — Fallbacks for common scenarios

This section solves a key problem: marketers don't know how to format data. We show them exactly.

### Process

A step-by-step walkthrough of what Claude does:

1. Validate input ← Report back findings to user
2. Analyze data ← Extract patterns
3. Human checkpoint ← Ask for approval before continuing
4. Generate output ← Create actionable result
5. Platform implementation ← Show how to use it in real tools

We embed **human checkpoints** everywhere. The skill doesn't just produce output — it pauses to ask if the user agrees with major decisions before proceeding.

### Benchmark Context

Inline, cited benchmarks:

```
> Average email open rate is 21.3%, click rate 2.6% (Mailchimp 2024 Email Marketing Benchmarks)
```

Every metric recommendation is grounded in:
- Current industry data (the year matters)
- Specific sources (we prefer published reports over "conventional wisdom")
- Context on what population it represents

### Confidence & Sample Size Note

A mandatory section explaining:
- When this analysis is reliable vs. directional
- What sample size threshold matters
- When to validate results with A/B testing
- How to communicate uncertainty to stakeholders

### Output Contract

Explicit specification of:
- What format(s) the output comes in (Markdown tables, CSV, HTML, XLSX)
- What columns/fields every output will have
- Examples of properly formatted output
- What a user should expect to paste into tools

### Platform Implementation Steps

Copy-paste instructions for actually using the output in:
- Google Sheets / Excel
- HubSpot / Salesforce / Pipedrive
- Specific CMS platforms
- GA4 / Looker Studio / analytics tools

Not "here's the data," but "here's exactly which buttons to click to implement this."

### Failure Modes

A table of "what goes wrong" scenarios:

| Failure | Cause | Recovery |
|---------|-------|----------|
| Data validation fails | Non-UTF8 encoding | Detect and ask user to re-export as UTF-8 |
| No data | User didn't export correctly | Provide sample export from each tool |

We *expect* failures. We document them. We explain how to recover.

### How to Get Your Data

Tool-by-tool export instructions:
- Google Keyword Planner → 5 steps
- Ahrefs → 5 steps
- SEMrush → 5 steps
- HubSpot → 5 steps
- Salesforce → 5 steps

Specific tools, specific buttons. Copy-paste level detail.

### Example

A real-world scenario showing:
- What user input looks like
- What Claude's analysis looks like
- What implementation looks like
- What decisions the user then makes

Every example is realistic — based on actual marketing problems we've seen.

### Related Skills

Explicit links to:
- Upstream skills (use this first)
- Downstream skills (use this next)
- Alternative skills for different situations
- Skills that feed data into each other

---

## 4. The Granularity Rule: One Skill, One Decision

We deliberately created 156 focused skills instead of 20 broad ones. This is a design choice with real consequences.

**Why granularity matters:**

When you need to cluster keywords, you don't need content strategy advice. When you're writing ad copy, you don't need a full competitive analysis. Narrow skills allow narrow focus.

**The "one decision" principle:**

Each skill should help you make *one specific marketing decision*:

- "Should I target these keywords together?" ← keyword-cluster-analyzer
- "What structure should my content have?" ← blog-outline-generator
- "Which subject lines work best?" ← email-subject-line-tester
- "Where should I allocate more budget?" ← marketing-roi-calculator

Not: "Tell me about my marketing." (Too broad. Can't be done well in one session.)

**How this enables chaining:**

Narrow skills chain together naturally:

```
keyword-cluster-analyzer
    ↓ (output = topic clusters)
content-brief-generator
    ↓ (output = SEO brief for each cluster)
blog-outline-generator
    ↓ (output = article structure)
blog-section-expander
    ↓ (output = polished article draft)
on-page-seo-auditor
    ↓ (output = optimization checklist)
seo-reporting-dashboard
    ↓ (tracks ranking progress)
```

A marketer can execute a complete SEO content strategy by chaining 6 skills, each one focused on a single decision.

---

## 5. No-API-Key Architecture: Why This Matters

Traditional AI marketing tools require API keys. This creates friction:

**The API key trap:**
- You need to generate credentials (security risk if not handled carefully)
- You need to store them securely (environment variables, secret managers)
- You depend on the vendor's API stability (they can change, rate-limit, charge)
- Data travels through their servers (privacy implications)
- Integration requires engineering work (not accessible to solo marketers)

**Our alternative:**

A marketer can:
1. Export CSV from their tool
2. Paste into Claude
3. Paste Claude's output into another tool
4. Move on

**Why this works:**
- Every marketing tool exports CSV
- CSV is portable, readable, versioned
- No authentication required
- No costs hidden in API quotas
- Full transparency on data flow
- Works in 10 years when the tool is legacy

**The tradeoff we accept:**

This architecture is less automated. It requires human judgment at each step. That's intentional. Marketing decisions shouldn't be fully automated — they should be AI-augmented human decisions.

**Future considerations:**

As Claude's capabilities expand, we could add:
- Direct integrations with popular tools (optional, not required)
- Automated scheduling of analyses (monthly deep-dives)
- Multi-file processing (analyze a whole folder of exports)
- Real-time connectors for high-frequency data

But the CSV-in core would remain the default. The no-API-key principle isn't a limitation — it's a feature.

---

## 6. Benchmark & Citation Standards

Every recommendation is grounded in evidence. This is non-negotiable.

**Citation format:**

We use footnote-style citations within the text:

```
Average email open rate is 21.3%, click rate 2.6% [Mailchimp 2024 Email Marketing Benchmarks]
```

Not pretty hyperlinks, but clear source attribution inline.

**Source selection criteria:**

We prefer benchmarks in this order:

1. **Published industry reports** — Mailchimp Email Marketing Benchmarks, HubSpot State of Marketing, Semrush studies
2. **Academic research** — Published, peer-reviewed papers when available
3. **Large-scale surveys** — 500+ respondents, reputable organization
4. **Vendor data with transparency** — If a vendor publishes their dataset, we use it

We avoid:
- Single anecdotes from blogs ("I got 40% open rates")
- Outdated benchmarks (if it's more than 18 months old, we flag it)
- Benchmarks without sample context ("Great CTR! What industry?")

**Refresh cycle:**

Every skill documents the year of its benchmarks. If a benchmark is more than 2 years old, we flag it as potentially dated and recommend validation.

**Transparency on limitations:**

When benchmarks conflict (email open rates vary wildly by industry), we show the range:

```
Average email open rate:
- B2B SaaS: 20-25%
- E-commerce: 16-20%
- Nonprofit: 22-28%
Source: Mailchimp 2024, based on 300M+ emails
```

Not a single number. Context that matters.

---

## 7. How Skills Are Developed

We follow a deliberate development process. It's not fast, but it's rigorous.

### 1. Identify the Gap

We start with: "What decision is a marketer stuck on?"

Recent examples:
- "I have 200 keywords. How do I organize them?" → keyword-cluster-analyzer
- "My email open rates are dropping. Are my subject lines the problem?" → email-subject-line-tester
- "I have 5 marketing channels. Where should I spend more money?" → marketing-roi-calculator

### 2. Research Best Practices

For each skill, we:
- Read industry reports (HubSpot, Semrush, Mailchimp, etc.)
- Review academic research if available
- Interview 3-5 practitioners ("How do *you* solve this?")
- Analyze what top tools do (without copying them)
- Document the frameworks we use (AIDA, Jobs to Be Done, Kano, etc.)

### 3. Design the Prompt

We design Claude's behavior:
- What inputs do we need?
- How do we validate them?
- What analysis should happen step-by-step?
- Where do we ask for human judgment?
- What output format is most actionable?

### 4. Test with Real Data

Before shipping, we:
- Run the skill on 5-10 real datasets
- Have actual marketers use it
- Measure: Can they implement the output in under an hour?
- Check: Did they need to ask follow-up questions?
- Validate: Did the output change their decision?

### 5. Iterate Based on Feedback

If 3+ testers struggle with something, we change it:
- Clearer input instructions
- Different output format
- Additional context gathering steps
- Better fallback advice

### 6. Quality Checklist Before Publish

Before shipping a skill, we verify:

- [ ] Frontmatter is specific to this problem (not generic)
- [ ] Granularity check: Can this be done in 1 Claude session?
- [ ] Input contract: Clear examples of data format
- [ ] At least 3 cited benchmarks with years
- [ ] Confidence note: When should users trust/validate results
- [ ] Platform implementation: At least 2 specific tool walkthroughs
- [ ] Failure modes: At least 5 "what goes wrong" scenarios
- [ ] Related skills: At least 2-3 adjacent skills listed
- [ ] Real-world example: Tested with actual marketer scenario
- [ ] Tone review: Honest, practical, not overselling capabilities

Skills that don't pass this checklist don't ship.

### 7. Community Contribution Guidelines

We welcome contributions under these rules:

**You should contribute a skill if:**
- It's a decision a marketer makes regularly (not a one-time task)
- No existing skill covers it (check the full list first)
- You can test it with 5+ real datasets
- You have 3+ cited benchmarks with sources and years
- You're willing to revise based on community feedback

**You shouldn't contribute if:**
- It overlaps significantly with an existing skill (propose merging instead)
- You're automating a decision (these should augment human judgment, not replace it)
- Benchmarks are outdated or poorly sourced
- It requires API keys or external infrastructure

---

## 8. What Makes This Different

This collection exists because we believe marketing skills are fundamentally different from general prompt engineering.

### Comparison to Other Prompt Collections

**Generic prompt libraries ("101 prompts for ChatGPT"):**
- Often generic across industries
- Rarely include benchmarks or confidence levels
- Don't show how to implement outputs in real tools
- Optimized for engagement, not accuracy

**Task automation tools:**
- Often require API keys and setup
- Create dependence on a single vendor
- Hide the thinking inside a black box
- Optimized for speed, not transparency

**Our approach:**
- Marketing-specific frameworks
- Every metric sourced and cited
- Step-by-step implementation walkthroughs
- Optimized for human decision-making, not automation

### Why Marketing-Specific Skills Beat General Prompts

A general "analyze this email" prompt doesn't know that:
- B2B email needs different metrics than B2C
- Email performance varies wildly by send time, day of week, audience size
- Open rate isn't the right metric for a re-engagement campaign
- Unsubscribe rate > 0.5% indicates list quality issues
- A/B test results need 100+ opens to be statistically valid

Marketing-specific skills encode this expertise. They're not just well-written prompts — they're decision frameworks that have been battle-tested by practitioners.

### The Thought Leadership Angle

This collection is fundamentally about encoding marketing expertise into reusable patterns.

We're saying:
- "Here's how experts think about this problem"
- "Here's what the data shows about what works"
- "Here's how to implement the output in the tools you actually use"
- "Here's what we *don't* know and when you should validate further"

That's not prompt engineering. That's operationalized marketing knowledge.

---

## 9. The Future of Skill Development

This collection isn't static. We're building toward:

**Near term (6 months):**
- 50+ additional skills covering analytics, attribution, compliance
- Workflow chains connecting 5+ skills for complete use cases
- Community contributions from top-tier practitioners
- Skill customization for specific industries

**Medium term (12-18 months):**
- Optional API connectors for popular tools (HubSpot, GA4, LinkedIn)
- Skill versioning with benchmark refresh cycles
- Skill performance tracking ("which skills create ROI")
- Integration with academic marketing research

**Long term:**
- Real-time analysis as new benchmarks emerge
- Personalization: skills that adapt to your industry, company size, budget
- Predictive capabilities: "Based on your data, you'll likely hit this KPI in X weeks"
- Cause-and-effect analysis: "This channel drives 3x the LTV of that one"

Through all of this, we're maintaining the core principles:
- **No vendor lock-in**
- **Human judgment is central**
- **Honest about confidence levels**
- **Every metric is sourced**
- **Every output is actionable**

---

## Conclusion: The Philosophy in Practice

This collection represents a specific bet about the future of marketing:

1. **Marketing is increasingly data-driven**, but most data is fragmented across tools
2. **AI can help synthesize that data**, but only if it's transparent about uncertainty
3. **Infrastructure-heavy solutions create friction** that excludes most practitioners
4. **The best marketing decisions combine machine intelligence and human judgment**
5. **Expertise can be encoded and shared** without losing the ability to adapt

We built awesome-martech-skills as a practical expression of these beliefs.

The goal isn't to automate marketing. It's to empower practitioners — whether they're solo founders or directors at Fortune 500 companies — to make better, faster, more confident marketing decisions.

Every CSV exported, every analysis run, every decision made with the help of these skills is a step toward a more transparent, equitable, and intelligent marketing future.

---

*Built by CodeCoinCognition LLC. A labor of love for the marketing community.*
