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

## Restated Understanding
- 我理解当前任务是：
- 当前核心目标是：
- 当前边界是：
- 暂不处理：

## Checkpoint Summary
- 当前任务理解：
- 当前核心目标：
- 当前进度：
- 下一步 1:
- 下一步 2:
- 涉及文件 / 模块：
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

- `fast` 任务也至少保留 `Goal / Restated Understanding / Checkpoint Summary / Approval / Change Log / Validation`。
- `standard` 任务通常补齐全部区块即可。
- `deep` 任务在此基础上扩展，但仍避免写成巨型 spec。
- spec 一旦形成或更新，应尽快落盘。
- 用户输入任务后，先写 `Restated Understanding`，再进入后续动作。
- `Checkpoint Summary` 里要明确区分：`任务理解`、`核心目标`、`当前进度`，不要混写成一个概念。
- 执行前先把 `Execution Approval` 置为 `Pending`，获批后再改为 `Approved`。
- 编码前、切换任务点前、收尾前，回读当前相关区块，不整份重载。
