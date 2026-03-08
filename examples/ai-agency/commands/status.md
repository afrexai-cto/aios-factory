---
description: Check status of active projects and pipeline
argument-hint: ""
---

# /status

Review the current state of all active projects, pipeline prospects, and agency capacity. Produces a dashboard-style overview.

## Usage

```
/status
```

## Process

1. **Read context** — Review `context/business-info.md` and `context/team.md` for current state.

2. **Active projects** — For each active project, summarize:
   - Client name and vertical
   - Current phase (Kickoff/Build/Review/Testing/Launch/Support)
   - Health (Green/Yellow/Red)
   - Next milestone and date
   - Any blockers

3. **Pipeline** — For each prospect:
   - Client name and vertical
   - Stage (Inquiry/Qualified/Discovery Scheduled/Discovery Complete/Proposal Sent)
   - Next action and date
   - Probability of closing (High/Medium/Low)

4. **Capacity** — Calculate:
   - Active project count vs maximum
   - Hours committed this week
   - Next available slot for a new project

5. **Action items** — List the top 3 things to do today, prioritized by urgency and impact.

## Output

```
AGENCY STATUS — [Date]

ACTIVE PROJECTS:
  [Client] — [Phase] — [Health]
    Next: [Milestone] by [Date]
    Blockers: [None / Description]

  [Client] — [Phase] — [Health]
    Next: [Milestone] by [Date]

PIPELINE:
  [Prospect] — [Stage] — [Probability]
    Next action: [What to do] by [Date]

CAPACITY:
  Active projects: [X] / [Max]
  Hours committed: [X] / [Available]
  Next available slot: [Date]

TODAY'S TOP 3:
  1. [Action] — [Why it's urgent]
  2. [Action]
  3. [Action]
```

## Tips

- Run `/status` at the start of every work session to orient yourself
- If capacity is at maximum, focus on delivery and pipeline nurturing, not new intake
- Use the health indicators to identify projects that need attention before they become problems
