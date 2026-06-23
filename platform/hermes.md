# Hermes Agent Adapter

## Status

Six Wise Minds Skill is a document-based skill package that follows the same general progressive-disclosure shape used by Hermes Agent skills:

- one skill directory;
- a required `SKILL.md`;
- optional references, assets, schemas, examples, and eval assets;
- no required scripts, UI, external services, or long-term memory.

Hermes Agent documentation says user skills live under:

```text
~/.hermes/skills/
```

## Recommended install

Clone or copy this repository into:

```text
~/.hermes/skills/six-wise-minds/
```

Then start a new Hermes session so the skill list is refreshed.

## Suggested category

For Hermes hub, bundled, or optional catalog review, classify this skill under one of:

- `decision-support`
- `knowledge-work`
- `productivity`
- `autonomous-ai-agents`

Preferred category: `decision-support`.

## Runtime behavior

When true subagent isolation is available, Hermes may run the non-blue hats in separate contexts. If not, use `simulated_isolated_turns` and disclose that mode in the final report.

Minimum files Hermes should load for a standard run:

```text
SKILL.md
references/01-chair.md
references/02-repair-policy.md
references/03-safety-boundaries.md
references/04-observability-traceability-evaluation.md
references/05-output-contract.md
references/roles/*.md
assets/council-report-template.md
```

## Safety notes

This skill is instruction-only and does not require shell commands, secrets, remote services, browser automation, or local file modification during normal use.

High-risk topics must follow `references/03-safety-boundaries.md`.

For L3 and L4 cases, Hermes should not run ordinary decision deliberation as if the harmful or professional-risk action were a normal choice.

## Submission notes

Before submitting to Hermes hub, optional catalog, or upstream bundled catalog:

1. Verify `SKILL.md` metadata is accepted by Hermes.
2. Confirm whether Hermes expects additional catalog metadata outside `SKILL.md`.
3. Confirm whether the skill should remain a standalone repository or be copied under a Hermes category path.
4. Run the examples under `examples/` and high-risk cases under `evals/high-risk-cases.jsonl`.
5. Keep adapter claims conservative unless true subagent isolation has been tested in Hermes.
