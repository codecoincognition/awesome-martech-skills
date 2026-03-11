---
name: ai-content-generator
description: >
  Design AI-powered content generation workflows — prompts, quality control, and human-AI collaboration.
  Use this skill when the user says "AI content generation", "AI writing workflow", "using AI
  for content creation", "AI content strategy", "prompt engineering for marketing", "AI copywriting
  workflow", "LLM content pipeline", "AI content quality control", "human-AI content collaboration",
  "AI content at scale", or "generative AI for marketing content". Also trigger for AI content
  governance, AI writing guidelines, or scaling content with AI.
---

# AI Content Generator

Designs AI-powered content generation workflows with prompt engineering, quality control processes, human-AI collaboration frameworks, and governance policies for producing high-quality marketing content at scale.

## Granularity Check

> **Time**: ~5 min data prep → ~10 min Claude session → ~30-60 min configuring in your marketing platform. If implementing, add 1-2 weeks for workflow setup. Input is content needs, brand guidelines, and current process. Output is Markdown AI content workflow with prompts and governance.

## User Intent Mapping

- "How to use AI for content creation" (getting started)
- "AI content workflow for our team" (workflow)
- "Prompt templates for marketing content" (prompts)
- "Quality control for AI-generated content" (quality)
- "Scale content production with AI" (scaling)
- "AI content governance policy" (governance)
- "Human-AI collaboration for content" (collaboration)
- "AI writing guidelines for our team" (guidelines)
- "Which content types work best with AI?" (type selection)
- "AI content that doesn't sound generic" (quality improvement)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Content Types | Text | Blog, email, social, product descriptions, etc. |
| Brand Voice | Text | Tone, style, audience |
| Content Volume | Text | Current and desired output volume |

### If You Don't Have This Data

- **No brand voice guide?** Claude helps you define voice attributes and creates prompt templates that enforce them.
- **No AI experience?** Claude provides a beginner-friendly workflow with step-by-step prompt templates.
- **No quality benchmarks?** Claude creates a quality scorecard for evaluating AI output against your standards.
- **Not sure what to automate?** Claude maps your content types to an AI-suitability matrix showing where AI adds the most value.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Example Content | Text | Samples of your best content for AI to learn from |
| Team Structure | Text | Who will use AI, who will review |
| Current Tools | Text | AI tools already in use |
| Budget | Text | AI tool and process budget |
| Compliance | Text | Industry regulations or disclosure requirements |

## Process

### Step 1: AI Suitability Assessment
| Content Type | AI Suitability | Human Role | Efficiency Gain |
|---|---|---|---|
| Product descriptions | High | Review and brand check | 5-10x faster |
| Social media posts | High | Creative direction, approval | 3-5x faster |
| Email subject lines | High | A/B test selection | 10x more variants |
| Blog first drafts | Medium | Heavy editing, fact-checking | 2-3x faster |
| Thought leadership | Low | AI assists research only | 1.5x faster |
| Legal/compliance content | Very low | Human-written, AI proofreads | Minimal |
| Data-driven reports | High | Data validation | 5x faster |
| Ad copy variations | High | Performance selection | 10x more variants |

### Step 2: Prompt Engineering Framework
- **System prompt**: Brand voice, tone guidelines, audience context, constraints
- **Task prompt**: Specific content type, format, length, requirements
- **Context prompt**: Topic data, research, examples, competitive context
- **Output prompt**: Format specification, quality criteria, what to include/exclude
- **Iteration prompt**: Refinement instructions based on first output

### Step 3: Quality Control Pipeline
1. **AI generates**: First draft from optimized prompt
2. **Auto-check**: Automated brand voice scoring, readability check, plagiarism scan
3. **Human review**: Editor checks accuracy, adds expertise, refines voice
4. **Fact-check**: Verify all claims, statistics, and quotes
5. **Final edit**: Polish and approve for publication

### Step 4: Governance Framework
- AI disclosure policy (when to disclose AI assistance)
- Content types approved for AI generation
- Human review requirements by content type and risk level
- Data privacy rules (what data can be input to AI tools)
- IP and copyright considerations
- Training data restrictions (don't input proprietary data to public models)

### Step 5: Workflow Integration
- Prompt library organized by content type
- Template system for repeatable content (product descriptions, emails, social)
- Feedback loop: track which prompts produce best results
- Version control for prompts and templates
- Performance tracking: AI-assisted content vs. fully human content

### Step 6: Team Training
- Prompt engineering basics for marketing teams
- When to use AI vs. when to write from scratch
- How to effectively edit AI output (not just accept/reject)
- Brand voice enforcement in AI prompts
- Tool-specific training (Claude, ChatGPT, Jasper, etc.)

### Confidence & Sample Size

> **Confidence Note**: AI content quality depends heavily on prompt quality and human editing. The best results come from AI generating 60-80% of the draft with humans adding expertise, nuance, and fact-checking. AI content without human review will eventually damage your brand. Performance of AI-generated content varies by channel — test before scaling. AI tools improve rapidly; revisit your workflow quarterly.

### ⚠️ Human Checkpoint
> Every piece of AI-generated content must be reviewed by a human before publication. Verify all facts, statistics, and claims. Check for hallucinations, especially in technical or industry-specific content. Review for brand voice consistency.

> **Benchmark Context**: See Salesforce 2024 State of Marketing for current industry benchmarks relevant to this analysis.
## Output Contract

### Deliverable: Markdown AI Content Workflow

```markdown
# AI Content Workflow: [Brand]

## AI Suitability Matrix
| Content Type | AI Role | Human Role | Quality Standard |
|---|---|---|---|

## Prompt Library
### [Content Type]
- System prompt: [prompt]
- Task prompt template: [template]
- Quality criteria: [checklist]

## Quality Pipeline
| Step | Owner | Tool | Criteria | SLA |
|---|---|---|---|---|

## Governance Policy
- Approved uses: [list]
- Prohibited uses: [list]
- Disclosure requirements: [policy]
- Data privacy rules: [rules]

## Team Roles
| Role | AI Responsibilities | Human Responsibilities |
|---|---|---|

## Measurement
| Metric | AI-Assisted | Human-Only | Difference |
|---|---|---|---|
```

## Platform Implementation Steps

### Tool Setup
1. Select AI tools by use case (Claude for long-form, specialized tools for images)
2. Create organization-level accounts with usage tracking
3. Build prompt library in shared workspace (Notion, Google Docs)
4. Set up API access for high-volume content types (product descriptions, meta tags)

### Workflow Integration
1. Add AI generation step to content production workflow
2. Create review checklist specific to AI content (fact-check, hallucination check)
3. Set up content scoring to compare AI-assisted vs. human-only performance
4. Build feedback loop for prompt improvement

### Governance
1. Draft and publish AI content policy for the organization
2. Train all content team members on policy and workflow
3. Set up audit trail for AI-generated content (tag in CMS)
4. Schedule quarterly governance review

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Generic, bland output | Weak prompts without brand voice context | Improve system prompts with brand examples; add "don't" guidelines |
| Factual errors published | Insufficient fact-checking | Add mandatory fact-check step; never publish AI content without human review |
| Brand voice inconsistency | No voice guidelines in prompts | Create detailed voice prompt with examples; review output against brand scorecard |
| Team resistance | Fear of replacement or unclear value | Position AI as assistant, not replacement; show time savings data; involve team in workflow design |

## How to Get Your Data

- **Content inventory**: CMS → list content types and monthly volume per type
- **Brand voice**: Existing style guide or 5-10 examples of your best content
- **Performance data**: Analytics → compare engagement of AI-assisted vs. human content
- **No data**: Describe your content needs and team — Claude designs a starter AI workflow

## Example

**Input**: "AI content workflow for a B2B SaaS marketing team. 3 content people. Currently producing 4 blog posts/month, want to reach 12. Also need 30 social posts/month and weekly email newsletter. Using Claude and HubSpot."

**Output**: AI workflow by content type: (1) Blog posts — AI generates first draft from detailed brief (outline, key points, target keyword, tone). Human editor adds expertise, case studies, and brand voice. Quality: AI produces ~70% of draft, human adds ~30% of value. Output: 12 posts/month with same team. (2) Social posts — AI generates 5 variants per prompt for LinkedIn, Twitter, and Instagram. Human selects and refines top performers. Output: 30+/month in 2 hours/week vs. current 8 hours. (3) Email newsletter — AI drafts from content roundup + key message. Human personalizes intro and verifies all links/facts. Output: weekly newsletter in 1 hour vs. current 3 hours. Prompt library: 8 templates (blog intro, blog body, social LinkedIn, social Twitter, email newsletter, email subject lines, meta descriptions, product updates). Governance: all AI content tagged "AI-assisted" in HubSpot. Fact-check required on all blog posts. Social posts require tone review only. No AI for customer case studies (quotes must be real). Training: 2-hour team workshop on prompt engineering + weekly prompt review for first month.

## Related Skills

- **[Sentiment Analysis Monitor](./sentiment-analysis-monitor.md)** — Analyze audience reception of your AI-generated content to identify what messaging resonates best.
- **[Customer Segmentation Engine](./customer-segmentation-engine.md)** — Use to tailor AI content generation to specific audience segments and personalize at scale.
- **[Content Personalization Engine](../content/content-personalization-engine.md)** — Extend AI-generated content with dynamic personalization rules for individual users.
- **[Email Automation Workflow](../email/email-automation-workflow.md)** — Deploy AI-generated email content through automated nurture sequences.
