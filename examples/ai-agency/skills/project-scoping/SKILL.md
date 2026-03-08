---
name: project-scoping
description: >
  Project scoping methodology for AIOS builds. Auto-activates when scoping
  a new project, estimating effort, defining requirements, or mapping client
  needs to the Five Elements architecture.
version: 1.0.0
triggers:
  - "scope"
  - "estimate"
  - "requirements"
  - "how long will it take"
  - "project plan"
  - "what do we need to build"
---

# Project Scoping

## Overview

Project scoping translates a client's pain points into a concrete AIOS build plan. It maps their business onto the Five Elements, identifies which skills and integrations are needed, estimates the effort, and produces a scope document that feeds directly into the proposal.

Good scoping prevents scope creep, sets realistic expectations, and ensures the delivered workspace actually solves the client's problems.

---

## The Scoping Process

```
Discovery Debrief → Element Mapping → Skill Inventory → Integration Audit → Effort Estimate → Scope Document
```

### Step 1: Review Discovery Debrief

Pull in the outputs from the discovery call:
- Confirmed pain points
- Initial Five Elements mapping
- Automation opportunities
- Client's technical comfort level

### Step 2: Deep Element Mapping

For each of the Five Elements, define the specific implementation:

**E1: Intake**
- What types of work will the system receive?
- What fields need to be captured?
- What validation is required?
- What is the primary intake method? (form, email, chat, etc.)

**E2: Processing**
- What AI capabilities are needed? (text analysis, document parsing, etc.)
- What business rules must be encoded?
- Are there approval or review steps?
- What external data sources are needed?

**E3: Output**
- What does the client deliver to their end customers?
- What format? (PDF, email, dashboard, verbal advice)
- What quality standards apply?
- How often are outputs generated?

**E4: Tracking**
- What statuses are needed?
- Who needs visibility? (staff, clients, managers)
- Are there SLA or deadline requirements?
- What metrics matter?

**E5: Deployment**
- Local workspace or hosted application?
- Single user or team?
- Mobile access needed?
- Integration with existing tools required?

### Step 3: Skill Inventory

Based on the element mapping, list the skills the workspace needs:

| Skill | Element | Complexity | Priority |
|-------|---------|-----------|----------|
| [Skill name] | E[number] | Low/Med/High | Must/Should/Could |

**Complexity guide:**
- **Low**: Template-based, minimal domain logic (1-2 hours)
- **Medium**: Requires domain research, custom prompts (3-5 hours)
- **High**: Complex workflows, multiple integrations, domain expertise (5-10 hours)

### Step 4: Integration Audit

Identify every external tool the workspace needs to connect with:

| Integration | Purpose | MCP Available | Effort |
|-------------|---------|--------------|--------|
| [Tool] | [Why] | Yes/No | [Hours] |

If an MCP server is not available, determine:
- Can the tool be accessed via API?
- Is manual data entry acceptable?
- Is there an alternative tool with MCP support?

### Step 5: Effort Estimate

**Workspace build components:**

| Component | Hours | Notes |
|-----------|-------|-------|
| CLAUDE.md and context setup | 2-4 | Business context, team, terminology |
| Skills (per skill) | 2-8 | Depends on complexity |
| Commands | 1-2 | Standard set plus niche-specific |
| Integrations (per integration) | 2-6 | MCP config, testing, documentation |
| Testing and validation | 2-4 | End-to-end workflow testing |
| Documentation and handoff | 2-3 | README, onboarding guide |

**Total estimate formula:**
```
Base setup:           4 hours
Skills:               [count] x [avg complexity hours]
Integrations:         [count] x [avg setup hours]
Testing:              3 hours
Documentation:        2 hours
Buffer (15%):         [subtotal x 0.15]
─────────────────────────────────
Total:                [sum] hours
```

### Step 6: Produce Scope Document

---

## Output Format

**Project Scope: [Project Name]**
*Prepared for [Client Name] — [Date]*

---

**Client**: [Business name]
**Vertical**: [Industry]
**Project summary**: [One paragraph describing what will be built]

**Five Elements Implementation:**

| Element | Implementation | Complexity |
|---------|---------------|-----------|
| E1: Intake | [Specific plan] | [Low/Med/High] |
| E2: Processing | [Specific plan] | [Low/Med/High] |
| E3: Output | [Specific plan] | [Low/Med/High] |
| E4: Tracking | [Specific plan] | [Low/Med/High] |
| E5: Deployment | [Specific plan] | [Low/Med/High] |

**Skills to Build:**
1. [Skill name] — [Description] — [Hours]
2. [Skill name] — [Description] — [Hours]
3. [Skill name] — [Description] — [Hours]

**Integrations:**
1. [Tool] — [Purpose] — [Hours]
2. [Tool] — [Purpose] — [Hours]

**Estimated Effort**: [Total hours]
**Estimated Timeline**: [Weeks]
**Assumptions**: [List key assumptions]
**Exclusions**: [What is NOT included]

---

**Example:**

```
Project Scope: Smith & Associates AIOS
Prepared for Smith & Associates — 2026-03-06

Client: Smith & Associates, Personal Injury Law Firm, 12 staff
Project summary: Build an AIOS workspace that automates limitation date
tracking, generates client update emails, and provides a digital intake
form for new matters.

Five Elements Implementation:
  E1: Digital intake form for new PI matters (Low complexity)
  E2: AI-powered limitation date monitoring + alert system (High)
  E3: Automated client update email drafts (Medium)
  E4: Matter status dashboard with deadline tracking (Medium)
  E5: Claude Code workspace, desktop access (Low)

Skills to Build:
  1. Matter intake — Digital form with validation — 4 hrs
  2. Limitation tracking — AI date analysis + alerts — 8 hrs
  3. Client updates — Auto-draft emails from notes — 5 hrs
  4. Matter dashboard — Status overview + deadline view — 4 hrs

Integrations:
  1. Slack — Team notifications for deadline alerts — 2 hrs
  2. Google Calendar — Limitation date reminders — 3 hrs

Estimated Effort: 32 hours
Estimated Timeline: 2 weeks
Assumptions: Client provides access to current matter data
Exclusions: Existing case management system migration
```
