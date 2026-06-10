# Misconception Review Subskill (CPA)

## Role

Track user misunderstandings about CPA concepts and convert them into review prompts. In CPA, misconceptions are especially valuable because exam traps often target precisely the distinctions that learners find confusing.

## Core Principle

CPA misunderstandings are useful traces of knowledge growth. They reveal where the learner is imposing an incorrect mental model on a regulatory framework. Preserve them as material for review instead of treating them as failure.

## Misconception Table Format

Use this format:

```markdown
| 科目 | 概念 | 原始误解 | 为什么不准确 | 修正后理解 | 复习问题 | 相关笔记 |
|---|---|---|---|---|---|---|
| 会计 | 收入确认 | 以为收款时确认 | 权责发生制要求履约完成时确认 | ... | ... | [[...]] |
```

## Review Prompt Rules

Good CPA prompts ask the user to:

1. Explain the business rationale in their own words.
2. Compare two similar rules or treatments (the hallmark of CPA exams).
3. Give a concrete business example.
4. Give an example where the wrong rule would produce a different outcome.
5. Explain why a certain condition or exception exists.

Avoid prompts that only ask for memorized definitions or条文 numbers.

## Example Review Prompts (by Subject)

**会计:**
```
请你举一个具体的交易例子说明：为什么「预收账款」是负债而不是收入？
```

```
「存货跌价准备」和「固定资产减值准备」的后续处理有什么不同？为什么不同？
```

**审计:**
```
在一个审计项目里，审计师发现了一笔 50 万元的错报，而重要性水平是 100 万元。审计师可以忽略这笔错报吗？为什么？
```

```
「合理保证」和「绝对保证」的区别是什么？用审计成本的视角解释为什么审计只能提供合理保证。
```

**财务成本管理:**
```
一个项目 NPV 是正的，但 IRR 低于资本成本——这可能吗？请举一个具体的现金流例子。
```

```
为什么 MM 理论说「资本结构不影响企业价值」，但现实中企业仍然很在意负债率？
```

**税法:**
```
企业将自产产品发给员工当福利，增值税和企业所得税分别怎么处理？为什么处理方式不同？
```

```
「混合销售」和「兼营」的区别是什么？用一家销售空调并提供安装服务的公司举例。
```

**经济法:**
```
「要约」和「要约邀请」的关键区别是什么？超市货架上标价 5 元的商品是要约还是要约邀请？
```

```
股东会决议和董事会决议，哪些事项必须由股东会决定而不能授权董事会？为什么？
```

**公司战略与风险管理:**
```
「成本领先战略」和「差异化战略」是否可以同时执行？如果能，在什么条件下？如果不能，为什么？
```

```
「风险规避」和「风险转移」的区别是什么？用一家外贸企业面对汇率波动的例子说明。
```

## Review Workflow

1. Select one misconception from the user's history.
2. Ask the user to explain the corrected version.
3. Ask for a business example or counterexample.
4. Evaluate the answer.
5. If still unclear, ask one targeted follow-up.
6. Update the misconception table if the user asks for note output.
