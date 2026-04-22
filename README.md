# ⚡️ SDD-RIPER: AI Agent Harness for Human Control

> **A lightweight harness for riding with non-deterministic AI agents.**
> 不是把 AI 锁进旧流程，而是让模型探索河道，让人类跟着水势调整位置，在关键处设闸、验收、开垦。

---

## 📖 30秒读懂 SDD-RIPER

**SDD-RIPER** 不是传统意义上“先写完整 Spec，再让模型按图施工”的重型 SDD。

它是一套面向大模型时代的 **AI Agent Harness**：用最小真相源、Checkpoint、Approval、Validation 和 Reverse Sync，把一个聪明但非确定性的模型纳入可观察、可验证、可接手的工程轨道。

这个仓库的主推实现是 **`sdd-riper-one-light`**。它不是“简化版”，而是强模型时代的日常主力 Harness：允许模型自己分解、探索和执行，同时让人类始终掌握目标、边界、节奏和验收。

标准版 **`sdd-riper-one`** 仍然有价值：它更重、更显式，更适合团队训练、复杂任务、低模型能力环境、严格审计和跨人交接。它相对 light 更保守，但它的核心仍然是**给人看、让人驾驭模型**，这和传统 SDD 把 Spec 当模型操作系统的思路截然不同。

### 核心公式

> **AI (Subject) + Human (Steward) + Harness (Control Surface) = Software 2.0**

### ⚡️ 为什么你需要它？

大模型有四个绕不开的工程痛点：

- 🧠 **上下文腐烂**（大模型的阿喀琉斯之踵）：对话越长，AI 越容易遗忘前文约束，悄悄破坏已有逻辑——这是模型架构的固有局限，无法靠"更强的模型"解决
- 👀 **审查瘫痪**：AI 秒生成 500 行代码，人根本 Review 不过来，质量失控
- 🔌 **维护断层**：全是 AI 生成的陌生代码，两周后不敢动，改一行崩三处
- 🤔 **代码不信任**：不知道 AI 为什么这么写，不敢上线、不敢重构——很多人因此根本不敢用大模型编程

| 🚫 痛点 (Without Harness) | ✅ SDD-RIPER 解法 |
| --- | --- |
| **上下文腐烂**：AI 聊着聊着就忘了前文约束，破坏旧逻辑。 | **最小真相源**：用 Spec / Handoff 记录目标、边界、结论，关键节点按需回读和复述。 |
| **审查瘫痪**：AI 秒生成 500 行代码，人类根本 Review 不过来。 | **Checkpoint + Approval**：先看目标、风险、方案和验证方式，**审节奏代替逐行盯代码**。 |
| **不可维护**：全是 AI 生成的陌生代码，两周后不敢动。 | **Reverse Sync**：把已经验证的河道回写成可接手的上下文，让后续人和模型都能恢复。 |
| **代码不信任**：不敢用大模型写的代码上线，怕有雷。 | **证据闭环**：Spec + 执行日志 + 测试结果 + 代码交叉验证，需求是否完成、Bug 出在哪里一目了然。 |

### 🌊 从挖水渠到跟着河道开垦

传统软件工程和传统重 SDD，更像是人类先挖好水渠，再要求水按预设路径流到自己的田里。

大模型时代，水本身有了强大的流动能力。更好的方式不是提前挖死每一条渠，而是允许水先漫溢、探索、自己找到河道；人类要做的是跟着水势调整自己的方向和位置，在关键位置设闸、筑堤、验收，并沿着已经形成的河道开垦田地。

这就是 SDD-RIPER 从“重 Spec 流程”转向 “Harness Engineering” 的核心变化：

- **传统重 SDD**：人预设路径，模型按图施工。
- **SDD-RIPER Light**：模型探索路径，人类控制边界、节奏和验收。
- **标准 SDD-RIPER**：用更显式的阶段门禁，把这种控盘方式教给团队、留给交接、用于高风险任务。

### 🏇 从工具到事件主体

强模型不再只是人类的助手，也不只是“按命令补代码”的工具。它开始成为事件推进的主体：提出方案、尝试路径、暴露风险、推动任务向前流动。

这更像骑手和马的关系。骑手不替马迈腿，马也不是被动工具；在赛道上，马的速度、力量和判断才是主力。骑手的价值在于选赛道、控节奏、看风险、给信号、判输赢。

`sdd-riper-one-light` 承认这种主体性：让模型成为主力，让人类成为控盘者。Harness 不是把马绑在旧流程里，而是让人和模型能在同一条赛道上协作，并且始终可观察、可设闸、可验收、可复用。

---

## 🎯 一句话：这个项目解决了什么问题？

**AI 编程最大的坑不是"AI 不够聪明"，而是"人还在用旧身份管理新能力"。**

你一定遇到过：AI 聊着聊着就忘了之前的约束，改着改着就把旧逻辑搞坏了，生成 500 行代码你根本审不过来，两周后再看全是"AI 写的陌生代码"不敢动……

**SDD-RIPER** 就是为了解决这些问题而生的——一套让人类从“亲手写每一行代码”迁移到“定义目标、控制节奏、验证结果”的 Harness。它配套可一键安装的 Skill，让你从"被 AI 带着跑"变成"驾驭 AI 的探索能力"。

### 虚构项目演练（以下场景与数据为教学示例，用于说明方法的适用范围）

- ✅ 在**百万行 Java 代码**的遗留系统上，用 Code Map 战术 **20 分钟梳理清楚核心链路**
- ✅ **零 Java 经验**的情况下，靠 SDD 协议完成复杂业务需求开发
- ✅ Bug 率显著下降：主语言 **-18%**，非主语言（Go/Python/Node.js）**-37%**
- ✅ 日常需求周期：**1~2 周 → 3~4 天**；大型需求：**2 个月 → 1 个月**
- ✅ 复杂交付场景的人力投入：**可显著下降**，团队协作效率同步提升
- ✅ 30 天 **10.8 亿 Token** 重度实战，四窗口并行，核心人员只做阶段性 Review

### 典型应用场景

| 场景 | 痛点 | SDD-RIPER 怎么解 |
| --- | --- | --- |
| **老业务交接与持续维护** | 遗留系统无人敢动，交接靠口头、靠"看代码"；核心研发不应长期困在老需求里 | Code Map 20 分钟梳理核心链路，Spec 固化业务上下文，**低代码经验的同学也能接手老业务的日常迭代和维护**，释放核心研发投入新业务 |
| **低经验人员交付核心业务** | 新人/跨团队支援不熟悉代码库，上手周期长 | 有 Spec + Code Map 就能按图施工，**零 Java 经验也能完成复杂需求** |
| **人力紧张时的并行交付** | 核心研发不够用，但需求排不完 | 核心人员只写 Spec + 审 Plan，**执行交给 AI + 非核心研发人力**，一人指挥多路并行 |
| **高敏感代码安全合规** | 核心代码不敢用外部模型 | 先在受控环境中整理抽象接口与约束 Spec，再让外部模型基于抽象 Spec 做设计，**原始代码不外发** |

### 组织影响力

- 📦 主推可日常使用的 Harness Skill：`sdd-riper-one-light`
- 🧭 保留更重的标准协议：`sdd-riper-one`，用于训练、复杂任务、审计与交接
- 📚 提供配套协议、方法论文章与落地教程，形成完整学习路径
- 🧩 支持从个人试用到团队推广的渐进式落地
- 🔐 文档以仓库内可审阅内容为主，便于统一治理与示例维护

---

## 🚀 快速开始

### 方式一：使用 Skill（推荐 - 开箱即用）

**Skill 是什么？** 将 SDD-RIPER 协议封装为可执行命令的配置文件，让 AI 自动遵循相应工作流。

#### 先选版本

| Skill | 定位 | 适用场景 | 目录 |
| --- | --- | --- | --- |
| `sdd-riper-one-light` | **主推 Harness**：checkpoint-driven + 契约式控制 | `GPT-5.4`、高输入、多轮、高频 coding；适合日常 AI coding / agentic coding。核心工作流是 Restate、Checkpoint、Spec Truth、Validation、Reverse Sync | [`skills/sdd-riper-one-light/`](./skills/sdd-riper-one-light/) |
| `sdd-riper-one` | **重型控盘协议**：完整 RIPER 阶段门禁 | 团队训练、复杂重构、跨项目协作、低模型能力环境、严格审计、长周期交接 | [`skills/sdd-riper-one/`](./skills/sdd-riper-one/) |

- **默认推荐 `sdd-riper-one-light`**：这是本项目主推的日常 Harness。
- **复杂任务升级到 `sdd-riper-one`**：需要完整 `Research -> Innovate -> Plan -> Execute -> Review`、团队教学或强审计时使用。
- **不要把标准版理解成过时方案**：它仍然领先于传统 SDD，因为它的 Spec 首先是给人类控盘、验收和交接看的，而不是让模型每轮机械重载的巨型上下文。

#### 安装步骤

1. **选择你的 AI 平台**
   - **Claude Desktop / Claude.ai**：复制选定版本的 `SKILL.md` 到 Custom Instructions
     - Light: [`skills/sdd-riper-one-light/SKILL.md`](./skills/sdd-riper-one-light/SKILL.md)
     - Standard: [`skills/sdd-riper-one/SKILL.md`](./skills/sdd-riper-one/SKILL.md)
   - **Cursor**：将选定版本的 `SKILL.md` 复制为项目根目录的 `.cursorrules` 文件
   - **其他 AI Agent**：查看对应安装指南
     - Light: [README](./skills/sdd-riper-one-light/README.md)
     - Standard: [README](./skills/sdd-riper-one/README.md)

2. **验证安装**

   ```text
   在 AI 对话中输入：create_codemap
   或直接要求先复述任务理解，再建立/更新最小 spec，并输出 checkpoint。
   如果 AI 识别并按协议执行，说明安装成功 ✅
   ```

3. **开始第一个任务**

   `Light` 示例：

   ```text
   请启用 $sdd-riper-one-light，并先用你自己的话复述对任务的理解，明确核心目标、边界和暂不处理项；然后建立/更新最小 spec，给我 checkpoint；获批后再执行：
   - task=用户登录功能
   - goal=实现完整的登录流程
   - requirement=docs/requirements/login.md
   ```

   `Standard` 示例：

   ```text
   create_codemap: mode=project, scope=my-project
   build_context_bundle: ./docs/requirements/
   sdd_bootstrap: task=用户登录功能, goal=实现完整的登录流程
   ```

#### 核心命令速查

| 命令 | 用途 | 示例 |
|------|------|------|
| `create_codemap` | 生成代码地图（功能级/项目级） | `create_codemap: mode=feature, scope=登录模块` |
| `build_context_bundle` | 整理需求上下文 | `build_context_bundle: ./docs/requirements/` |
| `sdd_bootstrap` | 启动 SDD 任务 | `sdd_bootstrap: task=用户认证, goal=...` |
| `FAST` | 快速修改（小改动） | `FAST: 修改按钮颜色为蓝色` |
| `DEBUG` | 日志驱动排查 | `DEBUG: log_path=./logs/error.log` |

📖 **完整文档**：[`Light` 使用指南](./skills/sdd-riper-one-light/README.md) ｜ [`Standard` 使用指南](./skills/sdd-riper-one/README.md)

---

### 方式二：手动遵循协议

如果你不想安装 Skill，也可以手动引导 AI 遵循 RIPER 流程：

1. **选择协议文件**（根据任务复杂度）
   - 标准任务：[`SDD-RIPER-ONE.md`](./protocols/SDD-RIPER-ONE.md)
   - 文档生成：[`RIPER-DOC.md`](./protocols/RIPER-DOC.md)
   - 复杂重构：[`RIPER-5.md`](./protocols/RIPER-5.md)

2. **在对话开始时发送**

   ```text
   请阅读并严格遵循以下协议：
   [粘贴协议文件内容]
   ```

3. **手动推进阶段**

   ```text
   现在进入 Research 阶段，请调研代码库现状...
   现在进入 Plan 阶段，请输出详细的实施计划...
   Plan Approved，现在进入 Execute 阶段...
   ```

---

## 🔄 The RIPER Loop (标准作业流)

我们强制 AI 遵循以下五步状态机，拒绝"一发入魂"的幻觉代码：

```mermaid
graph LR
    R[🔍 Research<br>调研/事实锁定] --> I[💡 Innovate<br>方案设计]
    I --> P[📝 Plan<br>原子级规划]
    P -->|Human Sign-off| E[🚀 Execute<br>按图施工]
    E --> V[👀 Review<br>反向验收]
    V -->|Fix Spec| P
```

1. **Research**: 拒绝瞎猜，先查代码库现状。
2. **Innovate**: 审讯式设计，寻找最优解。
3. **Plan**: **核心环节**。输出详细步骤，人类批准后才准动手。
4. **Execute**: 无脑执行，不仅是 Coder，更是 Builder。
5. **Review**: AI 自查 + 生成验收报告。

---

## 📂 协议资产清单

| 协议文件 | 适用场景 | 对应模型建议 |
| --- | --- | --- |
| [`skills/sdd-riper-one-light`](./skills/sdd-riper-one-light/SKILL.md) | **主推 Harness**：日常 AI coding / agentic coding 的默认入口。 | GPT-5.4 / Claude 4.6 opus |
| [`SDD-RIPER-ONE.md`](./protocols/SDD-RIPER-ONE.md)  | **标准控盘协议**：更显式的完整闭环，适合团队训练、复杂任务、审计与交接。 | Claude 4.5 / GPT-5.1 / Qwen3 |
| [`RIPER-DOC.md`](./protocols/RIPER-DOC.md)  | **文档专家**：专门用于生成 README/API 文档。 | DeepSeek V3 / Gemini Pro |
| [`RIPER-5.md`](./protocols/RIPER-5.md) | **严格版**：上一代状态机，适合复杂逻辑重构。 | o3 / o4-mini |

---

## 📚 深度阅读 (Deep Dive)

| 文档 | 适合人群 | 核心内容 |
|------|---------|---------|
| 🧠 [从传统编程转向大模型编程](./docs/从传统编程转向大模型编程.md) | 个人开发者 | 思维转型：如何从工匠变为建筑师 |
| 📜 [AI 原生研发范式](./docs/AI%20原生研发范式：从"代码中心"到"文档驱动"的演进.md) | 架构师/技术负责人 | 理论体系：为什么 Spec 是新时代的源代码 |
| 🚀 [团队落地指南](./docs/团队落地指南.md) | TL/主管/团队负责人 | 实战指南：如何在一周内让团队跑通大模型编程 |
