---
name: discovery-process
description: Run a full discovery cycle from problem hypothesis to validated solution. Use when a team needs a structured path through framing, interviews, synthesis, and experiments.
intent: >-
  Guide product managers through a complete discovery cycle—from initial problem hypothesis to validated solution—by orchestrating problem framing, customer interviews, synthesis, and experimentation skills into a structured process. Use this to systematically explore problem spaces, validate assumptions, and build confidence before committing to full development—avoiding "build it and they will come" syndrome and ensuring you're solving real customer problems.
type: workflow
theme: discovery-research
best_for:
  - "Running a full discovery cycle from hypothesis to validated solution"
  - "Investigating a retention or churn problem systematically"
  - "Setting up continuous discovery as an ongoing practice"
scenarios:
  - "I have a hypothesis that B2B customers struggle with onboarding and want to validate it before building anything"
  - "Our activation rate dropped 15% this quarter and I need to run discovery to find out why"
estimated_time: "30-60 min"
---


## Purpose
指导产品经理完成一个完整的发现流程——从最初的问题假设到经过验证的解决方案——通过将问题定义、客户访谈、综合分析和实验等技能协调成一个结构化流程。使用此工作流系统地探索问题空间、验证假设，在投入完整开发之前建立信心——避免"建好了客户自然会来"的综合症，确保你解决的是真实的客户问题。

这不是一次性的研究项目——而是一个与交付并行运行的持续发现实践，通常每个季度进行1-2个发现循环。

## Key Concepts

### 什么是发现流程？

发现流程（Teresa Torres, Marty Cagan）是一种在构建之前探索问题空间和验证解决方案的结构化方法。它包含：

1. **定义问题** — 明确你要研究什么以及为什么
2. **进行研究** — 收集定性和定量证据
3. **综合洞察** — 识别模式、痛点和机会点
4. **生成解决方案** — 探索多个解决方案选项
5. **验证解决方案** — 通过实验测试假设
6. **决策与文档** — 决定构建、转向或放弃

### 为什么这有效
- **降低产品决策风险：** 在昂贵的构建之前测试假设
- **以客户为中心：** 将决策建立在真实的客户问题之上，而非内部观点
- **迭代式：** 通过小实验逐步建立信心
- **快速学习：** 尽早发现"不可行"信号，节省无效努力

### Anti-Patterns（这不是什么）
- **不是瀑布式研究：** 发现是持续运行的，不是在开发前进行一次
- **不是用户测试：** 发现验证问题；测试验证解决方案
- **不是交付的替代品：** 发现为交付提供信息，但不能取代交付

### 何时使用
- 探索新的产品/功能领域
- 调查留存或流失问题
- 在路线图承诺之前验证战略举措
- 持续发现（每周与客户接触）

### 何时不使用
- 对于已经充分理解的问题（转向执行）
- 当利益相关者已经承诺了某个解决方案（先解决对齐问题）
- 对于战术性的 bug 修复或技术债务（不需要发现）

---

### Facilitation Source of Truth

将此工作流作为引导式对话运行时，使用 [`workshop-facilitation`](../workshop-facilitation/SKILL.md) 作为交互协议。

它定义了：
- 会议预热 + 入场模式（引导式、上下文转储、最佳猜测）
- 单问题轮次，使用通俗语言的提示
- 进度标签（例如，Context Qx/8 和 Scoring Qx/5）
- 中断处理和暂停/恢复行为
- 决策点的编号建议
- 常规问题的快速选择编号响应选项（在有用时包含"其他（请说明）"）

本文件定义了工作流顺序和特定领域的输出。如果存在冲突，请遵循本文件的工作流逻辑。

## Application

使用 `template.md` 获取完整的填写结构。

此工作流在 **2-4 周** 内协调 **6 个阶段**，使用多个组件和交互式技能。

---

## Phase 1: 定义问题（Day 1-2）

**目标：** 明确你要研究什么，谁受到影响，以及成功标准。

### Activities

**1. 运行问题定义画布**
- **使用：** `skills/problem-framing-canvas/SKILL.md`（交互式 - MITRE）
- **参与者：** PM、设计、工程负责人
- **时长：** 120 分钟
- **输出：** 问题陈述 + "我们如何才能"问题

**2. 创建正式问题陈述**
- **使用：** `skills/problem-statement/SKILL.md`（组件）
- **参与者：** PM
- **时长：** 30 分钟
- **输出：** 带假设的结构化问题陈述

**3. 定义原型用户画像（如需要）**
- **使用：** `skills/proto-persona/SKILL.md`（组件）
- **适用场景：** 目标客户细分不明确时
- **时长：** 60 分钟
- **输出：** 假设驱动的用户画像

**4. 绘制待完成工作地图（如需要）**
- **使用：** `skills/jobs-to-be-done/SKILL.md`（组件）
- **适用场景：** 客户动机不明确时
- **时长：** 60 分钟
- **输出：** JTBD 陈述

### Phase 1 输出

- **问题假设：** "我们相信[用户画像]正在与[问题]作斗争，因为[根本原因]，导致[后果]。"
- **研究问题：** 通过发现要回答的 3-5 个问题
- **成功标准：** 什么可以验证/否定这个问题？

### 决策点 1：我们是否有足够的上下文开始研究？

**如果 是：** 进入阶段 2（研究规划）

**如果 否：** 先收集现有数据：
- 审查支持工单、流失调查、NPS 反馈
- 分析产品分析数据（流失点、使用模式）
- 审查竞品研究、市场趋势
- **时间影响：** +2-3 天

---

## Phase 2: 研究规划（Day 3）

**目标：** 设计研究方法招募参与者，准备访谈指南。

### Activities

**1. 准备发现访谈**
- **使用：** `skills/discovery-interview-prep/SKILL.md`（交互式）
- **参与者：** PM、设计
- **时长：** 90 分钟
- **输出：** 包含方法论、问题、需要避免的偏见的访谈计划

**2. 招募参与者**
- **目标：** 每个发现循环 5-10 个客户（Teresa Torres：持续发现 = 每周 1 次访谈）
- **细分：** 聚焦阶段 1 中的用户画像
- **招募渠道：**
  - 现有客户（邮件、应用内提示）
  - 流失客户（退出访谈）
  - 冷联系（LinkedIn、社区）
- **激励：** $50-100 礼品卡或产品积分
- **时长：** 2-3 天（与阶段 1 并行）

**3. 安排访谈**
- **格式：** 每次访谈 45-60 分钟（30-40 分钟对话 + 缓冲）
- **时间线：** 分布在 1-2 周内
- **录制：** 获得同意，录制用于综合分析

### Phase 2 输出

- **访谈指南：** 5-7 个开放式问题（Mom Test 风格）
- **参与者名单：** 5-10 个已安排的访谈
- **综合计划：** 如何捕获和分析洞察

---

## Phase 3: 进行研究（Week 1-2）

**目标：** 通过客户访谈收集定性证据。

### Activities

**1. 进行发现访谈**
- **方法论：** 来自 `skills/discovery-interview-prep/SKILL.md`（问题验证、JTBD、转换访谈等）
- **参与者：** PM + 可选观察者（设计、工程）
- **时长：** 在 1-2 周内进行 5-10 次访谈
- **焦点领域：**
  - 过去行为（而非假设）："告诉我你上次[遇到这个问题]是什么时候"
  - 变通方法："你目前如何处理这个问题？"
  - 尝试过的替代方案："你尝试过其他解决方案吗？为什么放弃了？"
  - 痛苦强度："这花费了你多少时间/金钱？"

**2. 做结构化笔记**
- **模板：**
  - 参与者：[姓名、角色、公司规模]
  - 背景：他们何时/何地遇到问题
  - 行为：他们做什么，步骤是什么
  - 痛点：挫败感、阻碍因素
  - 变通方法：目前的解决方案
  - 引言：客户的原话
  - 洞察：模式、惊喜

**3. 审查支持工单和分析（并行）**
- **支持工单：** 按主题标记（入职、功能困惑、bug）
- **分析：** 识别流失点、功能使用、队列行为
- **调查：** 审查 NPS 评论、退出调查、功能请求

### Phase 3 输出

- **访谈记录：** 录制会话 + 详细笔记
- **支持工单主题：** 按频率排名的前 10 个问题
- **分析洞察：** 行为定量数据（例如，"60% 在步骤 3 放弃入职"）

### 决策点 2：我们是否达到了饱和？

**饱和度 = 相同的痛点在 3+ 次访谈中出现，没有新洞察**

**如果 是**（5-7 次访谈后饱和）：进入阶段 4（综合分析）

**如果 否**（仍在学习新东西）：再安排 3-5 次访谈
- **时间影响：** +1 周

---

## Phase 4: 综合洞察（Week 2 末）

**目标：** 识别模式，优先排序痛点，绘制机会点。

### Activities

**1. 亲和图（主题分析）**
- **方法：**
  - 将每个洞察/引言写在便签上
  - 按主题分组（例如"入职困惑"、"价格反对"、"移动端访问"）
  - 统计频率（多少客户提到每个主题）
- **参与者：** PM、设计、可选工程
- **时长：** 90-120 分钟
- **输出：** 带频率计数的主题聚类

**2. 创建客户旅程图（可选）**
- **使用：** `skills/customer-journey-mapping-workshop/SKILL.md`（交互式）
- **适用场景：** 痛点跨越多个阶段时（发现、尝试、购买、使用、支持）
- **时长：** 90 分钟
- **输出：** 按影响力排序的机会点旅程图

**3. 优先排序痛点**
- **标准：**
  - **频率：** 有多少客户提到这个？
  - **强度：** 有多痛苦？（浪费的时间、损失的钱、情绪挫败）
  - **战略契合度：** 解决这个问题是否符合业务目标？
- **方法：** 每个痛点按频率、强度、战略契合度打分（1-5 分）
- **输出：** 要解决的排名前 3-5 的痛点列表

**4. 更新问题陈述**
- **使用：** `skills/problem-statement/SKILL.md`（组件）
- **根据研究优化：** 初始假设是否成立？如需要进行调整。
- **输出：** 经过验证的问题陈述

### Phase 4 输出

- **亲和图：** 带频率的主题
- **前 3-5 个痛点：** 按频率 × 强度 × 战略契合度排序
- **客户引言：** 每个痛点 3-5 条原话
- **经过验证的问题陈述：** 基于证据优化

---

## Phase 5: 生成和验证解决方案（Week 3）

**目标：** 探索解决方案选项，设计实验，验证假设。

### Activities

**1. 生成机会解决方案树**
- **使用：** `skills/opportunity-solution-tree/SKILL.md`（交互式）
- **输入：** 阶段 4 的前 3 个痛点
- **参与者：** PM、设计、工程负责人
- **时长：** 90 分钟
- **输出：** 3 个机会点，每个机会点 3 个解决方案，POC 推荐

**备选：使用精益 UX 画布**
- **使用：** `skills/lean-ux-canvas/SKILL.md`（交互式）
- **适用场景：** 比起 OST 更喜欢假设驱动的方法
- **输出：** 要测试的假设、最小实验

**2. 设计实验**
- **对于每个解决方案：** 定义"了解下一个最重要的事情需要最少的工作是什么？"
- **实验类型：**
  - **礼宾服务测试：** 手动向 10 个客户提供解决方案，观察
  - **原型测试：** 可点击模型，用 10 个用户进行可用性测试
  - **着陆页测试：** 假门测试（展示功能，衡量兴趣）
  - **A/B 测试：** 构建最小版本，用 50% 的用户测试
- **成功标准：** 什么指标/行为可以验证假设？

**3. 运行实验**
- **时间线：** 每个实验 1-2 周
- **参与者：** PM + 设计（原型），工程（A/B 测试）
- **输出：** 定量和定性验证数据

### Phase 5 输出

- **解决方案选项：** 3-9 个解决方案（每个机会点 3 个）
- **实验结果：** 假设是被验证还是被否定？
- **客户反馈：** 对原型/概念的定性反应

### 决策点 3：实验是否验证了解决方案？

**如果 是**（经过验证）：进入阶段 6（决策与文档）

**如果 否**（被否定）：
- 转向下一个解决方案选项
- 用调整后的方法重新运行实验
- **时间影响：** +1-2 周

---

## Phase 6: 决策与文档（Week 3-4 末）

**目标：** 承诺构建，文档化决策，传达给利益相关者。

### Activities

**1. 做出通过/不通过决定**
- **标准：**
  - 问题是否被验证？（阶段 3-4）
  - 解决方案是否被验证？（阶段 5）
  - 战略契合度？（是否符合业务目标）
  - 可行性？（工程能力、技术复杂性）
- **决定：**
  - **通过：** 进入路线图，编写 Epic/用户故事
  - **转向：** 探索替代解决方案
  - **放弃：** 降低优先级，现在不值得解决

**2. 定义 Epic 假设（如通过）**
- **使用：** `skills/epic-hypothesis/SKILL.md`（组件）
- **参与者：** PM
- **时长：** 每个 Epic 60 分钟
- **输出：** 带成功标准的 Epic 假设陈述

**3. 编写 PRD（如通过）**
- **使用：** `skills/prd-development/SKILL.md`（工作流）
- **参与者：** PM
- **时长：** 1-2 天
- **输出：** 包含问题、解决方案、成功指标的结构化 PRD

**4. 传达发现**
- **格式：** 30 分钟汇报，涵盖：
  - 问题验证（阶段 3-4 洞察）
  - 解决方案验证（阶段 5 实验）
  - 建议（通过/转向/放弃）
- **参与者：** 高管、产品领导层、关键利益相关者
- **输出：** 对下一步达成共识

### Phase 6 输出

- **决定：** 通过、转向或放弃
- **Epic 假设：**（如通过）可测试的 Epic 陈述
- **PRD：**（如通过）正式产品需求文档
- **利益相关者共识：** 高管对建议的认同

---

## Complete Workflow: End-to-End Summary

```
Week 1:
├─ Day 1-2: Frame the Problem
│  ├─ skills/problem-framing-canvas/SKILL.md (120 min)
│  ├─ skills/problem-statement/SKILL.md (30 min)
│  └─ [Optional] skills/proto-persona/SKILL.md, skills/jobs-to-be-done/SKILL.md
│
├─ Day 3: Research Planning
│  ├─ skills/discovery-interview-prep/SKILL.md (90 min)
│  ├─ Recruit participants (2-3 days)
│  └─ Schedule 5-10 interviews
│
└─ Day 4-5: Conduct Research (Start)
   └─ First 2-3 customer interviews

Week 2:
├─ Day 1-3: Conduct Research (Continue)
│  └─ Remaining customer interviews (3-7 more)
│
├─ Day 4-5: Synthesize Insights
│  ├─ Affinity mapping (120 min)
│  ├─ [Optional] skills/customer-journey-mapping-workshop/SKILL.md (90 min)
│  ├─ Prioritize pain points
│  └─ Update problem statement
│
└─ Decision: Reached saturation? (if NO, +1 week more interviews)

Week 3:
├─ Day 1-2: Generate & Validate Solutions
│  ├─ skills/opportunity-solution-tree/SKILL.md (90 min)
│  └─ Design experiments
│
├─ Day 3-5: Run Experiments
│  ├─ Concierge tests, prototypes, or A/B tests
│  └─ Gather validation data
│
└─ Decision: Validated? (if NO, pivot to next solution, +1-2 weeks)

Week 4:
└─ Decide & Document
   ├─ Make GO/NO-GO decision
   ├─ [If GO] skills/epic-hypothesis/SKILL.md (60 min per epic)
   ├─ [If GO] skills/prd-development/SKILL.md (1-2 days)
   └─ Communicate findings (30 min readout)
```

**总时间投入：**
- **快速通道：** 3 周（5 次访谈，1 个实验）
- **典型：** 4 周（7-10 次访谈，1-2 个实验）
- **彻底：** 6-8 周（10+ 次访谈，多轮实验）

---

## Examples

参见 `examples/sample.md` 获取完整的发现流程示例。

迷你示例节选：

```markdown
**Problem:** Onboarding drop-off due to jargon
**Insight:** 6/10 users quit at step 3
**Decision:** Go with guided checklist experiment
```

## Common Pitfalls

### Pitfall 1: 跳过客户访谈
**症状：** 仅依赖分析数据和支持工单，没有定性研究

**后果：** 错过行为背后的"为什么"，构建错误的解决方案

**修复：** 每个发现循环始终访谈 5-10 个客户（即使你有数据）

---

### Pitfall 2: 问引导性问题
**症状：** "如果我们构建[功能 X]，你会使用吗？"

**后果：** 确认偏误，客户出于礼貌说"是"

**修复：** 使用来自 `skills/discovery-interview-prep/SKILL.md` 的 Mom Test 问题（聚焦过去行为）

---

### Pitfall 3: 未达到饱和
**症状：** 访谈 2-3 个客户后宣布发现完成

**后果：** 样本量小，不具代表性

**修复：** 继续访谈直到相同的模式在 3+ 个客户中出现（通常最少 5-7 次访谈）

---

### Pitfall 4: 分析瘫痪
**症状：** 花 6 周综合洞察，从未转向解决方案

**后果：** 没有交付，团队失去动力

**修复：** 将发现限制在 3-4 周；阶段 6 之后转向执行

---

### Pitfall 5: 将发现作为一次性活动
**症状：** 在构建之前运行一次发现，然后停止

**后果：** 错过不断变化的客户需求、市场变化

**修复：** 持续发现（Teresa Torres）：每周 1 次客户访谈，持续进行

---

## References

### Related Skills（由此工作流编排）

**Phase 1：**
- `skills/problem-framing-canvas/SKILL.md`（交互式）
- `skills/problem-statement/SKILL.md`（组件）
- `skills/proto-persona/SKILL.md`（组件，可选）
- `skills/jobs-to-be-done/SKILL.md`（组件，可选）

**Phase 2：**
- `skills/discovery-interview-prep/SKILL.md`（交互式）

**Phase 4：**
- `skills/customer-journey-mapping-workshop/SKILL.md`（交互式，可选）

**Phase 5：**
- `skills/opportunity-solution-tree/SKILL.md`（交互式）
- `skills/lean-ux-canvas/SKILL.md`（交互式，备选）

**Phase 6：**
- `skills/epic-hypothesis/SKILL.md`（组件）
- `skills/prd-development/SKILL.md`（工作流）

### External Frameworks
- Teresa Torres, *Continuous Discovery Habits* (2021) — 每周客户接触、OST 框架
- Rob Fitzpatrick, *The Mom Test* (2013) — 如何提出好的访谈问题
- Marty Cagan, *Inspired* (2017) — 产品发现原则

### Dean's Work
- Productside Blueprint — 战略性发现流程
- [If Dean has discovery resources, link here]

---

**Skill type:** Workflow
**Suggested filename:** `discovery-process.md`
**Suggested placement:** `/skills/workflows/`
**Dependencies:** 在 6 个阶段中编排 10+ 个组件和交互式技能
