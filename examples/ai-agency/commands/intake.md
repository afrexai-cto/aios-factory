---
description: Process a new client inquiry through discovery
argument-hint: "<client name or business>"
---

# /intake

Process a new client inquiry. This command walks through qualification, prepares for the discovery call, and produces a structured debrief after the call.

## Usage

```
/intake $ARGUMENTS
```

**Examples:**
- `/intake "Smith & Associates"`
- `/intake "Greenfield Dental, 15 staff, referred by Jane"`

## Process

1. **Capture inquiry** — Record the client name, business type, source, and initial request. If details are missing, ask for them.

2. **Qualify the lead** — Run through the qualification checklist:
   - Business type: Is this professional services, knowledge work, or operations-heavy?
   - Team size: 2-50 staff?
   - Pain clarity: Can they articulate a specific problem?
   - Budget signals: Currently paying for software or manual labor?
   - Decision maker: Is the contact a buyer or influencer?

3. **Prepare for discovery** — If the lead qualifies, generate:
   - Pre-call research checklist (what to look up about the business)
   - Industry-specific discovery questions
   - Five Elements mapping prompts for the call

4. **Post-call debrief** — After the discovery call, produce:
   - Structured debrief with pain points, element mapping, and fit assessment
   - Recommended next step (scope, decline, or follow up later)

5. **Pipeline update** — Suggest updates to the project tracking system

## Output

```
CLIENT INQUIRY: [Name]

Qualification:
  Business type:    [Type] — PASS/FAIL
  Team size:        [Size] — PASS/FAIL
  Pain clarity:     [Assessment] — PASS/FAIL
  Budget signals:   [Assessment] — PASS/FAIL
  Decision maker:   [Assessment] — PASS/FAIL

Result: QUALIFIED / NOT QUALIFIED

[If qualified:]
Discovery Call Prep:
  Research: [What to look up]
  Key questions: [Industry-specific questions]
  Elements to probe: [Which Five Elements to explore]
```

## Tips

- Include the industry vertical for better discovery questions: `/intake "Acme Corp, landscaping, 8 staff"`
- Run this again after the discovery call with notes to generate the debrief
- The qualification step saves time by filtering out poor-fit leads early
