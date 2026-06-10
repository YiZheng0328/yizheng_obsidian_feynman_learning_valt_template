# Wiki Compiler Subskill (CPA)

## Role

Transform Feynman-style CPA learning sessions into Obsidian-compatible Wiki pages, concept notes, quick-reference sheets (速查表), and session summaries.

## Core Principle

The CPA Wiki is not a static textbook summary. It is a living record of how the user's understanding of business rules and their rationale grows. Prioritize **why the rule exists** alongside **what the rule says**.

## Output Types

When the user asks to generate notes, produce one or more of:

- Subject Wiki page update (学科主页).
- Concept note (概念笔记).
- Quick-reference sheet (速查表) for exam-oriented formula/provision review.
- Session summary (学习会话总结).
- Misconception table (误解与复习清单).
- Next learning question (下一问).

Use `templates/` files when exact structure is needed.

## Subject Wiki Rules

A CPA subject Wiki should record:

1. Learning goal (学习目标).
2. Core starting business problem (核心起点问题).
3. Current concept growth chain (概念生长链).
4. Concept nodes with progress tracking.
5. User's own explanation versions.
6. Mistakes and confusions.
7. Next learning question (下一问).

Use Obsidian links for concept notes:

```markdown
- [[会计等式]]
- [[借贷记账法]]
- [[收入确认五步法]]
```

Include Dataview queries for dynamic progress tracking:

```markdown
## 进行中的笔记
```dataview
TABLE WITHOUT ID
  file.link AS "笔记",
  type AS "类型",
  next AS "下一步",
  review AS "复习"
FROM "100_learning"
WHERE status = "进行中"
AND subject = "会计"
SORT file.mtime DESC
```
```

## Concept Note Rules

Each CPA concept note should focus on one concept and include:

1. **One-sentence explanation** (一句话解释).
2. **What business problem existed without it** (为什么需要它).
3. **What problem it solves** (它解决了什么问题).
4. **Core rule / provision / formula** (核心规则). For accounting: journal entries. For tax: calculation formulas. For law: key article summary.
5. **Minimal business example** (最小商业例子). A realistic, concrete scenario.
6. **Counterexample or common mistake** (反例或易错点).
7. **What it naturally leads to** (它自然引出什么).
8. **Related concepts** with `[[wiki links]]`.

### Subject-Specific Formatting

**会计 (Accounting) — Journal entry format:**

```
借：{科目}  {金额}
  贷：{科目}  {金额}
```

**税法 (Tax Law) — Calculation format:**

```
应纳税额 = 计税基础 × 适用税率 - 税收抵免
```

**审计 (Auditing) — Procedure format:**

```
审计程序：{程序名}
目标：验证 {认定} 
方法：{具体步骤}
```

**财务成本管理 — Formula format:**

Use LaTeX for formulas:

$$
NPV = \sum_{t=0}^{n} \frac{CF_t}{(1+r)^t}
$$

**经济法 — Rule format:**

```
《{法律名}》第 {X} 条：
{条文主旨}
适用条件：{条件}
法律效果：{效果}
```

## Quick-Reference Sheet (速查表) Rules

CPA 速查表 follow the same pattern as math 速查表 but adapted for regulatory/business content:

1. **Group by module** (按知识模块分组).
2. **Use tables** for comparisons (e.g., accounting treatments under different scenarios).
3. **Include core formulas/entries** in a clean, scannable format.
4. **Add a "common traps" section** (常见陷阱速查).
5. **Include a "required memorization" section** (必背条目清单).
6. **Link back to concept notes** for deeper understanding.

See `templates/quick-reference-template.md`.

## Session Summary Rules

Session summaries should record:

- The core business question discussed.
- The user's initial explanation.
- The assistant's key follow-up question.
- The user's repaired understanding.
- New concept nodes created.
- Suggested note updates.
- The next learning entry point.

Use `templates/session-summary-template.md`.

## Trigger Discipline

Only generate full Wiki output when the user says things like:

- 整理成笔记
- 生成 Obsidian 笔记
- 更新 Wiki / 更新学科主页
- 总结本轮学习
- 生成子笔记
- 沉淀成 Markdown
- 整理速查表
- 生成公式/条文速查

Do not create large notes after every small answer unless explicitly requested.

## Frontmatter Convention

All CPA notes use consistent frontmatter:

```yaml
---
type: 概念 | 错题 | 速查
subject: {CPA subject — 会计 / 审计 / 财务成本管理 / 税法 / 经济法 / 公司战略与风险管理}
chapter: "{chapter number or name}"
status: 进行中 | 已完成 | 待复习
review: {YYYY-MM-DD or empty}
next: "{next learning question}"
tags:
  - cpa/concept
  - cpa/{subject shorthand}
created: {YYYY-MM-DD}
source:
  - {textbook or source reference}
---
```
