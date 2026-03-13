# Getting Started

A step-by-step guide to installing AIOS Factory and generating your first workspace.

---

## Prerequisites

- [Claude Code](https://claude.ai/code) installed and configured
- A Claude Code API key or subscription
- A terminal or command line

---

## Step 1: Get the Factory

Clone the repository:

```bash
git clone https://github.com/afrexai-cto/aios-factory.git
cd aios-factory
```

## Step 2: Install as a Plugin

Add AIOS Factory as a Claude Code plugin:

```bash
# Option A: Install from the directory
claude plugin add /path/to/aios-factory

# Option B: Copy to your plugins directory
cp -r aios-factory ~/.claude/plugins/aios-factory
```

Verify the plugin is available by checking your Claude Code plugin list.

## Step 3: Try the Example

Before generating your own workspace, try the included AI Agency example to see what a finished workspace looks like:

```bash
# Copy the example to a working directory
cp -r aios-factory/examples/ai-agency ~/my-test-workspace
cd ~/my-test-workspace
```

Open this directory in Claude Code and run:

```
/prime
```

Claude should read the context files and confirm it understands the agency workspace. Try running the other commands:

```
/intake "Test Corp, accounting firm, 10 staff"
/status
/scope "Test Corp AIOS"
```

## Step 4: Generate Your First Workspace

Now generate a workspace for your own vertical:

```
/aios-factory:create-vertical "Your Industry Here"
```

Be specific for better results:

```
/aios-factory:create-vertical "UK Dental Practices, 5-20 staff"
/aios-factory:create-vertical "US Property Management Companies"
/aios-factory:create-vertical "Australian Accounting Firms, sole practitioners"
```

The factory will:
1. Research the industry (terminology, workflows, pain points)
2. Map the 10 universal terms to domain-specific language
3. Scaffold a complete workspace with skills, commands, and context
4. Validate the output for quality

## Step 5: Review and Customize

The generated workspace is a strong starting point, but you should review it:

1. Open the generated workspace directory
2. Read `CLAUDE.md` — does it accurately describe the vertical?
3. Check each skill — is the domain knowledge correct?
4. Review the terminology — are these the terms practitioners actually use?
5. Update anything that does not match your knowledge of the industry

## Step 6: Validate

Run the validator to check for common issues:

```
/aios-factory:validate path/to/generated/workspace
```

Fix any issues reported before deploying the workspace.

## Step 7: Deploy

Follow the clone pipeline to prepare the workspace for a specific business:

1. Fill in `context/business-info.md` with the specific business details
2. Fill in `context/team.md` with real team members
3. Configure `.env` with API keys
4. Set up `.mcp.json` for active integrations
5. Run `/prime` and verify Claude understands the business
6. Hand off to the business owner

---

## What Next?

- Read [How It Works](HOW_IT_WORKS.md) to understand the architecture
- Read [Creating Verticals](CREATING_VERTICALS.md) for a deep dive into custom verticals
- Check [Examples](EXAMPLES.md) for inspiration on what verticals look like
- Explore the `core/` directory for the underlying frameworks

---

## Troubleshooting

### "Plugin not found" when running commands

Make sure the plugin is installed correctly. Check your Claude Code plugin list and verify the `aios-factory` directory contains a `.claude-plugin/plugin.json` file.

### Generated workspace has generic terms

The terminology mapping may not have been deep enough. Review `niche-config.yaml` and update any terms that do not match the vertical's professional language. Then regenerate or manually update the workspace files.

### Skills feel too generic

The factory generates skills from publicly available knowledge. For deeper domain expertise, customize the skills manually or check [AfrexAI](https://afrexai.com) for premium vertical plugins with validated industry knowledge.

### Commands produce errors

Check that `CLAUDE.md` and all context files are properly formatted Markdown. Verify that skills are in the correct directory structure (`skills/{name}/SKILL.md`).
