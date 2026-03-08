# CLAUDE.md — AIOS Factory

This file provides guidance to Claude Code when working within the AIOS Factory project.

---

## What This Is

**AIOS Factory** generates complete AI Operating System workspaces for any business vertical. It is a Claude Code plugin that uses the Five Elements architecture to scaffold domain-specific workspaces with skills, commands, context templates, and integrations.

The AIOS concept originates from the [AAA Accelerator](https://aaaaccelerator.com). AIOS Factory is the open-source tooling that makes the concept reproducible.

---

## How to Use This Factory

### Generate a Workspace

```
/aios-factory:create-vertical "Niche Name"
```

This command:
1. Researches the niche (terminology, workflows, pain points, integrations)
2. Maps the 10 universal terms to domain-specific language
3. Scaffolds a complete workspace using the Five Elements architecture
4. Validates the output for quality and completeness

### Generate from Existing Config

```
/aios-factory:create-workspace
```

If you already have a `niche-config.yaml`, this skips research and scaffolds directly.

### Validate a Workspace

```
/aios-factory:validate
```

Checks a generated workspace for completeness, consistency, and usability.

---

## The Five Elements

Every workspace follows this universal architecture:

| Element | Purpose | Question It Answers |
|---------|---------|---------------------|
| **E1: Intake** | How work enters the system | "How does new work arrive?" |
| **E2: Processing** | Where domain intelligence lives | "What happens to work after it arrives?" |
| **E3: Output** | What gets delivered | "What does the client receive?" |
| **E4: Tracking** | How progress is monitored | "Can the user always see what's happening?" |
| **E5: Deployment** | How the system reaches users | "How does this become a running service?" |

When building a workspace, map each element to the vertical's specific context. A law firm's E1 is "new instruction." A clinic's E1 is "patient referral." Same element, different language.

---

## Terminology Engine

The factory maps 10 universal terms to each vertical's language:

| # | Universal Term | What It Means |
|---|----------------|---------------|
| 1 | **Case** | The primary unit of work |
| 2 | **Client** | Who submits or receives work |
| 3 | **Document** | Files and records |
| 4 | **Workflow** | The sequence of steps |
| 5 | **Intake** | Receiving new work |
| 6 | **Outcome** | The final result |
| 7 | **Provider** | The professional doing the work |
| 8 | **Status** | Current state of work |
| 9 | **Report** | Structured output document |
| 10 | **Invoice** | Financial record |

Every generated workspace replaces universal terms with the vertical's own language. No generic terms should appear in a finished workspace.

---

## Project Structure

```
aios-factory/
├── core/                          # Universal framework
│   ├── five-elements/             # Architecture pattern (E1-E5)
│   ├── terminology-engine/        # Term mapping system
│   ├── niche-discovery/           # Validation framework
│   └── clone-pipeline/            # Deployment process
├── factory/
│   ├── commands/                  # Slash commands
│   ├── agents/                    # Sub-agents
│   └── templates/                 # Boilerplate with placeholders
├── examples/
│   └── ai-agency/                 # Working example workspace
└── docs/                          # Guides
```

---

## Key References

When building or modifying the factory, consult:

- `core/five-elements/SKILL.md` — Full architecture pattern with validation criteria
- `core/terminology-engine/SKILL.md` — How to map terms across verticals
- `core/niche-discovery/SKILL.md` — How to evaluate whether a vertical is viable
- `core/clone-pipeline/SKILL.md` — How to deploy a finished workspace
- `factory/templates/` — All boilerplate templates used during generation

---

## Quality Standards

Generated workspaces must meet these criteria:

1. All 10 terminology terms mapped to domain-specific equivalents
2. At least 3 skills with actionable, domain-specific content
3. At least 3 commands with clear process steps
4. Context templates with meaningful placeholders (not generic)
5. A working `/prime` command that initializes a session
6. No universal terms visible in user-facing text
7. No TODO, TBD, or placeholder text in final output
8. Every file under 300 lines

---

## Creating New Verticals

The recommended flow:

1. Run `/aios-factory:create-vertical "Niche Name"` to auto-generate
2. Review the generated workspace for domain accuracy
3. Run `/aios-factory:validate` to check quality
4. Customize skills and commands for deeper domain coverage
5. Test by running `/prime` in the generated workspace

For manual creation, follow `docs/CREATING_VERTICALS.md`.

---

## Conventions

- Skills live in `skills/{skill-name}/SKILL.md` with optional `references/` subdirectory
- Commands live in `commands/{command-name}.md` with frontmatter
- Context templates use bracket placeholders: `[Your business name here]`
- Niche config uses YAML with clear section headers
- All files use Markdown unless there is a specific reason for another format
