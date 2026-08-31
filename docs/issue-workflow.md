# Issue-driven Workflow

## 1. 为什么使用 Issue

Issue 是训练过程的控制面，用来承载：

```text
当前 Case / Book
当前训练目标
已揭示范围
Session 摘要
关键 finding
knowledge gap
next action
```

Issue 不是：

- 第三方真实意图的事实数据库
- 完整聊天记录备份
- Pattern 最终真理来源

## 2. Primary Case Issue

推荐关系：

```text
1 Case ↔ 1 Primary Case Issue
```

Issue 标题示例：

```text
[Case] 同事回复明显变短 — 判断是否需要主动确认
[Case] 模拟：领导说“这个方案再想想”
```

真实 Case 标题也必须去标识化。

Primary Case Issue 至少包含：

```text
case_id
case_type
training_goal
minimal_context
privacy_check
current_phase
revealed_range
latest_session_summary
open_hypotheses
next_action
```

## 3. Case 生命周期

```text
Case captured
↓
Privacy / boundary check
↓
Primary Issue created
↓
Input 1 revealed
↓
Analysis Session
↓
Response / prediction
↓
New Input revealed
↓
Model update
↓
重复若干轮
↓
Retrospective
↓
Candidate Pattern / Gap
↓
Pause / Archive / Replay later
```

## 4. No-lookahead

对于真实历史复盘或书籍案例，如果最终结果已经已知，训练时仍应尽可能按时间切片：

```text
T1 已知信息
→ 判断
→ 记录

然后 reveal T2
→ 比较
→ 更新
```

不能：

```text
先读取全部结果
→ 再声称“当时应该这样判断”
```

## 5. Session 不默认建独立 Issue

一个 Case 可以有多个 Session：

```text
Learning
Prediction
ResponsePlanning
Replay
Retrospective
Transfer
```

默认都挂在 Primary Case Issue 下。

只有当某项工作具有独立生命周期时，才额外建 Issue，例如：

- 机制设计缺口
- 隐私规则缺口
- Pattern taxonomy 设计
- 工具 bug
- 某个长期 Book reading project

## 6. Book Issue

候选书籍与正式阅读分开：

```text
Reading Backlog Issue
→ candidate books

selected book
→ Primary Book Issue
```

推荐：

```text
1 Book ↔ 1 Primary Book Issue
1 Book ↔ N Reading / Case Training Sessions
```

Book Issue 不应该只追踪“读到第几页”，而应该追踪：

```text
当前章节 /案例
当前训练问题
已经建立的 reasoning pattern
仍未理解的概念
待验证的迁移能力
next action
```

## 7. Pattern 不直接由单个 Issue 晋升

单个 Case 的总结只能产生：

```text
Candidate Pattern
```

正式 Pattern 必须跨多个 Case Review。

推荐未来使用独立 Pattern Review Issue：

```text
[Pattern Review] 间接拒绝信号是否具有可迁移性
```

Review 时至少检查：

- supporting cases
- counterexamples
- context differences
- misclassification risk
- safe default action

## 8. Issue 状态不是事实状态

例如 Issue `closed` 只表示当前工作不再推进，不能解释为：

```text
“已经确定对方真实意图”
```

同样：

```text
Session complete ≠ Case truth resolved
Case archived ≠ Pattern proven
```

## 9. 最小 Issue 输出

每次 Session 后，Primary Issue 只需要补充简洁 checkpoint：

```text
revealed through: Input N
current problem: ...
leading hypotheses: ...
key evidence change: ...
reasoning gap: ...
next action: ...
```

不要把完整 AI transcript 长期塞入 Issue。

## 10. 第一个 Pilot 的成功标准

只需证明：

1. 一个 Case 能按顺序 reveal；
2. 事实与解释能够分离；
3. 至少能保留两个合理假设；
4. 新信息可以显式更新旧判断；
5. 原判断不会被事后覆盖；
6. Issue checkpoint 足以换会话继续；
7. 最终只能产生 Candidate Pattern，而不是草率的人性结论。