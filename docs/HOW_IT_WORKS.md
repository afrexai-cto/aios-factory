# How It Works

An explanation of the architecture and design decisions behind AIOS Factory.

---

## The Core Idea

Every business, regardless of industry, performs the same fundamental operations: it receives work, processes that work, delivers results, tracks progress, and makes the system available to its team. The specific details change — a law firm processes "matters," a dental practice processes "appointments" — but the structure is universal.

AIOS Factory exploits this universal structure. It provides a framework (the Five Elements), a translation layer (the Terminology Engine), and a generation pipeline (the Factory) that together can produce a working AI workspace for any vertical.

---

## Architecture Overview

```
┌─────────────────────────────────────────────────────┐
│                    AIOS FACTORY                       │
├─────────────────────────────────────────────────────┤
│                                                       │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  │
│  │    CORE      │  │   FACTORY    │  │  EXAMPLES    │  │
│  │  frameworks  │  │  machinery   │  │  references  │  │
│  └──────┬──────┘  └──────┬──────┘  └─────────────┘  │
│         │                │                            │
│         ▼                ▼                            │
│  ┌─────────────────────────────┐                     │
│  │    Generated Workspace       │                     │
│  │  (CLAUDE.md + skills +       │                     │
│  │   commands + context +       │                     │
│  │   integrations)              │                     │
│  └─────────────────────────────┘                     │
│                                                       │
└─────────────────────────────────────────────────────┘
```

---

## The Three Layers

### Layer 1: Core Frameworks

The `core/` directory contains the universal patterns that apply to every workspace:

**Five Elements** — The architecture pattern. Every workspace has:
- E1: Intake (how work enters)
- E2: Processing (where intelligence lives)
- E3: Output (what gets delivered)
- E4: Tracking (how progress is monitored)
- E5: Deployment (how users access it)

**Terminology Engine** — The translation layer. 10 universal terms mapped to every vertical's language. This ensures generated workspaces speak the language of the industry, not generic business language.

**Niche Discovery** — The evaluation framework. 7 criteria for assessing whether a vertical is viable before investing time in building for it.

**Clone Pipeline** — The deployment process. How to take a generated workspace and prepare it for a specific business with real data, real integrations, and real team members.

### Layer 2: Factory Machinery

The `factory/` directory contains the tools that do the generation:

**Commands** — Three slash commands that orchestrate the process:
- `create-vertical` — Full pipeline: research, map, scaffold, validate
- `create-workspace` — Scaffold from existing config (skip research)
- `validate` — Quality check a generated workspace

**Agents** — Specialized sub-agents for each phase:
- `niche-researcher` — Deep industry research
- `workspace-scaffolder` — File generation from config
- `quality-validator` — Completeness and consistency checks

**Templates** — Boilerplate files with placeholders:
- CLAUDE.md template with `{{VERTICAL_NAME}}`, `{{TERMINOLOGY_TABLE}}`, etc.
- Skill, command, and agent templates
- Configuration file templates

### Layer 3: Examples

The `examples/` directory contains working reference workspaces:

- `ai-agency/` — A complete workspace for an AI automation agency

Examples serve two purposes:
1. They are immediately usable (copy and start working)
2. They demonstrate what generated output should look like

---

## The Generation Pipeline

When you run `/aios-factory:create-vertical "Dental Practices"`, here is what happens:

### Step 1: Research

The niche-researcher agent uses web search and domain knowledge to build a niche profile:

```
Input:  "Dental Practices"
Output: Structured YAML with terminology, workflows, pain points,
        integrations, and compliance landscape
```

### Step 2: Terminology Mapping

The 10 universal terms are mapped to dental-specific language:

```
case → appointment
client → patient
intake → booking
provider → dentist
...
```

### Step 3: Five Elements Mapping

Each element gets a concrete implementation plan:

```
E1: Online booking form + phone appointment capture
E2: Schedule optimization + treatment plan AI
E3: Treatment summaries + patient communications
E4: Daily schedule dashboard + appointment status
E5: Claude Code workspace on reception desk computer
```

### Step 4: Scaffolding

The workspace-scaffolder agent reads the templates and fills them with the niche profile data:

```
templates/CLAUDE_MD_TEMPLATE.md
  + niche profile
  = workspace/CLAUDE.md (fully populated)
```

This produces every file in the workspace.

### Step 5: Validation

The quality-validator agent checks the output:
- Structure (all files present)
- Content (no placeholders remaining)
- Terminology (no universal terms leaked)
- Skills (domain-specific, actionable)
- Commands (clear processes)
- Usability (would `/prime` work?)

---

## Design Decisions

### Why Five Elements?

The Five Elements pattern emerged from observing dozens of business automation projects. Every successful project had the same five layers, even when the teams did not explicitly design for them. Making the pattern explicit makes it reproducible.

### Why 10 Universal Terms?

Ten is enough to cover every business concept we have encountered. Fewer terms would force awkward mappings. More terms would add complexity without benefit. The terms were chosen by analyzing terminology across 15+ verticals and finding the common denominators.

### Why Templates with Placeholders?

Template-based generation is predictable and debuggable. When a generated workspace has an issue, you can trace it to the template and fix it once. AI-only generation (no templates) produces inconsistent output that is harder to maintain.

### Why Agents Instead of a Single Script?

Breaking the pipeline into specialized agents (researcher, scaffolder, validator) allows each to be improved independently. It also allows running individual steps when you need research without scaffolding, or validation without regeneration.

---

## Extending the Factory

### Adding New Templates

Add new template files to `factory/templates/`. Use `{{PLACEHOLDER_NAME}}` syntax for values that change per vertical.

### Adding New Core Skills

Add new skill directories to `core/`. Each skill needs a `SKILL.md` with frontmatter and an optional `references/` directory.

### Adding Example Verticals

Add new directories to `examples/`. Each should be a complete, self-contained workspace that someone can copy and start using.

---

## Relationship to Premium Offerings

AIOS Factory provides the framework and the machinery for generating workspaces. It uses publicly available knowledge for niche research.

For verticals that require deep, validated domain expertise — regulatory compliance specifics, quantified pain points, decision-maker intelligence, battle-tested workflows — [AfrexAI](https://afrexai.com) offers premium vertical plugins built from real-world deployments.

The factory and premium plugins are complementary: the factory generates the workspace structure, and premium plugins can enhance specific skills with deeper domain knowledge.
