---
name: email-deliverability-auditor
description: >
  Audit email deliverability — inbox placement, sender reputation, authentication, and spam triggers.
  Use this skill when the user says "email deliverability audit", "why are emails going to spam",
  "inbox placement rate", "sender reputation check", "email authentication setup", "SPF DKIM DMARC
  audit", "email bounce rate high", "email spam score", "email deliverability best practices",
  "warmup sending domain", or "email blacklist check". Also trigger for email infrastructure
  review, sending domain reputation, or inbox placement testing.
---

# Email Deliverability Auditor

Audits email deliverability with sender reputation analysis, authentication verification (SPF/DKIM/DMARC), spam trigger identification, and inbox placement optimization recommendations.

## Granularity Check

> **Session time**: ~5 min data prep + ~10 min Claude session. If implementing fixes, add 1-4 hours for DNS and authentication changes. Input is email performance data and domain info. Output is Markdown audit with prioritized fixes.

## User Intent Mapping

- "Our emails are going to spam" (diagnosis)
- "Email deliverability audit for our domain" (full audit)
- "Set up SPF, DKIM, and DMARC" (authentication)
- "High bounce rate — how to fix" (bounce issues)
- "Our sender reputation is low" (reputation)
- "Email warmup strategy for new domain" (warmup)
- "Inbox placement rate is dropping" (decline)
- "Are we on any email blacklists?" (blacklist)
- "Email deliverability best practices" (best practices)
- "Our open rates suddenly dropped" (diagnosis)

## Input Contract

### Required Inputs

| Input | Format | Description |
|---|---|---|
| Sending Domain | Text | Domain used for sending emails |
| ESP | Text | Email service provider (Mailchimp, SendGrid, HubSpot, etc.) |
| Current Issues | Text | What problems you're experiencing |

### If You Don't Have This Data

- **No deliverability metrics?** Check your ESP dashboard for open rates, bounce rates, and spam complaints. Most ESPs show this data by default.
- **No authentication records?** Claude walks you through checking your DNS records and provides exact records to add.
- **No blacklist info?** Use free tools like MXToolbox or mail-tester.com. Claude provides the full checklist.
- **New domain?** Claude provides a complete warmup plan from scratch.

### Optional Inputs

| Input | Format | Description |
|---|---|---|
| Open/Click Rates | Text | Current and historical engagement metrics |
| Bounce Data | CSV/Text | Hard bounces, soft bounces, rates |
| List Size | Number | Total subscribers and growth rate |
| Complaint Rate | Number | Spam complaint rate |
| Sending Volume | Text | Daily/weekly email volume |

## Process

### Step 1: Authentication Audit
- SPF record verification (correct syntax, not exceeding 10 DNS lookups)
- DKIM signing validation (key present, properly configured)
- DMARC policy review (none/quarantine/reject, reporting enabled)
- BIMI setup check (brand logo in inbox)
- Return-path alignment verification

### Step 2: Sender Reputation Assessment
- Check major reputation services (Google Postmaster Tools, Microsoft SNDS)
- Blacklist scanning (Spamhaus, Barracuda, SORBS, etc.)
- IP reputation vs. domain reputation
- Sending history and volume patterns
- Complaint rate analysis (target: <0.1%)

### Step 3: List Health Audit
- Hard bounce rate (target: <2%)
- Soft bounce monitoring and retry logic
- List hygiene practices (sunset policies, re-engagement)
- Permission and consent verification
- List acquisition source quality
- Role-based address identification

### Step 4: Content Spam Triggers
- Subject line spam word analysis
- HTML-to-text ratio
- Image-to-text ratio
- Link analysis (broken links, URL shorteners, suspicious domains)
- Unsubscribe link presence and functionality
- Physical address inclusion (CAN-SPAM)

### Step 5: Infrastructure Review
- Dedicated vs. shared IP analysis
- Sending IP warmup status
- ESP configuration and sending limits
- Feedback loop (FBL) setup
- Suppression list management

### Step 6: Monitoring Plan
- Google Postmaster Tools setup
- Inbox placement testing cadence
- Reputation monitoring alerts
- Engagement metric tracking
- Blacklist monitoring

### Confidence & Sample Size
> **Confidence Note**: Deliverability is an ongoing process, not a one-time fix. Inbox placement varies by recipient provider (Gmail, Outlook, Yahoo handle differently). Open rate tracking is less reliable since Apple Mail Privacy Protection (MPP) — use click rates as a more reliable engagement signal. Reputation improvements take 2-4 weeks to show results.

### ⚠️ Human Checkpoint
> Have your DNS administrator review all authentication record changes before publishing. Incorrect SPF/DKIM/DMARC records can block ALL email (including transactional). Test changes with a small segment before full deployment.

> **Benchmark Context**: Average inbox placement rate is 83%. DMARC enforcement (p=reject) improves deliverability by 10%. Spam complaint rate above 0.3% triggers reputation issues at major providers. Emails authenticated with SPF+DKIM+DMARC have 10% higher inbox placement. Google requires bulk senders (5,000+/day) to have one-click unsubscribe and maintain complaint rate below 0.1%.

## Output Contract

### Deliverable: Markdown Deliverability Audit

```markdown
# Email Deliverability Audit: [Domain]

## Authentication Status
| Protocol | Status | Issue | Fix |
|---|---|---|---|

## Sender Reputation
| Provider | Score | Status | Action |
|---|---|---|---|

## List Health
| Metric | Value | Target | Status |
|---|---|---|---|

## Content Issues
| Issue | Severity | Fix |
|---|---|---|

## Blacklist Status
| Blacklist | Status | Action if Listed |
|---|---|---|

## Action Plan
| Priority | Fix | Impact | Effort |
|---|---|---|---|

## Monitoring Setup
| Tool | Purpose | Frequency |
|---|---|---|
```

## Platform Implementation Steps

### DNS Configuration
1. Add/update SPF record: `v=spf1 include:[esp-domain] ~all`
2. Configure DKIM signing via your ESP (domain verification)
3. Set up DMARC: start with `v=DMARC1; p=none; rua=mailto:dmarc@yourdomain.com`
4. Gradually move DMARC from p=none → p=quarantine → p=reject
5. Verify all records with MXToolbox or dmarcian.com

### ESP Configuration
1. Verify sending domain in your ESP
2. Set up dedicated sending IP (if volume >50K/month)
3. Configure suppression lists (bounces, complaints, unsubscribes)
4. Enable feedback loops with major mailbox providers
5. Set up engagement-based sending (active subscribers first)

### Monitoring Tools
1. Google Postmaster Tools (free): domain reputation and spam rate
2. Microsoft SNDS: Outlook deliverability data
3. MXToolbox: blacklist monitoring and DNS checks
4. Mail-tester.com: per-email spam score testing

## Failure Modes

| Failure | Cause | Recovery |
|---|---|---|
| Blacklisted | High complaint rate or spam trap hits | Request delisting; clean list; reduce volume temporarily |
| SPF too many lookups | Too many `include` statements (limit: 10) | Flatten SPF record; remove unused includes |
| DMARC rejecting legitimate email | Policy too strict before alignment | Roll back to p=none; fix alignment; re-tighten gradually |
| Open rate drop after iOS 15 | Apple MPP inflating/obscuring opens | Switch to click-based engagement metrics; adjust segmentation |

## How to Get Your Data

- **ESP dashboard**: Most ESPs show bounce rates, open rates, complaint rates
- **DNS records**: Use MXToolbox.com → enter your domain → check SPF/DKIM/DMARC
- **Google Postmaster Tools**: Set up at postmaster.google.com (free, essential for Gmail senders)
- **No data**: Provide your sending domain — Claude runs an authentication check and provides setup guidance

## Example

**Input**: "Email deliverability audit: our marketing emails to 50K subscribers are seeing 35% open rates dropping to 18% over 3 months. Using Mailchimp. Domain: acmecorp.com. Getting some spam complaints."

**Output**: Authentication: SPF present but missing Mailchimp include (critical fix), DKIM configured correctly, no DMARC record (set up immediately). Reputation: Google Postmaster shows domain reputation dropped from High to Medium — correlates with 0.25% complaint rate (target <0.1%). List health: 8.2% of list hasn't opened in 6 months (sunset these contacts). Content: subject lines using caps and exclamation marks flagged as spam triggers in 4 of last 10 campaigns. Action plan: (1) Fix SPF record — add `include:servers.mcsv.net` (30 min, critical), (2) Set up DMARC with p=none for monitoring (30 min), (3) Sunset 6-month inactive subscribers (reduce list by ~4,100), (4) Run re-engagement campaign for 3-6 month inactives before removing, (5) Audit subject lines against spam trigger list. Expected recovery: 18% → 28%+ open rate within 60 days of implementing fixes.
