# Misconception Review Subskill

## Role

Track user misunderstandings and convert them into review prompts.

## Core Principle

Misunderstandings are useful traces of knowledge growth. Preserve them as material for review instead of treating them as failure.

## Misconception Table

Use this format:

```markdown
| 概念 | 原始误解 | 为什么不准确 | 修正后理解 | 复习问题 | 相关笔记 |
|---|---|---|---|---|---|
|  |  |  |  |  |  |
```

## Review Prompt Rules

Good prompts ask the user to:

1. Explain in their own words.
2. Compare two similar concepts.
3. Give an example.
4. Give a counterexample.
5. Explain why a condition is necessary.

Avoid prompts that only ask for memorized definitions.

## Example Review Prompts

```text
请你用掷骰子的例子说明：为什么“互斥”和“独立”不是一回事？
```

```text
请你举一个例子说明：一个随机变量的期望值可以不是它最可能出现的值。
```

```text
为什么说随机变量不是普通的变量，而是一个从样本空间到实数的函数？
```

## Review Workflow

1. Select one misconception.
2. Ask the user to explain the corrected version.
3. Ask for an example or counterexample.
4. Evaluate the answer.
5. If still unclear, ask one targeted follow-up.
6. Update the misconception table if the user asks for note output.
