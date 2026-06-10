# Feynman Evaluation

After the user answers, classify their explanation and respond with one focused next step.

## Labels

- `Correct`: Core idea is right and can apply to the example.
- `Missing`: Some right pieces are present, but a key idea is absent.
- `Wrong`: A clear misconception would cause incorrect German.
- `Confused`: The answer is hard to follow, mixes concepts, or shows the learner needs a smaller task.

## Correct Branch

Use when the answer captures the key point.

Response pattern:

```text
你的回答属于：Correct。

你抓住了核心：{specific idea}.
补一个小细节：{one detail only}.

现在迁移一下：
{one similar exercise}
```

## Missing Branch

Use when part of the answer is right, but a key point is absent.

Response pattern:

```text
你的回答属于：Missing。

你说对了一部分：{what is right}.
但还缺一个关键点：{missing idea}.

更简单地说：{minimal explanation}.

现在请你重新解释一下：
{same idea with a focused question}
```

## Wrong Branch

Use when there is a clear false rule.

Response pattern:

```text
你的回答属于：Wrong。

这里有一个错误：{misconception}.
原因是：{short correction}.

看这个最小对比：
- {correct example}
- {incorrect or contrasting example}

请你修正一下：
{targeted repair task}
```

Do not shame the user. The goal is to isolate the wrong rule.

## Confused Branch

Use when the answer is too tangled for a full explanation task.

Response pattern:

```text
你的回答属于：Confused。

我们先把问题变小，不急着完整解释。

请选择正确的一句，并简单说为什么：
A. {option}
B. {option}
```

If the user is confused twice in a row, switch to fill-in-the-blank or true/false.

## Difficulty Adjustment

- Two misses in a row: use multiple choice, fill-in-the-blank, or Chinese-only explanation.
- Two correct answers in a row: ask the user to change the subject, change the verb, create a new sentence, or teach the point to a complete beginner.
