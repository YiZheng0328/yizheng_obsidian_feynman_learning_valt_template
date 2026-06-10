---
cssclasses:
  - vault-home
banner_header: false
banner_icon: false
---

# Feynman Learning Vault

> 目标：把“我学过”变成“我能解释、能迁移、能复盘、能输出”。

这个 vault 是一套学习工作台，不是一堆文件夹。它的核心假设是：稳定的知识来自反复回答一个问题：

> 如果没有这个概念、规则或方法，我会在哪个问题上失败？

---

## 1. 工作流总览

```text
输入材料
↓
提出核心问题
↓
用自己的话解释
↓
AI / 自我追问
↓
修正解释
↓
沉淀结构化笔记
↓
安排复习和错题
↓
输出文章、项目或讲解
```

这套流程避免直接摘抄教材。每条长期笔记都应说明：

- 它解决什么问题。
- 为什么旧概念不够用。
- 最小定义或规则是什么。
- 一个最小例子是什么。
- 常见误区是什么。
- 它自然通向下一个什么问题。

---

## 2. 日常使用节奏

### 每次学习前

1. 把临时材料放进 `000_inbox/` 或 `900_raw_sources/`。
2. 新建一条学习会话，使用 `templater/学习会话模板.md`。
3. 写下今天的核心问题，而不是先写章节标题。

### 学习中

1. 先用自己的话解释，不急着整理成正式笔记。
2. 用 AI skill 追问：定义是否清楚、例子是否成立、边界是否遗漏。
3. 当解释稳定后，再生成概念、定理、证明或错题笔记。

### 学习后

1. 给笔记加 frontmatter：`type`、`subject`、`status`、`review`、`next`。
2. 把未解决问题写进 `next` 或任务列表。
3. 在日报中记录今天真正推进的一点。

---

## 3. 目录说明

| 目录 | 用途 | 推荐内容 |
|---|---|---|
| `000_inbox/` | 临时收件箱 | 待整理摘录、问题、想法 |
| `100_learning/` | 学习笔记主体 | 概念、定理、证明、错题、学习会话 |
| `200_subjects/` | 学科主页 | 每个学科的目标、路线、概念链 |
| `300_literature/` | 文献阅读 | 论文笔记、研究问题、证据链 |
| `400_books/` | 读书笔记 | 书籍结构、章节卡片、可迁移观点 |
| `500_projects/` | 项目管理 | 项目主页、开发简报、决策记录 |
| `600_archive/` | 归档 | 完成、废弃或暂缓内容 |
| `700_outputs/` | 对外输出 | 文章、讲稿、报告、作品草稿 |
| `800_languages/` | 语言学习 | 语法、词汇、例句、复述练习 |
| `900_raw_sources/` | 原始资料 | PDF、图片、导出的 Markdown；默认不提交 |
| `templater/` | 模板 | Templater 笔记模板 |

---

## 4. 笔记类型

| 类型 | 什么时候使用 | 核心问题 |
|---|---|---|
| `学习会话` | 一次学习过程 | 今天到底解决哪个问题？ |
| `概念` | 新概念或新规则 | 没有它会失败在哪里？ |
| `定理` | 数学结论、公式、规则 | 它在什么前提下解决什么问题？ |
| `证明` | 证明或推导 | 每一步为什么必须这样转化？ |
| `错题` | 错误、误区、卡点 | 真正缺失的是哪个概念？ |
| `日报` | 每日复盘 | 今天理解推进了什么？ |
| `项目简报` | 项目变更记录 | 这次改动改变了什么，验证了什么？ |

推荐 frontmatter：

```yaml
---
type: 概念
subject: 示例学科
status: 进行中
review: 2026-01-01
next:
tags:
  - learning/concept
created: 2026-01-01 09:00
---
```

---

## 5. 看板

### 今日新建笔记

```dataview
TABLE file.folder AS "位置", file.ctime AS "创建时间"
FROM "000_inbox" OR "100_learning" OR "200_subjects" OR "300_literature" OR "400_books" OR "500_projects" OR "700_outputs" OR "800_languages"
WHERE file.cday = date(today)
SORT file.ctime DESC
LIMIT 20
```

### 最近未完成任务

```dataview
TASK
FROM "000_inbox" OR "100_learning" OR "200_subjects" OR "300_literature" OR "400_books" OR "500_projects" OR "700_outputs" OR "800_languages"
WHERE !completed
SORT file.mtime DESC
LIMIT 20
```

### 待复习内容

```dataview
TABLE review AS "复习日期", status AS "状态", next AS "下一步", file.folder AS "位置"
FROM "100_learning" OR "200_subjects" OR "300_literature" OR "400_books" OR "800_languages"
WHERE review AND review <= date(today)
SORT review ASC
LIMIT 20
```

### 学习热力图

```dataviewjs
const year = new Date().getFullYear();

if (typeof renderHeatmapCalendar !== "function") {
  dv.paragraph("Heatmap Calendar 插件尚未加载。");
} else {
  const days = new Map();

  for (const page of dv.pages('"100_learning" OR "200_subjects" OR "800_languages"')) {
    if (!page.file?.cday) continue;
    const date = page.file.cday.toFormat("yyyy-MM-dd");
    if (!date.startsWith(String(year))) continue;
    days.set(date, (days.get(date) ?? 0) + 1);
  }

  renderHeatmapCalendar(this.container, {
    year,
    entries: [...days.entries()].map(([date, count]) => ({
      date,
      intensity: count,
      content: "",
    })),
    intensityScaleStart: 1,
    intensityScaleEnd: 5,
    defaultEntryIntensity: 5,
  });
}
```

---

## 6. Skills 说明

### `math-feynman-learning`

用途：学习数学、统计、线性代数、概率论、微积分等抽象学科。

工作方式：

1. 从一个原始问题开始，而不是从定义开始。
2. 让学习者先解释。
3. 检查定义、例子、边界和误区。
4. 把稳定理解整理为 Obsidian 概念笔记或学科 Wiki。

适合请求：

```text
使用 math-feynman-learning 帮我理解条件概率。
把我刚才对中心极限定理的解释整理成 Obsidian 概念笔记。
用费曼法检查我对协方差的理解哪里不清楚。
```

### `cpa-feynman-learning`

用途：学习 CPA 或规则密集型知识。它把法规、分录、公式都还原成“为了解决什么业务问题”。

工作方式：

1. 从业务场景开始。
2. 追问如果没有这条规则会出现什么问题。
3. 用最小交易、最小案例或最小计算解释规则。
4. 输出概念笔记、速查表或错题复盘。

适合请求：

```text
使用 cpa-feynman-learning 帮我理解货币时间价值为什么必要。
把这道财管错题整理成错题复盘。
用业务问题解释借贷记账法。
```

### `feynman-german-beginner`

用途：A0-A1 德语入门。它不是翻译器，而是小步解释、复述、纠错和迁移练习。

工作方式：

1. 一次只学一个小语法点或句型。
2. 给 3 个以内例句。
3. 要求学习者用自己的话解释。
4. 根据回答标记 `Correct`、`Missing`、`Wrong` 或 `Confused`。
5. 生成 Obsidian 语言学习笔记。

适合请求：

```text
使用 feynman-german-beginner 教我 sein。
检查我对 der / die / das 的解释是否正确。
把今天的德语课整理成 Obsidian 笔记。
```

### `project-brief-log`

用途：把开发工具、AI 编程助手或人工整理的变更说明，按项目沉淀到 `500_projects/`。

工作方式：

1. 识别项目名。
2. 找到或创建 `500_projects/<项目名>/开发简报.md`。
3. 记录时间、来源、摘要、关键变更、验证、风险和相关文件。
4. 保持时间线可追溯。

适合请求：

```text
使用 project-brief-log 记录这次 Cursor 改动。
把下面的开发总结追加到项目简报。
整理这个项目最近三次变更的风险和后续。
```

---

## 7. 推荐命名规则

- 学科主页：`200_subjects/<学科名>/_<学科名>.md`
- 概念笔记：`100_learning/<学科名>/<概念名>.md`
- 错题笔记：`100_learning/<学科名>/错题_<题目关键词>.md`
- 日报：`100_learning/daily/YYYY-MM-DD.md`
- 项目简报：`500_projects/<项目名>/开发简报.md`
- 输出作品：`700_outputs/<主题>-<版本>.md`

---

## 8. 开源和隐私边界

这个模板仓库应该提交：

- 目录结构。
- 空白说明页。
- Obsidian 可共享配置。
- Templater 模板。
- Skills 和方法文档。

不应该提交：

- 个人笔记、日报、项目经历。
- PDF、截图、课程原文和版权材料。
- `.obsidian/plugins/` 插件源码。
- `.obsidian/workspace.json` 本地布局。
- `.claudian/sessions/`、AI 对话记录。
- API key、token、账号信息、本地路径。
