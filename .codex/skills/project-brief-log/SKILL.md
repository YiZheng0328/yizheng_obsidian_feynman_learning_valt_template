---
name: project-brief-log
description: Manage per-project development brief logs in an Obsidian-style notes vault. Use when the user provides a Cursor change brief, implementation summary, release/change note, or asks Codex to organize development changes for the same project into one chronological project note, creating the note if it does not exist.
---

# Project Brief Log

## Overview

Maintain one chronological development note per project. Each Cursor change brief becomes one dated entry in the project's log so the user can reconstruct development order later.

## Workflow

1. Identify the project.
   - Prefer an explicit project name from the user.
   - Otherwise infer from repository name, package/app name, path, brief title, or repeated context.
   - If two existing projects could match and merging would be risky, ask one concise clarification before editing.

2. Locate the project log.
   - Search existing notes first with `rg` for `project_brief_log: true`, the project name, `开发简报`, `开发记录`, and `变更简报`.
   - Prefer an existing project folder under `500_projects/`.
   - If no log exists, create `500_projects/<项目名>/开发简报.md`.
   - If the project folder does not exist, create it.

3. Normalize the incoming brief.
   - Preserve the user's factual content.
   - Extract or infer: time, source, short title, summary, key changes, verification, risks, follow-ups, and related files.
   - Use the brief's stated timestamp when present. Otherwise use the current local date and time available in the environment.
   - Do not invent test results, changed files, or decisions. Use `未说明` for missing important fields.

4. Insert chronologically.
   - Keep entries under `## 开发时间线`.
   - Sort entries from oldest to newest unless the existing note already uses newest-first ordering; then preserve that ordering.
   - If an entry for the same timestamp and same brief already exists, update that entry instead of duplicating it.
   - Do not rewrite unrelated historical entries except for minimal ordering or formatting consistency.

5. Maintain navigation metadata.
   - Update frontmatter `updated`.
   - Keep a compact `## 项目概览` section if present, but do not over-summarize every entry into it.
   - Add wiki links for related project notes when they are obvious and already exist.

## Note Template

Use this template when creating a new project log:

```markdown
---
project: <项目名>
project_brief_log: true
created: YYYY-MM-DD
updated: YYYY-MM-DD
---

# <项目名>开发简报

## 项目概览

- 当前状态：未说明
- 主要目标：未说明
- 相关入口：未说明

## 开发时间线

### YYYY-MM-DD HH:mm - <简短标题>

- 来源：Cursor 变更简报
- 变更摘要：<1-3 句话>
- 关键变更：
  - <变更 1>
  - <变更 2>
- 验证：<测试、检查、未运行或未说明>
- 风险与后续：
  - <风险或下一步>
- 相关文件：
  - `<path>`
```

## Entry Quality

- Use concise Chinese by default when the user's notes are Chinese.
- Preserve exact file paths, command names, branch names, issue IDs, and dates.
- Prefer bullets over long paragraphs for scannability.
- Record development sequence, not a polished release note. Include failed checks or unresolved risks when present.
- If the brief is very long, condense repeated implementation details while keeping decisions, changed areas, verification, and next actions.
