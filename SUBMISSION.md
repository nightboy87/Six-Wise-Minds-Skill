# Submission Notes

This document is for maintainers or registry reviewers considering Six Wise Minds Skill for a skill store, catalog, hub, or curated list.

## Project

Name:

```text
six-wise-minds
```

Display name:

```text
Six Wise Minds
```

Repository:

```text
https://github.com/nightboy87/Six-Wise-Minds-Skill
```

License:

```text
MIT
```

Version:

```text
1.0.0
```

## What it does

Six Wise Minds Skill helps an agent turn fuzzy decisions into structured advisory reports.

It uses:

- a Chair for intake, real-question diagnosis, risk gate, and final synthesis;
- White, Red, Black, Yellow, and Green Hat roles for facts, emotional signals, risks, value, and alternatives;
- a Blue Secretary for process audit, role-boundary checks, and one-time repair decisions;
- trace summaries and claim IDs for observability and traceability;
- eval assets for trigger behavior, role boundaries, high-risk handling, and output quality.

## Why it is useful

Typical agent answers to decision questions can blend facts, intuition, risk, optimism, and advice in one untraceable response. This skill separates those functions and makes the final recommendation inspectable.

It is useful for:

- product and project decisions;
- writing-topic decisions;
- enterprise demand review;
- personal choice clarification;
- lightweight daily decisions.

## What it is not

This skill is not:

- a standalone app;
- a UI;
- an automation script package;
- a medical, legal, financial, or psychological advisor;
- a celebrity role-play prompt;
- a long-term memory system.

The named figures are cognitive anchors only. The skill must not imitate their voice or biography.

## Safety model

The skill has a five-level risk gate:

- L0: low-risk daily decision;
- L1: normal decision;
- L2: high personal, project, or organizational impact;
- L3: professional high-risk domain;
- L4: unsafe or disallowed.

For L3 cases, the skill should clarify the question and recommend qualified professional input.

For L4 cases, the skill should refuse unsafe decision framing and redirect to safety support.

The skill also limits each deliberation to at most one local repair pass.

## Execution and dependency profile

This is an instruction-only skill package:

- no required scripts;
- no API keys;
- no MCP servers;
- no browser automation;
- no external network calls;
- no UI;
- no long-term memory.

Normal operation requires only reading the skill files and producing an answer.

## Validation completed

Before submission, the current release was checked with:

- Codex skill validation via `quick_validate.py`;
- JSON and JSONL parsing;
- TOML parsing for adapter templates;
- YAML parsing for `agents/openai.yaml`;
- role-card example validation against `schemas/hat-output.schema.json`;
- one product-decision manual test;
- one L4 psychological-crisis gate manual test.

## Platform notes

### Codex

The repository includes `.codex-plugin/plugin.json` and `agents/openai.yaml`.

The plugin manifest points to:

```text
skills/
```

The `skills/six-wise-minds/` directory is a Codex plugin distribution copy of the root skill package. The root-level files remain the source package used for direct GitHub, OpenClaw, Hermes, and generic-agent installation.

When changing the core skill, keep the root package and the Codex distribution copy in sync.

### OpenClaw

See:

```text
platform/openclaw.md
platform/openclaw-publish.md
```

### Hermes Agent

See:

```text
platform/hermes.md
```

## Reviewer checklist

- Confirm `SKILL.md` metadata is accepted.
- Confirm the registry category and tags.
- Confirm no executable scripts or hidden runtime dependencies are required.
- Run one normal decision example from `examples/`.
- Run one high-risk case from `evals/high-risk-cases.jsonl`.
- Check that outputs include trace summary and do not impersonate historical figures.
