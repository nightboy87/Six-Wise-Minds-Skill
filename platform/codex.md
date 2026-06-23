# Codex Adapter

## Recommended install

Place this folder under:

```text
.agents/skills/six-wise-minds/
```

## Optional custom agents

Codex adapter templates are provided in:

```text
platform/codex/agents/
```

Verify the active Codex environment supports this custom-agent TOML schema before treating these files as automatically loadable.

If the environment supports subagents, the main agent should:

1. Run Chair intake and create a decision brief.
2. Dispatch White, Red, Black, Yellow, and Green hats independently.
3. Run Blue Secretary after hat outputs.
4. Apply at most one local repair if needed.
5. Synthesize final report.

## If subagents are unavailable

Use `simulated_isolated_turns`.

The final report must state:

```text
智能体模式：simulated_isolated_turns
说明：当前环境未确认支持真正多智能体隔离，本次使用顺序隔离提示模拟。
```
