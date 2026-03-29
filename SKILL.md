---
name: openclaw-novel-write
version: 0.0.1-alpha
description: OpenClaw 小说创作 Skill - 基于七步方法论的 AI 辅助写作系统
tags:
  - novel
  - writing
  - creative-writing
  - chinese
  - fiction
author: MartinYing
homepage: https://clawhub.ai
based-on: https://github.com/wordflowlab/novel-writer-skills
acknowledgments: |
  本 Skill 基于 wordflowlab/novel-writer-skills 改编，
  继承了其七步方法论和写作知识库。
---

# Novel Write Skill - OpenClaw 小说创作系统

## 概述

基于七步方法论的 OpenClaw Skill，用于在 OpenClaw 环境下完成 AI 辅助小说创作。支持都市、古代、玄幻、悬疑等多种题材，内置反AI检测写作规范。

## 核心能力

- 📚 **七步方法论**：从宪法到写作的完整创作流程
- 🔍 **自动追踪**：角色状态、情节进度、线索管理
- ✍️ **反AI检测**：内置自然化写作规范，避免AI味
- 📊 **质量分析**：一致性、节奏、视角、对话检查
- 🎯 **按卷分拆**：任务细化到章节，含字数要求

## 七步方法论

```
1. /novel init           → 初始化项目
2. /novel constitution   → 创建创作宪法 + 风格设置
3. /novel specify        → 定义故事规格
4. /novel clarify       → 澄清关键决策
5. /novel plan          → 制定创作计划
6. /novel track-init    → 初始化追踪系统
7. /novel tasks         → 分解任务清单
                          ↓
开始写作 ↓
          ↓
8. /novel write [章节]  → 执行写作
9. /novel track --check → 自动追踪验证
10. /novel analyze      → 每5章质量分析
```

## 核心命令

### /novel init [项目名]
初始化新小说项目，创建标准目录结构。
- 自动创建追踪JSON文件
- 复制写作知识库

### /novel constitution
创建创作宪法，定义核心原则。
- **必须**完成风格设置（选择预设/参考作品/自定义）

### /novel specify
定义故事规格（类型、角色、世界观、冲突等）

### /novel clarify
澄清关键决策（5个关键问题）

### /novel plan
制定创作计划（卷结构、章节、线索、伏笔、节奏）

### /novel track-init
从计划填充追踪系统（角色状态、关系网络、情节追踪）

### /novel tasks
生成按卷分拆的任务清单，含字数要求

### /novel write [章节编号]
执行章节写作。
- **必须先完成前7步**
- 自动加载风格和规范
- 遵循反AI写作规范

### /novel track --check
追踪验证（字数、角色一致性、情节进度）

### /novel analyze
综合质量分析（每5章自动触发）

## 写作知识库

| 目录 | 内容 |
|------|------|
| `genres/` | 5种小说类型知识（romance, mystery, revenge, historical, wuxia） |
| `styles/` | 写作风格（自然人声、网文爽文、文学质感、古风典雅、极简白描） |
| `requirements/` | 写作规范（反AI-v4、快节奏等） |

## 自动化规则

- **after_each_chapter**：每次写作后自动 `/novel track --check`
- **every_5_chapters**：自动 `/novel analyze`

## 项目结构

```
<项目名>/
├── memory/
│   ├── constitution.md          # 创作宪法
│   └── style-reference.md       # 风格参考
├── stories/
│   └── <项目>/
│       ├── specification.md     # 故事规格
│       ├── creative-plan.md     # 创作计划
│       ├── tasks.md             # 任务清单
│       └── content/             # 正文
│           └── volumeX/
│               └── chapter-XX.md
├── spec/
│   ├── knowledge/               # 项目知识库
│   └── tracking/                # 追踪文件
│       ├── character-state.json
│       ├── relationships.json
│       ├── plot-tracker.json
│       ├── progress.json
│       └── validation-rules.json
└── .claude/
    └── knowledge-base/          # 写作知识库
        ├── genres/
        ├── styles/
        └── requirements/
```

## 反AI检测写作规范

核心要点：
- 30%-50% 段落应为单句成段
- 每段控制在 50-100 字
- 避免 AI 高频词（唯一的、直到、弥漫、摇摇欲坠等）
- 具象化描写（具体时间、人物、数量、场景）

详见 `commands/write.md`

## 使用示例

```
用户: /novel init 我的小说
用户: /novel constitution
      → 选择风格：1（预设）
      → 选择：自然人声
用户: /novel specify
      → 都市言情、甜宠、双豪门
用户: /novel clarify
用户: /novel plan
用户: /novel track-init
用户: /novel tasks
用户: /novel write 第1章
      → 自动追踪 + track --check
用户: /novel write 第5章
      → 自动分析
```

## 依赖

- OpenClaw
- bash（用于辅助脚本）

## 版本

- v0.0.1-alpha：首次发布（alpha）
