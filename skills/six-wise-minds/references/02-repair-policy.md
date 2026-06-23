# 02. Repair Policy

## Purpose

The repair mechanism prevents weak council outputs from going directly into final synthesis. It must not become an infinite loop.

## Hard limit

Each user-requested deliberation allows:

- one main deliberation;
- at most one local repair pass;
- then final synthesis.

No automatic third round is allowed.

If the user later asks for another deliberation, treat it as a new deliberation. The new deliberation also allows at most one repair pass.

## User-facing notice

When repair is triggered, tell the user:

> 为避免反复审议导致决策拖延，本 Skill 每轮审议最多允许一次局部返修。返修完成后会直接进入最终汇总。如需之后再审议，请补充新的事实或明确新的审议问题。

## When repair is allowed

The Blue Secretary may trigger one repair pass only if at least one of these is true:

1. A hat clearly did not perform its assigned function.
2. A hat seriously crossed role boundaries.
3. The council question is unclear or inconsistent.
4. A key decision dimension is missing.
5. High-risk boundaries were ignored.
6. The final synthesis would be unsupported without correction.
7. The run mode was mislabeled.

## When repair is not allowed

Do not repair just because:

- the answer could be prettier;
- one hat could say more;
- the issue is naturally uncertain;
- the Chair wants more confidence;
- the user may prefer a stronger conclusion;
- the output is already good enough for a bounded advisory report.

## Repair scope

Repair must be local.

Examples:

- rerun only Black Hat if risk analysis was missing;
- ask Blue Secretary to re-audit if it overstepped;
- ask Chair to revise the decision brief if the council question was unclear.

Do not rerun the entire council unless the council question itself was invalid.

## After repair

After repair:

1. Blue Secretary briefly confirms whether the repaired output is acceptable.
2. Chair synthesizes final report.
3. No more repair is allowed in the same deliberation.
