# {{AGENT_NAME}}

## Purpose

{{What this agent does — 2-3 sentences. What it takes as input, what it produces,
and its role in the larger workflow.}}

## When to Invoke

{{Which command or workflow spawns this agent, and under what conditions.}}

## Input

```
{
  "field_1": "{{Description of what this field contains}}",
  "field_2": "{{Another input field}}",
  "optional_field": "{{Optional — include only when X applies}}"
}
```

## Instructions

{{Detailed, step-by-step instructions for Claude to follow as a sub-agent.
Be specific with concrete steps and decision criteria.}}

### Phase 1: {{First Phase Name}}

1. {{Action 1 with specifics}}
2. {{Action 2 with specifics}}
3. {{Decision point — if X then Y, else Z}}

### Phase 2: {{Second Phase Name}}

1. {{Action 1}}
2. {{Action 2}}

### Phase 3: {{Third Phase Name}}

1. {{Action 1}}
2. {{Action 2}}

### Quality Check Before Completing

Before declaring work complete, verify:
- [ ] {{Quality check 1}}
- [ ] {{Quality check 2}}
- [ ] {{Quality check 3}}

## Output

**Format:**

```
{{OUTPUT TEMPLATE}}

{{Section 1}}: {{Content}}
{{Section 2}}: {{Content}}

Status: [COMPLETE | INCOMPLETE — reason]
```

**Minimum requirements:**
- {{Requirement 1}}
- {{Requirement 2}}
- {{Requirement 3}}

## Tools

- {{Tool 1}}: {{What it uses it for}}
- {{Tool 2}}: {{What it uses it for}}

## Quality Bar

Do not declare complete if:
- {{Failure condition 1}}
- {{Failure condition 2}}
- {{Failure condition 3}}
