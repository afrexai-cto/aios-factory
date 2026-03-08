---
name: client-onboarding
description: >
  Client onboarding workflow for AI automation agencies. Auto-activates when
  discussing new clients, discovery calls, client intake, onboarding processes,
  or first meetings with potential clients.
version: 1.0.0
triggers:
  - "new client"
  - "discovery call"
  - "onboard"
  - "first meeting"
  - "client intake"
  - "initial consultation"
  - "prospect"
---

# Client Onboarding

## Overview

Client onboarding is the process of taking a prospect from first contact to active engagement. For an AI automation agency, the discovery call is the critical moment — it determines whether the client is a good fit and surfaces the pain points that the AIOS build will address. A structured onboarding process ensures nothing falls through the cracks and sets the engagement up for success.

---

## The Onboarding Lifecycle

```
Inquiry → Qualification → Discovery Call → Debrief → Decision → Kickoff
```

### Stage 1: Inquiry

A potential client reaches out via website, referral, LinkedIn, or cold outreach.

**What to capture immediately:**
- Client name and business name
- How they found the agency
- What prompted them to reach out (the trigger event)
- Brief description of what they need help with

**Response time target**: Within 4 business hours. Speed signals professionalism.

### Stage 2: Qualification

Before booking a discovery call, assess basic fit:

| Check | Pass Criteria |
|-------|--------------|
| Business type | Professional services, knowledge work, or operations-heavy |
| Team size | 2-50 staff (sweet spot for AIOS) |
| Pain clarity | Can articulate a specific problem, not just "AI sounds cool" |
| Budget signals | Currently paying for software or manual labor to solve this |
| Decision maker | The person reaching out can make or influence the buying decision |

If 4 of 5 checks pass, book the discovery call. If fewer than 3 pass, politely decline or refer elsewhere.

### Stage 3: Discovery Call

**Duration**: 45-60 minutes

**Pre-call preparation** (15 minutes):
1. Research the client's business (website, LinkedIn, reviews)
2. Identify their industry vertical
3. Prepare industry-specific questions
4. Review any information they provided in the inquiry

**Discovery Call Agenda:**

1. **Warm-up** (5 min) — Build rapport, confirm their role and the business
2. **Current state** (15 min) — How does the business operate today?
   - Walk me through a typical day
   - What tools do you currently use?
   - How many people are involved in [key process]?
   - What takes the most time?
3. **Pain identification** (15 min) — Where does it hurt?
   - What keeps you up at night about the business?
   - What would you automate if you could wave a magic wand?
   - What mistakes happen most often?
   - What do your staff complain about?
4. **Vision** (10 min) — What does success look like?
   - If we solved this, what would change?
   - How would you measure success?
   - What is this problem costing you? (time, money, stress)
5. **Next steps** (5 min) — Set expectations
   - Explain the scoping process
   - Timeline for proposal
   - Any information needed from them

**Key discovery questions by element:**

| Element | Question |
|---------|---------|
| E1: Intake | "How does new work arrive at your business?" |
| E2: Processing | "What happens to that work? Who touches it and in what order?" |
| E3: Output | "What does your client receive at the end?" |
| E4: Tracking | "How do you currently track where things are?" |
| E5: Deployment | "How technical is your team? What devices do they use?" |

### Stage 4: Debrief

Within 2 hours of the discovery call, document:

1. **Client profile**: Name, business, size, vertical
2. **Pain points identified**: Ranked by severity
3. **Five Elements mapping**: Initial mapping based on the call
4. **Automation opportunities**: What AI can address
5. **Fit assessment**: Good fit / Marginal fit / Not a fit
6. **Next steps**: Scope → Propose → or Decline

### Stage 5: Decision

Based on the debrief:
- **Good fit**: Proceed to `/scope` for detailed project scoping
- **Marginal fit**: Discuss internally, potentially propose a smaller engagement
- **Not a fit**: Send a polite decline with referral if possible

### Stage 6: Kickoff

Once the proposal is accepted:
1. Send engagement agreement for signature
2. Set up project in Notion (or project management tool)
3. Create Slack channel for the project
4. Schedule kickoff call
5. Begin build phase using `/scope` outputs

---

## Output Format

**Discovery Call Debrief**
*[Date] — [Client Name]*

---

**Client**: [Business name], [Vertical], [Size]
**Contact**: [Name], [Role]
**Source**: [How they found the agency]

**Pain Points:**
1. [Pain point 1] — Severity: High/Medium/Low
2. [Pain point 2] — Severity: High/Medium/Low

**Five Elements Initial Map:**
- E1 (Intake): [How work arrives]
- E2 (Processing): [What happens to it]
- E3 (Output): [What they deliver]
- E4 (Tracking): [How they track]
- E5 (Deployment): [How they will use it]

**Automation Opportunities:**
- [Opportunity 1]: [Estimated time savings]
- [Opportunity 2]: [Estimated time savings]

**Fit Assessment**: [Good / Marginal / Not a Fit]
**Recommended Next Step**: [Scope / Decline / Follow up in X weeks]

---

**Example:**

```
Discovery Call Debrief
2026-03-06 — Smith & Associates

Client: Smith & Associates, Law Firm (PI), 12 staff
Contact: John Smith, Managing Partner
Source: AAA Accelerator community referral

Pain Points:
1. Manual limitation date tracking across 200+ matters — Severity: High
2. Client update emails taking 5+ hours/week — Severity: High
3. New matter intake still done via paper forms — Severity: Medium

Five Elements Initial Map:
- E1 (Intake): Paper forms and phone calls → needs digital intake
- E2 (Processing): Solicitors manually review each matter weekly
- E3 (Output): Advice letters and client updates via email
- E4 (Tracking): Spreadsheet with matter status — frequently outdated
- E5 (Deployment): Desktop in office, some staff use laptops

Automation Opportunities:
- Limitation tracking: AI monitors dates, alerts before deadlines (~3 hrs/week)
- Client updates: AI drafts update emails from matter notes (~5 hrs/week)
- Intake digitization: Online form replaces paper (~2 hrs/week)

Fit Assessment: Good Fit
Recommended Next Step: Proceed to /scope
```
