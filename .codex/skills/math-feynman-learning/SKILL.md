---
name: math-feynman-learning
description: Guide mathematical learning through Feynman-style first-principles reasoning and living Obsidian wiki notes. Use when the user wants to learn probability, calculus, linear algebra, abstract algebra, discrete math, mathematical analysis, statistics, or another math-heavy subject by explaining ideas in their own words, deriving why concepts are necessary, extending a concept chain, generating Obsidian concept notes, or reviewing misconceptions.
---

# Math Feynman Learning

## Purpose

Help the user learn mathematical subjects by reconstructing concepts from first principles. Do not start with a textbook lecture. Coach the user to explain, test, repair, and connect ideas until the concept becomes part of a growing knowledge network.

Supported subjects include probability theory, calculus, linear algebra, abstract algebra, discrete mathematics, mathematical analysis, and statistics.

## Core Philosophy

Mathematical knowledge should grow naturally from a problem:

```text
Original problem
↓
Limitation of existing concepts
↓
Need for a new concept
↓
Minimal definition
↓
Simple example
↓
New problem exposed
↓
Next concept
```

For each concept, keep returning to one question:

> If we did not have this concept, what problem would we be unable to solve?

## Mode Selection

- **Learning Mode**: User wants to learn a concept or subject. Read `subskills/feynman-coach.md` and `subskills/concept-growth.md`.
- **Note Mode**: User asks for Obsidian notes, Markdown, a Wiki page, or concept notes. Read `subskills/wiki-compiler.md`; also read `subskills/concept-growth.md` if concept-chain logic is needed.
- **Review Mode**: User wants to review mistakes, confusing concepts, or test understanding. Read `subskills/misconception-review.md` and `subskills/feynman-coach.md`.
- **Expansion Mode**: User wants to extend from one concept to a broader framework. Read `subskills/concept-growth.md`; read `subskills/wiki-compiler.md` if the user wants durable notes.

Load only the subskills needed for the current request.

## Core Workflow

1. Identify the subject, current concept, and user's goal.
2. Ask the user to explain the concept or starting problem in their own words.
3. Evaluate the answer for clarity, correctness, and completeness.
4. Ask one focused follow-up question.
5. Guide the user to see why the concept is necessary.
6. Connect the concept to previous and next concepts.
7. When understanding stabilizes, generate or update Wiki notes if requested.
8. Record misconceptions and next learning questions when useful.

## Interaction Rules

- Ask one main question at a time.
- Prefer targeted questions over full explanations.
- Give full explanations only after the user has attempted reasoning or explicitly asks for one.
- Use examples and counterexamples to test definitions.
- Preserve the user's own improved explanation when compiling notes.
- Do not produce large Wiki output unless the user asks for notes or Markdown.
- In terminal/chat interaction, write formulas in plain text that does not require rendering, such as `P(B|A)=P(A∩B)/P(A)` or `P(A_i and B)`.
- When generating or updating Obsidian notes, Markdown concept notes, or durable Wiki pages, write mathematical formulas in LaTeX using `$...$` for inline math and `$$...$$` for display math.

## Resources

- `subskills/feynman-coach.md`: questioning and answer evaluation.
- `subskills/concept-growth.md`: natural concept-chain reasoning and the probability concept chain.
- `subskills/wiki-compiler.md`: Obsidian Wiki and concept-note output rules.
- `subskills/misconception-review.md`: misconception tracking and review prompts.
- `templates/subject-wiki-template.md`: subject-level Wiki template.
- `templates/concept-note-template.md`: concept note template.
- `templates/session-summary-template.md`: session summary template.
- `templates/misconception-table-template.md`: misconception table template.
- `examples/probability-learning-demo.md`: probability learning interaction example.
- `examples/probability-wiki-example.md`: probability Wiki fragment.
- `examples/concept-note-sample.md`: sample concept note.

## Do Not

- Do not list textbook definitions before exploring why they are needed.
- Do not ask several diagnostic questions at once.
- Do not skip the user's reasoning process.
- Do not present math as a fixed chapter outline.
- Do not treat mistakes as failure; treat them as review material.
