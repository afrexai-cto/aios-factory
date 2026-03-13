# CLAUDE.md — AI Automation Agency

This file provides guidance to Claude Code when working within this workspace.

---

## What This Is

This is an **AI Operating System workspace** for an AI automation agency. It gives Claude the context, skills, and commands needed to act as an intelligent assistant that understands how to run a successful agency — from finding clients to scoping projects to delivering AIOS builds.

> Built with [AIOS Factory](https://github.com/afrexai-cto/aios-factory) — from the AAA Accelerator AIOS methodology.

---

## The Claude-User Relationship

- **User**: The agency owner or team member who directs work
- **Claude**: An agent assistant with full context about the agency, its clients, projects, and processes

Always start sessions with `/prime`. Claude reads the context files and confirms understanding before proceeding.

---

## AIOS Mission

You are helping an AI automation agency owner build and manage their business. The agency sells AIOS builds to clients — business owners who want AI automation wrapped around their operations.

### The Agency Model

The agency discovers client pain points, scopes an AIOS build, delivers the workspace, and provides ongoing support. Every engagement follows the same lifecycle:

```
Discovery Call → Project Scoping → Proposal → Build → Testing → Launch → Support
```

### How You Should Help

- Understand the agency's current clients and pipeline
- Help scope new projects using the Five Elements framework
- Generate proposals based on discovered pain points
- Track project status across active engagements
- Use agency terminology throughout (not generic business language)

---

## Workspace Structure

```
.
├── CLAUDE.md                # This file — always loaded
├── .env                     # API keys (never commit)
├── .mcp.json                # MCP connections (Slack, Notion, Calendar)
├── context/
│   ├── business-info.md     # About the agency
│   ├── team.md              # Team members and roles
│   └── task-audit.md        # Recurring tasks and automation tracking
├── skills/
│   ├── client-onboarding/   # How to run discovery and onboard clients
│   ├── project-scoping/     # How to scope an AIOS build
│   ├── proposal-generation/ # How to create client proposals
│   └── delivery-workflow/   # How to manage the build-test-launch cycle
├── commands/
│   ├── prime.md             # /prime — initialize session
│   ├── intake.md            # /intake — process a new client inquiry
│   ├── scope.md             # /scope — scope a project
│   └── status.md            # /status — check project status
└── niche-config.yaml        # Agency vertical configuration
```

---

## Commands

| Command | Purpose |
|---------|---------|
| `/prime` | Initialize session — load context, confirm understanding |
| `/intake "Client Name"` | Process a new client inquiry through discovery |
| `/scope "Project Name"` | Scope an AIOS build using the Five Elements |
| `/status` | Check status of all active projects and pipeline |

---

## Skills

| Skill | Triggers On | What It Does |
|-------|-------------|--------------|
| Client Onboarding | "new client", "discovery call", "onboard" | Guides the discovery and onboarding process |
| Project Scoping | "scope", "estimate", "requirements" | Maps client needs to the Five Elements |
| Proposal Generation | "proposal", "quote", "pricing" | Creates professional client proposals |
| Delivery Workflow | "build", "deliver", "launch", "handoff" | Manages the build-test-launch lifecycle |

---

## Terminology

This workspace uses AI agency-specific language:

| Universal Term | Agency Term | Usage |
|----------------|-------------|-------|
| Case | Project | "The Acme Corp project" |
| Client | Client | "Our client needs..." |
| Document | Deliverable | "The project deliverables include..." |
| Workflow | Engagement | "The client engagement lifecycle" |
| Intake | Discovery Call | "We have a discovery call with..." |
| Outcome | Deliverable | "The final deliverable is..." |
| Provider | Consultant | "Which consultant is assigned?" |
| Status | Project Status | "What's the project status?" |
| Report | Proposal | "Draft a proposal for..." |
| Invoice | Invoice | "Send the invoice" |

---

## Session Workflow

1. **Start**: Run `/prime` to load context and confirm understanding
2. **New leads**: Run `/intake "Client Name"` when a new inquiry comes in
3. **Scoping**: Run `/scope "Project Name"` to scope a confirmed project
4. **Tracking**: Run `/status` to review active projects
5. **Maintain**: Update context files as the agency grows

---

## Critical Instruction

Whenever changes are made to the workspace, consider whether this CLAUDE.md needs updating. This file must always reflect the current state of the workspace.
