---
description: Generate workspace from existing niche config
argument-hint: "<path to niche-config.yaml>"
---

# /aios-factory:create-workspace

Generate a complete AIOS workspace from an existing `niche-config.yaml` file. Use this when you have already done the niche research and want to scaffold the workspace directly.

## Usage

```
/aios-factory:create-workspace $ARGUMENTS
```

**Examples:**
- `/aios-factory:create-workspace niche-config.yaml`
- `/aios-factory:create-workspace examples/ai-agency/niche-config.yaml`

## Process

### Step 1: Read Configuration

Read the provided `niche-config.yaml` and validate:
- All required fields are present
- Terminology mapping is complete (10 terms)
- At least 3 workflows defined
- At least 2 pain points identified
- Five Elements mapping present

If any required field is missing, report what is needed before proceeding.

### Step 2: Scaffold Directory

Create the workspace directory structure:

```
<niche-slug>/
├── CLAUDE.md
├── .env.example
├── .mcp.json
├── context/
│   ├── business-info.md
│   ├── team.md
│   └── task-audit.md
├── skills/
│   └── [generated from config]
├── commands/
│   ├── prime.md
│   └── [generated from config]
└── niche-config.yaml
```

### Step 3: Generate Files

Using the templates in `factory/templates/`, generate each file:

1. **CLAUDE.md** — from `CLAUDE_MD_TEMPLATE.md`, filled with niche config data
2. **Skills** — from `SKILL_TEMPLATE.md`, one per workflow in the config
3. **Commands** — from `COMMAND_TEMPLATE.md`, standard set plus niche-specific
4. **Context** — from templates, with domain-appropriate placeholders
5. **Configuration** — `.env.example` and `.mcp.json` from templates

### Step 4: Validate

Run the quality checks from `/aios-factory:validate` automatically.

### Step 5: Report

Output the workspace location and file summary.

## Input Format

The `niche-config.yaml` must follow this structure:

```yaml
niche:
  name: "Vertical Name"
  slug: "vertical-slug"
  description: "One-line description"

terminology:
  case: "Domain term"
  client: "Domain term"
  # ... all 10 terms

workflows:
  - name: "Workflow Name"
    trigger: "What starts it"
    steps: [list of steps]
    output: "What it produces"

pain_points:
  - name: "Pain Point"
    description: "Description"
    frequency: "daily/weekly"

five_elements:
  intake: "How work arrives"
  processing: "What happens to it"
  output: "What gets delivered"
  tracking: "How progress is monitored"
  deployment: "How users access it"

integrations:
  - name: "Tool Name"
    purpose: "Why it's needed"
```

## Output

A complete workspace directory adjacent to the input config file, containing:

- `CLAUDE.md` — workspace identity and session guide, derived from the config
- `.env.example` — required API keys and integration credentials
- `.mcp.json` — MCP server connections for the integrations listed in the config
- `context/` — three context templates pre-filled with vertical-appropriate prompts
- `skills/` — one skill file per workflow defined in the config
- `commands/` — standard command set plus niche-specific commands
- `niche-config.yaml` — copy of the input config embedded in the workspace

## Tips

- Use the example at `examples/ai-agency/niche-config.yaml` as a reference
- Validate your YAML syntax before running this command
- The more detail in your config, the better the generated workspace
