---
name: content-governance-framework
description: >
  Build content governance policies — editorial standards, approval workflows, taxonomy, and content lifecycle management.
  Use this skill when the user says "content governance", "editorial standards", "content approval
  workflow", "content taxonomy", "content lifecycle management", "content style guide", "editorial
  workflow design", "content quality standards", "content operations framework", "content archival
  policy", or "content management process". Also trigger for content audit framework, publishing
  standards, or content team workflow design.
---

# Content Governance Framework

Builds comprehensive content governance policies covering editorial standards, approval workflows, content taxonomy, lifecycle management, and quality assurance for consistent, scalable content operations.

## Granularity Check

> **Time**: ~10 min data prep → ~15 min Claude session → ~60-120 min building in your project management tool. If implementing, add 1-2 weeks for team adoption. Input is current content processes and team structure. Output is Markdown governance framework.

## User Intent Mapping

- "We need content governance policies" (full framework)
- "Editorial approval workflow" (workflow)
- "Content style guide for our team" (style guide)
- "Content taxonomy and tagging system" (taxonomy)
- "When should we archive or delete old content?" (lifecycle)
- "Content quality standards" (quality)
- "Content operations framework" (operations)
- "Our content process is chaotic" (process fix)
- "Content audit framework" (audit)
- "Publishing standards for our blog" (standards)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Team Structure | Text | Who creates, reviews, and publishes content |
| Content Types | Text | Blog, landing pages, email, social, docs |
| Current Process | Text | How content moves from idea to publication today |

### If You Don't Have This Data

- **No existing process?** Claude builds a governance framework from scratch based on your team size and content volume.
- **Solo content creator?** Claude provides a streamlined self-governance checklist rather than a multi-person workflow.
- **No style guide?** Claude creates a starter style guide covering the most impactful editorial standards.
- **No taxonomy?** Claude designs a content taxonomy based on your topics and content types.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Content Volume | Text | How many pieces published per week/month |
| CMS Platform | Text | WordPress, HubSpot, Contentful, etc. |
| Compliance Needs | Text | Industry regulations, legal review requirements |
| Brand Guidelines | Text | Existing voice, tone, or visual guidelines |
| Pain Points | Text | Current content process problems |

## Process

### Step 1: Editorial Standards
- Voice and tone guidelines (with examples of do/don't)
- Grammar and style preferences (AP, Chicago, house style)
- Formatting standards (heading hierarchy, list usage, paragraph length)
- Image and media standards (sizing, alt text, attribution)
- Accessibility requirements (WCAG compliance for content)
- Legal and compliance requirements (disclaimers, disclosures)

### Step 2: Approval Workflow
| Stage | Owner | Action | SLA |
|---|---|---|---|
| Ideation | Content strategist | Approve topic and brief | 2 days |
| Draft | Writer | Submit first draft | Per brief timeline |
| Editorial review | Editor | Style, quality, accuracy | 2 days |
| Subject matter review | SME | Technical accuracy | 3 days |
| Legal/compliance | Legal | Regulatory compliance | 3 days |
| Final approval | Content lead | Publication approval | 1 day |
| Publication | Publisher | Schedule and publish | Same day |

### Step 3: Content Taxonomy
- Content types (blog, guide, case study, whitepaper, etc.)
- Topic categories (aligned with pillar strategy)
- Audience segments (by persona or funnel stage)
- Content tags (searchable attributes)
- Naming conventions (file names, URLs, titles)

### Step 4: Lifecycle Management
| Stage | Duration | Action |
|---|---|---|
| Active | 0-12 months | Promote and distribute |
| Review | 12-18 months | Check accuracy, update stats |
| Refresh | 18-24 months | Major update or consolidation |
| Archive | 24+ months | Redirect or remove if no traffic |

### Step 5: Quality Assurance Checklist
- [ ] Content matches approved brief
- [ ] SEO requirements met (keyword, meta, internal links)
- [ ] Brand voice and tone consistent
- [ ] All facts and statistics sourced
- [ ] Images have alt text and proper attribution
- [ ] Links tested and working
- [ ] Mobile rendering checked
- [ ] Legal disclaimers included (if required)
- [ ] CTA present and aligned with content goal

### Confidence & Sample Size

> **Confidence Note**: Governance frameworks must balance quality control with publishing speed. Over-governance kills content velocity — under-governance creates inconsistency and risk. Start with essential standards and add rules only when you see recurring problems. The framework should evolve with your team and content maturity.

### ⚠️ Human Checkpoint
> Have all stakeholders (content, legal, leadership) review and sign off on governance policies before implementation. Pilot the workflow with 5-10 content pieces before full rollout. Collect team feedback after 30 days and adjust.

> **Benchmark Context**: See Content Marketing Institute 2024 B2B Research for current industry benchmarks relevant to this analysis.
## Output Contract

### Deliverable: Markdown Governance Framework

```markdown
# Content Governance Framework: [Brand]

## Editorial Standards
### Voice & Tone
- [Guidelines with examples]

### Style Guide
- [Key rules]

### Formatting Standards
- [Requirements]

## Approval Workflow
| Stage | Owner | SLA | Criteria |
|---|---|---|---|

## Content Taxonomy
### Content Types
| Type | Definition | Approval Level | Template |
|---|---|---|---|

### Topic Categories
| Category | Description | Owner |
|---|---|---|

## Lifecycle Management
| Stage | Trigger | Action | Owner |
|---|---|---|---|

## Quality Checklist
- [ ] [Item]

## Roles & Responsibilities
| Role | Responsibilities | Authority |
|---|---|---|

## Escalation Process
| Issue | Escalation Path | Timeline |
|---|---|---|
```

## Platform Implementation Steps

### CMS Configuration
1. Set up content statuses matching your workflow (Draft → Review → Approved → Published)
2. Configure role-based permissions (writers can't publish, editors can)
3. Create content templates for each content type
4. Set up required fields (category, tags, meta description) before publishing

### Project Management
1. Create content workflow template in Asana, Monday, or Trello
2. Set up automated notifications for review stages
3. Create content calendar view showing pipeline status
4. Track cycle time from ideation to publication

### Documentation
1. Publish governance framework in shared wiki (Notion, Confluence)
2. Create quick-reference one-pager for daily use
3. Schedule quarterly governance review meetings
4. Maintain changelog for policy updates

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Team ignores governance | Too complex or bureaucratic | Simplify to essential rules; automate enforcement where possible |
| Bottleneck at review stage | Too many approvers or unclear SLAs | Reduce approvers; set hard SLAs; create "fast track" for low-risk content |
| Inconsistent application | Ambiguous standards | Add examples to every rule; create do/don't comparisons |
| Governance not maintained | No owner or review schedule | Assign governance owner; schedule quarterly reviews |

## How to Get Your Data

- **Current process**: Document how your last 5 pieces went from idea to publication — who did what, how long each step took
- **Pain points**: Ask content team what frustrates them about current process
- **Compliance needs**: Check with legal about required reviews or disclaimers
- **No process**: Describe your team size and content volume — Claude designs appropriate governance

## Example

**Input**: "Content governance framework. B2B SaaS, team of 5 (1 content lead, 2 writers, 1 designer, 1 SEO specialist). Publishing 8 blog posts/month plus monthly whitepaper. No formal process — everything goes through Slack."

**Output**: Framework: 4-stage workflow (Brief → Draft → Review → Publish) with 7-day standard cycle time. Approval: blog posts need editor review only (2-day SLA). Whitepapers need editor + SME review (5-day SLA). No legal review needed unless claims about competitors or customer data. Style guide: casual professional tone, AP style, first-person plural ("we"), avoid jargon, max 3 heading levels. Taxonomy: 5 content types (blog, whitepaper, case study, landing page, email), 8 topic categories aligned with product features. Lifecycle: review all content at 12 months, refresh or redirect at 18 months. Implementation: (1) Move from Slack to Asana board with 4 columns matching workflow stages. (2) Create brief template in Asana (required before writing starts). (3) Build publishing checklist in CMS (required fields before publish). (4) Monthly content retrospective (15 min) to identify process issues. Quick win: content lead creates 5-point style cheat sheet that writers reference daily.

## Related Skills

- **[Editorial Calendar Builder](./editorial-calendar-builder.md)** — Use alongside this skill to embed governance workflows into your content production calendar.
- **[Content Localization Planner](./content-localization-planner.md)** — Use to establish governance standards for multilingual and localized content.
- **[Content Performance Scorecard](./content-performance-scorecard.md)** — Use to measure whether governance standards are being followed and producing quality content.
- **[Brand Asset Compliance Checker](../martech-ops/brand-asset-compliance-checker.md)** — Use to audit existing content for compliance with your new governance framework.
