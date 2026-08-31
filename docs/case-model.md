# Case Model

## 1. 为什么需要 Case 模型

人际训练的对象不是“某个人”，而是一个**在特定时间和上下文中逐步展开的互动场景**。

因此本仓库以 `Case` 作为最小长期训练对象。

```text
Case
→ Input / Event
→ Analysis Session
→ Response
→ New Input / Outcome
→ Update
→ Retrospective
```

## 2. Case

一个 `Case` 表示一个边界清晰的人际互动问题。

建议字段：

```text
case_id
case_type            # real / simulated / book-derived
context_summary
training_goal
participants_aliases
privacy_status
current_phase
primary_issue
```

`Case` 不保存“某人的人格结论”。

## 3. Input / Event

`Input` 是当时真正出现的信息。

可以是：

- 一句话
- 一段可安全引用的去标识化表达
- 一个行为
- 一个时间变化
- 一个明确外部事件

建议字段：

```text
input_index
observed_at
observed_content
source_type
revealed_at
```

核心要求：只记录可观察内容，不把推断写进 `observed_content`。

## 4. Analysis Session

一次 Session 是在某个信息截面上的分析。

```text
session_id
case_id
revealed_input_range
mode
```

推荐 mode：

```text
Learning
Prediction
ResponsePlanning
Replay
Retrospective
Transfer
```

## 5. Reasoning Snapshot

每次 Session 保存的是**可观察、可复盘的推理结构**，不是完整聊天 transcript，也不是模型私有 chain-of-thought。

建议结构：

```text
observed_facts
immediate_interpretation
emotional_reaction        # 可选，针对学习者自身
hypotheses[]
  - statement
  - supporting_evidence
  - counter_evidence
  - missing_evidence
  - confidence_band
current_problem
interaction_goal
response_options[]
selected_response
selection_reason
risk_if_wrong
next_information_to_watch
```

`confidence_band` 第一版只需要粗粒度：

```text
low
medium
high
```

不要伪造精确概率。

## 6. Response

回应是一个决策，不代表对对方真实意图的确认。

好的回应通常同时考虑：

```text
当前目标
误判成本
关系成本
边界
是否能继续获得信息
是否会无谓升级冲突
```

可以记录：

```text
response_text_or_strategy
expected_effect
main_risk
fallback
```

## 7. Outcome

`Outcome` 是随后真实发生的新信息。

```text
outcome_observation
source
which_hypotheses_supported
which_hypotheses_weakened
new_unknowns
```

Outcome 只能更新过去判断，不能重写过去判断。

## 8. Update

Update 显式描述模型变化：

```text
before
→ new evidence
→ after
```

例如：

```text
之前：
“对方对我个人不满” = medium

新证据：
对方随后说明正在赶紧急项目，并对其他人也保持极短回复

更新：
“时间压力” ↑
“针对我个人” ↓
```

重点是保留变化，而不是只保存最后结论。

## 9. Knowledge Gap / Reasoning Gap

每个 Case 应允许记录：

```text
missing_context
missed_signal
overinterpretation
premature_certainty
ignored_alternative
response_too_aggressive
response_too_passive
boundary_not_expressed
```

这些 gap 比“猜对了没有”更有训练价值。

## 10. Reusable Pattern

Case 中出现的经验默认只是：

```text
candidate pattern
```

只有满足 Pattern Promotion Gate 后，才能进入稳定 Pattern Library。

至少需要：

1. 在多个独立 Case 中重复出现；
2. 能说明适用条件；
3. 能说明反例或失效条件；
4. 不依赖某一个具体人的人格猜测；
5. 不把相关性写成因果；
6. 不把文化/组织/关系语境差异抹平。

Pattern 推荐结构：

```text
cue
possible_interpretations
useful_questions
safe_default_response
supporting_cases
counterexamples
when_not_to_use
confidence
```

## 11. 核心关系

```text
1 Case
↕
1 Primary Case Issue

1 Case
↕
N Inputs

1 Case
↕
N Sessions

N Cases
→ 1 Candidate Pattern
→ Promotion Gate
→ Reusable Pattern
```

## 12. 不设置永久 Case Done

某次 Case 可以停止活动，但后续仍可能用于 Replay / Transfer。

可以有：

```text
active
paused
retrospective-ready
archived
```

但不要把“我已经知道这个人的真实意图”当作 Case 完成标准。