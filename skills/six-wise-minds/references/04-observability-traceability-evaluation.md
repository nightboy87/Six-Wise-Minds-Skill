# 04. Observability, Traceability, Evaluation

## Goal

This skill must be observable, traceable, and evaluable.

This does not require a standalone application, UI, or monitoring service. It is implemented through output protocol, claim IDs, trace summaries, and evaluation assets.

## Observability

Every final report should include a trace summary.

Minimum trace fields:

```json
{
  "run_mode": "quick|standard|deep",
  "agent_mode": "true_multi_agent|simulated_isolated_turns",
  "stages_completed": [
    "chair_intake",
    "decision_brief",
    "risk_gate",
    "hat_deliberation",
    "blue_secretary_audit",
    "optional_repair",
    "chair_synthesis"
  ],
  "repair_triggered": false,
  "repair_count": 0,
  "risk_level": "L0|L1|L2|L3|L4",
  "boundary_violations": [],
  "missing_information_count": 0,
  "trace_complete": true
}
```

If the platform supports files, the agent may write trace logs. If not, include the summary in the final report.

## Traceability

Each important claim should have a claim ID.

Recommended claim ID format:

- White Hat: `white:F1`, `white:F2`
- Red Hat: `red:E1`, `red:E2`
- Black Hat: `black:R1`, `black:R2`
- Yellow Hat: `yellow:V1`, `yellow:V2`
- Green Hat: `green:A1`, `green:A2`
- Blue Secretary: `blue:Q1`, `blue:Q2`
- Chair: `chair:S1`, `chair:J1`

Every final recommendation should list supporting and counter claims.

Example:

```text
Recommendation: Start with a document-only V1.0 skill package.
Supporting claims: [black:R1], [green:A2], [blue:Q1]
Counter claims: [yellow:V2]
Uncertainty: platform-specific subagent support may vary.
```

## Evaluation

Evaluation assets live in `evals/`.

Evaluate:

1. Trigger correctness.
2. Non-trigger correctness.
3. Role boundary discipline.
4. High-risk handling.
5. Repair limit compliance.
6. Output traceability.
7. Actionability.
8. Overall user value.

## Output-quality rubric

Use the rubric in `evals/output-quality-rubric.md`.

Minimum acceptable output:

- reframes the real decision question;
- separates six roles;
- includes Blue Secretary audit;
- includes at most one repair;
- includes next action;
- includes uncertainty;
- includes safety boundary when needed;
- includes trace summary.

## Anti-hallucination rule

If factual verification is required but not available, mark it as missing information. Do not invent sources, data, policies, product specs, legal rules, or medical facts.
