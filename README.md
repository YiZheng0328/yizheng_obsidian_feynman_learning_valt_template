# Feynman Learning Vault Template

一个面向 Obsidian + AI assistant 的学习型知识库模板。它把笔记系统拆成三层：

1. **学习工作流**：从问题、解释、追问、修正到复习。
2. **结构化 vault**：用固定目录、frontmatter、Dataview 和模板沉淀知识。
3. **AI skills**：让 Codex / Claude 按同一套费曼式学习方法辅导、整理和复盘。

这个仓库是脱敏模板，不包含个人笔记、日报、课程原文、PDF、图片或项目记录。

## 快速开始

1. 用 Obsidian 打开本目录作为 vault。
2. 让 Codex / Claude 自动配置：AI 会读取 vault 内已有的 `.claude/skills/` 或 `.codex/skills/` 并自行加载。无需手动复制 skills 文件。详见 [自动配置说明](docs/auto-setup-guide.md)。
3. 安装并启用 `.obsidian/community-plugins.json` 中列出的社区插件。
4. 从 `!_home.md` 开始阅读工作流说明。
5. 用 `templater/` 中的模板创建概念、定理、证明、错题、学习会话和日报。

## 推荐插件

- Dataview：主页看板、复习列表、未完成任务聚合。
- Templater：结构化生成笔记。
- QuickAdd：快速创建学习会话、概念、错题等。
- Omnisearch：全库搜索。
- Heatmap Calendar：学习热力图。
- Iconize：主页图标显示。
- Git：版本管理。
- Latex Suite：数学输入增强。
- Claudian：Claude 与 Obsidian 深度集成，AI 可直接读写、搜索 vault 内容。

## 仓库结构

```text
!_home.md                 工作流总入口
000_inbox/                临时输入和待处理材料
100_learning/             概念、定理、证明、错题、学习会话
200_subjects/             学科主页和长期学习路径
300_literature/           文献阅读
400_books/                读书笔记
500_projects/             项目日志和开发简报
600_archive/              归档内容
700_outputs/              文章、报告、讲稿等输出物
800_languages/            语言学习
900_raw_sources/          原始材料占位目录，默认不提交内容
templater/                Obsidian Templater 模板
.codex/skills/            Codex skills
.claude/skills/           Claude skills
.obsidian/                可共享 Obsidian 配置
```

## 开源前检查

发布自己的 fork 前，建议执行：

```bash
rg -n "姓名|手机号|邮箱|token|api[_-]?key|password|secret|/home/|C:\\\\|微信|身份证" .
find . -type f -size +10M -print
```

并确认没有提交：

- 个人笔记、日报、项目记录。
- 课程原文、教材扫描件、PDF、图片素材。
- `.obsidian/workspace.json`、插件源码、会话记录。
- API key、账号、设备信息和本地绝对路径。

