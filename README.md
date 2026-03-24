# BAZI.md

一个受中国八字文化启发、但面向工程实践的开放规范。  
An open standard inspired by Chinese Bazi culture and designed for practical engineering use.

它的目标不是把文化概念做成玄学 prompt，而是把它们转译成可预测、可组合、可被不同 agent framework 消费的 profile format。  
The goal is not to turn culture into mystical prompting, but to translate it into a predictable, composable profile format that different agent frameworks can consume.

## 项目定位 / Positioning

`BAZI.md` 用于描述 agent 的稳定底盘，包括默认气质、决策偏好、协作方式与风险边界。  
`BAZI.md` describes an agent's stable constitution, including temperament, decision bias, collaboration posture, and risk boundaries.

当前版本聚焦 `BAZI.md`。`bagua.md` 代表动态模式切换层，但这部分仍需更多研究，因此暂未纳入正式模板与 schema，后续版本会补上。  
The current draft focuses on `BAZI.md`. `bagua.md` is the planned dynamic mode-switching layer, but it needs more research and is not yet part of the formal template or schema.

官方文件名采用全大写：`BAZI.md`，与 `AGENTS.md` 保持一致。  
The official filename is uppercase: `BAZI.md`, aligned with `AGENTS.md`.

## 核心关系与文件职责 / Core Relationship & File Responsibilities

| `AGENTS.md` | `BAZI.md` |
| --- | --- |
| 仓库的操作契约。<br>`AGENTS.md` is the repository's operational contract. | Agent 的体质档案。<br>`BAZI.md` is the agent's constitutional profile. |
| 回答“在这个仓库里该怎么工作”。<br>Answers: how should work happen in this repository? | 回答“这个 agent 默认是什么样的”。<br>Answers: what kind of agent is this by default? |
| 管工作。<br>Governs the work. | 管工作者。<br>Governs the worker. |
| **适合放**仓库内才成立的内容；**use for** repository-local rules:<br>— setup / test / lint / build 命令；setup / test / lint / build commands<br>— 仓库结构与关键路径；repository structure and important paths<br>— 提交流程、校验方式、修改约束；contribution flow, validation rules, and change constraints<br>— 项目特定的执行规则；project-specific execution rules | **适合放**脱离仓库仍成立的内容；**use for** instructions that still make sense outside the repo:<br>— 核心原型与默认气质；core archetype and default temperament<br>— 五行权重与阴阳倾向；five-element weighting and yin-yang bias<br>— 决策方式、协作方式、沟通风格；decision style, collaboration style, and communication style<br>— 风险偏好、任务适配、稳定边界；risk tolerance, task affinity, and stable boundaries |

判断标准：如果一条说明脱离这个仓库仍然成立，它更可能属于 `BAZI.md`；如果只在这个仓库里成立，它更可能属于 `AGENTS.md`。  
Simple test: if an instruction still makes sense outside the repo, it likely belongs in `BAZI.md`; if it only makes sense inside the repo, it likely belongs in `AGENTS.md`.

## 为什么做这个项目 / Why This Exists

很多 agent 配置仍然停留在长 prompt、人格描述与工具指令的拼接上，难以做到：  
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

这个项目尝试提供更稳定的结构：  
This project proposes a more stable structure:

- `AGENTS.md`：仓库操作手册  
  `AGENTS.md`: repository operations manual
- `BAZI.md`：稳定行为底盘  
  `BAZI.md`: stable behavioral constitution
- `schemas/`：机器可读校验规则  
  `schemas/`: machine-readable validation rules
- `adapters/`：不同 framework 的映射文档  
  `adapters/`: framework-specific mappings
- `examples/`：五个团队角色与一个团队协作入口示例  
  `examples/`: five team-role examples plus one team coordination entrypoint
- `skills/`：辅助 agent 生成或改写 `BAZI.md` 的技能  
  `skills/`: reusable skills for generating or refining `BAZI.md`

## 仓库结构 / Repository Structure

```text
.
├── AGENTS.md
├── BAZI.md (official filename, used in projects)
├── LICENSE
├── README.md
├── SPEC.md
├── adapters/
│   ├── README.md
│   ├── claude/
│   │   └── claude-mapping.md
│   └── codex/
│       └── codex-mapping.md
├── examples/
│   ├── team/
│   │   ├── AGENTS.md
│   ├── strategy-planner/
│   │   ├── AGENTS.md
│   │   └── BAZI.md
│   ├── project-manager/
│   │   ├── AGENTS.md
│   │   └── BAZI.md
│   ├── product-designer/
│   │   ├── AGENTS.md
│   │   └── BAZI.md
│   ├── developer/
│   │   ├── AGENTS.md
│   │   └── BAZI.md
│   └── growth-operations/
│       ├── AGENTS.md
│       └── BAZI.md
├── schemas/
│   └── bazi-profile.schema.json
├── skills/
│   ├── LICENSE
│   └── bazi-profile-builder/
│       ├── SKILL.md
│       ├── assets/
│       ├── examples/
│       └── references/
└── templates/
    └── BAZI.md
```

## 快速开始 / Quick Start

1. 复制 `templates/BAZI.md`。  
   Copy `templates/BAZI.md`.
2. 先由用户或系统检测 agent 创建时间，得到年、月、日、时与时区。  
   First detect the agent creation time, including year, month, day, hour, and timezone.
3. 根据创建时间自动推导四柱，再结合项目语义填写 `BAZI.md`。  
   Auto-derive the four pillars from the creation time, then interpret them through project semantics in `BAZI.md`.
4. 参考 `examples/` 下的五个团队角色示例与 `examples/team/AGENTS.md` 协作入口。  
   Use the five team-role examples under `examples/` together with `examples/team/AGENTS.md` as the coordination entrypoint.
5. 用 `AGENTS.md` 承载仓库内的操作规则。  
   Use `AGENTS.md` for repository-specific operational rules.
6. 用 `schemas/bazi-profile.schema.json` 校验结构化 JSON。  
   Validate normalized JSON with `schemas/bazi-profile.schema.json`.

## 生成工作流 / Generation Workflow

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

- 创建时间负责“盘”的生成。  
  Creation time is responsible for generating the chart.
- 项目语义负责“义”的解释。  
  Project semantics are responsible for interpreting the chart.

## 智能体技能 / Agent Skill

仓库内包含一个可复用技能：`skills/bazi-profile-builder/`。  
The repository includes a reusable skill at `skills/bazi-profile-builder/`.

它参考 Stitch skills 的组织方式，用来帮助 agent framework 或 coding agent 读取项目上下文，区分 `AGENTS.md` 与 `BAZI.md` 的边界，并生成或改写项目特定的 `BAZI.md`。  
It follows the Stitch skills pattern and helps an agent framework or coding agent inspect project context, separate `AGENTS.md` from `BAZI.md` concerns, and generate or refine a project-specific `BAZI.md`.

## Web 工具 / Web Tool

仓库现在包含一个适合 GitHub Pages 部署的单页工具：[index.html](/Users/douglas/Desktop/bazi.md/index.html)。  
The repository now includes a single-page tool for GitHub Pages deployment: [index.html](/Users/douglas/Desktop/bazi.md/index.html).

它允许用户输入 agent 的出生/创建日期与时间，然后：
It lets users input an agent birth/creation date and time, then:

- 自动推导四柱  
  auto-derive the Four Pillars
- 生成基础 `BAZI.md` 文本  
  generate a base `BAZI.md`
- 一键复制或下载  
  copy or download in one click

当前选择的浏览器计算引擎是 `lunisolar`，因为它明确支持浏览器直接引入并暴露八字 `char8` 数据。  
The chosen browser-side engine is `lunisolar`, because it explicitly supports direct browser inclusion and exposes `char8` Bazi data.

## 许可证 / Licensing

仓库根目录采用 MIT License。  
The repository root is licensed under the MIT License.

`skills/` 子目录单独采用 Apache License 2.0。  
The `skills/` subtree is separately licensed under the Apache License 2.0.

如果文件同时受两个范围影响，以离文件最近的 `LICENSE` 为准。  
If a file is covered by multiple scopes, the nearest `LICENSE` file takes precedence.

## 设计原则 / Design Principles

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

## 当前解析优先级 / Current Resolution Order

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

## 当前状态 / Current Status

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
