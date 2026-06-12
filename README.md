# AI 制片厂 · AI Studio

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Version](https://img.shields.io/badge/version-v1.3-blue)](#)
[![Claude Code](https://img.shields.io/badge/Claude%20Code-compatible-blueviolet)](https://claude.ai/code)
[![Codex](https://img.shields.io/badge/Codex%20CLI-compatible-green)](https://github.com/openai/codex)

![AI 制片厂 Banner](assets/banner_cinematic.png)

> 用电影工业的分工逻辑做短视频：AI 负责执行，你负责判断。

---

## 这是什么

AI 制片厂是一套运行在 AI 编程工具（Claude Code / Codex）上的短视频制作系统。

它把电影工厂的角色分工移植进来：研究员、制片人、编剧、导演、美术指导、分镜师、配音、剪辑、宣发、数据分析师——10 个角色各司其职，每一步 AI 先执行、先自检，你只做品质判断。系统有记忆（频道配置持久化），有规则（Layer 1 自动守），有闭环（数据分析 → 配置迭代）。

和"让 AI 帮我写脚本"的本质区别：**这不是一次性生成，这是建一个自己的制片厂**。

![系统架构蓝图](assets/banner_blueprint.png)

→ 详细介绍见 [`介绍文档.md`](介绍文档.md)

---

## 前提条件（必读）

在开始之前，你需要：

| 工具 | 用途 | 获取方式 |
|------|------|---------|
| **Claude Code** | 运行整套系统 | [claude.ai/code](https://claude.ai/code) |
| **Claude Pro 或 Max 订阅** | Claude Code 的使用前提 | [claude.ai](https://claude.ai) |
| **Node.js** | Claude Code 的运行依赖 | [nodejs.org](https://nodejs.org) |

> 如果使用 **OpenAI Codex CLI**，则需要 Codex CLI + OpenAI API Key，无需 Claude 订阅。

---

## 快速开始

```bash
# 1. 克隆仓库
git clone https://github.com/Lucas-Ren/ai-studio.git
cd ai-studio

# 2. 建立你的个人配置文件（gitignored，不会随系统更新被覆盖）
cp User_Overrides.md User_Overrides.local.md

# 3. 启动 Claude Code
claude
```

启动后，系统自动检测到 `Projects/` 为空，进入初始化引导。用一段话描述你想做的频道，AI 帮你整理成配置文件。

确认配置后，输入 `生成选题` 开始第一期。

→ 详细操作步骤见 [`使用说明.md`](使用说明.md)

---

## 更新系统

```bash
git pull
```

`User_Overrides.local.md` 和 `Projects/` 已在 `.gitignore` 中，**不会被覆盖**。

---

## 支持的 AI 工具

| 工具 | 入口文件 |
|------|---------|
| Claude Code | `CLAUDE.md` |
| OpenAI Codex CLI | `AGENTS.md` |

两个工具的系统规则统一由 `_System/AI_Studio_Core.md` 管理，行为完全一致。

---

## 文件结构

```
├── CLAUDE.md                    ← Claude Code 入口（2行）
├── AGENTS.md                    ← Codex 入口（2行）
├── _System/
│   └── AI_Studio_Core.md        ← 系统核心规则（唯一需要维护的系统文件）
├── _Templates/                  ← 频道配置模板
├── _Config/                     ← API 配置说明
├── 00_Researcher/ ~ 10_Analyst/ ← 各角色 Skill 文件
├── User_Overrides.md            ← 个人调整模板（复制为 .local.md 后填写）
└── Projects/                    ← 你的频道内容（gitignored）
    └── [频道名]/
        ├── Channel_Config.md
        ├── 01_Topics/ ~ 05_Edit/
        ├── 10_Analytics/
        └── media/
```

---

## 5 种内容类型

| 类型 | 适合做什么 |
|------|-----------|
| 知识讲解 | 用框架/规律重新解释世界，AI 生图辅助 |
| 历史/人物故事 | 按时间线或人物讲具体历史，AI 生图还原时代 |
| 商业故事 | 一家公司或创业者的命运，商业逻辑+人性 |
| 创意叙事 | 原创虚构短篇，科幻/物品自述/拟人化视角 |
| 睡前故事 | 舒缓节奏，声音为主，画面极简，助眠陪伴 |

---

## License

MIT License · 详见 [LICENSE](LICENSE)
