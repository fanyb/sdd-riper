# sdd-riper-one-light

面向 `GPT-5.4` 等强模型的轻量 SDD / RIPER coding skill。

它不是把原版弱化，而是把重点从“强制 phase 展开”切到“强制 checkpoint 校准”：

- `Spec is Truth`
- `No Spec, No Code`
- `No Approval, No Execute`
- `Restate First`
- `Reverse Sync`
- 默认中文、短汇报、按需加载深模块

## 工作方式优先

这个 skill 更适合被理解成一种**轻量但有硬门禁的工作方式**，而不是一句 prompt 技巧。

真正要让团队先记住的不是某条调用咒语，而是下面这些习惯：

- 先复述理解，再进入计划
- 先形成 `micro-spec` 或最小 spec，再进入执行
- 先讲清 `目标`、`范围`、`约束`、`验证方式`
- 获批后再执行
- 执行后回写结论

如果先把这些习惯建立起来，`sdd-riper-one-light` 才会发挥出“短协议 + 强控制”的优势。

## 适用场景

适用于高输入、高频、多轮的 coding / agentic coding 任务，尤其适合：

- 大上下文、多文件、长链路任务
- 强模型已能自行分解任务，不需要反复喂整份 spec
- 更希望通过先复述任务理解、再反复强调核心目标、持续总结进度来维持注意力
- 希望减少重型协议常驻 token 开销，同时保留硬门禁

## 核心特点

- `checkpoint-driven`：强制保留校准点，不强制保留整套 phase 文本
- 双门禁：必须先有最小 spec，且必须先获批准再执行
- 自分解优先：默认由模型自行拆解任务与补足局部计划
- `Restate First`：用户给任务后，先用模型自己的话复述理解
- 轻量 spec：用最小文档承载目标、边界、进度、计划与结论
- 按需模块：`Deep Planning` / `Debug` / `Review` / `Multi-project`

## 最小工作流

1. 先复述模型自己的任务理解
2. 建立或更新最小 spec，并落盘
3. 输出简短 checkpoint：区分任务理解、核心目标、当前进度
4. 等待用户明确批准
5. 执行修改
6. 回写 spec 中的 `Change Log / Validation`

## 推荐的最小启动方式

默认不要让使用者先背 prompt，而是让他们按下面这套方式给任务：

- 先说 `目标`
- 再说 `范围`
- 再说 `约束`
- 再说 `验证方式`

然后要求 skill：

- 先复述理解
- 先输出 `micro-spec / summary`
- 先给 checkpoint
- 批准后再执行

如果一定要给一个最小模板，可以给这种级别：

```text
请使用 sdd-riper-one-light 先收敛任务，不要直接改代码。
先给我：
- 你对任务的理解
- micro-spec / summary
- 下一步动作
- 风险
- 验证方式
我批准后再执行。
```

## 使用提示

- 小任务：使用 `micro-spec + micro-summary`
- 中任务：走 `standard`
- 复杂任务：升级到 `deep`，必要时加载按需模块
- 每轮只回读当前相关 spec 区块，不整份重载
- 关键不是展开阶段，而是持续复述理解、强调目标、同步进度

## 说明

这个仓库是 light 版实现，强调：

- 少文本
- 强校准
- 强门禁
- 高可控
- 更适配强模型的自分解与自回顾能力

README 负责说明默认工作方式；真正的协议约束以 `SKILL.md` 为准。

## 脱敏示例

仓库内提供了 3 份脱敏后的真实案例，分别对应：

- `standard spec`：[examples/specs/spec-standard-security-status-race.md](examples/specs/spec-standard-security-status-race.md)
- `light spec`：[examples/specs/spec-light-runtime-compat.md](examples/specs/spec-light-runtime-compat.md)
- `feature codemap`：[examples/codemap/codemap-feature-content-control.md](examples/codemap/codemap-feature-content-control.md)

这些示例保留了真实任务中的问题形态、分析结构和闭环方式，但移除了内部项目、类名、路径与日志标识。
