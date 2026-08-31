# Learning Sources

## 1. Source 类型

本仓库可以使用三类训练 Source：

```text
真实去标识化 Case
模拟 Case
书籍 / 教材 / 文章中的公开案例
```

三类 Source 都服务于同一个目标：

```text
输入逐步揭示
→ 当下判断
→ 回应或预测
→ 新信息
→ 修正
→ 迁移
```

## 2. 真实 Case

真实 Case 价值最高，但隐私风险也最高。

进入仓库前必须经过：

```text
必要性检查
→ 去标识化
→ 最小上下文
→ 可公开性检查
```

不因为“训练价值高”就保留不必要的身份细节。

真实 Case 优先保存结构：

```text
Observed event
Context required for interpretation
My interpretation
Hypotheses
Response
Outcome
Update
```

而不是保存完整原始聊天记录。

## 3. 模拟 Case

模拟 Case 用于先跑通机制。

优点：

- 没有第三方隐私问题；
- 可以严格控制 reveal 顺序；
- 可以专门设计某一 reasoning gap；
- 方便重复 Replay。

首个 Pilot 应优先使用模拟 Case。

## 4. 书籍 Source

书籍不是为了“读完”而进入本仓库，而是为了产生训练输入。

典型流程：

```text
Book candidate
→ Reading Backlog
→ selected
→ Primary Book Issue
→ 按章节 / 案例 source-first 阅读
→ 遇到可训练 Case 时暂停
→ 学习者先判断
→ 再 reveal 作者后续分析
→ compare
→ update
→ transfer
```

## 5. Reading Backlog 与 Book Issue 分开

建议建立一个长期 Reading Backlog Issue，只保存候选：

```text
title
author
topic
why_candidate
training_capability
priority
status
```

状态可以简单使用：

```text
candidate
selected
reading
reviewed
```

当一本书正式开始阅读后，再建立：

```text
[Book] <Title>
```

作为 Primary Book Issue。

## 6. Book Issue 的真正目标

Book Issue 不只是记录进度，而是记录：

```text
current source position
current concept / case
reasoning patterns encountered
prediction / response exercises
misconceptions
transfer questions
next action
```

## 7. 书籍案例训练模式

如果书里出现一个场景：

```text
A 说一句话
B 做一个反应
```

不要立刻看作者解释。

优先：

```text
当前已知 Source
↓
字面发生了什么
↓
可能的隐含含义有哪些
↓
哪些证据支持 / 反对
↓
如果是我，下一步怎么回应
↓
freeze prediction / response
↓
再 reveal 作者后续内容
↓
比较
↓
更新
```

这样书籍就从“知识输入”变成了“反应机制训练器”。

## 8. 不把作者观点自动升级为事实

沟通类书籍中的：

```text
作者模型
作者建议
案例解释
```

仍然需要区分：

```text
source claim
reasoning model
empirical evidence
personal applicability
```

即使一本书很经典，也不能把作者对人类行为的概括直接写成普遍定律。

## 9. Candidate Pattern 的来源

候选 Pattern 可以来自：

- 多个真实 Case；
- 多个模拟 Case；
- 多本独立来源；
- 真实 Case + 书籍模型交叉验证。

但最终晋升仍需要 Pattern Promotion Gate。

## 10. 推荐的第一阶段

先不建立大规模书单。

只做：

```text
机制文档
→ 1 个 Reading Backlog Issue
→ 选 1 本书
→ 1 个 Primary Book Issue
→ 1 个小 Case Pilot
```

如果这一条链自然，再扩展更多书籍与真实 Case。