---
name: five-elements
description: >
  Universal Five Elements architecture for building AI Operating System workspaces.
  Auto-activates when discussing intake, processing, output, tracking, deployment,
  system architecture, or workspace design for any business vertical.
version: 1.0.0
triggers:
  - "intake"
  - "processing"
  - "output"
  - "tracking"
  - "deployment"
  - "five elements"
  - "system architecture"
  - "workspace design"
  - "AIOS architecture"
references:
  - references/five-elements-guide.md
---

# Five Elements Architecture

## Overview

Every AI Operating System workspace — regardless of industry — is built on five elements. This universal architecture makes workspaces reproducible across verticals, upgradeable element-by-element, and auditable by separating concerns cleanly.

Think of it as the blueprint. The Five Elements define the shape of every workspace. The vertical's terminology, workflows, and domain knowledge fill in the details.

---

## The Five Elements

```
┌─────────────────────────────────────────────────────────────┐
│                  AIOS WORKSPACE ARCHITECTURE                  │
├─────────────────────────────────────────────────────────────┤
│  E1: INTAKE          │ How the workspace receives new work    │
│  E2: PROCESSING      │ Where domain intelligence lives        │
│  E3: OUTPUT          │ What the workspace delivers             │
│  E4: TRACKING        │ How progress is monitored               │
│  E5: DEPLOYMENT      │ How the workspace reaches users         │
└─────────────────────────────────────────────────────────────┘
```

---

## E1: Intake — How Work Enters

**Core question**: "How does the system learn about new work?"

Every business receives work somehow. The intake element captures and validates that entry point.

### Common Intake Patterns

| Pattern | Description | Best For |
|---------|-------------|----------|
| Form Wizard | Multi-step guided data collection | Complex intake with many fields |
| Email Parser | Inbox monitoring and extraction | Businesses that receive work via email |
| Conversational | Chat-based intake via AI | Low-friction, exploratory intake |
| Document Upload | File ingestion with parsing | Work that arrives as documents |
| API Webhook | External system push notification | Automated integrations |
| Scheduled Pull | System fetches work on a schedule | Batch processing |

### Intake Requirements

Every intake must provide:
1. **Validation** — reject bad input early with clear errors
2. **Deduplication** — prevent the same work from entering twice
3. **Confirmation** — acknowledge receipt to the submitter
4. **Metadata** — capture source, timestamp, and method
5. **Queuing** — decouple intake from processing

---

## E2: Processing — Where Intelligence Lives

**Core question**: "What happens to work after intake?"

This is the heart of the workspace. Domain expertise, business rules, and AI capabilities converge here.

### Common Processing Patterns

| Pattern | Description | Best For |
|---------|-------------|----------|
| AI Analysis | LLM processes domain data | Unstructured data, expert reasoning |
| Rule Engine | Codified business rules | Compliance, classification, routing |
| Workflow Orchestration | Multi-step with branching | Complex business processes |
| Human-in-Loop | Review gates in automated flow | High-stakes decisions |
| Aggregation | Combining multiple data sources | Reporting and dashboards |
| Scoring/Ranking | Evaluating against criteria | Prioritization and triage |

### Processing Layers

```
Processing Core
├── Domain Models        ← Entities specific to the vertical
├── Business Rules       ← Encoded policies and SLAs
├── AI Prompts           ← Domain-specific prompt engineering
├── Validation Logic     ← Beyond format — domain-specific checks
├── Workflow Engine      ← State machines, approval flows
└── Integration Calls    ← External service connections
```

---

## E3: Output — What Gets Delivered

**Core question**: "What does the user actually receive?"

The output element defines the value the workspace produces. Every output must be complete, accurate, and formatted for the vertical's professional standards.

### Common Output Patterns

| Pattern | Description | Best For |
|---------|-------------|----------|
| Structured Report | Formatted document with sections | Professional deliverables |
| Dashboard View | Visual summary of status and metrics | Ongoing monitoring |
| Notification | Push, email, or SMS alerts | Time-sensitive updates |
| Data Export | CSV, JSON, or PDF for downstream use | Integration with other tools |
| Recommendation | AI-generated suggestions with reasoning | Decision support |
| Automation Action | System performs action on behalf of user | Repetitive tasks |

### Output Quality Standards

1. **Completeness** — all required fields populated
2. **Accuracy** — data matches source of truth
3. **Formatting** — consistent with the vertical's professional standards
4. **Traceability** — references the inputs it was derived from
5. **Versioning** — outputs are immutable once delivered

---

## E4: Tracking — How Progress Is Monitored

**Core question**: "Can the user always see what is happening?"

Tracking is the connective tissue. It receives events from intake, processing, and output, maintaining a complete picture of workspace state.

### What to Track

```
For every work item:
├── Status              ← current state (pending, active, complete, failed)
├── Created at          ← when intake occurred
├── Updated at          ← when last state change happened
├── Completed at        ← when output was delivered
├── Owner               ← who is responsible
└── History             ← timestamped log of all events
```

### Universal Status Flow

```
PENDING → IN PROGRESS → COMPLETE
                     ↘ FAILED → RETRY → IN PROGRESS
```

---

## E5: Deployment — How Users Access It

**Core question**: "How does the workspace become a running service?"

For AIOS workspaces, deployment is typically the simplest element — the workspace runs inside Claude Code. But as workspaces grow into production tools, deployment becomes critical.

### Deployment Patterns

| Pattern | Description | Best For |
|---------|-------------|----------|
| Local Workspace | Claude Code on the user's machine | Personal productivity |
| Shared Repository | Git repo shared with team | Team collaboration |
| Cloud Deployment | Hosted web application | Client-facing products |
| White-Label | Branded deployment per client | Agency model |

---

## Element Interaction Map

```
┌──────────────┐    ┌──────────────┐    ┌──────────────┐
│  E1: INTAKE  │───▶│ E2: PROCESS  │───▶│  E3: OUTPUT  │
└──────────────┘    └──────────────┘    └──────────────┘
       │                   │                   │
       │            ┌──────▼──────┐            │
       └───────────▶│ E4: TRACK   │◀───────────┘
                    └──────┬──────┘
                    ┌──────▼──────┐
                    │ E5: DEPLOY  │
                    └─────────────┘
```

---

## Applying Five Elements to a New Vertical

### Step 1: Map the Current State

For each element, ask how the business handles it today:
- E1: How does new work currently arrive? (phone, email, walk-in, portal)
- E2: Where does expert judgment happen? (someone's head, a spreadsheet)
- E3: What gets delivered to the end customer? (report, advice, service)
- E4: How is work tracked today? (whiteboard, CRM, nothing)
- E5: How will users access this workspace? (laptop, mobile, shared)

### Step 2: Select Patterns

Choose the implementation pattern for each element based on:
- The business owner's technical comfort level
- Budget and timeline constraints
- Integration requirements with existing tools
- The volume and complexity of work

### Step 3: Map Terminology

Use the terminology engine to replace every universal term with the vertical's language.

### Step 4: Validate the Design

Confirm that data flows correctly between elements and that no element is missing.

---

## References

- `references/five-elements-guide.md` — Detailed decomposition guide for each element
