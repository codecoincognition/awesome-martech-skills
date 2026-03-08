# Contributing to awesome-martech-skills

Thanks for considering contributing! This guide explains how to add new skills, improve existing ones, and report issues.

## Quick Start

1. Fork the repo
2. Copy `SKILL-TEMPLATE.md` to `skills/<category>/your-skill-name.md`
3. Fill in all required sections
4. Test your skill with 3 real-world prompts
5. Submit a PR

## Skill Quality Checklist

Before submitting, verify your skill passes the granularity check and meets our quality standards.

### The Granularity Check

Ask yourself: **"Can this be completed in a single 10-minute Claude session?"**

If the answer is no, your skill is too broad. Split it into smaller, focused skills that can chain together.

**Too broad:** "Write a complete blog post with SEO optimization"
**Right size:** "Generate a blog outline from a content brief" → "Expand a blog outline section into full prose" → "Optimize blog post meta tags and internal links"

### Required Sections

Every skill must include these sections (see `SKILL-TEMPLATE.md`):

- YAML frontmatter with `name` and `description`
- User Intent Mapping (10+ trigger phrases)
- Input Contract with required/optional fields, sample rows, validation rules
- Process with numbered steps and at least one human checkpoint
- Output Contract with format, schema, sample output
- Failure Modes table
- "How to Get Your Data" section for at least one marketing tool
- At least one complete example

### What Makes a Good Description

The `description` field in YAML frontmatter is how Claude decides whether to use your skill. Make it specific and slightly "pushy" — Claude tends to under-trigger skills.

**Weak:** "Analyze keywords"
**Strong:** "Cluster a list of keywords into topical groups based on search intent and semantic similarity. Use this skill whenever the user mentions keyword research, keyword grouping, content planning around keywords, topic clusters, or SEO content strategy."

### Input/Output Contracts

Skills must have strict, testable contracts. Every input and output should specify column names, data types, and validation rules.

**Weak:** "Accepts a CSV of keywords"
**Strong:** "Requires a CSV with columns: `keyword` (string, required), `search_volume` (integer, optional, default 0), `difficulty` (float 0-100, optional). Validation: at least 5 rows, no duplicate keywords."

## Naming Conventions

- Skill files: `kebab-case.md` (e.g., `keyword-cluster-analyzer.md`)
- Directory skills: `kebab-case/SKILL.md` (only for complexity: high skills)
- Category folders: lowercase (e.g., `seo`, `email`, `ads`)

## Categories

Place your skill in the most specific applicable category:

| Category | Folder | For skills about... |
|---|---|---|
| SEO | `seo/` | Search engine optimization, keywords, technical SEO |
| Email | `email/` | Email marketing, sequences, deliverability |
| Social | `social/` | Social media marketing, content, scheduling |
| Ads | `ads/` | Paid advertising, PPC, display, social ads |
| Analytics | `analytics/` | Marketing analytics, attribution, dashboards |
| CRM | `crm/` | CRM management, lead scoring, segmentation |
| CRO | `cro/` | Conversion rate optimization, A/B testing |
| Content | `content/` | Content creation, repurposing, strategy |
| PR & Events | `pr-events/` | Public relations, events, communications |
| MarTech Ops | `martech-ops/` | Marketing technology stack operations |
| Video & Podcast | `video-podcast/` | Video marketing, podcast marketing |
| Growth | `growth/` | Growth strategy, cross-channel, planning |
| Insights | `insights/` | Market research, competitive intel, creative strategy |
| AI Marketing | `ai-marketing/` | AI-specific marketing tools and workflows |
| B2B & ABM | `b2b/` | Account-based marketing, B2B-specific |

## Pull Request Process

1. Ensure your skill passes the quality checklist above
2. Include a brief description of the skill and its use case
3. If your skill chains with existing skills, mention which ones
4. A maintainer will review within 48 hours
5. Feedback is incorporated, then merged

## Reporting Issues

Use GitHub Issues for:

- Skills that don't trigger correctly
- Output quality problems
- Missing categories or skill gaps
- Improvement suggestions

## Code of Conduct

Be respectful, constructive, and helpful. We're building tools for marketers of all technical levels.
