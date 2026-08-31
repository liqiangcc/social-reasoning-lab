# Social Reasoning Lab

一个用于训练**人际场景中的观察、解释、假设、回应、反馈与修正能力**的个人学习仓库。

本仓库的目标不是建立“识人术”“读心术”或操控他人的技巧库，而是训练在信息不完整的人际环境中：

```text
当前输入
+ 已知上下文
→ 区分事实与解释
→ 保留多个假设
→ 评估证据与误判成本
→ 选择低风险回应
→ 接收后续反馈
→ 更新判断
→ 提炼可迁移模式
```

## 核心原则

1. **事实 ≠ 解释 ≠ 意图**：对方说了什么、我怎么理解、对方真实想法必须分开。
2. **不把第一反应当事实**：自动解释只是候选假设。
3. **多假设并存**：证据不足时不锁死单一结论。
4. **顺序揭示**：复盘和训练时尽量只使用当时已经知道的信息，避免后见之明。
5. **反馈驱动更新**：新信息出现后允许提高、降低或推翻原判断。
6. **保留错误判断**：不能用最终结果反向美化当时预测。
7. **低风险回应优先**：在不确定时优先选择能继续获得信息、又不无谓升级冲突的回应。
8. **模式必须跨案例验证**：单一经历不能直接上升为“人性规律”。
9. **训练理解，不训练操控**：不以欺骗、胁迫、利用脆弱性或隐蔽控制为目标。
10. **隐私优先**：真实案例默认去标识化；公开仓库不得提交真实姓名、联系方式、账号、完整私密聊天记录或其他可识别个人的信息。

## 核心训练链

```text
Observed
→ Interpretation
→ Hypotheses
→ Evidence
→ Response
→ Outcome
→ Update
→ Reusable Pattern
```

其中：

- `Observed`：可直接观察到的言语、行为、时间、环境。
- `Interpretation`：我当时赋予这些事实的意义。
- `Hypotheses`：至少一个、通常多个可能解释。
- `Evidence`：支持、反对、仍缺失的信息。
- `Response`：在当时信息条件下选择的回应。
- `Outcome`：后续实际反馈或事件。
- `Update`：哪些判断被加强、削弱或推翻。
- `Reusable Pattern`：经过多个案例验证后才可沉淀的可迁移模式。

## Issue 驱动

仓库采用 Issue 作为训练控制面，而不是把 Issue 当作事实真相数据库。

长期关系：

```text
1 Case ↔ 1 Primary Case Issue
1 Case ↔ N Analysis / Replay / Training Sessions

1 Book ↔ 1 Primary Book Issue（正式开始阅读后）
1 Book ↔ N Reading / Case Training Sessions
```

候选书籍可以先进入一个 Reading Backlog；正式开始某本书时再创建独立 Book Issue。

## 文档

- `docs/boundaries.md` — 仓库边界、隐私与安全约束
- `docs/case-model.md` — Case / Session / Pattern 的领域模型
- `docs/issue-workflow.md` — Issue 驱动生命周期
- `docs/reasoning-principles.md` — 人际推理训练原则
- `docs/learning-sources.md` — 书籍、真实案例、模拟案例如何进入训练

## 当前阶段

当前只建立机制，不批量录入案例，不急于建立 Pattern Library。

下一阶段应先用一个**去标识化的小型模拟 Case**跑通：

```text
Input
→ Analysis
→ Response
→ New Input
→ Update
→ Retrospective
```

机制跑通后，再决定 Issue 模板、标签体系、Session artifact schema 和 Pattern promotion gate。