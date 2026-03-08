---
description: Scope an AIOS build using the Five Elements
argument-hint: "<project name or client>"
---

# /scope

Scope a new AIOS build project. Takes the discovery call debrief and produces a detailed project scope document with element mapping, skill inventory, integration audit, and effort estimate.

## Usage

```
/scope $ARGUMENTS
```

**Examples:**
- `/scope "Smith & Associates AIOS"`
- `/scope "Greenfield Dental — appointment automation"`

## Process

1. **Review context** — Read the discovery debrief (if available) or ask for client details: business name, vertical, pain points, team size, and current tools.

2. **Map the Five Elements** — For each element, define the specific implementation:
   - E1 Intake: What types of work, what fields, what method
   - E2 Processing: What AI capabilities, what rules, what review steps
   - E3 Output: What format, what standards, what frequency
   - E4 Tracking: What statuses, who needs visibility, what metrics
   - E5 Deployment: Where it runs, who accesses it, what devices

3. **Build skill inventory** — List every skill the workspace needs with complexity rating (Low/Medium/High) and priority (Must/Should/Could).

4. **Audit integrations** — Identify external tools needed, check MCP availability, estimate setup effort.

5. **Estimate effort** — Calculate total hours using the scoping formula:
   - Base setup + (skills x avg hours) + (integrations x avg hours) + testing + documentation + 15% buffer

6. **Produce scope document** — Generate the complete project scope with all details.

## Output

```
PROJECT SCOPE: [Project Name]
Prepared for: [Client Name]
Date: [Date]

Summary: [One paragraph]

Five Elements:
  E1 Intake:      [Implementation] — [Complexity]
  E2 Processing:  [Implementation] — [Complexity]
  E3 Output:      [Implementation] — [Complexity]
  E4 Tracking:    [Implementation] — [Complexity]
  E5 Deployment:  [Implementation] — [Complexity]

Skills:
  1. [Name] — [Description] — [Hours] — [Priority]
  2. [Name] — [Description] — [Hours] — [Priority]
  ...

Integrations:
  1. [Tool] — [Purpose] — [Hours]
  ...

Effort Estimate: [Total hours]
Timeline: [Weeks]
Assumptions: [List]
Exclusions: [List]
```

## Tips

- Run `/intake` first to capture the discovery debrief — it feeds directly into scoping
- Be conservative with time estimates; builds always take longer than expected
- Flag any assumptions explicitly — they become scope management tools later
- Use the skill complexity guide: Low (1-2 hrs), Medium (3-5 hrs), High (5-10 hrs)
