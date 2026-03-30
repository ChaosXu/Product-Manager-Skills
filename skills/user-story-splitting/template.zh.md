# 用户故事拆分模板

使用此模板将大故事拆分为更小的、可独立交付的用户故事。

## 出处

改编自 `prompts/user-story-splitting-prompt-template.md` in the `https://github.com/deanpeters/product-manager-prompts` repo。

## 拆分逻辑（按顺序使用）

1. 工作流步骤
2. 业务规则变体
3. 数据变体
4. 验收标准复杂度（多个当/则对）
5. 主要工作里程碑
6. 外部依赖
7. DevOps 步骤
8. 如果都不适用，使用微小发现行为（TADs）

## 输出模板

```markdown
### 原始故事
[使用 `skills/user-story/template.md` 编写的故事]

### 建议拆分
1. 使用 **[规则名称]** 的拆分 1：
   - [左拆分故事，使用 `skills/user-story/template.md`]
   - [右拆分故事，使用 `skills/user-story/template.md`]
2. 使用 **[规则名称]** 的拆分 2：
   - [左拆分故事]
   - [右拆分故事]
3. 使用 **[规则名称]** 的拆分 3：
   - [左拆分故事]
   - [右拆分故事]
```

## 注意事项

- 每个拆分应该能够独立交付用户价值。
- 如果没有规则适用，提出 TADs 在编写故事之前降低风险并澄清。
