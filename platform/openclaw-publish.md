# OpenClaw / ClawHub Publish Checklist

## Status

Six Wise Minds Skill is compatible with the basic OpenClaw skill shape:

- one skill directory;
- a required `SKILL.md` with YAML frontmatter and Markdown body;
- optional references, assets, schemas, examples, and eval assets;
- no required scripts, UI, external service credentials, or long-term memory.

OpenClaw skill loading can discover skills from workspace, project, personal, managed, bundled, and extra skill directories. This package should work as a workspace, project, or personal skill after placement in a configured skill root.

## Suggested ClawHub metadata

Name:

```text
six-wise-minds
```

Display name:

```text
Six Wise Minds
```

Short description:

```text
Traceable six-role decision deliberation for fuzzy decisions.
```

Category:

```text
Productivity
```

Alternative categories:

```text
Knowledge Work
Decision Support
AI Agents
```

Tags:

```text
agent-skill
decision-support
multi-agent
six-thinking-hats
traceability
evaluation
product-management
prompt-engineering
```

Repository:

```text
https://github.com/nightboy87/Six-Wise-Minds-Skill
```

License:

```text
MIT
```

## Security profile

This skill is low-risk from an execution standpoint:

- no bundled executable scripts;
- no MCP servers;
- no API keys;
- no browser automation;
- no file mutation required for normal use;
- no external network calls required.

The main safety concern is output policy, not code execution. Reviewers should inspect:

- L3 and L4 risk gate behavior;
- psychological crisis handling;
- medical, legal, and financial boundary handling;
- role-boundary discipline;
- anti-loop repair policy.

## Validation before submission

Run:

```bash
python C:\Users\night\.codex\skills\.system\skill-creator\scripts\quick_validate.py .
```

Also verify:

- all `.json` and `.jsonl` files parse;
- all `.toml` files parse;
- `agents/openai.yaml` parses;
- role-card examples validate against `schemas/hat-output.schema.json`;
- at least one product-decision example and one L4 high-risk example behave correctly.

## OpenClaw runtime notes

If OpenClaw supports true subagents in the target environment, non-blue hats may run in isolated contexts. If not, the agent should use:

```text
simulated_isolated_turns
```

The final report must disclose the agent mode.

Do not claim true multi-agent isolation unless it was actually used.
