---
name: terminology-engine
description: >
  Maps 10 universal business terms to domain-specific language for any vertical.
  Auto-activates when adapting workspace language, rebranding, translating terms
  across industries, or generating niche-specific UI labels and content.
version: 1.0.0
triggers:
  - "terminology"
  - "domain language"
  - "vertical terms"
  - "rename for"
  - "what do they call"
  - "niche language"
  - "map terms"
  - "UI labels"
references:
  - references/universal-terms.md
---

# Terminology Engine

## Overview

Every AIOS workspace speaks the language of its vertical. A dental practice does not have "cases" — it has "appointments." A landscaping company does not have "providers" — it has "crews." The terminology engine ensures that no generic business terms leak into a finished workspace.

The engine works by mapping 10 universal terms to their domain-specific equivalents. When generating a workspace, every user-facing string, field label, command name, and documentation phrase is run through this mapping.

---

## The 10 Universal Terms

| # | Universal Term | Core Meaning |
|---|----------------|--------------|
| 1 | **Case** | The primary unit of work the system processes |
| 2 | **Client** | The person or organization that submits or receives work |
| 3 | **Document** | A file, record, or structured data object |
| 4 | **Workflow** | The sequence of steps that process a case |
| 5 | **Intake** | The act of receiving new work into the system |
| 6 | **Outcome** | The final result delivered to the client |
| 7 | **Provider** | The professional who performs the work |
| 8 | **Status** | The current state of a case |
| 9 | **Report** | A structured output document |
| 10 | **Invoice** | A financial record for services rendered |

---

## How Mapping Works

For each universal term, the engine produces:

```
mapTerm(universalTerm, targetVertical) → {
  displayName:      What professionals call it
  uiLabel:          What appears in the UI
  plural:           Plural form for lists
  searchHint:       Placeholder text for search inputs
  commandVerb:      The verb used in commands (e.g., "intake" → "book")
}
```

---

## Example Mappings

### AI Automation Agency

| Universal | Display Name | UI Label | Plural | Command Verb |
|-----------|-------------|----------|--------|-------------|
| Case | Project | Client Project | Projects | scope |
| Client | Client | Client | Clients | onboard |
| Document | Deliverable | Project Deliverable | Deliverables | share |
| Workflow | Engagement | Client Engagement | Engagements | manage |
| Intake | Discovery Call | Discovery Call | Discovery Calls | book |
| Outcome | Deliverable | Final Deliverable | Deliverables | deliver |
| Provider | Consultant | Consultant | Consultants | assign |
| Status | Project Status | Project Status | — | check |
| Report | Proposal | Client Proposal | Proposals | draft |
| Invoice | Invoice | Invoice | Invoices | send |

### Dental Practice

| Universal | Display Name | UI Label | Plural | Command Verb |
|-----------|-------------|----------|--------|-------------|
| Case | Appointment | Patient Appointment | Appointments | schedule |
| Client | Patient | Patient | Patients | register |
| Document | Record | Clinical Record | Records | file |
| Workflow | Treatment Plan | Treatment Plan | Treatment Plans | plan |
| Intake | Booking | New Booking | Bookings | book |
| Outcome | Treatment | Treatment Outcome | Treatments | complete |
| Provider | Dentist | Dentist | Dentists | assign |
| Status | Appointment Status | Status | — | check |
| Report | Treatment Report | Treatment Report | Reports | generate |
| Invoice | Bill | Patient Bill | Bills | send |

### Accounting Firm

| Universal | Display Name | UI Label | Plural | Command Verb |
|-----------|-------------|----------|--------|-------------|
| Case | File | Client File | Files | open |
| Client | Client | Client | Clients | onboard |
| Document | Document | Financial Document | Documents | upload |
| Workflow | Process | Accounting Process | Processes | run |
| Intake | Engagement | New Engagement | Engagements | start |
| Outcome | Submission | Tax Submission | Submissions | file |
| Provider | Accountant | Accountant | Accountants | assign |
| Status | File Status | File Status | — | check |
| Report | Accounts | Management Accounts | Reports | prepare |
| Invoice | Invoice | Invoice | Invoices | send |

### Landscaping Company

| Universal | Display Name | UI Label | Plural | Command Verb |
|-----------|-------------|----------|--------|-------------|
| Case | Job | Landscaping Job | Jobs | schedule |
| Client | Customer | Customer | Customers | add |
| Document | Plan | Garden Plan | Plans | draw |
| Workflow | Schedule | Job Schedule | Schedules | manage |
| Intake | Enquiry | New Enquiry | Enquiries | log |
| Outcome | Completion | Job Completion | Completions | sign-off |
| Provider | Crew | Site Crew | Crews | dispatch |
| Status | Job Status | Job Status | — | check |
| Report | Quote | Customer Quote | Quotes | send |
| Invoice | Invoice | Invoice | Invoices | send |

---

## Creating a New Mapping

### Step 1: Research the Professional Language

Find out what practitioners actually say. Sources:
- Industry trade publications and forums
- Professional association glossaries
- Existing software in the vertical (what labels do they use?)
- Conversations with people who work in the field

### Step 2: Map Each Universal Term

For each of the 10 terms, identify:
- What the professional calls this concept in conversation
- What the UI label should be (sometimes slightly different)
- The plural form
- The natural verb associated with this action

### Step 3: Validate Completeness

Check that every universal term has a mapping. If a term does not apply to the vertical (rare), document why and provide a close equivalent.

### Step 4: Test in Context

Read through the generated workspace and check that every user-facing string sounds natural to someone in the vertical. If anything reads as generic business language rather than domain language, revise the mapping.

---

## Common Mistakes

| Mistake | Impact | Fix |
|---------|--------|-----|
| Using the universal term in user-facing text | Workspace feels generic | Replace every instance with the mapped term |
| Missing plural forms | UI shows "1 Appointments" instead of "1 Appointment" | Include singular and plural in every mapping |
| Literal translation instead of professional term | Sounds unnatural to practitioners | Use the term professionals actually use, not a dictionary translation |
| Inconsistent mapping across files | Confusing user experience | Use the terminology config as a single source of truth |

---

## References

- `references/universal-terms.md` — Full details on each universal term with edge cases
