# Spec Lite Template

spec 是持久化上下文与压缩记忆层；没有最小 spec，不进入代码实现。

```markdown
# Spec: <Task Name>

## Goal
- 要解决什么问题：
- 验收结果：

## Scope
- In:
- Out:

## Facts / Constraints
- 已确认事实：
- 技术/业务约束：
- 已知风险：

## Open Questions
- [ ] 待确认项 1

## Summary / Plan
- 当前理解：
- Step 1:
- Step 2:
- 风险：
- 验证方式：
- Execution Approval: `Pending` / `Approved`

## Change Log
- YYYY-MM-DD: 决策/改动摘要

## Validation
- 已执行检查：
- 结果：
- 剩余风险：
```

建议：

- `fast` 任务也至少保留 `Goal / Summary / Plan / Approval / Change Log / Validation`。
- `standard` 任务通常补齐全部区块即可。
- `deep` 任务在此基础上扩展，但仍避免写成巨型 spec。
- 执行前先把 `Execution Approval` 置为 `Pending`，获批后再改为 `Approved`。
- 每轮只回读当前相关区块，不整份重载。
