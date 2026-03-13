# CLAUDE.md — {{VERTICAL_NAME}} AIOS Workspace

This file provides guidance to Claude Code when working within this workspace.

---

## What This Is

This is an **AI Operating System workspace** for a {{VERTICAL_NAME}} business. It gives Claude the context, skills, and commands needed to act as an intelligent assistant that understands the {{VERTICAL_DESCRIPTION}}.

> Built with [AIOS Factory](https://github.com/afrexai-cto/aios-factory) — from the AAA Accelerator AIOS methodology.

---

## The Claude-User Relationship

- **User**: The business owner or team member who directs work
- **Claude**: An agent assistant that reads context, understands the business, and executes commands using domain-specific knowledge

Always start sessions with `/prime`. Claude reads the context files and confirms understanding before proceeding.

---

## Workspace Structure

```
.
├── CLAUDE.md                # This file — always loaded
├── .env                     # API keys (never commit)
├── .mcp.json                # MCP server connections
├── context/
│   ├── business-info.md     # About the business
│   ├── team.md              # Team members and roles
│   └── task-audit.md        # Tasks and automation tracking
├── skills/
│   ├── <skill-1>/SKILL.md       # [Skill description]
│   ├── <skill-2>/SKILL.md       # [Skill description]
│   ├── <skill-3>/SKILL.md       # [Skill description]
│   └── <skill-4>/SKILL.md       # [Skill description]
├── commands/
│   ├── prime.md                 # /prime — initialize session
│   ├── intake.md                # /intake — process new work
│   ├── status.md                # /status — check current status
│   └── scope.md                 # /scope — scope new work
└── niche-config.yaml        # Vertical configuration
```

---

## Commands

{{COMMANDS_TABLE}}

---

## Skills

{{SKILLS_LIST}}

---

## Terminology

This workspace uses {{VERTICAL_NAME}}-specific language:

{{TERMINOLOGY_TABLE}}

---

## Session Workflow

1. **Start**: Run `/prime` to load context and confirm understanding
2. **Work**: Use commands or give direct instructions
3. **Track**: Update `context/task-audit.md` as tasks get automated
4. **Maintain**: Keep context files current as the business evolves

---

## Critical Instruction

Whenever changes are made to the workspace — new commands, updated skills, structural changes — consider whether this CLAUDE.md needs updating. This file must always reflect the current state.
