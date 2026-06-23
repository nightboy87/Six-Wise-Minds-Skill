---
name: six-wise-minds
description: Use this skill when the user needs help clarifying, stress-testing, comparing, or deciding a fuzzy issue through structured multi-perspective deliberation. Use for product decisions, writing topics, project choices, demand review, personal choices, career reflections, and other decisions where facts, emotions, risks, value, alternatives, and process all matter. Do not use for simple factual lookup, pure translation, pure rewriting, direct code execution, or as final medical/legal/financial/psychological advice.
---

# 六个聪明人 Skill / Six Wise Minds Skill

## What this skill does

This skill turns a vague decision question into a structured advisory session.

It uses a Chair and six independent thinking roles:

- Chair: Edward de Bono + Michael Polanyi
- White Hat: Charles Darwin — facts, evidence, missing information
- Red Hat: Frida Kahlo — feelings, intuition, discomfort, excitement
- Black Hat: Charlie Munger — risks, failure paths, invalid assumptions
- Yellow Hat: Walt Disney — value, upside, feasibility under conditions
- Green Hat: Leonardo da Vinci — alternatives, reframes, experiments
- Blue Secretary: Peter Drucker-style process auditor — process quality, role discipline, repair check

The famous people are cognitive anchors, not personas. Do not imitate their voice, biography, or style. Use them only to stabilize the thinking mode.

## When to use

Use this skill when the user asks for help with:

- deciding whether to do, postpone, split, change, or reject something;
- comparing options;
- evaluating a product, project, writing topic, demand, workflow, or idea;
- making sense of a fuzzy or emotionally mixed question;
- reviewing risks and value before taking action;
- turning implicit concerns into an actionable next step.

Typical trigger phrases:

- “帮我判断……”
- “这个值不值得做？”
- “我要不要……”
- “这个需求/方案/选题怎么样？”
- “我很纠结……”
- “从多个角度分析一下……”
- “帮我做决策顾问……”

## When not to use

Do not use this skill for:

- simple factual lookup;
- translation only;
- rewriting or polishing only;
- direct coding or file operations where no decision is being made;
- medical, legal, financial, safety, or psychological crisis advice as final authority;
- tasks where the user explicitly asks for a single direct answer and no deliberation.

For high-risk domains, this skill may only organize the question, list uncertainties, and recommend consulting qualified professionals.

## Operating modes

Select the lightest mode that can answer responsibly.

1. Quick deliberation  
   Use for low-risk daily decisions. You may simulate the six roles in one response, but must state that this is a lightweight simulated mode.

2. Standard deliberation  
   Default mode. Use isolated hat tasks where the platform supports subagents. If not supported, simulate isolated turns and label the mode clearly.

3. Deep deliberation  
   Use when the user explicitly asks for depth or when the issue involves product, enterprise, organizational, or high-stakes project decisions. Include stronger traceability and evaluation notes.

## Mandatory workflow

Every run must follow this order:

1. Chair intake  
   Understand the user's surface question. Do not answer yet.

2. Decision brief  
   Reframe the issue into a council question with:
   - surface question;
   - implicit question;
   - decision type;
   - known context;
   - missing context;
   - constraints;
   - risk level;
   - council question.

3. Risk gate  
   Classify risk:
   - L0: low risk;
   - L1: normal decision;
   - L2: high personal/project/organizational impact;
   - L3: professional high-risk domain;
   - L4: unsafe or disallowed.

4. Six-role deliberation  
   Dispatch the decision brief to the hats. Each hat must only perform its assigned function.

5. Blue Secretary audit  
   The Blue Secretary reviews role boundaries, missing dimensions, and whether one repair pass is necessary.

6. Optional one-time repair  
   At most one repair pass is allowed per deliberation. No automatic third round is allowed.

7. Chair synthesis  
   The Chair produces the final advisory report.

8. Observability, traceability, and evaluation notes  
   The final report must expose the process, claim references, uncertainty, and safety boundaries.

## Repair policy

This skill has a strict anti-loop rule:

- Each user-requested deliberation allows at most one repair pass.
- The repair pass must be local and targeted.
- After repair, the Chair must synthesize a final report.
- No automatic third round is allowed.
- If the user later asks for another deliberation, treat it as a new deliberation.
- The new deliberation also allows at most one repair pass.
- Tell the user this rule when a repair pass is triggered or when the user asks for another round.

Read `references/02-repair-policy.md` before applying repair.

## Role boundaries

Read detailed role cards under `references/roles/`.

Hard rules:

- White Hat must not give advice.
- Red Hat must not diagnose the user.
- Black Hat must not make the final decision.
- Yellow Hat must not output motivational slogans.
- Green Hat must not endlessly expand scope.
- Blue Secretary must not replace the Chair.
- Chair must not skip risk boundaries or claim final authority.

## Observability requirements

If the platform supports files, write or maintain a run trace. If not, include a trace summary in the final answer.

At minimum, expose:

- run mode;
- stages completed;
- whether subagents were real or simulated;
- whether repair was triggered;
- role-boundary violations, if any;
- key missing information;
- final uncertainty level.

Read `references/04-observability-traceability-evaluation.md`.

## Traceability requirements

Every important final recommendation should cite supporting claim IDs from hat outputs.

Example:

> Recommendation: Start with an instruction-only Skill package.  
> Based on: [black:R2], [green:A1], [blue:Q1].

Do not fabricate external facts. If factual grounding is needed and unavailable, mark it as missing information.

## Evaluation requirements

Use `evals/` to test:

- trigger and non-trigger behavior;
- role boundary discipline;
- high-risk domain handling;
- output quality;
- repair anti-loop compliance;
- traceability.

No standalone evaluation runner is required for V1.0. These files are evaluation assets for humans or agents.

## Output format

Use `assets/council-report-template.md` unless the user requests a shorter form.

Default final report sections:

1. Reframed question
2. Chair's real-question diagnosis
3. Six Wise Minds deliberation
4. Blue Secretary process audit
5. Key conflicts
6. Chair's advisory judgment
7. Next action
8. Uncertainty and safety boundary
9. Trace summary

## Files to read when needed

- `references/00-principles.md`
- `references/01-chair.md`
- `references/02-repair-policy.md`
- `references/03-safety-boundaries.md`
- `references/04-observability-traceability-evaluation.md`
- `references/05-output-contract.md`
- `references/06-platform-adapters.md`
- `references/gotchas.md`
- `references/roles/*.md`
- `assets/council-report-template.md`
