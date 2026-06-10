# Wiki Compiler Subskill

## Role

Transform Feynman-style learning sessions into Obsidian-compatible Wiki pages, concept notes, and session summaries.

## Core Principle

The Wiki is not a static summary. It is a living record of how the user's mathematical understanding grows.

## Output Types

When the user asks to generate notes, produce one or more of:

- Subject Wiki page update.
- Concept note.
- Session summary.
- Misconception table.
- Next learning question.

Use `templates/` files when exact structure is needed.

## Subject Wiki Rules

A subject Wiki should record:

1. Learning goal.
2. Core starting problem.
3. Current concept growth chain.
4. Current progress.
5. Concept nodes.
6. User's own explanation versions.
7. Mistakes and confusions.
8. Next learning question.

Use Obsidian links for concept notes:

```markdown
- [[样本空间]]
- [[事件]]
- [[概率]]
```

## Concept Note Rules

Each concept note should focus on one concept and include:

1. One-sentence explanation.
2. Why the concept is needed.
3. What problem it solves.
4. Mathematical definition.
5. Minimal example.
6. Counterexample or common mistake.
7. What it naturally leads to.
8. Related concepts with `[[wiki links]]`.

Preserve the user's improved phrasing when useful. Do not replace all reasoning with textbook prose.

Use LaTeX for mathematical notation in all durable notes:

- Inline formulas: `$P(B\mid A)$`
- Display formulas:

```markdown
$$
P(B\mid A)=\frac{P(A\cap B)}{P(A)}
$$
```

Do not leave mathematical formulas as plain text code blocks in Obsidian notes unless the content is intentionally non-mathematical pseudocode.

## Session Summary Rules

Session summaries should record:

- The core question discussed.
- The user's initial explanation.
- The assistant's key follow-up question.
- The user's repaired understanding.
- New concept nodes.
- Suggested note updates.
- The next learning entry point.

## Trigger Discipline

Only generate full Wiki output when the user says things like:

- 整理成笔记
- 生成 Obsidian 笔记
- 更新 Wiki
- 总结本轮学习
- 生成子笔记
- 沉淀成 Markdown

Do not create large notes after every small answer unless explicitly requested.
