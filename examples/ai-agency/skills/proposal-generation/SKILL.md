---
name: proposal-generation
description: >
  Client proposal creation for AI automation agencies. Auto-activates when
  drafting proposals, creating quotes, preparing pricing, or putting together
  a client-facing project document.
version: 1.0.0
triggers:
  - "proposal"
  - "quote"
  - "pricing"
  - "pitch"
  - "client document"
  - "engagement letter"
---

# Proposal Generation

## Overview

A proposal is the bridge between scoping and commitment. It takes the project scope and translates it into a professional document that communicates value, sets expectations, and asks for the sale. For an AI automation agency, the proposal should demonstrate exactly the kind of clarity and professionalism that the AIOS itself will bring to the client's business.

---

## Proposal Structure

Every agency proposal follows this structure:

### 1. Executive Summary

One paragraph that answers three questions:
- What problem are we solving?
- How are we solving it?
- What will the result be?

**Do not** open with a description of the agency. Open with the client's problem.

**Good**: "Smith & Associates is spending 10+ hours per week on manual limitation date tracking, creating compliance risk across 200+ active matters. We propose building an AI Operating System workspace that automates date monitoring, generates alerts before deadlines, and drafts client update emails — recovering 15 hours per week and eliminating missed deadline risk."

**Bad**: "We are a leading AI automation agency with expertise in building AIOS solutions for professional services firms."

### 2. Understanding Your Business

Demonstrate that the discovery call was productive:
- Summarize the client's business in 3-4 sentences
- Name the specific pain points discussed
- Reference specific details from the conversation

This section builds trust. The client should think: "They actually listened."

### 3. Proposed Solution

Describe what will be built, organized by the Five Elements:

| Element | What We Build | What It Solves |
|---------|--------------|----------------|
| Intake | [Description] | [Pain point it addresses] |
| Processing | [Description] | [Pain point it addresses] |
| Output | [Description] | [Pain point it addresses] |
| Tracking | [Description] | [Pain point it addresses] |
| Deployment | [Description] | [How they access it] |

Keep descriptions in the client's language. Do not use technical jargon unless the client is technical.

### 4. Deliverables

List exactly what the client receives:
- Complete AIOS workspace with X skills
- X commands for daily operations
- Integration with [tools]
- Documentation and training
- Post-launch support (specify duration)

### 5. Timeline

Break the project into phases with milestones:

| Week | Phase | Milestone |
|------|-------|-----------|
| 1 | Setup and Configuration | Workspace structure, context, terminology |
| 2 | Core Build | Skills and commands implemented |
| 3 | Integration and Testing | MCP connections, end-to-end testing |
| 4 | Launch and Training | Handoff call, documentation, go-live |

### 6. Investment

Present pricing clearly:

**Option A: Project-Based Pricing**
```
AIOS Build: $X,XXX
Includes: workspace design, X skills, X integrations, training, 30-day support
```

**Option B: Tiered Pricing**
```
Essential:  $X,XXX — Core workspace + 3 skills + 1 integration
Standard:   $X,XXX — Full workspace + 5 skills + 3 integrations + 60-day support
Premium:    $X,XXX — Everything in Standard + custom plugins + 90-day support
```

**Option C: Monthly Retainer**
```
Build phase: $X,XXX (one-time)
Ongoing support and optimization: $XXX/month
```

Present 2-3 options when possible. Anchoring with a premium option makes the standard option feel reasonable.

### 7. Next Steps

Make the path forward crystal clear:
1. Review this proposal
2. Schedule a follow-up call to discuss questions
3. Sign the engagement agreement
4. Kickoff call within [X] business days

### 8. About the Agency

Brief section (3-5 sentences) about the agency, relevant experience, and credentials. Keep it short — the proposal should be about the client, not the agency.

---

## Pricing Guidelines

### How to Price AIOS Builds

**Cost-plus approach:**
```
Estimated hours x hourly rate = base price
Add 20% margin for project management and revisions
Add integration complexity premium if applicable
```

**Value-based approach:**
```
Time saved per week x hourly cost of that time x 52 weeks = annual value
Price at 10-25% of annual value
```

**Market reference points (2026):**
- Simple workspace (3 skills, no integrations): $2,000-5,000
- Standard workspace (5 skills, 2-3 integrations): $5,000-12,000
- Complex workspace (8+ skills, 5+ integrations, compliance): $12,000-25,000
- Monthly support retainer: $500-2,000/month

These are reference points, not rules. Price based on the value you deliver.

---

## Output Format

**Proposal: [Project Name]**
*Prepared for [Client Name] by [Agency Name]*
*[Date]*

---

[Full proposal following the structure above]

---

**Example executive summary:**

```
Greenfield Dental is losing 8 hours per week to manual appointment
confirmations and patient follow-up calls. With 15 practitioners and
200+ appointments per week, missed confirmations lead to no-shows
that cost the practice an estimated $3,000 per month in lost revenue.

We propose building an AI Operating System workspace that automates
appointment confirmations, generates patient follow-up messages, and
provides a real-time dashboard showing daily schedule status and
no-show risk.

The result: 8 hours per week recovered, no-show rate reduced by an
estimated 40%, and a practice that runs smoothly even when the office
manager is away.
```
