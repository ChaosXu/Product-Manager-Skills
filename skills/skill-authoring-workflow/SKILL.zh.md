---
name: skill-authoring-workflow
description: 将原始PM内容转换为符合标准、可发布就绪的技能。在创建或更新仓库技能时不破坏标准时使用。
intent: >-
  创建或更新PM技能，避免混乱。此工作流将粗糙的笔记、工作坊内容或半成品的提示词转储转化为符合标准的 `skills/<skill-name>/SKILL.md` 资产，这些资产实际上能够通过验证并属于此仓库。
type: workflow
best_for:
  - "从笔记或源材料创建新的仓库技能"
  - "在保持标准完整的同时更新现有技能"
  - "在提交前运行完整的创作和验证工作流"
scenarios:
  - "帮我把这些工作坊笔记转化成一个新PM技能"
  - "我需要更新现有技能但不破坏仓库标准"
  - "我应该使用什么工作流在此仓库中创作新技能？"
---

## 目的

创建或更新PM技能，避免混乱。此工作流将粗糙的笔记、工作坊内容或半成品的提示词转储转化为符合标准的 `skills/<skill-name>/SKILL.md` 资产，这些资产实际上能够通过验证并属于此仓库。

当你想要发布一个新技能而不陷入"我觉得不错"的轮盘赌时使用它。

## 关键概念

### 优先自用（Dogfood First）

在发明自定义流程之前，先使用仓库原生工具和标准：

- `scripts/find-a-skill.sh`
- `scripts/add-a-skill.sh`
- `scripts/build-a-skill.sh`
- `scripts/test-a-skill.sh`
- `scripts/check-skill-metadata.py`

### 选择正确的创建路径

- **引导式向导（`build-a-skill.sh`）**：当你有一个想法但还没有最终文章时最佳。
- **内容优先生成器（`add-a-skill.sh`）**：当你已经有源内容时最佳。
- **手动编辑 + 验证**：适用于精简现有技能。

### 完成定义（无例外）

只有当以下条件都满足时，技能才算完成：

1. 前置matter有效（`name`、`description`、`intent`、`type`）
2. 部分顺序符合规范
3. 元数据限制被遵守（`name` <= 64 字符，`description` <= 200 字符）
4. 描述说明技能做什么以及何时使用
5. Intent携带更完整的仓库面向摘要，而不替代面向触发器的描述
6. 交叉引用可解析
7. README目录计数和表格已更新（如果添加/删除技能）

### 引导真相来源

当将此工作流作为引导式对话运行时，使用 [`workshop-facilitation`](../workshop-facilitation/SKILL.md) 作为交互协议。

它定义：

- 会议预告 + 进入模式（引导式、上下文转储、最佳猜测）
- 带通俗语言提示的一次一问式对话
- 进度标签（例如，Context Qx/8 和 Scoring Qx/5）
- 中断处理和暂停/恢复行为
- 决策点的编号推荐
- 常规问题的快速选择编号响应选项（有用时包含"其他（指定）"）

此文件定义工作流顺序和领域特定输出。如果存在冲突，请遵循此文件的工作流逻辑。

## 应用

### 阶段 1：预检（避免重复工作）

1. 搜索重叠的技能：

```bash
./scripts/find-a-skill.sh --keyword "<topic>"
```

2. 决定类型：
- **组件**：一个产物/模板
- **交互式**：3-5 个适应性问题和编号选项
- **工作流**：多阶段编排

### 阶段 2：生成草稿

如果你有源材料：

```bash
./scripts/add-a-skill.sh research/your-framework.md
```

如果你想要引导式提示：

```bash
./scripts/build-a-skill.sh
```

### 阶段 3：精简技能

手动审查：

- 清晰的"何时使用"指导
- 一个具体示例
- 一个明确的反模式
- 无填充语或模糊的顾问式言论

### 阶段 4：严格验证

在考虑提交之前运行严格检查：

```bash
./scripts/test-a-skill.sh --skill <skill-name> --smoke
python3 scripts/check-skill-metadata.py skills/<skill-name>/SKILL.md
python3 scripts/check-skill-triggers.py skills/<skill-name>/SKILL.md --show-cases
```

### 阶段 5：与仓库文档集成

如果是新技能：

1. 将其添加到正确的 README 类别表中
2. 更新技能总数和类别计数
3. 验证链接路径可解析

### 阶段 6：可选打包

如果面向 Claude 自定义技能上传：

```bash
./scripts/zip-a-skill.sh --skill <skill-name>
# 或者打包一种类型：
./scripts/zip-a-skill.sh --type component --output dist/skill-zips
# 或者使用策划的起始预设：
./scripts/zip-a-skill.sh --preset core-pm --output dist/skill-zips
```

## 示例

### 示例：将工作坊笔记转化为技能

输入：`research/pricing-workshop-notes.md`
目标：新的交互式 advisor

```bash
./scripts/add-a-skill.sh research/pricing-workshop-notes.md
./scripts/test-a-skill.sh --skill <new-skill-name> --smoke
python3 scripts/check-skill-metadata.py skills/<new-skill-name>/SKILL.md
```

预期结果：

- 新技能文件夹存在
- 技能通过结构和元数据检查
- README 目录条目已添加/更新

### 反模式示例

"我们写了一个很酷的技能，跳过验证，忘记 README 计数，然后还是发布了。"

结果：

- 断开的引用
- 不一致的目录编号
- 贡献者和用户感到困惑

## 常见陷阱

- 发布的是感觉，而不是标准。
- 当任务实际上是一个组件模板时选择 `workflow`。
- 超出上传限制的冗长描述。
- 描述说明技能是什么但没有说明 Claude 何时应该触发它。
- 描述在 200 字符限制处静默截断，半途而废。
- 让 `intent` 成为弱触发描述的替代品。
- 忘记在添加技能后更新 README 计数。
- 将生成的输出视为最终版本而不进行审查。

## 参考

- `README.md`
- `AGENTS.md`
- `CLAUDE.md`
- `docs/Building PM Skills.md`
- `docs/Add-a-Skill Utility Guide.md`
- Anthropic 的 [Building Skills for Claude 完整指南](https://resources.anthropic.com/hubfs/The-Complete-Guide-to-Building-Skill-for-Claude.pdf)
- `scripts/add-a-skill.sh`
- `scripts/build-a-skill.sh`
- `scripts/find-a-skill.sh`
- `scripts/test-a-skill.sh`
- `scripts/check-skill-metadata.py`
- `scripts/check-skill-triggers.py`
- `scripts/zip-a-skill.sh`
