# sdd-riper-one-light

面向 `GPT-5.4` 的轻量 SDD / RIPER coding skill。

目标不是弱化流程，而是用更少常驻文本保留 SDD-RIPER 的核心控制力：

- `Spec is Truth`
- `No Spec, No Code`
- `No Approval, No Execute`
- `Reverse Sync`
- 默认中文、短汇报、按需加载深模块

## 适用场景

适用于高输入、高频、多轮的 coding / agentic coding 任务，尤其适合：

- 大上下文、多文件、长链路任务
- 希望先收敛 spec，再总结汇报，再执行
- 希望减少重型协议常驻 token 开销
- 使用强模型时保留控制内核，而不是保留冗余流程文本

## 核心特点

- 轻量常驻：只保留必要规则，不常驻大段 phase/state machine
- 双门禁：必须先有最小 spec，且必须先获批准再执行
- fast / standard / deep 分流：小改不冗长，大任务再展开
- 按需模块：`Deep Planning` / `Debug` / `Review` / `Multi-project`
- spec 持久化：将多轮任务的上下文、计划、结论沉淀到文档，而不是漂在聊天历史里

## 目录结构

- `SKILL.md`：主 skill 定义与常驻规则
- `agents/openai.yaml`：UI 元数据与默认提示
- `references/spec-lite-template.md`：最小 spec 模板
- `references/modules.md`：按需加载的深模块说明

## 最小工作流

1. 建立或更新最小 spec
2. 输出简短 `summary / plan`
3. 等待用户明确批准
4. 执行修改
5. 回写 spec 中的 `Change Log / Validation`

## 使用提示

- 小任务：使用 `micro-spec + micro-summary`
- 中任务：走 `standard`
- 复杂任务：升级到 `deep`，必要时加载按需模块
- 每轮只回读当前相关 spec 区块，不整份重载

## 说明

这个仓库是 light 版实现，强调：

- 少文本
- 强约束
- 高可控
- 更适配 `GPT-5.4` 的强上下文与强推理能力
