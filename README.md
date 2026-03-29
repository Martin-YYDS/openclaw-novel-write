# Novel Write - OpenClaw 小说创作助手

基于 [novel-writer-skills](https://github.com/wordflowlab/novel-writer-skills) 改编的 OpenClaw Skill，基于七步方法论的 AI 小说创作系统，支持都市、古代、玄幻、悬疑等多种题材。

## 快速开始

```
1. /novel init [项目名]      # 初始化项目
2. /novel constitution        # 创建宪法 + 设置风格
3. /novel specify             # 定义故事规格
4. /novel clarify             # 澄清关键决策
5. /novel plan                # 制定创作计划
6. /novel track-init          # 初始化追踪系统
7. /novel tasks               # 生成任务清单
8. /novel write 第1章         # 开始写作！
```

## 风格设置

constitution 步骤中必须选择风格：

| 选项 | 说明 |
|------|------|
| 1️⃣ 选择预设风格 | 自然人声、网文爽文、文学质感、古风典雅、极简白描 |
| 2️⃣ 提供参考作品 | AI 分析对标作品风格 |
| 3️⃣ 自定义描述 | 描述你的风格偏好 |

## 主要功能

- **七步方法论**：从规划到写作的完整流程
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
- `styles/` - 写作风格
- `requirements/` - 写作规范

## 安装

```bash
clawhub install novel-write
```

## 更多信息

参见 [SKILL.md](./SKILL.md)

## 致谢

本 Skill 基于 [wordflowlab/novel-writer-skills](https://github.com/wordflowlab/novel-writer-skills) 改编，继承了其七步方法论和写作知识库。
