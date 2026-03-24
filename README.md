# BAZI.md

一个受中国八字文化启发、但面向工程实践的开放规范。  
An open standard inspired by Chinese Bazi culture and designed for practical engineering use.

`BAZI.md` 的目标不是把文化概念包装成玄学 prompt，而是把它们转译为可预测、可组合、可被不同 agent framework 消费的 profile format。  
`BAZI.md` does not treat cultural language as mystical prompting. It translates it into a predictable, composable profile format that different agent frameworks can consume.

- Web 工具 / Web tool: [Demo](https://bazimd.github.io/bazi.md/)

## What It Is

`BAZI.md` 用于描述 agent 的稳定底盘，包括默认气质、决策偏好、协作方式与风险边界。  
`BAZI.md` describes an agent's stable constitution, including temperament, decision bias, collaboration posture, and risk boundaries.

当前版本聚焦 `BAZI.md`。`bagua.md` 代表未来的动态模式切换层，但尚未纳入正式模板与 schema。  
The current draft focuses on `BAZI.md`. `bagua.md` is the planned dynamic mode-switching layer, but it is not yet part of the formal template or schema.

官方文件名采用全大写：`BAZI.md`，与 `AGENTS.md` 保持一致。  
The official filename is uppercase: `BAZI.md`, aligned with `AGENTS.md`.

## Why This Exists

很多 agent 配置仍然是长 prompt、人格描述与工具指令的拼接，难以做到：  
Many agent configurations are still flat bundles of prompts, persona text, and tool instructions, which makes it hard to achieve:

- 文件入口可预测  
  predictable file entrypoints
- 语义层次清晰  
  clear semantic layering
- 可验证  
  validation
- 可继承与覆盖  
  inheritance and overrides
- 跨 framework 迁移  
  portability across frameworks

这个项目尝试提供更稳定的分层：  
This project proposes a more stable layered structure:

- `AGENTS.md`：仓库操作手册  
  `AGENTS.md`: repository operations manual
- `BAZI.md`：稳定行为底盘  
  `BAZI.md`: stable behavioral constitution
- `schemas/`：机器可读校验规则  
  `schemas/`: machine-readable validation rules
- `adapters/`：不同 framework 的映射文档  
  `adapters/`: framework-specific mappings
- `examples/`：参考 profile  
  `examples/`: reference profiles
- `skills/`：辅助 agent 生成或改写 `BAZI.md` 的技能  
  `skills/`: reusable skills for generating or refining `BAZI.md`

## Core Model

| File | Role |
| --- | --- |
| `AGENTS.md` | 仓库的操作契约，回答“在这个仓库里该怎么工作”。<br>Repository operational contract: how should work happen in this repository? |
| `BAZI.md` | Agent 的体质档案，回答“这个 agent 默认是什么样的”。<br>Agent constitutional profile: what kind of agent is this by default? |

判断标准：如果一条说明脱离这个仓库仍然成立，它更可能属于 `BAZI.md`；如果只在这个仓库里成立，它更可能属于 `AGENTS.md`。  
Simple test: if an instruction still makes sense outside the repo, it likely belongs in `BAZI.md`; if it only makes sense inside the repo, it likely belongs in `AGENTS.md`.

## Quick Start

1. 复制 [templates/BAZI.md](/Users/douglas/Desktop/bazi.md/templates/BAZI.md)。  
   Copy [templates/BAZI.md](/Users/douglas/Desktop/bazi.md/templates/BAZI.md).
2. 检测 agent 创建时间，得到年、月、日、时与时区。  
   Detect the agent creation time, including year, month, day, hour, and timezone.
3. 根据创建时间自动推导四柱，再结合项目语义填写 `BAZI.md`。  
   Auto-derive the four pillars from the creation time, then interpret them through project semantics in `BAZI.md`.
4. 用 `AGENTS.md` 承载仓库内的操作规则。  
   Use `AGENTS.md` for repository-specific operational rules.
5. 用 [schemas/bazi-profile.schema.json](/Users/douglas/Desktop/bazi.md/schemas/bazi-profile.schema.json) 校验结构化 JSON。  
   Validate normalized JSON with [schemas/bazi-profile.schema.json](/Users/douglas/Desktop/bazi.md/schemas/bazi-profile.schema.json).

## Live Demo

在线快速体验： [https://bazimd.github.io/bazi.md/](https://bazimd.github.io/bazi.md/)  
Try the browser demo here: [https://bazimd.github.io/bazi.md/](https://bazimd.github.io/bazi.md/)

它允许用户输入 agent 的出生/创建日期与时间，然后：  
It lets users input an agent birth/creation date and time, then:

- 自动推导四柱  
  auto-derive the Four Pillars
- 生成基础 `BAZI.md` 文本  
  generate a base `BAZI.md`
- 一键复制或下载  
  copy or download in one click

## Generation Workflow

推荐生成流程如下：  
Recommended generation flow:

1. 用户或系统检测 agent 创建时间。  
   The user or system detects the agent creation timestamp.
2. 提取 `year`、`month`、`day`、`hour` 与 `timezone`。  
   Extract the year, month, day, hour, and timezone.
3. 用这些输入自动推导四柱。  
   Use those inputs to auto-derive the four pillars.
4. 再根据项目上下文解释四柱，并补全日主、十神、系统映射与边界。  
   Then interpret the pillars through project context and complete the day master, ten gods, system mapping, and boundaries.
5. 输出正式 `BAZI.md`。  
   Output the final `BAZI.md`.

这里的原则是：  
The principle is:

- 创建时间负责“盘”的生成  
  creation time is responsible for generating the chart
- 项目语义负责“义”的解释  
  project semantics are responsible for interpreting the chart

## Repository Structure

```text
.
├── AGENTS.md
├── BAZI.md
├── LICENSE
├── README.md
├── SPEC.md
├── adapters/
├── examples/
├── index.html
├── schemas/
├── skills/
└── templates/
```

## Design Principles

- 文化语义与系统语义并行存在  
  cultural semantics and system semantics must coexist
- 核心规范不绑定单一 framework  
  the core spec must remain framework-agnostic
- 仓库操作层与 agent 身份层分离  
  repository rules and agent identity must stay separate
- 解析顺序明确，支持 override  
  resolution order should be explicit and override-friendly
- 示例尽量短、清晰、可复用  
  examples should stay concise, clear, and reusable

## Resolution Order

1. 用户任务 / 运行时指令  
   User task / runtime instruction
2. 场景级覆盖  
   Scenario-specific override
3. `AGENTS.md`
4. `BAZI.md`
5. Framework 默认值  
   Framework default

未来若加入 `bagua.md`，它会位于 `AGENTS.md` 与 `BAZI.md` 之间，作为动态行为层。  
If `bagua.md` is added later, it should sit between `AGENTS.md` and `BAZI.md` as the dynamic behavior layer.

## Agent Skill

仓库内包含一个可复用技能：`skills/bazi-profile-builder/`。  
The repository includes a reusable skill at `skills/bazi-profile-builder/`.

它帮助 agent framework 或 coding agent 读取项目上下文，区分 `AGENTS.md` 与 `BAZI.md` 的边界，并生成或改写项目特定的 `BAZI.md`。  
It helps an agent framework or coding agent inspect project context, separate `AGENTS.md` from `BAZI.md` concerns, and generate or refine a project-specific `BAZI.md`.

## Current Status

当前仓库是 `v0.1-draft` 草案，先固定最小标准骨架：  
This repository is an initial `v0.1-draft` focused on the minimum standard shape:

- 规范  
  specification
- `BAZI.md` 模板  
  `BAZI.md` template
- schema
- adapters
- examples
- skills

后续可以继续补：  
Future work can add:

- `bagua.md` 草案  
  `bagua.md` draft
- compiler / parser
- validation CLI
- 更多 framework adapter  
  more framework adapters
- 更多 agent archetype 示例  
  more agent archetype examples

## Author

由 [Douglas](https://github.com/Douglasymlai) 发起与维护。  
Created and maintained by [Douglas](https://github.com/Douglasymlai).

## Licensing

仓库根目录采用 MIT License。  
The repository root is licensed under the MIT License.

`skills/` 子目录单独采用 Apache License 2.0。  
The `skills/` subtree is separately licensed under the Apache License 2.0.

如果文件同时受两个范围影响，以离文件最近的 `LICENSE` 为准。  
If a file is covered by multiple scopes, the nearest `LICENSE` file takes precedence.
