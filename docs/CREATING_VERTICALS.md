# Creating Verticals

A step-by-step guide to creating your own AIOS workspace for a specific business vertical.

---

## When to Create a Vertical

Create a new vertical when:
- You have a client in an industry not covered by existing examples
- You see an opportunity in a specific market
- You want to productize your agency's knowledge of an industry

---

## Two Paths

### Path A: Automated (Recommended)

Use the factory command and let the pipeline do the work:

```
/aios-factory:create-vertical "Your Vertical Name"
```

This is faster, more consistent, and produces a validated workspace. After generation, review and customize as needed.

### Path B: Manual

Build the workspace yourself, step by step. This takes longer but gives you full control. The rest of this guide covers the manual path.

---

## Step 1: Evaluate the Vertical

Before building, assess whether the vertical is viable using the niche discovery framework.

Answer these questions:

1. **Market size**: Are there enough businesses in this vertical?
2. **Pain severity**: Is the problem painful enough that they will pay?
3. **Regulatory environment**: Does regulation create ongoing demand?
4. **Technology adoption**: Are they comfortable with software?
5. **Workflow complexity**: Is there enough to automate?
6. **Community density**: Will satisfied users refer others?
7. **Automation potential**: Can AI meaningfully improve the work?

If most answers are positive, proceed. If pain severity and automation potential are both low, reconsider.

---

## Step 2: Research the Vertical

Spend time understanding the industry. Sources:

- **Industry forums and communities**: What do practitioners complain about?
- **Trade publications**: What trends and challenges are discussed?
- **Existing software**: What tools already serve this vertical? What do reviews say?
- **Professional associations**: What standards, events, and resources exist?
- **Direct conversations**: If possible, talk to someone in the industry

### What to Document

1. **Industry overview**: What do businesses in this vertical do every day?
2. **Common workflows**: The 3-5 most important operational processes
3. **Pain points**: Where time is wasted, mistakes happen, or money is lost
4. **Technology landscape**: What software they already use
5. **Compliance requirements**: What regulations apply (if any)

---

## Step 3: Map Terminology

The most important step. Map all 10 universal terms:

| Universal Term | Your Vertical's Term |
|----------------|---------------------|
| Case | |
| Client | |
| Document | |
| Workflow | |
| Intake | |
| Outcome | |
| Provider | |
| Status | |
| Report | |
| Invoice | |

### How to Find the Right Terms

Ask practitioners: "What do you call _____?"

| Universal Term | Question to Ask |
|----------------|-----------------|
| Case | "What do you call a unit of work?" |
| Client | "What do you call the people you serve?" |
| Document | "What files or records do you work with?" |
| Workflow | "What do you call the process you follow?" |
| Intake | "How does new work arrive?" |
| Outcome | "What does your client get at the end?" |
| Provider | "What do you call the person doing the work?" |
| Status | "How do you describe where something is in the process?" |
| Report | "What formal documents do you produce?" |
| Invoice | "How do you bill for your work?" |

---

## Step 4: Map the Five Elements

For each element, describe how this vertical handles it:

### E1: Intake
- How does new work currently arrive?
- What information is captured?
- What validation is needed?
- What would the ideal intake look like?

### E2: Processing
- What does the professional actually do with the work?
- What decisions do they make?
- Which decisions follow clear rules (automatable)?
- Which require genuine expertise (AI-assisted)?

### E3: Output
- What does the client receive at the end?
- In what format?
- What quality standards apply?
- How often are outputs generated?

### E4: Tracking
- How is work status tracked today?
- What statuses are needed?
- Who needs visibility?
- Are there deadlines or SLAs?

### E5: Deployment
- Who will use the workspace?
- On what devices?
- Is team access needed?
- What is the technical comfort level?

---

## Step 5: Build the Niche Config

Create `niche-config.yaml` with all the information gathered:

```yaml
niche:
  name: "Your Vertical Name"
  slug: "your-vertical-slug"
  description: "One-line description"
  geography: "Target geography"
  business_size: "Typical size range"

terminology:
  case: "domain term"
  client: "domain term"
  # ... all 10 terms

workflows:
  - name: "Workflow Name"
    trigger: "What starts it"
    steps: [list of steps]
    output: "What it produces"
    ai_opportunity: "How AI helps"
  # ... 3-5 workflows

pain_points:
  - name: "Pain Point Name"
    description: "Description"
    frequency: "daily/weekly/per-client"
    current_solution: "What they do now"
    ai_solution: "How AI solves it"
  # ... 2-3 pain points

five_elements:
  intake: "Description"
  processing: "Description"
  output: "Description"
  tracking: "Description"
  deployment: "Description"

integrations:
  - name: "Tool Name"
    purpose: "Why it's needed"
    mcp_available: true/false
```

---

## Step 6: Scaffold the Workspace

Create the directory structure:

```
your-vertical/
├── CLAUDE.md
├── .env.example
├── .mcp.json
├── context/
│   ├── business-info.md
│   ├── team.md
│   └── task-audit.md
├── skills/
│   ├── skill-1/SKILL.md
│   ├── skill-2/SKILL.md
│   └── skill-3/SKILL.md
├── commands/
│   ├── prime.md
│   ├── intake.md
│   ├── status.md
│   └── scope.md
└── niche-config.yaml
```

Or use the factory to scaffold from your config:

```
/aios-factory:create-workspace niche-config.yaml
```

---

## Step 7: Write the Content

For each file, use the vertical's terminology and domain knowledge:

**CLAUDE.md**: Describe the workspace in the vertical's language. List commands and skills. Explain the session workflow.

**Skills**: Each skill should describe a real process that a practitioner would recognize. Include step-by-step instructions, examples, and output formats.

**Commands**: Each command should have a clear process, expected input, and structured output.

**Context templates**: Use domain-appropriate questions and examples. Pre-populate the task audit with common tasks for the vertical.

---

## Step 8: Validate

Run the validator:

```
/aios-factory:validate your-vertical/
```

Check for:
- Missing files or empty sections
- Universal terms in user-facing text
- Placeholder text that was not replaced
- Skills with generic content instead of domain-specific processes

---

## Step 9: Test

The ultimate test: copy the workspace, open it in Claude Code, and run `/prime`. Does Claude understand the business? Do the commands work? Does it speak the right language?

---

## Tips for Better Verticals

1. **Be specific**: "US Personal Injury Law Firms" produces better output than "Law Firms"
2. **Use real language**: Find out what practitioners actually say, not what you think they say
3. **Focus on pain**: The most valuable skills address real, recurring problems
4. **Start with 3 skills**: You can always add more. Quality beats quantity.
5. **Test with a real person**: If possible, have someone from the industry review the workspace
