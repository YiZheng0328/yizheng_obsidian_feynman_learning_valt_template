# Auto Setup Guide

> 无需手动配置 skills 或插件——下载、解压，剩下的交给 Codex / Claude。

## 1. 下载

从 [GitHub Releases](https://github.com/YiZheng0328/yizheng_obsidian_feynman_learning_valt_template/releases) 或仓库首页下载 ZIP 包，解压到本地目录。

## 2. 让 AI 配置 Obsidian Vault

### 用 Claude Code（推荐）

```bash
# 进入 vault 目录
cd feynman-learning-vault-template

# 启动 Claude
claude
```

Claude 启动后会自动读取 `.claude/skills/` 下的 skills 并加载。然后直接说：

```text
帮我根据 !_home.md 和 .obsidian/ 配置文件设置这个 vault。
```

Claude 会自动完成：
- 读取 `!_home.md` 理解工作流
- 加载 `math-feynman-learning`、`cpa-feynman-learning`、`feynman-german-beginner`、`project-brief-log` 四个 skills
- 检查 `.obsidian/community-plugins.json` 并提示你安装缺失的插件
- 确认 Templater 模板路径是否正确

### 用 Codex

```bash
# 进入 vault 目录
cd feynman-learning-vault-template

# 启动 Codex
codex
```

Codex 启动后会读取 `.codex/skills/`，同样直接说：

```text
帮我根据 !_home.md 配置学习工作台，加载 skills。
```

## 3. 用 Obsidian 打开

1. 打开 Obsidian → 「Open folder as vault」
2. 选择解压后的目录
3. Obsidian 会自动读取 `.obsidian/` 下的配置（外观、快捷键、社区插件列表等）
4. 进入设置 → 社区插件，按列表安装插件
5. 回到 `!_home.md`，开始学习

## 4. 验证安装

用以下请求验证 AI 端是否正常：

```text
使用 math-feynman-learning 帮我理解一个简单的数学概念：为什么负数乘以负数等于正数？
```

如果 AI 按费曼方式引导你先解释、再追问、最后整理笔记，说明配置成功。

---

## 文件结构说明

AI 能自行识别和配置，因为 vault 内已包含所有必要文件：

- `.claude/skills/` — Claude Code 的 skill 定义（4 个 skills）
- `.codex/skills/` — Codex 的 skill 定义（同上）
- `.obsidian/` — Obsidian 的可共享配置
- `templater/` — 7 种笔记模板
- `!_home.md` — 工作流总入口
- `README.md` — 仓库说明

手动复制 skills 到 AI 工具的全局 skills 目录也可以，但**不必要**——AI 启动时在 vault 目录内，skills 已经在工作范围内。
