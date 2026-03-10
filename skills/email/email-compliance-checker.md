---
name: email-compliance-checker
description: >
  Audit email marketing for legal compliance — CAN-SPAM, GDPR, CCPA, CASL, and platform policies.
  Use this skill when the user says "email compliance audit", "CAN-SPAM compliance", "GDPR email
  compliance", "email marketing legal requirements", "CASL compliance", "email consent management",
  "unsubscribe compliance", "email privacy regulations", "double opt-in requirements", "email
  compliance checklist", or "email marketing laws". Also trigger for email data retention policy,
  consent record management, or email compliance for international senders.
---

# Email Compliance Checker

Audits email marketing programs for compliance with CAN-SPAM, GDPR, CCPA, CASL, and other regulations — covering consent management, unsubscribe processes, data handling, and content requirements.

## Granularity Check

> **Time**: ~5 min data prep → ~10 min Claude session → ~30-45 min setup in Mailchimp / Klaviyo / HubSpot. If implementing fixes, add 2-8 hours for process and technical changes. Input is current email practices and target regions. Output is Markdown compliance audit with fix recommendations.

## User Intent Mapping

- "Are our emails CAN-SPAM compliant?" (US compliance)
- "GDPR compliance for our email list" (EU compliance)
- "Email compliance audit" (full audit)
- "Do we need double opt-in?" (consent)
- "Our unsubscribe process — is it legal?" (unsubscribe)
- "Sending emails to Canadian contacts — CASL rules" (Canada)
- "Email data retention policy" (data handling)
- "Consent management for email" (consent records)
- "International email compliance" (multi-region)
- "Email marketing legal checklist" (checklist)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Target Regions | Text | Where your subscribers are (US, EU, Canada, etc.) |
| Email Types | Text | Marketing, transactional, or both |
| Current Practices | Text | How you collect emails, manage consent, handle unsubscribes |

### If You Don't Have This Data

- **Not sure about subscriber regions?** Claude covers major regulations (CAN-SPAM, GDPR, CASL) to ensure broad compliance. Check your ESP for subscriber geography.
- **No consent records?** This is a compliance risk. Claude provides a plan to retroactively establish consent or clean your list.
- **Not sure if you're compliant?** That's exactly what this audit addresses. Describe your current practices — Claude identifies gaps.
- **No legal team?** Claude provides actionable compliance checklists. For complex situations, Claude recommends when to consult legal counsel.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| List Sources | Text | How subscribers were acquired |
| ESP | Text | Email platform used |
| Privacy Policy URL | Text | Current privacy policy |
| Consent Records | Text | How consent is captured and stored |
| Industry | Text | Healthcare, finance, etc. (special rules apply) |

## Process

### Step 1: Regulation Mapping
| Regulation | Region | Key Requirement | Penalty |
|---|---|---|---|
| CAN-SPAM | US | Opt-out with 10-day processing, physical address, no deceptive headers | Up to $51,744/email |
| GDPR | EU/EEA | Explicit opt-in consent, right to erasure, data portability | Up to 4% global revenue |
| CASL | Canada | Express or implied consent, identification requirements | Up to $10M CAD |
| CCPA/CPRA | California | Right to know, delete, opt-out of sale | $2,500-$7,500/violation |
| PECR | UK | Similar to GDPR, soft opt-in for existing customers | Varies |

### Step 2: Consent Audit
- How are email addresses collected? (form, purchase, event, third-party)
- Is consent explicit (opt-in) or assumed?
- Are consent records stored with timestamp and method?
- Is there a clear privacy policy linked at collection point?
- Double opt-in vs. single opt-in decision and implementation
- Separate consent for different email types (marketing vs. product updates)

### Step 3: Email Content Compliance
Per email:
- Sender identification (accurate "From" name and email)
- Physical mailing address included
- Clear subject line (not misleading)
- Unsubscribe link present and functional
- Unsubscribe processing time (<10 days CAN-SPAM, immediate best practice)
- Transactional vs. marketing classification correct
- Advertising disclosure (if applicable)

### Step 4: Data Handling
- Data storage location and security
- Data retention policy (how long subscriber data is kept)
- Right to access and portability (GDPR/CCPA)
- Right to erasure (GDPR "right to be forgotten")
- Data processing agreements with third parties (ESP, analytics)
- Breach notification procedures

### Step 5: Unsubscribe Process
- One-click unsubscribe (required by Google/Yahoo for bulk senders)
- No login required to unsubscribe
- Unsubscribe takes effect within 10 days (CAN-SPAM) / immediately (best practice)
- Preference center option (reduce unsubscribes by offering frequency/topic choices)
- Suppression list management (never email someone who unsubscribed)

### Step 6: Industry-Specific Requirements
- Healthcare (HIPAA): no PHI in marketing emails without authorization
- Financial (FINRA, SEC): record retention, advertising rules
- Education (FERPA): student data protections
- Children (COPPA): no marketing to children under 13

### Confidence & Sample Size
> **Confidence Note**: This skill provides compliance guidance based on regulations as of the knowledge cutoff. Laws change — verify current requirements. Claude is not a lawyer and cannot provide legal advice. For complex compliance situations (cross-border data transfer, industry-specific regulations), consult qualified legal counsel. This audit covers the most common email compliance issues but may not cover every regulation applicable to your specific situation.

### ⚠️ Human Checkpoint
> Have legal counsel review compliance findings, especially for GDPR, CCPA, and industry-specific regulations. Verify consent records are legally sufficient for your jurisdiction. Test unsubscribe process end-to-end before relying on compliance.

> **Benchmark Context**: 85% of marketing emails have at least one compliance issue. Google and Yahoo now require one-click unsubscribe for bulk senders (5,000+/day). GDPR fines for email violations have increased 50% year-over-year. Companies with documented consent records reduce regulatory risk by 80%. Average cost of a data breach involving email data is $4.45 million.

## Output Contract

### Deliverable: Markdown Compliance Audit

```markdown
# Email Compliance Audit: [Brand]

## Regulatory Coverage
| Regulation | Applicable? | Current Status | Risk Level |
|---|---|---|---|

## Consent Audit
| Collection Point | Consent Type | Documented? | Compliant? | Fix |
|---|---|---|---|---|

## Email Content Compliance
| Element | Requirement | Current State | Action |
|---|---|---|---|

## Data Handling
| Requirement | Status | Action |
|---|---|---|

## Unsubscribe Process
| Requirement | Status | Action |
|---|---|---|

## Risk Matrix
| Issue | Regulation | Risk Level | Fix Priority | Effort |
|---|---|---|---|---|

## Action Plan
| Priority | Fix | Regulation | Timeline |
|---|---|---|---|
```

## Platform Implementation Steps

### ESP Configuration
1. Verify sender domain authentication (SPF, DKIM, DMARC)
2. Configure unsubscribe link in every email template
3. Set up list-unsubscribe header for one-click unsubscribe
4. Enable suppression list management (automatic bounce and unsubscribe handling)
5. Configure data retention policies in ESP settings

### Consent Management
1. Update signup forms with explicit consent language and privacy policy link
2. Implement double opt-in for GDPR markets (confirmation email after signup)
3. Store consent records: timestamp, method, IP address, consent text shown
4. Create preference center for granular consent management
5. Implement consent withdrawal process (unsubscribe = consent withdrawal)

### Documentation
1. Create or update email marketing privacy policy
2. Document all data processing activities for GDPR accountability
3. Maintain data processing agreements with ESP and third-party tools
4. Create data breach notification procedure
5. Train team on compliance requirements annually

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Regulatory fine | Non-compliant practices (missing unsubscribe, no consent) | Fix immediately; document remediation; consult legal |
| List-unsubscribe not working | Technical configuration issue | Test unsubscribe flow; fix ESP settings; verify header implementation |
| Consent records missing | Never implemented proper consent tracking | Run re-permission campaign for list; set up proper tracking going forward |
| Sending to unsubscribed contacts | Suppression list not synced across systems | Audit all sending systems; centralize suppression management |

## How to Get Your Data

- **Current practices**: Document how you collect emails, what your forms say, and how unsubscribes work
- **ESP settings**: Check your ESP's compliance settings and suppression list configuration
- **Consent records**: Export consent data from your signup forms or CRM
- **No data**: Describe your email marketing practices — Claude identifies compliance gaps

## Example

**Input**: "Email compliance audit. US-based SaaS with EU customers (~20% of list). Using HubSpot. Single opt-in via website forms. Unsubscribe link in footer. 50K subscribers. No consent records stored separately."

**Output**: Risk assessment: MEDIUM-HIGH. Critical issues: (1) GDPR non-compliance — EU subscribers (10K) require explicit opt-in consent with documented records. Current single opt-in is insufficient. Action: implement double opt-in for EU signups; run re-permission campaign for existing EU contacts. (2) No one-click unsubscribe header — required by Google/Yahoo for 50K+ sends. HubSpot supports this but may need configuration. (3) Consent records not stored — for GDPR, you need timestamp, consent text, and method for every subscriber. HubSpot tracks this if configured properly. Compliance fixes: (1) URGENT — add double opt-in for new EU subscribers (HubSpot Settings → Forms → Consent), (2) URGENT — run EU re-permission campaign (send consent email, suppress non-responders after 30 days), (3) HIGH — enable one-click unsubscribe in HubSpot email settings, (4) MEDIUM — create preference center to reduce unsubscribes while maintaining compliance, (5) LOW — document data processing activities for GDPR accountability. Timeline: Week 1 — double opt-in and one-click unsubscribe (technical setup); Week 2-3 — EU re-permission campaign; Week 4 — preference center and documentation.

## Related Skills

- **[Email Automation Workflow](./email-automation-workflow.md)** — Use to ensure your automation workflows comply with regulations before launching.
- **[Email List Segmentation](./email-list-segmentation.md)** — Use to implement consent-based segmentation and preference center strategies that support compliance.
- **[Email Deliverability Auditor](./email-deliverability-auditor.md)** — Use alongside compliance checks to ensure authentication and delivery best practices are met.
- **[Marketing Compliance Pre-Checker](../martech-ops/marketing-compliance-pre-checker.md)** — Use for broader marketing compliance review beyond just email requirements.
