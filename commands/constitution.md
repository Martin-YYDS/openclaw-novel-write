# /novel constitution - 创建创作宪法

## 触发方式

```
/novel constitution [创作原则描述]
```

或对话式：
```
创建创作宪法
定义我的小说创作原则
```

---

## 目标

建立小说创作的核心原则和价值观，形成创作的"宪法"文件。这些原则将指导后续所有创作决策。

---

## 执行步骤

### 1. 检查现有文档

**先检查风格参考文档**（如通过历史分析生成）：
```bash
test -f memory/style-reference.md && echo "exists" || echo "not-found"
```

**再检查现有宪法**：
```bash
test -f memory/constitution.md && echo "exists" || echo "not-found"
```

- 如果存在：读取并准备更新
- 如果不存在：准备创建新宪法

---

### 2. 收集创作原则

基于用户输入，收集以下维度的原则：

#### 核心价值观
- 作品要传递什么核心理念？
- 什么是绝对不能违背的底线？
- 创作的根本目的是什么？

#### 质量标准
- 逻辑一致性要求
- 文字质量标准
- 更新频率承诺
- 完成度保证

#### 约束条件
- 禁止出现的内容
- 必须包含的元素
- 敏感话题处理方式

---

### 3. ⚠️ 强制风格设置

**在生成宪法前，必须完成风格设置**。

向用户展示以下选项：

```
━━━━━━━━━━━━━━━━━━━━━━━━━━
🎨 风格参考设置（必须）

在开始创作前，我需要了解您的写作风格偏好。

请选择：

1️⃣ 选择预设风格（快速）
   - 自然人声（natural-voice）
   - 网文爽文（web-novel）
   - 文学质感（literary）
   - 古风典雅（ancient-style）
   - 极简白描（minimal）

2️⃣ 提供参考作品（推荐）
   "我的风格想参考《斗破苍穹》"
   我会分析对标作品的风格特点并生成风格参考

3️⃣ 自定义描述
   直接描述您的风格偏好：
   "口语化、短句多、节奏快、金手指要爽"

请回复 1、2 或 3
━━━━━━━━━━━━━━━━━━━━━━━━━━
```

#### 选项1处理：预设风格

根据用户选择，记录预设风格（使用中文名称）：

| 用户看到的中文 | 实际配置值 |
|---------------|-----------|
| 自然人声 | natural-voice |
| 网文爽文 | web-novel |
| 文学质感 | literary |
| 古风典雅 | ancient-style |
| 极简白描 | minimal |

根据用户选择，在 `specification.md` 的 YAML frontmatter 中写入：
```yaml
writing-style: [实际配置值]
```

#### 选项2处理：参考作品

用户说出参考作品名称或上传参考章节后：
- 分析参考作品的风格特点（叙事节奏、句式特征、描写密度、情感基调）
- 生成 `memory/style-reference.md`：
  ```markdown
  # 风格参考
  
  ## 参考来源
  [作品名称]
  
  ## 风格特征分析
  - 叙事节奏：
  - 句式特征：
  - 描写密度：
  - 情感基调：
  
  ## 写作要点
  - 应该：
  - 避免：
  ```
- 在 `specification.md` 中写入：
  ```yaml
  writing-style: custom
  style-reference: memory/style-reference.md
  ```

#### 选项3处理：自定义描述

用户描述风格偏好后：
- 生成 `memory/style-reference.md`：
  ```markdown
  # 风格参考
  
  ## 用户定义
  [用户的原始描述]
  
  ## 解析后的风格特征
  [AI解析提炼的风格要点]
  ```
- 在 `specification.md` 中写入：
  ```yaml
  writing-style: custom
  style-reference: memory/style-reference.md
  ```

---

### 4. 生成宪法文件

输出到 `memory/constitution.md`

```markdown
# 创作宪法

_本文件是不可妥协的创作原则，所有创作决策必须遵循。_

## 风格设置

- **风格类型**：[preset/custom]
- **预设风格**：[自然人声/网文爽文/文学质感/古风典雅/极简白描]
- **风格参考**：[memory/style-reference.md 路径，如有]

## 核心价值观

[作品理念、根本目的、绝对底线]

## 质量标准

[一致性要求、文字标准、完稿承诺]

## 约束清单

[禁止内容、必备元素、敏感话题]

## 创作哲学

[你对这部作品的深层理解]
```

---

### 5. 确认和迭代

- 向用户展示草稿（包含风格设置部分）
- 根据反馈调整
- 最终确认后保存

---

## 输出

| 文件 | 说明 |
|------|------|
| `memory/constitution.md` | 创作宪法（包含风格设置） |
| `memory/style-reference.md` | 风格参考（如选择选项2或3） |
| `specification.md`（更新） | YAML frontmatter 写入 writing-style |

---

## 提示下一步

宪法创建完成后，建议执行：
```
/novel specify - 开始定义故事规格
```
