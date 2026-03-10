---
name: ad-compliance-checker
description: >
  Pre-screen ad copy and creative for platform policy compliance before submission.
  Use this skill when the user says "check my ad for compliance", "will this ad get rejected",
  "ad policy check", "Facebook ad compliance", "Google Ads policy review", "ad approval checklist",
  "why was my ad rejected", "ad creative compliance", "advertising regulations check",
  "FTC disclosure requirements for ads", or "ad platform policy audit". Also trigger for
  healthcare ad compliance, financial services ad rules, alcohol/cannabis advertising rules,
  or political ad requirements.
---

# Ad Compliance Checker

Pre-screens ad copy and creative against platform advertising policies, FTC guidelines, and industry-specific regulations to prevent rejections and policy violations.

## Granularity Check

> **Session time**: ~5 min data prep + ~5 min Claude session. No platform implementation needed — output is a compliance report with fix recommendations. Input is ad copy/creative description. Output is Markdown compliance checklist.

## User Intent Mapping

- "Will this ad get approved on Facebook?" (pre-screening)
- "Check my Google Ads copy for policy issues" (platform-specific)
- "My ad was rejected — why?" (rejection diagnosis)
- "Ad compliance checklist for healthcare" (industry-specific)
- "FTC requirements for testimonial ads" (regulatory)
- "Can I make this claim in my ad?" (claim verification)
- "Political ad disclosure requirements" (regulatory)
- "Before/after photos in ads — is this allowed?" (format-specific)
- "Competitor mention in ads — what's allowed?" (competitive)
- "Landing page compliance for ads" (landing page review)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Ad Copy | Text | Headline, body text, CTA, any claims |
| Platform(s) | Text | Google, Meta, LinkedIn, TikTok, Pinterest |
| Industry | Text | Your industry (affects which rules apply) |

### If You Don't Have This Data

- **No final ad copy yet?** Share your draft — Claude flags issues before you finalize.
- **No landing page?** Describe what's on it. Platform reviewers check landing pages too.
- **Don't know your industry rules?** Tell Claude what you're advertising — it will surface relevant regulations.
- **Ad was rejected but unsure why?** Paste the rejection message and the ad copy — Claude diagnoses the issue.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Landing Page URL | Text | For landing page compliance check |
| Creative Description | Text | Image/video content description |
| Target Geography | Text | Region-specific ad laws |
| Previous Rejections | Text | Past rejection reasons |
| Substantiation | Text | Evidence supporting claims in the ad |

## Process

### Step 1: Universal Policy Check
Flag common violations across all platforms:
- Misleading claims ("guaranteed results", "proven to cure")
- Before/after imagery rules
- Personal attribute references ("Are you overweight?")
- Profanity, violence, or adult content
- Clickbait tactics ("You won't believe...")
- Deceptive formatting (fake UI elements, fake notifications)
- Grammar and capitalization violations
- Prohibited products/services

### Step 2: Platform-Specific Rules
| Platform | Key Rules |
|---|---|
| Meta | No personal attributes, special ad categories (housing/credit/employment), no misleading claims, image text <20% (guideline) |
| Google | Trademark rules, editorial standards, healthcare restrictions, financial services disclaimers |
| LinkedIn | Professional content standards, no aggressive CTAs, B2B focus |
| TikTok | Authenticity requirements, music licensing, age-appropriate content |
| Pinterest | Positive content policy, no weight loss before/after, body neutrality |

### Step 3: Industry-Specific Regulations
| Industry | Key Regulations |
|---|---|
| Healthcare/Pharma | FDA guidelines, no diagnosis/cure claims, fair balance requirement |
| Financial Services | SEC/FINRA disclaimers, APR disclosure, risk warnings |
| Alcohol | Age restrictions, no appeal to minors, moderation messaging |
| Real Estate | Fair Housing Act, no discriminatory targeting |
| Supplements | FTC guidelines, structure/function claims only, FDA disclaimer |
| Gambling | Licensing requirements, responsible gambling messaging |

### Step 4: FTC Compliance
- Material connection disclosures (#ad, #sponsored, "Paid partnership")
- Testimonial substantiation (typical results, not best-case)
- Clear and conspicuous disclosure placement
- Endorsement guidelines compliance

### Step 5: Landing Page Alignment
- Landing page must match ad claims
- Pricing transparency (no hidden fees)
- Clear terms and conditions
- Privacy policy accessible
- Easy opt-out/unsubscribe

### Confidence & Sample Size
> **Confidence Note**: Claude flags likely policy violations based on published platform policies, but platform review is ultimately done by humans and AI at each platform, which can be inconsistent. A "clear" compliance check doesn't guarantee approval — platforms may flag issues Claude doesn't catch. For regulated industries (healthcare, finance), always get legal review beyond this automated check.

### ⚠️ Human Checkpoint
> This skill provides a first-pass compliance check. It does NOT replace legal review for regulated industries. Always consult legal counsel for healthcare, financial services, alcohol, cannabis, or political advertising. Platform policies change frequently — verify current policies before launch.

> **Benchmark Context**: 10-20% of ads are initially rejected across major platforms. Most common rejection reasons: misleading claims (30%), personal attributes (20%), prohibited content (15%), landing page issues (15%). Appeal success rate is 40-60% when the ad is actually compliant. Average review time: 24 hours (Meta), 1-3 business days (Google).

## Output Contract

### Deliverable: Markdown Compliance Report

```markdown
# Ad Compliance Check: [Ad Name]

## Overall Status: ✅ LIKELY APPROVED / ⚠️ ISSUES FOUND / ❌ LIKELY REJECTED

## Platform Compliance
### Meta
| Check | Status | Issue | Fix |
|---|---|---|---|

### Google
| Check | Status | Issue | Fix |
|---|---|---|---|

## Industry-Specific Flags
| Regulation | Status | Required Action |
|---|---|---|

## FTC Compliance
| Requirement | Status | Notes |
|---|---|---|

## Landing Page Checks
| Check | Status | Issue |
|---|---|---|

## Recommended Changes
1. [Change with rationale]

## Disclaimer Language (if needed)
"[Required disclaimer text]"
```

## Platform Implementation Steps

### Pre-Submission Workflow
1. Write ad copy draft
2. Run through this compliance checker
3. Fix flagged issues
4. Submit to platform
5. If rejected, use rejection diagnosis mode to fix and resubmit

### Meta Ad Review
1. Appeals: Go to Account Quality → select rejected ad → Request Review
2. Special Ad Categories: Campaign level → toggle Housing/Credit/Employment if applicable
3. Verify landing page loads correctly and matches ad claims

### Google Ads Policy Center
1. Check Policy Manager for active violations
2. Review editorial guidelines: google.com/ads/policies
3. Appeal: Ads → select disapproved ad → Appeal
4. Fix landing page issues before resubmitting

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| False negative (approved but shouldn't be) | Policy loophole or reviewer oversight | Self-audit periodically; don't rely on platform approval as legal clearance |
| False positive (flagged but actually compliant) | Overly cautious check | Review platform policy directly; submit and appeal if rejected |
| Rejected despite compliance check | Platform policy change or subjective review | Appeal with policy citations; reword to be less ambiguous |
| Repeated rejections | Fundamental approach violates platform spirit | Rethink creative strategy; consult platform's ad guidelines documentation |

## How to Get Your Data

- **No data needed**: Paste your ad copy and describe your creative — Claude runs the compliance check
- **Rejection details**: Copy the rejection reason from your ad platform dashboard
- **Platform policies**: Meta: facebook.com/policies/ads | Google: support.google.com/adspolicy

## Example

**Input**: "Check this Meta ad: Headline: 'Lose 20 Pounds in 30 Days — Guaranteed!' Body: 'Our supplement is clinically proven to burn fat fast. Before and after photos show real results. Limited time: 50% off.' Industry: dietary supplements. Landing page has testimonials with dramatic weight loss results."

**Output**: ❌ LIKELY REJECTED. Issues found: (1) "Guaranteed" weight loss claim — violates Meta's misleading claims policy AND FTC guidelines. Fix: Remove "guaranteed", use "may help support healthy weight management." (2) "Clinically proven" — requires substantiation documentation. Fix: "Formulated with ingredients studied for metabolism support" with citation. (3) Before/after photos — restricted on Meta; prohibited on Pinterest. Fix: Use lifestyle imagery instead. (4) "Burn fat fast" — prohibited health claim. Fix: "Support your wellness journey." (5) Landing page testimonials with dramatic results — FTC requires "Results not typical" and average results disclosure. Required disclaimer: "These statements have not been evaluated by the FDA. This product is not intended to diagnose, treat, cure, or prevent any disease." Revised headline: "Support Your Weight Management Goals — 50% Off Today."
