---
name: lucide-icons
description: Enforce Lucide native icon usage (`:LiIconName:`) instead of emojis throughout the vault. Use when creating folders, adding icons to section headings, or choosing icons for any markdown content.
---

# Lucide Icons Convention

## Purpose

This vault uses the **Iconize** plugin with the **Lucide native icon pack** for all icons. Every icon in the vault must use the `:LiIconName:` shortcode syntax — never emoji, never raw HTML icon markup, never other icon packs.

## Why

- **Consistency**: All icons across the vault share a uniform line-art style.
- **System-native rendering**: The Iconize plugin renders Lucide icons natively in Obsidian, both in editor and reading mode.
- **Future-proof**: When the user browses files in the file explorer, folder/file icons assigned via Iconize match the inline icons in content.

## Icon Format

```
:LiIconName:
```

Examples: `:LiSigma:`, `:LiCalculator:`, `:LiBookOpen:`, `:LiZap:`

The colon `:` is the configured identifier in the Iconize plugin settings. The `Li` prefix denotes the Lucide icon pack in native mode.

## Current Vault Icon Assignments

The following icon assignments exist in `icon-folder` config (`data.json`):

| Target | Icon | Context |
|--------|------|---------|
| `!_home.md` | `LiBadgeCent` | 主页 |
| `000_inbox/` | `LiInbox` | 临时输入 |
| `100_learning/` | `LiBookOpen` | 学习笔记 |
| `200_subjects/` | `LiNetwork` | 学科主页 |
| `300_literature/` | `LiBookText` | 文献阅读 |
| `400_books/` | `LiLibrary` | 读书笔记 |
| `500_projects/` | `LiKanban` | 项目管理 |
| `600_archive/` | `LiArchive` | 归档 |
| `700_outputs/` | `LiFileOutput` | 输出作品 |
| `800_languages/` | `LiLanguages` | 语言学习 |
| `900_raw_sources/` | `LiArchive` | 原始资源 |
| `templater/` | `LiLayoutTemplate` | 模板 |

## Semantic Icon Mapping

When choosing an icon for a new folder, section heading, or any content, follow this semantic guide. Prefer icons already established in the vault for consistency.

### Core Sections (Homepage)

| Semantic | Icon | Used In |
|----------|------|---------|
| Quick access / fast | `:LiZap:` | 快速入口 |
| Book / learning | `:LiBookOpen:` | 学习/最近学习 |
| Research / science | `:LiFlaskConical:` | 阅读与研究 |
| Package / project | `:LiPackage:` | 项目与输出 |
| Bookmark / current | `:LiBookMarked:` | 当前学习主题 |
| New file / create | `:LiFilePlus:` | 今日新建笔记 |
| Calendar days | `:LiCalendarDays:` | 近期日报 |
| Checklist / tasks | `:LiListChecks:` | 未完成任务 |
| Refresh / review | `:LiRefreshCw:` | 待复习 |
| Blocks / modules | `:LiBlocks:` | 可扩展模块 |
| Door / entry | `:LiDoorOpen:` | 科目入口 |
| Help / question | `:LiHelpCircle:` | 本周问题 |

### Learning Subjects

| Semantic | Icon | Used In |
|----------|------|---------|
| Math general / sum | `:LiSigma:` | 数学 |
| Compute / formula | `:LiCalculator:` | 公式、计算 |
| Probability / stats | `:LiPercent:` | 概率统计 |
| Charts / data | `:LiBarChart:` | 数据分析 |
| Table / structure | `:LiTable:` | 结构化知识 |
| Network / graph | `:LiNetwork:` | 概念网络 |

### Utilities

| Semantic | Icon | Used In |
|----------|------|---------|
| Archive | `:LiArchive:` | 归档/原始资源 |
| File / document | `:LiFileText:` | PDF/文档 |
| Image / picture | `:LiImage:` | 图片 |
| Template | `:LiLayoutTemplate:` | 模板 |
| Calendar (single) | `:LiCalendar:` | 日报文件夹 |
| Tag / label | `:LiTag:` | 标签相关 |
| Folder | `:LiFolder:` | 目录 |
| Link | `:LiLink:` | 链接 |
| Search | `:LiSearch:` | 搜索 |
| Settings | `:LiSettings:` | 设置 |

### Extension Modules

When creating new modules, choose icons that fit the module's domain:

| Module | Suggested Icon | Rationale |
|--------|---------------|-----------|
| 文献阅读 | `:LiBookText:` or `:LiScrollText:` | Academic papers, literature |
| 读书笔记 | `:LiBookHeart:` or `:LiLibrary:` | Books, reading |
| 项目管理 | `:LiKanban:` or `:LiTarget:` | Project management |
| 输出作品 | `:LiPenLine:` or `:LiFileOutput:` | Writing, output |
| 归档 | `:LiArchive:` | Completed/archived content |

## Rules

### When Creating a New Folder

1. Determine the folder's purpose and domain.
2. Consult the semantic mapping above.
3. Choose a Lucide icon that matches semantically.
4. The icon name must use CamelCase after `Li`, e.g. `:LiBookOpen:` not `:LiBookopen:`.
5. If unsure, prefer simplicity — use `:LiFolder:` as a fallback.

### When Adding Icons to Section Headings

```
## :LiIconName: Section Title
```

- Icon comes before the title text, separated by a space.
- Always use the `:Li` prefix, never emoji (🚀📚🔬📦📐🆕🗓️✅🔁🧩).
- If the section is a variation of an existing one (e.g., a different kind of "review"), reuse the same icon (`:LiRefreshCw:`) for consistency.

### When Replacing Existing Emoji

- Never leave emoji in newly created or modified content.
- If you see emoji in a file being edited, replace it with the appropriate `:LiIconName:`.
- If no exact match exists, pick the closest semantic equivalent.

### Icon Discovery

If you need an icon not in the mapping above:

1. Think about the semantic meaning (e.g., "mind map", "connection", "branch").
2. Common Lucide icon naming pattern: `Li` + PascalCase description, e.g. `LiGitBranch`, `LiCloudSun`, `LiBrain`.
3. Prefer shorter, more common icon names — they are more likely to exist in the Lucide pack.
4. Refer to the [Lucide icon library](https://lucide.dev/icons) for the full catalog.

## Examples

### Good

```markdown
## :LiBookOpen: 最近学习

## :LiRefreshCw: 待复习

| :LiBookOpen: 学习 | :LiFlaskConical: 研究 |
```

### Bad

```markdown
## 📚 最近学习

## 🔁 待复习

| 📚 学习 | 🔬 研究 |
```

## Scope

- This convention applies to **all markdown files** in the vault.
- It applies to both content creation (section headings, tables) and folder/file icon assignment (via Iconize plugin config).
- External contexts (non-vault files) are exempt.
