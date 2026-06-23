# Claude Code Adapter

## Recommended install

Place this folder under:

```text
.claude/skills/six-wise-minds/
```

## Optional custom subagents

Claude Code adapter templates are provided in:

```text
platform/claude-code/agents/
```

Verify the active Claude Code environment supports this subagent frontmatter before treating these files as automatically loadable.

## Isolation

When the platform supports forked or subagent context, use it to prevent context pollution.

Each hat should receive:

- the decision brief;
- its role card;
- output contract;
- safety constraints.

It should not receive other hats' outputs.

## Repair

Only Blue Secretary may recommend repair. The Chair decides and applies at most one local repair pass.
