---
name: delivery-workflow
description: >
  Project delivery lifecycle for AIOS builds. Auto-activates when building,
  delivering, launching, testing, or handing off an AIOS workspace to a client.
version: 1.0.0
triggers:
  - "build"
  - "deliver"
  - "launch"
  - "handoff"
  - "testing"
  - "deploy"
  - "go live"
---

# Delivery Workflow

## Overview

Delivery is where the agency earns its reputation. The build-test-launch cycle takes the scoped project and turns it into a working AIOS workspace that the client can use from day one. A structured delivery process prevents scope creep, catches issues early, and ensures a smooth handoff.

---

## The Delivery Lifecycle

```
Kickoff → Build → Internal Review → Client Testing → Refinement → Launch → Support
```

### Phase 1: Kickoff (Day 1)

**Kickoff call agenda** (30-45 minutes):

1. Confirm the project scope (share the scope document)
2. Set expectations for timeline and communication cadence
3. Identify the client's primary contact for questions
4. Request access to any systems needed (Slack, Notion, etc.)
5. Agree on testing process (who tests, how feedback is given)
6. Schedule the next check-in

**Kickoff deliverables:**
- Shared project timeline
- Communication channel set up (Slack channel or email thread)
- Access credentials received
- Kickoff meeting notes shared with client

### Phase 2: Build (Week 1-2)

Follow the scope document. Build in this order:

**Day 1-2: Foundation**
- Create workspace directory structure
- Write CLAUDE.md with business context
- Set up context files (business-info, team, task-audit)
- Configure niche terminology
- Set up .env and .mcp.json

**Day 3-5: Core Skills**
- Build each skill from the scope, starting with the highest-priority one
- Test each skill individually as you build it
- Use domain-specific language throughout

**Day 6-8: Commands and Integration**
- Create all commands
- Configure MCP servers and test connections
- Verify integrations send and receive data correctly

**Day 9-10: Polish**
- Run `/prime` and verify the full experience
- Walk through each workflow end-to-end
- Fix any rough edges
- Run `/aios-factory:validate` against the workspace

**Build communication cadence:**
- Brief daily update in the project channel (3 sentences max)
- Detailed update at mid-build (end of week 1)
- Demo at end of build phase

### Phase 3: Internal Review (Day 11)

Before showing the client, review the workspace yourself:

**Review checklist:**
- [ ] `/prime` produces an accurate business summary
- [ ] Every command works without errors
- [ ] Every skill produces useful output with realistic inputs
- [ ] Terminology is consistent (no generic terms leaked through)
- [ ] Integrations connect and function correctly
- [ ] Context templates are filled with appropriate guidance
- [ ] No placeholder text, TODOs, or empty sections
- [ ] Documentation is clear for a non-technical user

### Phase 4: Client Testing (Day 12-14)

**Prepare testing instructions:**

Send the client a document that explains:
1. How to open the workspace in Claude Code
2. How to run `/prime`
3. A list of 3-5 specific scenarios to test
4. How to give feedback (structured form, not freeform)

**Test scenarios should cover:**
- Running `/prime` and confirming Claude understands the business
- Processing a realistic intake scenario
- Checking project status
- Running each command with real-world inputs
- Verifying integration behavior

**Feedback form template:**

| Scenario | What Happened | Expected | Issue? |
|----------|--------------|----------|--------|
| Ran /prime | [Client describes] | [Expected behavior] | Yes/No |
| Ran /intake | [Client describes] | [Expected behavior] | Yes/No |

### Phase 5: Refinement (Day 15-16)

Address client feedback:

1. Categorize feedback as: Bug / Enhancement / Out of Scope
2. Fix all bugs immediately
3. Implement quick enhancements (under 1 hour each)
4. Document out-of-scope requests for future phases
5. Re-test affected areas

**Scope management:**
If the client requests features not in the original scope:
- Acknowledge the request
- Explain it was not in the current scope
- Offer to include it in a follow-up phase or change order
- Do not add unscoped work to avoid setting precedent

### Phase 6: Launch (Day 17-18)

**Launch day checklist:**

- [ ] All client feedback addressed
- [ ] Final `/aios-factory:validate` passes
- [ ] Workspace transferred to client (Git repo or file share)
- [ ] `.env` credentials configured on client's machine
- [ ] Client has Claude Code installed and configured
- [ ] Launch call scheduled

**Launch call agenda** (30-45 minutes):
1. Walk through the workspace together
2. Client runs `/prime` independently
3. Run through one complete workflow together
4. Answer questions
5. Explain ongoing support terms
6. Celebrate the launch

### Phase 7: Support (Ongoing)

**First 30 days:**
- Check in weekly (short call or message)
- Address any issues within 24 hours
- Track usage — are they actually using it?
- Identify opportunities for additional skills

**After 30 days:**
- Transition to monthly check-ins
- Offer optimization reviews (quarterly)
- Suggest new skills or integrations based on usage patterns

---

## Project Status Tracking

For each active project, track:

| Field | Value |
|-------|-------|
| Client | [Name] |
| Phase | [Kickoff/Build/Review/Testing/Refinement/Launch/Support] |
| Start date | [Date] |
| Target launch | [Date] |
| Next milestone | [Description + Date] |
| Blockers | [Any blockers] |
| Health | [Green/Yellow/Red] |

**Health indicators:**
- **Green**: On track, no issues
- **Yellow**: Minor delays or open questions, manageable
- **Red**: Blocked, behind schedule, or client unresponsive

---

## Output Format

**Project Status: [Client Name]**
*Last updated: [Date]*

Phase: [Current phase]
Health: [Green/Yellow/Red]
Next milestone: [What + When]

**Completed:**
- [Milestone 1] — [Date]
- [Milestone 2] — [Date]

**In Progress:**
- [Current task] — [% complete]

**Upcoming:**
- [Next task] — [Planned date]

**Blockers:**
- [Blocker description] — [Action needed]
