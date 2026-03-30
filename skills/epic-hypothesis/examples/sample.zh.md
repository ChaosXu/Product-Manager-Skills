# Epic 假设示例

## 示例 1：好的 Epic 假设

```markdown
### Epic 假设：面向试用用户的 Google Calendar 集成

#### If/Then 假设

**If we** provide one-click Google Calendar integration during onboarding
**for** trial users who manage multiple meetings and tasks daily
**Then we will** increase activation rate (defined as completing setup + creating first task) from 40% to 50%

#### 微小的发现行为实验

**We will test our assumption by:**
1. Creating a clickable Figma prototype of the integration flow and testing with 10 trial users
2. Adding a "Connect Google Calendar" CTA to the onboarding flow (but it's non-functional) and measuring click-through rate
3. Manually syncing Google Calendar for 5 trial users and surveying them after 1 week on perceived value

#### 验证措施

**We know our hypothesis is valid if within 4 weeks we observe:**
- Click-through rate on the CTA is > 60% (quantitative)
- 8 out of 10 prototype testers say they'd use this feature regularly (qualitative)
- Manually synced users report saving 10+ minutes per day on task entry (qualitative)
```

---

## 示例 2：坏的 Epic 假设（模糊）

```markdown
### Epic 假设：改进仪表板

#### If/Then 假设

**If we** improve the dashboard
**for** users
**Then we will** make the product better

#### 微小的发现行为实验

**We will test our assumption by:**
1. Building the dashboard

#### 验证措施

**We know our hypothesis is valid if we observe:**
- Users like it
```

**为什么失败：**
- "Improve the dashboard" 不具体（如何改进？）
- "Users" 不是画像（哪些用户？所有用户？）
- "Make the product better" 不可衡量
- 实验是"构建它"（不是轻量级测试）
- 验证是主观的（"用户喜欢它" = 不可证伪）

**如何修复：**
- 指定假设："If we add real-time task status updates to the dashboard for project managers, then we will reduce time spent checking task progress from 20 min/day to 5 min/day"
- 定义画像："for project managers managing 10+ team members"
- 设计实验："Prototype the dashboard, test with 5 PMs, measure time savings"
- 指定验证："8 out of 10 PMs report saving 10+ min/day"

---

## 示例 3：被证伪的假设（好的流程）

```markdown
### Epic 假设：面向通知的 Slack 集成

#### If/Then 假设

**If we** send Slack notifications when tasks are assigned
**for** remote project managers
**Then we will** reduce task response time from 4 hours to 1 hour

#### 微小的发现行为实验

**We will test our assumption by:**
1. Manually send Slack notifications to 10 project managers for 2 weeks
2. Measure response time before/after
3. Survey users on perceived value

#### 验证措施

**We know our hypothesis is valid if within 2 weeks we observe:**
- Average response time drops from 4 hours to 1 hour (quantitative)
- 8 out of 10 users say Slack notifications helped them respond faster (qualitative)

---

**2 周后的结果：**
- 平均响应时间：3.5 小时（改善很小）
- 用户反馈："我已经收到太多 Slack 通知了。我忽略大多数。"
- **决定：假设被证伪。用户不想要更多 Slack 噪音。转向应用内通知或电子邮件摘要。**
```

**为什么这是好的：**
- 假设被测试了（不仅仅是构建）
- 实验是轻量级的（手动 Slack 消息，而不是完整集成）
- 结果表明假设是错误的
- 团队在浪费工程时间之前取消了 epic
