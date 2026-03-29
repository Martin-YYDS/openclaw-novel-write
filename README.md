# Novel Write - OpenClaw 小说创作助手

基于 [novel-writer-skills](https://github.com/wordflowlab/novel-writer-skills) 改编的 OpenClaw Skill。

## 开始创作

### 第一步：初始化项目

```
/novel init 项目名
```

自动创建项目目录结构和追踪文件。

---

### 第二步：创建宪法 + 风格设置

```
/novel constitution
```

1. 描述你的写作风格偏好
2. AI 分析并推荐预设风格
3. 确认或修改推荐结果

---

### 第三步：定义故事规格

```
/novel specify
```

1. 自由描述你的故事想法（题材、类型、主角、冲突等）
2. AI 自动分析并加载对应知识库
3. 确认或修改分析结果

---

### 第四步：澄清关键决策

```
/novel clarify
```

回答 5 个关键问题，确保创作方向清晰。

---

### 第五步：制定创作计划

```
/novel plan
```

生成章节架构、线索分布、伏笔设计、节奏规划。

---

### 第六步：初始化追踪系统

```
/novel track-init
```

根据计划填充角色状态、关系网络、情节追踪。

---

### 第七步：生成任务清单

```
/novel tasks
```

按卷分拆任务，细化到每章节，含字数要求。

---

### 开始写作

```
/novel write 第1章
```

**前置条件**：必须完成以上 7 步。

每次写作后自动执行 `/novel track --check` 追踪验证。
每 5 章自动执行 `/novel analyze` 质量分析。

---

## 命令一览

| 命令 | 说明 |
|------|------|
| `/novel init [项目名]` | 初始化项目 |
| `/novel constitution` | 创建宪法 + 风格设置 |
| `/novel specify` | 定义故事规格 |
| `/novel clarify` | 澄清关键决策 |
| `/novel plan` | 制定创作计划 |
| `/novel track-init` | 初始化追踪系统 |
| `/novel tasks` | 生成任务清单 |
| `/novel write [章节]` | 执行写作 |
| `/novel track --check` | 追踪验证 |
| `/novel analyze` | 质量分析 |

---

## 安装

```bash
clawhub install openclaw-novel-write
```

---

## 致谢

本 Skill 基于 [wordflowlab/novel-writer-skills](https://github.com/wordflowlab/novel-writer-skills) 改编。
