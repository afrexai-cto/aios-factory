---
name: niche-discovery
description: >
  Seven-point framework for evaluating whether a business vertical is viable for
  an AIOS workspace. Auto-activates when exploring new markets, evaluating niches,
  assessing automation potential, or deciding which vertical to build for.
version: 1.0.0
triggers:
  - "new niche"
  - "evaluate niche"
  - "should we build for"
  - "is this viable"
  - "market opportunity"
  - "new vertical"
  - "worth building"
  - "niche validation"
references:
  - references/validation-checklist.md
---

# Niche Discovery

## Overview

Not every business vertical is a good candidate for an AIOS workspace. Some have workflows that are too simple to benefit from AI. Others have regulatory environments too complex to navigate without deep expertise. The niche discovery framework helps you evaluate a vertical before investing time in building for it.

The framework uses 7 criteria. Score each one, and the total tells you whether to proceed, investigate further, or walk away.

---

## The 7 Criteria

| # | Criterion | What It Measures |
|---|-----------|-----------------|
| 1 | Market Size | Are there enough potential users? |
| 2 | Pain Point Severity | Is the problem painful enough to pay for? |
| 3 | Regulatory Environment | Does regulation create ongoing need? |
| 4 | Technology Adoption | Are they comfortable with software? |
| 5 | Workflow Complexity | Is there enough complexity to automate? |
| 6 | Community Density | Will satisfied users refer others? |
| 7 | Automation Potential | Can AI meaningfully improve the work? |

---

## Criterion 1: Market Size

**Question**: Are there enough businesses in this vertical to sustain a product?

### How to Evaluate

- Search for industry statistics (trade associations, government data)
- Count registered businesses in the vertical
- Estimate the addressable segment (not all businesses need this)

### Scoring Guide

| Score | Market Size | Example |
|-------|-------------|---------|
| Low | Fewer than 1,000 businesses in target geography | Niche within a niche |
| Medium | 1,000-10,000 businesses | Regional professional services |
| High | 10,000+ businesses | Common business type nationwide |

### What to Watch For

A small market with intense pain can be more valuable than a large market with mild inconvenience. Market size is a factor, not a gatekeeper.

---

## Criterion 2: Pain Point Severity

**Question**: How much does this problem hurt? Will they pay to solve it?

### How to Evaluate

- Talk to people in the industry (or research their complaints online)
- Look for manual processes that consume significant time
- Check for error-prone tasks with consequences

### Pain Level Indicators

**High pain signals:**
- Currently paying someone to do this manually
- Errors cause financial or legal consequences
- Task happens daily or weekly (not annually)
- People have complained about it publicly
- Workarounds exist (spreadsheets, sticky notes, WhatsApp groups)

**Low pain signals:**
- "It only takes a few minutes"
- "We already have something that works okay"
- No one has tried to automate this before
- The task is infrequent

---

## Criterion 3: Regulatory Environment

**Question**: Does regulation create permanent, unavoidable demand?

### How to Evaluate

- Research the primary regulator for the vertical
- Identify mandatory compliance obligations
- Check for periodic reporting or audit requirements

### Why Regulation Matters

Regulated industries cannot stop buying compliance tools. Regulations change, creating ongoing need for updates. Personal liability for compliance failures makes buyers highly motivated.

### Scoring Guide

| Score | Regulation Level | Example |
|-------|-----------------|---------|
| Low | No specific regulation | General retail |
| Medium | Industry best practice, not legally required | ISO certification |
| High | Legal obligations with personal liability | Healthcare, legal, finance |

---

## Criterion 4: Technology Adoption

**Question**: Are businesses in this vertical comfortable adopting new software?

### How to Evaluate

- What software do they currently use?
- Do they have an IT person or use managed IT?
- Are they already using cloud tools (Xero, Slack, etc.)?

### Scoring Guide

| Score | Adoption Level | Characteristics |
|-------|---------------|-----------------|
| Low | Paper-based, resistant to change | Need hand-holding, long onboarding |
| Medium | Some cloud tools, willing to try | Need clear ROI demonstration |
| High | Already use multiple SaaS products | Quick to adopt, self-serve friendly |

### What to Watch For

Low technology adoption does not mean the vertical is bad. It means the workspace needs to be simpler and the onboarding experience needs to be more guided.

---

## Criterion 5: Workflow Complexity

**Question**: Is the work complex enough that automation provides real value?

### How to Evaluate

- Map the main workflows end-to-end
- Count the number of steps, decisions, and handoffs
- Identify where delays, errors, or bottlenecks occur

### Scoring Guide

| Score | Complexity | Example |
|-------|-----------|---------|
| Low | 2-3 steps, straightforward | Simple order fulfillment |
| Medium | 5-10 steps, some decisions | Client onboarding with checks |
| High | 10+ steps, branching logic, approvals | Legal case management, clinical pathways |

### The Sweet Spot

The best verticals have medium-to-high workflow complexity. Too simple and there is nothing to automate. Too complex and the workspace becomes difficult to build and maintain.

---

## Criterion 6: Community Density

**Question**: Will satisfied users tell others in their network?

### How to Evaluate

- Are there active professional associations?
- Do practitioners attend conferences or meetups?
- Are there online communities (LinkedIn groups, forums, WhatsApp)?
- Is sharing tools culturally normal in this industry?

### Scoring Guide

| Score | Community | Characteristics |
|-------|-----------|-----------------|
| Low | Fragmented, competitive | Will not share tools with peers |
| Medium | Trade associations exist | Some networking, guarded sharing |
| High | Tight-knit professional networks | Active referral culture |

### Why This Matters

Word-of-mouth is the most efficient growth channel for niche products. A workspace that solves a real problem in a tight community will spread without marketing spend.

---

## Criterion 7: Automation Potential

**Question**: Can AI meaningfully improve the core work, not just speed it up?

### How to Evaluate

- Identify the most time-consuming tasks
- Assess whether those tasks follow patterns (AI learns patterns)
- Check if the task requires judgment that can be encoded
- Determine if speed or accuracy is the primary bottleneck

### Scoring Guide

| Score | AI Impact | What AI Does |
|-------|----------|-------------|
| Low | Cosmetic improvement | Formats text, minor time savings |
| Medium | Meaningful efficiency gain | Reduces manual effort significantly |
| High | Transformative | Enables something previously impossible or too expensive |

### What Makes Automation High-Value

- The task is repetitive and follows patterns
- Expert judgment can be partially encoded in prompts
- Speed matters (urgent deadlines, high-volume work)
- Errors are costly (compliance, liability)
- The task compounds (AI value increases with each repetition)

---

## Using the Framework

### Step 1: Score Each Criterion

Rate each criterion as Low, Medium, or High based on your research.

### Step 2: Identify Strengths and Weaknesses

Look for criteria that score High (these are your value drivers) and criteria that score Low (these are risks or limitations).

### Step 3: Make the Decision

| Pattern | Recommendation |
|---------|----------------|
| Most criteria High | Strong candidate — proceed with confidence |
| Mixed scores, High pain + High automation | Good candidate — pain drives adoption |
| Most criteria Medium | Viable but not exceptional — consider differentiation |
| Low pain OR Low automation | Weak candidate — reconsider before investing |
| Low market + Low community | Not viable — pivot to a different vertical |

### Step 4: Document the Assessment

Record the scores and reasoning in the niche config. This becomes the foundation for the workspace design.

---

## References

- `references/validation-checklist.md` — Printable checklist for niche evaluation
