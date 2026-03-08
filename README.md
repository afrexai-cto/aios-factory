# AIOS Factory

**Generate a complete AI Operating System workspace for any business vertical — in minutes.**

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Claude Code](https://img.shields.io/badge/Built%20for-Claude%20Code-blueviolet)](https://claude.ai/code)
[![AAA Accelerator](https://img.shields.io/badge/AIOS-AAA%20Accelerator-orange)](https://aaaaccelerator.com)

---

## What is an AIOS?

An **AI Operating System** is a layer of AI automation wrapped around a business. Instead of hiring more people or buying more tools, an AIOS gives business owners their time back — one automated workflow at a time.

The concept comes from the [AAA Accelerator](https://aaaaccelerator.com), the leading AI business launch and AIOS program. Every AIOS follows the same five-layer architecture, but speaks the language of the business it serves.

**AIOS Factory** is the tool that generates these workspaces. Give it a business vertical — "Dental Practices", "Accounting Firms", "Landscaping Companies" — and it produces a complete, working Claude Code workspace with domain-specific skills, commands, context templates, and integrations.

## Quick Start

### 1. Clone the repository

```bash
git clone https://github.com/1kalin/aios-factory.git
cd aios-factory
```

### 2. Install as a Claude Code plugin

```bash
# From within any Claude Code project
claude plugin add /path/to/aios-factory
```

Or add it directly to your Claude Code plugins directory:

```bash
cp -r aios-factory ~/.claude/plugins/aios-factory
```

### 3. Generate a workspace

```
/aios-factory:create-vertical "AI Automation Agency"
```

This researches the niche, maps terminology, identifies workflows, and scaffolds a complete workspace — ready for a business owner to clone and start using with Claude Code.

### 4. Try the included example

The `examples/ai-agency/` directory contains a fully built workspace for an AI automation agency. Copy it to a new directory, open it in Claude Code, and type `/prime`:

```bash
cp -r examples/ai-agency ~/my-agency-workspace
cd ~/my-agency-workspace
# Open in Claude Code, then run /prime
```

## What Gets Generated

When you run `/aios-factory:create-vertical`, you get a complete workspace:

```
my-vertical-workspace/
├── CLAUDE.md                    # Claude knows who you are and what you do
├── .env.example                 # API keys and credentials needed
├── .mcp.json                    # MCP server connections (Slack, Notion, etc.)
├── context/
│   ├── business-info.md         # Your business details (fill in the blanks)
│   ├── team.md                  # Team structure and roles
│   └── task-audit.md            # Track what gets automated
├── skills/
│   ├── client-workflow/
│   │   └── SKILL.md             # Domain-specific client management
│   ├── intake-process/
│   │   └── SKILL.md             # How new work enters the system
│   ├── delivery-workflow/
│   │   └── SKILL.md             # How work gets delivered
│   └── reporting/
│       └── SKILL.md             # What the system produces
├── commands/
│   ├── prime.md                 # /prime — start every session here
│   ├── intake.md                # /intake — process new work
│   ├── status.md                # /status — check project status
│   └── scope.md                 # /scope — scope new work
└── niche-config.yaml            # The vertical's configuration
```

Every file is populated with real domain knowledge — not placeholders. The generated workspace uses the language of the industry, understands the workflows, and knows which integrations matter.

## The Five Elements

Every AIOS workspace is built on the same universal architecture. This makes workspaces reproducible, auditable, and upgradeable — regardless of the business vertical.

| Element | Purpose | Example |
|---------|---------|---------|
| **E1: Intake** | How work enters the system | Client onboarding form, email parser, API webhook |
| **E2: Processing** | Where intelligence lives | AI analysis, business rules, workflow orchestration |
| **E3: Output** | What gets delivered | Reports, proposals, notifications, dashboards |
| **E4: Tracking** | How progress is monitored | Status updates, audit logs, KPI dashboards |
| **E5: Deployment** | How the system reaches users | Cloud hosting, white-label setup, self-hosted |

The factory maps these elements to your specific vertical. A law firm's "intake" is a "new instruction." A landscaper's "output" is a "customer quote." Same architecture, different language.

## Factory Commands

| Command | Purpose |
|---------|---------|
| `/aios-factory:create-vertical "Name"` | Research a niche and generate a complete workspace |
| `/aios-factory:create-workspace` | Generate a workspace from an existing niche config |
| `/aios-factory:validate` | Validate a generated workspace for quality and completeness |

## How It Works

```
         You say: /aios-factory:create-vertical "Dental Practices"
                              │
                              ▼
                   ┌─────────────────────┐
                   │   Niche Research     │  ← Researches the industry
                   │   (web + knowledge)  │     terminology, workflows,
                   └──────────┬──────────┘     integrations, pain points
                              │
                              ▼
                   ┌─────────────────────┐
                   │  Terminology Map     │  ← Maps universal terms to
                   │  (10 universal →     │     domain-specific language
                   │   domain terms)      │     ("patient", "appointment")
                   └──────────┬──────────┘
                              │
                              ▼
                   ┌─────────────────────┐
                   │  Workspace Scaffold  │  ← Generates CLAUDE.md, skills,
                   │  (Five Elements      │     commands, context templates,
                   │   architecture)      │     MCP config, niche config
                   └──────────┬──────────┘
                              │
                              ▼
                   ┌─────────────────────┐
                   │  Quality Validation  │  ← Checks completeness,
                   │  (automated checks)  │     consistency, and usability
                   └──────────┬──────────┘
                              │
                              ▼
                    Ready-to-use workspace
```

## Example: AI Automation Agency

The `examples/ai-agency/` directory is a complete, working workspace for someone running an AI automation agency (like an AAA Accelerator member). It includes:

- **Client onboarding skill** — How to run a discovery call and onboard a new client
- **Project scoping skill** — How to scope an AIOS build for a client's business
- **Proposal generation skill** — Create professional proposals with pricing
- **Delivery workflow skill** — Manage the build-test-launch lifecycle

**Terminology mapping:**
| Universal Term | Agency Term |
|----------------|-------------|
| Client | Client |
| Case | Project |
| Intake | Discovery Call |
| Workflow | Engagement |
| Outcome | Deliverable |
| Provider | Consultant |
| Report | Proposal |
| Invoice | Invoice |

Try it by copying the example and running `/prime` in Claude Code.

## Creating Your Own Vertical

The factory handles everything, but if you want to understand what goes into a vertical or build one manually, see the guides:

1. **[Getting Started](docs/GETTING_STARTED.md)** — Installation and first workspace
2. **[How It Works](docs/HOW_IT_WORKS.md)** — Architecture and design decisions
3. **[Creating Verticals](docs/CREATING_VERTICALS.md)** — Step-by-step guide for custom verticals
4. **[Examples Gallery](docs/EXAMPLES.md)** — What different verticals look like

## Project Structure

```
aios-factory/
├── core/                          # Universal framework (the theory)
│   ├── five-elements/             # Five Elements architecture pattern
│   ├── terminology-engine/        # Universal → domain term mapping
│   ├── niche-discovery/           # Niche validation framework
│   └── clone-pipeline/            # White-label deployment process
│
├── factory/                       # The factory itself (the machinery)
│   ├── commands/                  # Slash commands for Claude Code
│   ├── agents/                    # Sub-agents for research and generation
│   └── templates/                 # Boilerplate templates with placeholders
│
├── examples/                      # Ready-to-use example verticals
│   └── ai-agency/                 # Complete AI agency workspace
│
└── docs/                          # Guides and documentation
```

## Who Is This For?

- **AI Automation Agencies** building AIOS workspaces for clients
- **Business owners** who want to create their own AI workspace
- **AAA Accelerator members** looking to productize their offerings
- **Claude Code users** who want structured, domain-aware workspaces

## Premium Verticals

AIOS Factory gives you the framework and the machinery. For verticals with deep domain expertise — regulatory compliance, industry-specific workflows, decision-maker intelligence, and validated pain points — check out [AfrexAI](https://afrexai.com).

AfrexAI builds production-grade vertical plugins with:
- Deep compliance knowledge (SRA, CQC, FCA, and more)
- Quantified pain points with ROI metrics
- Decision-maker profiles and messaging
- Battle-tested workflows from real deployments

## Contributing

Contributions are welcome. The best ways to contribute:

1. **Add example verticals** — Build a workspace for your industry and submit a PR
2. **Improve templates** — Make the generated output better
3. **Fix bugs** — Report issues or submit fixes
4. **Improve docs** — Better documentation helps everyone

Please keep PRs focused and well-documented.

## Credits

- **AIOS concept and methodology**: [AAA Accelerator](https://aaaaccelerator.com)
- **Five Elements architecture and factory tooling**: [AfrexAI](https://afrexai.com)
- **Built for**: [Claude Code](https://claude.ai/code) by Anthropic

## License

MIT License. See [LICENSE](LICENSE) for details.

---

*Built with care by [AfrexAI](https://afrexai.com) — AI Engineers & Automation Specialists.*
