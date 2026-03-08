---
description: Validate an AIOS workspace for quality and completeness
argument-hint: "<path to workspace directory>"
---

# /aios-factory:validate

Check a generated AIOS workspace for completeness, consistency, and usability. Run this after generating a workspace to catch issues before deployment.

## Usage

```
/aios-factory:validate $ARGUMENTS
```

**Examples:**
- `/aios-factory:validate generated/dental-practices`
- `/aios-factory:validate examples/ai-agency`

## Process

### Step 1: Structure Check

Verify the workspace has the required directory structure:

- [ ] `CLAUDE.md` exists and is non-empty
- [ ] `context/` directory exists with at least `business-info.md`
- [ ] `skills/` directory exists with at least 3 skill directories
- [ ] `commands/` directory exists with at least `prime.md`
- [ ] `niche-config.yaml` exists

### Step 2: Content Quality

For each file, check:

- [ ] No placeholder text: no `[brackets]`, `TODO`, `TBD`, `PLACEHOLDER`
- [ ] No universal terminology in user-facing text (case, intake, outcome, provider)
- [ ] File length under 300 lines
- [ ] Proper Markdown formatting (headers, lists, tables)
- [ ] No empty sections

### Step 3: Terminology Completeness

Verify the terminology mapping:

- [ ] All 10 universal terms have domain-specific equivalents
- [ ] Domain terms appear consistently across all files
- [ ] No mixed terminology (using both universal and domain terms)
- [ ] Plural forms provided where applicable

### Step 4: Skill Quality

For each skill file:

- [ ] Has frontmatter with name, description, and version
- [ ] Overview section explains what the skill does
- [ ] Contains actionable, domain-specific content (not generic advice)
- [ ] Includes examples or output templates
- [ ] References section lists any reference files

### Step 5: Command Quality

For each command file:

- [ ] Has frontmatter with description and argument hint
- [ ] Process section has clear, numbered steps
- [ ] Output section describes what the command produces
- [ ] Tips section provides useful guidance

### Step 6: Integration Check

- [ ] `.env.example` documents all required environment variables
- [ ] `.mcp.json` only lists integrations relevant to the vertical
- [ ] No credentials or API keys are hardcoded in any file

### Step 7: Usability Test

Simulate running `/prime`:
- [ ] Read `CLAUDE.md` and `context/` files
- [ ] Verify Claude would understand the business and its workflows
- [ ] Verify Claude would know which commands are available
- [ ] Verify Claude would use domain-specific terminology

## Output

```
VALIDATION REPORT: [workspace name]

Structure:    PASS / FAIL (details)
Content:      PASS / FAIL (details)
Terminology:  PASS / FAIL (X/10 terms mapped)
Skills:       PASS / FAIL (X/Y complete)
Commands:     PASS / FAIL (X/Y complete)
Integrations: PASS / FAIL (details)
Usability:    PASS / FAIL (details)

Overall: PASS / FAIL

Issues found:
  1. [issue description and location]
  2. [issue description and location]

Recommendations:
  1. [suggested improvement]
  2. [suggested improvement]
```

## Tips

- Run validation immediately after generating a workspace
- Fix all FAIL items before deploying to a client
- Pay special attention to terminology consistency — it is the most common issue
- The usability test is the most important check: if `/prime` would not work, the workspace is not ready
