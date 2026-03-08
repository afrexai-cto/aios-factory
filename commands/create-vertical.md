---
description: Research a niche and generate a complete AIOS workspace
argument-hint: "<industry name>"
---

# /aios-factory:create-vertical

Generate a complete, ready-to-use AIOS workspace for any business vertical. Pass the industry name as the argument. Be specific for best results.

## Usage

```
/aios-factory:create-vertical $ARGUMENTS
```

**Examples:**
- `/aios-factory:create-vertical "Dental Practices"`
- `/aios-factory:create-vertical "UK Accounting Firms, 5-30 staff"`
- `/aios-factory:create-vertical "Landscaping Companies in the US"`

## Process

### Step 1: Niche Research

Spawn the `niche-researcher` agent to deeply understand the vertical:

- Industry terminology (what professionals actually call things)
- Core workflows (what they do every day)
- Common pain points (where they waste time or make mistakes)
- Technology landscape (what software they already use)
- Integration needs (Slack, Notion, Google Calendar, etc.)

Use web search for current data. Use the `niche-discovery` skill to evaluate viability.

### Step 2: Terminology Mapping

Using the `terminology-engine` skill, map all 10 universal terms:

| Universal Term | Domain Equivalent |
|----------------|-------------------|
| Case | ? |
| Client | ? |
| Document | ? |
| Workflow | ? |
| Intake | ? |
| Outcome | ? |
| Provider | ? |
| Status | ? |
| Report | ? |
| Invoice | ? |

Every term must have a real domain equivalent. No universal terms should appear in the final workspace.

### Step 3: Five Elements Mapping

Using the `five-elements` skill, map each element to the vertical:

- E1 Intake: How does new work arrive in this vertical?
- E2 Processing: What does the professional actually do with the work?
- E3 Output: What gets delivered to the end client?
- E4 Tracking: How is work status monitored?
- E5 Deployment: How will users access the workspace?

### Step 4: Workspace Scaffolding

Spawn the `workspace-scaffolder` agent to generate all workspace files:

```
generated/<niche-slug>/
├── CLAUDE.md
├── .env.example
├── .mcp.json
├── context/
│   ├── business-info.md
│   ├── team.md
│   └── task-audit.md
├── skills/
│   ├── <skill-1>/SKILL.md
│   ├── <skill-2>/SKILL.md
│   ├── <skill-3>/SKILL.md
│   └── <skill-4>/SKILL.md
├── commands/
│   ├── prime.md
│   ├── intake.md
│   ├── status.md
│   └── scope.md
└── niche-config.yaml
```

Every file must contain real, domain-specific content. No placeholders, no TODOs.

### Step 5: Quality Validation

Spawn the `quality-validator` agent to check:

- [ ] All 10 terminology terms mapped
- [ ] At least 3 skills with actionable content
- [ ] At least 3 commands with clear process steps
- [ ] Context templates have meaningful placeholders
- [ ] `/prime` command would produce a useful session initialization
- [ ] No universal terms in user-facing text
- [ ] No placeholder text (TBD, TODO, brackets)
- [ ] All files under 300 lines

### Step 6: Report

Report the results:

```
WORKSPACE CREATED: [vertical name]
Location: generated/<niche-slug>/

Files:      [count] created
Skills:     [count] / [count] complete
Commands:   [count] / [count] complete
Terminology: 10 / 10 terms mapped
Validation: PASS (or list of warnings)

To use:
  cp -r generated/<niche-slug> ~/my-workspace
  cd ~/my-workspace
  # Open in Claude Code, then run /prime
```

## Output

A complete workspace directory at `generated/<niche-slug>/` containing:

- `CLAUDE.md` — workspace identity and session guide, populated with vertical knowledge
- `.env.example` — required API keys and integration credentials
- `.mcp.json` — MCP server connections relevant to the vertical
- `context/` — three context templates pre-filled with vertical-specific prompts
- `skills/` — four or more skill files with actionable, domain-specific processes
- `commands/` — four or more command files with clear process steps
- `niche-config.yaml` — the full niche profile used to generate the workspace

Every file is populated with real domain knowledge. No placeholders, no TODOs.

## Tips

- Be specific: "UK Personal Injury Law Firms" produces better output than "Law Firms"
- Include geography for compliance accuracy: "Australian Dental Practices"
- Include business size for workflow relevance: "Solo accountants, 1-5 staff"
- Run `/aios-factory:validate generated/<niche-slug>` after creation for a second quality pass
