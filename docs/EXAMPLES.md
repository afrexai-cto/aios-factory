# Examples Gallery

A showcase of what AIOS workspaces look like across different business verticals.

---

## Included Example

### AI Automation Agency

**Location**: `examples/ai-agency/`

A complete workspace for an AI automation agency — the kind of business that builds AIOS workspaces for clients. This is the most relevant example for AAA Accelerator members.

**Skills included:**
- Client onboarding — discovery call process, qualification, debrief
- Project scoping — Five Elements mapping, effort estimation
- Proposal generation — professional proposal structure with pricing
- Delivery workflow — build-test-launch lifecycle management

**Commands included:**
- `/prime` — Session initialization
- `/intake` — Process new client inquiries
- `/scope` — Scope AIOS build projects
- `/status` — Dashboard of active projects and pipeline

**Terminology**: Projects, Clients, Discovery Calls, Engagements, Proposals, Consultants, Deliverables

---

## What Other Verticals Look Like

The factory can generate workspaces for any vertical. Here are examples of what different industries produce:

### Dental Practice

**Skills**: Patient booking, treatment planning, clinical documentation, recall management
**Commands**: `/book`, `/treatment-plan`, `/recall`, `/status`
**Terminology**: Patients, Appointments, Treatment Plans, Dentists, Clinical Records, Bookings
**Key integrations**: Practice management software, SMS for reminders, clinical imaging

### Accounting Firm

**Skills**: Client onboarding, tax preparation workflow, management accounts, deadline tracking
**Commands**: `/engage`, `/prepare`, `/deadline`, `/status`
**Terminology**: Clients, Files, Engagements, Accountants, Submissions, Management Accounts
**Key integrations**: Xero, QuickBooks, HMRC (UK) or IRS (US) e-filing

### Landscaping Company

**Skills**: Quote generation, job scheduling, crew dispatch, completion sign-off
**Commands**: `/quote`, `/schedule`, `/dispatch`, `/status`
**Terminology**: Customers, Jobs, Enquiries, Crews, Quotes, Job Schedules
**Key integrations**: Google Maps, weather API, invoicing software

### Property Management Company

**Skills**: Maintenance request intake, contractor dispatch, inspection reporting, tenant communication
**Commands**: `/request`, `/dispatch`, `/inspect`, `/status`
**Terminology**: Landlords, Tenants, Jobs, Contractors, Maintenance Requests, Inspection Reports
**Key integrations**: Property management portal, accounting software, contractor network

### Recruitment Agency

**Skills**: Vacancy intake, candidate sourcing, interview scheduling, placement tracking
**Commands**: `/vacancy`, `/source`, `/interview`, `/status`
**Terminology**: Employers, Candidates, Vacancies, Recruiters, Placements, Shortlists
**Key integrations**: LinkedIn, job boards, applicant tracking system

### Fitness Studio

**Skills**: Member onboarding, class scheduling, attendance tracking, retention outreach
**Commands**: `/member`, `/schedule`, `/attendance`, `/status`
**Terminology**: Members, Classes, Bookings, Instructors, Memberships, Attendance Records
**Key integrations**: Booking platform, payment processor, member app

---

## Anatomy of a Good Workspace

Regardless of vertical, the best workspaces share these qualities:

### 1. Immediate Clarity

Running `/prime` should give Claude complete understanding within 30 seconds. The CLAUDE.md and context files tell a clear story.

### 2. Domain-Native Language

Every skill, command, and output uses the vertical's professional language. A dental workspace talks about patients and appointments. A legal workspace talks about matters and instructions. No generic terms.

### 3. Actionable Skills

Each skill describes a real process with concrete steps. A practitioner in the vertical should read the skill and think: "Yes, that is how we do it" — or better, "That is how we should do it."

### 4. Useful Commands

Commands produce structured output that moves work forward. They do not just display information — they process, analyze, and recommend.

### 5. Realistic Context Templates

The context templates ask the right questions for the vertical. A dental practice template asks about number of practitioners, treatment rooms, and patient volume — not generic "describe your business."

### 6. Practical Integrations

The `.mcp.json` connects to tools the vertical actually uses. No integrations are included "just in case." Every connection has a clear purpose.

---

## Contributing Examples

Built a workspace for a vertical not listed here? Consider contributing it:

1. Ensure all content is domain-accurate
2. Remove any client-specific data
3. Run `/aios-factory:validate` and fix all issues
4. Submit a pull request to the repository

Every new example helps the community and demonstrates what is possible.

---

## Premium Verticals

For verticals that require deep domain expertise — validated compliance requirements, quantified pain points, decision-maker intelligence, and battle-tested workflows — visit [AfrexAI](https://afrexai.com).

Premium verticals are built from real-world deployments and include:
- Regulatory compliance knowledge
- Industry-validated workflows
- Pain point quantification with ROI metrics
- Integration specifications tested with real tools
