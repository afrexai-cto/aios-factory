---
name: clone-pipeline
description: >
  White-label deployment process for transforming a generated AIOS workspace into
  a client-ready, branded deployment. Auto-activates when deploying, branding,
  white-labelling, or preparing a workspace for a specific business.
version: 1.0.0
triggers:
  - "deploy"
  - "brand"
  - "white-label"
  - "clone"
  - "customize for client"
  - "prepare workspace"
  - "launch"
references:
  - references/deployment-checklist.md
---

# Clone Pipeline

## Overview

A generated workspace is a template. The clone pipeline transforms it into a workspace ready for a specific business. This means filling in the business details, configuring integrations, applying branding, and verifying that everything works.

The goal: a business owner clones the workspace, types `/prime`, and Claude immediately understands their business and is ready to help.

---

## The 4-Step Clone Process

```
STEP 1: PERSONALIZE
        Fill in business details, team info, and context

STEP 2: CONFIGURE
        Set up API keys, MCP connections, and integrations

STEP 3: VERIFY
        Run /prime and test that the workspace responds correctly

STEP 4: HAND OFF
        Share the workspace with the business owner
```

---

## Step 1: Personalize

Replace all placeholder content with the specific business's information.

### Files to Update

**`context/business-info.md`**
- Business name, what they do, who they serve
- Number of staff, locations, and key services
- Recent changes or priorities

**`context/team.md`**
- Team members and their roles
- Who handles what type of work
- Reporting structure

**`context/task-audit.md`**
- List of recurring tasks the business performs
- Time estimates for each task
- Which tasks are candidates for automation

**`CLAUDE.md`**
- Update the business name and description
- Verify that all skills and commands are relevant
- Remove any skills that do not apply to this business

**`niche-config.yaml`**
- Confirm terminology mappings match what this business uses
- Adjust any terms that differ from the generic vertical mapping

### Personalization Checklist

- [ ] Business name appears correctly in all files
- [ ] No placeholder text remains (no brackets, no "your X here")
- [ ] Team members listed by name and role
- [ ] At least 5 recurring tasks documented in task audit
- [ ] Terminology matches what this specific business uses

---

## Step 2: Configure

Set up the technical connections the workspace needs.

### `.env` File

Copy `.env.example` to `.env` and fill in:
- API keys for AI services (Anthropic, OpenAI, etc.)
- Integration credentials (Slack, Notion, Google, etc.)
- Any vertical-specific API keys

### `.mcp.json` File

Configure MCP servers for the integrations this business uses:
- Communication: Slack, email
- Project management: Notion, Linear, Asana
- Calendar: Google Calendar
- File storage: Google Drive, Dropbox
- Accounting: Xero, QuickBooks

Only enable integrations the business actually uses. Remove unused entries.

### Configuration Checklist

- [ ] `.env` file created from `.env.example`
- [ ] All required API keys filled in
- [ ] MCP servers configured for active integrations
- [ ] Unused MCP entries removed
- [ ] API connections tested (keys are valid)

---

## Step 3: Verify

Test the workspace end-to-end before handing it off.

### Verification Steps

1. **Run `/prime`** — Claude should summarize the business accurately
2. **Run each command** — Every command should produce meaningful output
3. **Check terminology** — No generic terms should appear in any response
4. **Test integrations** — If Slack is configured, verify messages send
5. **Simulate a workflow** — Walk through a typical work scenario

### Verification Checklist

- [ ] `/prime` produces accurate business summary
- [ ] All commands execute without errors
- [ ] All terminology matches the business's language
- [ ] Active integrations connect successfully
- [ ] At least one full workflow tested end-to-end
- [ ] No placeholder text appears in any output

---

## Step 4: Hand Off

Transfer the workspace to the business owner.

### Handoff Options

**Option A: Git Repository**
- Push the workspace to a private Git repository
- Share access with the business owner
- Include setup instructions in the README

**Option B: Direct Copy**
- Zip the workspace directory
- Share via secure file transfer
- Walk the owner through initial setup

**Option C: Guided Setup**
- Share the workspace and join the owner for first session
- Run `/prime` together
- Demonstrate key commands
- Answer questions in real time

### Handoff Checklist

- [ ] Workspace transferred to the business owner
- [ ] Owner has all necessary credentials (API keys, etc.)
- [ ] Owner has run `/prime` successfully at least once
- [ ] Owner knows which commands are available
- [ ] Support channel established (email, Slack, etc.)
- [ ] Follow-up session scheduled (optional but recommended)

---

## Post-Handoff

After the workspace is live, the business owner will:

1. Run `/prime` at the start of each session
2. Use commands to manage their workflows
3. Update `context/` files as their business evolves
4. Request new skills or commands as needs emerge

The workspace is designed to grow with the business. New skills can be added, existing ones refined, and the context updated as the business changes.

---

## References

- `references/deployment-checklist.md` — Complete pre-deployment checklist
