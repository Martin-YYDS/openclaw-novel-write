# Novel Write - OpenClaw 小说创作助手

基于 [novel-writer-skills](https://github.com/wordflowlab/novel-writer-skills) 改编的 OpenClaw Skill，基于七步方法论的 AI 小说创作系统，支持都市、古代、玄幻、悬疑等多种题材。

## 快速开始

```
1. /novel init [项目名]      # 初始化项目
2. /novel constitution        # 创建宪法 + AI分析风格
3. /novel specify             # 定义故事规格（AI自动分析+确认）
4. /novel clarify             # 澄清关键决策
5. /novel plan                # 制定创作计划
6. /novel track-init          # 初始化追踪系统
7. /novel tasks               # 生成任务清单
8. /novel write 第1章         # 开始写作！
```

## AI 自动分析

**constitution** 和 **specify** 步骤中，AI 会自动分析您的描述并推荐：

- **风格设置**：根据您的偏好推荐预设风格（可修改）
- **类型判断**：根据您的描述自动识别小说类型并加载对应知识库
- **规范选择**：推荐适合的写作规范（可修改）

每一步都会展示分析结果，等待您确认后再继续。

## 主要功能

- **七步方法论**：从规划到写作的完整流程
- **AI 智能辅助**：自动分析风格和类型，加载对应知识库
- **自动追踪**：角色状态、情节进度、线索管理
- **反AI检测**：内置自然化写作规范
- **按卷分拆**：任务细化到章节，含字数要求

## 项目结构

```
<项目名>/
├── memory/                    # 创作宪法、风格参考
├── stories/<项目>/           # 规格、计划、任务、正文
├── spec/
│   ├── knowledge/            # 项目知识库
│   └── tracking/             # 追踪文件
└── .claude/
    └── knowledge-base/       # 写作知识库
```

## 写作知识库

- `genres/` - 5种小说类型
- `styles/` - 写作风格（5种预设）
- `requirements/` - 写作规范（反AI、快节奏、甜文等）

## 安装

```bash
clawhub install openclaw-novel-write
```

## 更多信息

参见 [SKILL.md](./SKILL.md)

## 致谢

本 Skill 基于 [wordflowlab/novel-writer-skills](https://github.com/wordflowlab/novel-writer-skills) 改编，继承了其七步方法论和写作知识库。
