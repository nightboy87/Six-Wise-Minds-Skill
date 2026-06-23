# OpenClaw Adapter

OpenClaw environments may vary in how they support tools, skills, and subagents.

## Standard behavior

If true subagents are available, follow the standard council workflow.

## Fallback behavior

If true subagents are unavailable:

1. Use `simulated_isolated_turns`.
2. Process each role sequentially.
3. Insert a hard separator before each role.
4. Tell each role to ignore earlier roles unless explicitly allowed.
5. Label the final report as simulated, not true multi-agent isolation.

## Required disclosure

The final report must disclose:

- whether true subagents were used;
- whether repair was triggered;
- whether role-boundary issues occurred.
