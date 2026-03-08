# Deployment Checklist

Complete checklist for preparing and deploying an AIOS workspace for a specific business.

---

## Pre-Deployment

### Content Verification

- [ ] `CLAUDE.md` updated with correct business name and description
- [ ] `context/business-info.md` fully populated (no placeholders)
- [ ] `context/team.md` has real team members listed
- [ ] `context/task-audit.md` has at least 5 recurring tasks
- [ ] `niche-config.yaml` terminology verified against business usage
- [ ] All skill files contain domain-specific content (not generic)
- [ ] All command files have clear process steps
- [ ] `.env.example` documents every required variable

### Technical Configuration

- [ ] `.env` file created with valid API keys
- [ ] API keys tested (make a test call for each service)
- [ ] `.mcp.json` configured for active integrations only
- [ ] Unused MCP server entries removed
- [ ] Integration permissions verified (Slack workspace, Notion pages, etc.)

### Quality Check

- [ ] No files contain placeholder text ([brackets], TBD, TODO)
- [ ] No universal terminology appears in user-facing content
- [ ] Every file is under 300 lines
- [ ] File names follow conventions (lowercase, hyphens)
- [ ] Directory structure matches the expected layout

---

## Deployment

### Workspace Transfer

- [ ] Workspace files transferred to destination
- [ ] `.env` file included (or credentials shared separately)
- [ ] `.gitignore` excludes `.env` and sensitive files
- [ ] Git repository initialized (if using Git)
- [ ] Claude Code can access the workspace directory

### First Run

- [ ] Open workspace in Claude Code
- [ ] Run `/prime` — verify accurate business summary
- [ ] Run each available command — verify no errors
- [ ] Test at least one complete workflow scenario
- [ ] Verify integrations send/receive data correctly

---

## Post-Deployment

### Owner Onboarding

- [ ] Owner has successfully run `/prime` independently
- [ ] Owner understands available commands
- [ ] Owner knows how to update context files
- [ ] Owner has documentation or reference for common tasks
- [ ] Support channel established

### Follow-Up (1 Week)

- [ ] Check if owner has used the workspace
- [ ] Identify any pain points or confusion
- [ ] Add or modify skills based on feedback
- [ ] Update context files if business details changed
- [ ] Schedule next check-in if needed

---

## Rollback Plan

If deployment fails or the owner is unable to use the workspace:

1. Identify the specific failure point (technical, content, or usability)
2. Fix the issue in the source workspace
3. Re-deploy the corrected version
4. Re-verify using the first run checklist above
5. Document the issue for future deployments
