# 06. Platform Adapters

## General principle

This skill should run on any capable agent platform.

Do not assume every platform supports true subagents. Always label the run mode:

- `true_multi_agent`: platform supports independent subagents or forked contexts.
- `simulated_isolated_turns`: platform does not support true subagents; isolation is simulated through strict sequential prompts.

## Codex

Recommended installation:

```text
.agents/skills/six-wise-minds/
```

If custom subagents are supported, use the role definitions in:

```text
platform/codex/agents/
```

These files are adapter templates. Verify the active Codex environment supports the same custom-agent schema before treating them as automatically loadable.

Recommended execution:

1. Chair builds decision brief.
2. Spawn five non-blue hats in parallel if possible.
3. Run Blue Secretary after hat outputs.
4. Allow one local repair if needed.
5. Chair synthesizes.

## Claude Code

Recommended installation:

```text
.claude/skills/six-wise-minds/
```

If custom subagents are supported, use definitions in:

```text
platform/claude-code/agents/
```

These files are adapter templates. Verify the active Claude Code environment supports the same subagent frontmatter before treating them as automatically loadable.

When supported, use forked or subagent context to prevent context pollution.

## OpenClaw

If true subagents are available, follow the standard workflow.

If not, run simulated isolated turns:

1. The Chair writes a decision brief.
2. The agent processes each hat one by one.
3. Each hat must ignore previous hats except where explicitly allowed.
4. Output must label this as `simulated_isolated_turns`.

## Generic agents

If a platform only supports plain prompt execution:

- read `SKILL.md`;
- read the relevant role cards;
- use `assets/council-report-template.md`;
- do not claim true multi-agent isolation;
- include trace summary in the final report.

## File system

If the platform supports writing files, create a local run folder:

```text
runs/{run_id}/
```

This is a protocol requirement, not an automatic V1.0 script. The agent should create or maintain the folder during a run when file writing is available.

If file writing is unavailable or unnecessary for a quick run, include all trace and evaluation summary in the final answer.
