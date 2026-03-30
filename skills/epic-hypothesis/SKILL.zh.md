---
name: epic-hypothesis
description: 将 epic 框架为可测试的假设，包含目标用户、预期成果和验证方法。用于在路线图、发现或交付规划之前定义重大举措。
intent: >-
  使用 if/then 结构将 epic 框架为可测试的假设，阐述动作或解决方案、目标受益者、预期成果以及如何验证成功。使用此技能通过明确假设、定义轻量级实验（"微小的发现行为"）和在承诺全面构建之前建立可衡量的成功标准来管理产品开发中的不确定性。
type: component
---

## 目的

使用 if/then 结构将 epic 框架为可测试的假设，阐述动作或解决方案、目标受益者、预期成果以及如何验证成功。使用此技能通过明确假设、定义轻量级实验（"微小的发现行为"）和在承诺全面构建之前建立可衡量的成功标准来管理产品开发中的不确定性。

这不是需求规格——它是你正在测试的假设，而不是你承诺交付的功能。

## 关键概念

### Epic 假设框架

灵感来自 Tim Herbig 的精益 UX 假设格式，结构是：

**If/Then 假设：**
- **If we** [代表目标画像采取的动作或解决方案]
- **for** [目标画像]
- **Then we will** [获得或实现 desirable 的成果或待完成的工作]

**微小的发现行为实验：**
- **We will test our assumption by:**
  - [实验 1]
  - [实验 2]
  - [根据需要添加更多]

**验证措施：**
- **We know our hypothesis is valid if within** [时间范围]
- **we observe:**
  - [可量化的可衡量成果]
  - [可量化的定性成果]
  - [根据需要添加更多]

### 为什么这个结构有效
- **假设驱动：** 迫使你陈述你相信什么（以及可能错误的东西）
- **成果聚焦：** "Then we will" 强调用户利益，而不是功能产出
- **实验优先：** 在全面构建之前鼓励轻量级验证
- **可证伪：** 清晰的成功标准使得尽早扼杀坏想法成为可能
- **风险管理：** 将 epic 视为赌注，而不是承诺

### 反模式（这不是什么）
- **不是功能规格：** "构建一个带有 5 个图表的仪表板"是一个功能，而不是假设
- **不是保证承诺：** 假设可以被（也应该被）证伪
- **不是产出聚焦：** "在 Q2 前交付功能 X"错过了重点——它达到成果了吗？
- **不是无实验：** 如果你跳过实验直接构建，你不是在测试假设

### 何时使用
- 早期功能探索（在承诺全面路线图之前）
- 验证新能力的产品-市场契合度
- 优先级排序（经过验证的假设的 epic 获得更高优先级）
- 管理利益相关者期望（将工作框架为实验，而不是承诺）

### 何时不使用
- 对于经过充分验证的功能（如果你已经证明了需求，直接跳到用户故事）
- 对于微不足道的功能（不要过度工程化小调整）
- 当实验不可行时（很少见，但有时你必须在测试之前承诺）

---

## 应用

使用 `template.md` 获取完整的填写结构。

### 第一步：收集背景

在起草 epic 假设之前，确保你有：
- **问题理解：** 这解决了什么用户问题？（参考 `skills/problem-statement/SKILL.md`）
- **目标画像：** 谁受益？（参考 `skills/proto-persona/SKILL.md`）
- **待完成的工作：** 他们试图实现什么成果？（参考 `skills/jobs-to-be-done/SKILL.md`）
- **当前替代方案：** 用户今天做什么？（竞争对手、变通方法、无为）

**如果缺少背景：** 先进行发现访谈或问题验证工作。

---

### 第二步：起草 If/Then 假设

填写模板：

```markdown
### If/Then 假设

**If we** [代表目标画像采取的动作或解决方案]
**for** [目标画像]
**Then we will** [为画像获得或实现 desirable 的成果或待完成的工作]
```

**质量检查：**
- **"If we" 是具体的：** 不是"改进产品"而是"在任务被分配时添加一键 Slack 通知"
- **"For" 是清晰的画像：** 不是"用户"而是"管理 3+ 分布式团队远程项目经理"（参考 `skills/proto-persona/SKILL.md`）
- **"Then we will" 是成果：** 不是"用户将有通知"而是"用户对任务分配的响应速度将提高 50%"

**示例：**
- ✅ "If we add one-click Google Calendar integration for trial users, then we will increase activation rates by 20% within 30 days"
- ✅ "If we provide bulk delete functionality for power users managing 1000+ items, then we will reduce time spent on cleanup tasks by 70%"
- ❌ "If we build a dashboard, then users will use it" (模糊，不可衡量)

---

### 第三步：设计微小的发现行为实验

在构建完整 epic 之前，定义轻量级实验来测试假设：

```markdown
### 微小的发现行为实验

**We will test our assumption by:**
- [实验 1：低成本、快速测试]
- [实验 2：另一个低成本、快速测试]
- [根据需要添加更多]
```

**实验类型：**
- **原型 + 用户测试：** 用可点击原型模拟功能，用 5-10 个用户测试
- **礼宾测试：** 手动为几个用户执行功能，看看他们是否重视它
- **着陆页测试：** 描述功能，衡量注册或兴趣
- **Wizard of Oz 测试：** 呈现好像自动化的功能，但在幕后手动执行
- **A/B 测试（如果可行）：** 测试轻量级版本 vs. 对照

**质量检查：**
- **快速：** 实验应该需要天/周，而不是月
- **廉价：** 避免完整的工程构建——使用原型、手动流程或现有工具
- **可证伪：** 设计可能证明你*错误*的实验

**示例：**
- "Create a Figma prototype of the bulk delete flow and test with 5 power users"
- "Manually send Slack notifications to 10 trial users and track response time"
- "Add a 'Request this feature' button to the UI and measure click-through rate"

---

### 第四步：定义验证措施

指定成功是什么样的以及评估的时间范围：

```markdown
### 验证措施

**We know our hypothesis is valid if within** [时间范围（天或周）]
**we observe:**
- [Desirable quantitative, measurable outcome]
- [Desirable qualitative, measurable outcome]
- [根据需要添加更多]
```

**质量检查：**
- **时间范围是现实的：** 不是"6 个月内"（太慢）也不是"3 天内"（太快）
- **定量措施是具体的：** 不是"更多用户"而是"激活率提高 20%"
- **定性措施是可观察的：** 不是"用户喜欢它"而是"10 个用户中有 8 个表示他们会为这个功能付费"

**示例：**
- ✅ "Within 4 weeks, we observe:"
  - "Activation rate increases from 40% to 50% (quantitative)"
  - "75% of surveyed trial users say the integration saved them time (qualitative)"
- ❌ "Within 1 year, we observe:"
  - "Revenue goes up" (太模糊，太长)

---

### 第五步：运行实验并评估

- **执行实验：** 构建原型、运行测试、收集数据
- **衡量结果：** 你达到验证措施了吗？
- **决策点：**
  - ✅ **假设被验证：** 继续构建用户故事并添加到路线图
  - ❌ **假设被证伪：** 取消 epic 或转向不同的假设
  - ⚠️ **不确定：** 运行额外实验或收紧验证措施

---

### 第六步：转换为用户故事（如果已验证）

一旦假设被验证，将 epic 分解为用户故事：

```markdown
### Epic：[Epic 名称]

**Stories:**
1. [用户故事 1 - 参考 `skills/user-story/SKILL.md`]
2. [用户故事 2]
3. [用户故事 3]
```

---

## 示例

参见 `examples/sample.md` 获取完整的 epic 假设示例。

迷你示例节选：

```markdown
**If we** provide one-click Google Calendar integration
**for** trial users managing multiple meetings
**Then we will** increase activation rate from 40% to 50%
```

---

## 常见陷阱

### 陷阱 1：假设是功能，而不是成果
**症状：** "If we build a dashboard, then we will have a dashboard"

**后果：** 你在描述产出，而不是成果。这不能测试任何东西。

**修复：** 关注用户成果："If we build a dashboard showing real-time task status, then PMs will spend 50% less time asking for status updates."

---

### 陷阱 2：跳过实验
**症状：** "We'll test our assumption by building the full feature"

**后果：** 你在验证之前就承诺构建了。不是假设——是功能承诺。

**修复：** 设计轻量级实验（原型、礼宾测试、着陆页），需要天/周，而不是月。

---

### 陷阱 3：模糊的验证措施
**症状：** "We know it's valid if users are happy"

**后果：** 成功标准是主观的、不可衡量的。

**修复：** 定义具体的、可证伪的指标："80% of surveyed users rate the feature 4+ out of 5" or "Response time drops by 50%."

---

### 陷阱 4：不现实的时间范围
**症状：** "We know it's valid if within 6 months revenue increases"

**后果：** 太慢而无法为决策提供信息。到那时，你已经构建了它。

**修复：** 以 2-4 周的验证周期为目标。如果你不能在该时间范围内衡量，请选择一个领先指标（例如激活率，而不是年收入）。

---

### 陷阱 5：将 Epic 视为承诺
**症状：** "We already told the CEO we're shipping this, so we have to validate it"

**后果：** 实验是走过场——无论如何你都会构建它。

**修复：** 在做出承诺*之前*将 epic 框架为假设。如果利益相关者需要确定性，请解释构建未经验证功能的风险。

---

## 参考

### 相关技能
- `skills/problem-statement/SKILL.md` — 假设应该解决经过验证的问题
- `skills/proto-persona/SKILL.md` — 定义"for [persona]"部分
- `skills/jobs-to-be-done/SKILL.md` — 为"then we will"成果提供信息
- `skills/user-story/SKILL.md` — 经过验证的 epic 分解为用户故事
- `skills/user-story-splitting/SKILL.md` — 如何将经过验证的 epic 分解为故事

### 外部框架
- Tim Herbig，*精益 UX 假设声明* — if/then 假设格式的起源
- Jeff Gothelf & Josh Seiden，*精益 UX*（2013）— 假设驱动产品开发
- Alberto Savoia，*Pretotype It*（2011）— 验证想法的轻量级实验
- Eric Ries，*精益创业*（2011）— 构建-衡量-学习循环

### Dean's Work
- 待办事项 Epic 假设提示（灵感来自 Tim Herbig 的框架）

### 来源
- 改编自 `https://github.com/deanpeters/product-manager-prompts` repo 中的 `prompts/backlog-epic-hypothesis.md`。

---

**技能类型：** 组件
**建议文件名：** `epic-hypothesis.md`
**建议放置位置：** `/skills/components/`
**依赖：** 引用 `skills/problem-statement/SKILL.md`、`skills/proto-persona/SKILL.md`、`skills/jobs-to-be-done/SKILL.md`
**被使用：** `skills/user-story/SKILL.md`、`skills/user-story-splitting/SKILL.md`
