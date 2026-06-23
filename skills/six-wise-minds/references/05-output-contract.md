# 05. Output Contract

## Default report structure

Use this structure unless the user explicitly asks for a shorter answer.

```markdown
# 六个聪明人议事报告

## 1. 重新定义后的问题

## 2. 议长的真问题判断

## 3. 本次审议模式与风险等级

## 4. 六个聪明人的独立意见

### ⚪ 白帽：事实与缺失信息
### 🔴 红帽：情绪与直觉
### ⚫ 黑帽：风险与失败路径
### 🟡 黄帽：价值与机会
### 🟢 绿帽：替代方案与实验
### 🔵 蓝帽秘书长：流程质检

## 5. 关键冲突点

## 6. 议长顾问式判断

## 7. 下一步最小行动

## 8. 不确定性与边界

## 9. Trace 摘要
```

## Claim format

Each role should produce compact claims.

```json
{
  "claim_id": "black:R1",
  "claim_type": "risk",
  "content": "六个角色如果都输出长文，会导致用户被观点淹没。",
  "based_on": ["decision_brief:council_question"],
  "confidence": "high",
  "actionability": "high"
}
```

## Final recommendation format

```json
{
  "recommendation_id": "rec_001",
  "recommendation": "先做文档协议型 V1.0，而不是开发独立应用。",
  "supporting_claims": ["black:R1", "green:A1", "blue:Q1"],
  "counter_claims": ["yellow:V1"],
  "uncertainty": "不同平台对子智能体的支持不完全一致。",
  "next_action": "先生成完整 Skill 包，并用 5 个典型议题手工评测。"
}
```

## Length control

Default maximum:

- each non-blue hat: 3-5 claims;
- Blue Secretary: 3-5 audit notes;
- final report: concise but complete;
- no role may produce an essay unless user asks for deep mode.

## Required user notice when repair is used

If repair is triggered, include:

> 本次已使用一次局部返修。根据六个聪明人 Skill 的防循环规则，本轮不会自动开启第三次审议。如需重新审议，请补充新事实或提出新的审议问题。
