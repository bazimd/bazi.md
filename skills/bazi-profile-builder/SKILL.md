---
name: bazi-profile-builder
description: 基于真实项目上下文构建或改写项目专属 `BAZI.md` 体质档案，并清晰区分 `AGENTS.md` 的仓库规则与 `BAZI.md` 的 agent 身份。 / Build or refine a project-specific `BAZI.md` constitutional profile from real repository context while separating `AGENTS.md` repo rules from `BAZI.md` agent identity.
---

# BAZI.md 构建器 / BAZI.md Builder

当用户希望为一个真实项目创建或更新 `BAZI.md` 时，使用这个 skill。  
Use this skill when the user wants to create or update `BAZI.md` for a real project.

`BAZI.md` 是 agent 的体质档案，不是仓库操作手册。  
`BAZI.md` is the agent's constitutional profile, not the repository's operating manual.

## 目标 / Goal

基于项目证据产出一个稳定、可复用的 `BAZI.md`，表达：  
Produce a stable and reusable `BAZI.md` grounded in project evidence:

- 这个项目需要什么样的工作方式  
  what kind of work the project demands
- 什么样的气质最适配  
  what temperament best fits the work
- 哪些决策方式、风险偏好与协作姿态应当成为稳定默认值  
  what decision style, risk posture, and collaboration defaults should stay stable

仓库级命令与执行规则必须放在 `AGENTS.md`，不要塞进 `BAZI.md`。  
Keep repo-level commands and workflow rules in `AGENTS.md`, not in `BAZI.md`.

## 优先读取 / Read First

先读取目标项目中这些文件，如果存在：  
Read these files from the target project first, if they exist:

- `README.md`
- `AGENTS.md`
- 现有 `BAZI.md`  
  existing `BAZI.md`
- 产品文档或架构文档  
  product or architecture docs
- package manifest 与主要入口文件  
  package manifests and primary entrypoints

然后读取 skill 自带材料：  
Then read the bundled skill materials:

- `assets/bazi-template.md`
- `references/project-signals.md`
- `references/section-guidance.md`

如有需要，再读示例：  
If useful, also read the examples:

- `examples/minimal-bazi.md`
- `examples/project-inference-example.md`

## 工作流 / Workflow

### 1. 检查项目 / Inspect The Project

只读取足以推断稳定默认值的文件，不要一开始扫完整仓库。  
Read only the files needed to infer stable defaults; do not scan the entire repository at the start.

优先寻找这些信号：  
Prioritize these signals:

- 领域与产品目标  
  domain and product goals
- 目标用户  
  target users
- 正确性或安全性要求  
  safety or correctness bar
- 协作与评审风格  
  collaboration and review style
- 对外文案与沟通语气  
  external tone and communication style

在读取项目语义之前，先检查用户或系统是否已经提供 agent 创建时间。  
Before reading project semantics, first check whether the user or system has already provided the agent creation timestamp.

如果有，优先提取：  
If available, extract first:

- `year`
- `month`
- `day`
- `hour`
- `timezone`

### 2. 区分仓库规则与 agent 身份 / Separate Repo Rules From Agent Identity

把发现分成两类：  
Classify findings into two buckets:

- `AGENTS.md` 材料：  
  `AGENTS.md` material:
  - setup / test / lint / build 命令  
    setup / test / lint / build commands
  - 文件路径  
    file paths
  - contribution 规则  
    contribution rules
  - 仓库专属执行约束  
    repo-specific execution constraints
- `BAZI.md` 材料：  
  `BAZI.md` material:
  - 默认气质  
    default temperament
  - 默认决策方式  
    default decision style
  - 任务适配  
    task affinity
  - 风险偏好  
    risk tolerance
  - 沟通风格  
    communication style
  - 稳定边界  
    stable boundaries

如果一条说明脱离仓库仍然成立，它大概率属于 `BAZI.md`。  
If a statement still makes sense outside the repo, it probably belongs in `BAZI.md`.

### 3. 推断体质结构 / Infer The Constitutional Shape

先做时间推导，再做语义解释。  
Derive from time first, then interpret through semantics.

#### 3.1 时间推导 / Time-Derived Base

如果用户或系统能检测 agent 创建时间：  
If the user or system can detect the agent creation time:

- 先用创建时间推导四柱  
  first derive the four pillars from the timestamp
- 再把项目语义映射到使命、策略、边界与系统映射  
  then map project semantics into mission, strategy, boundaries, and system mapping

不要反过来直接用项目语义替代四柱。  
Do not use project semantics to replace the four pillars entirely.

把项目信号映射到：  
Map project evidence into:

- 四柱  
  four pillars
- 日主  
  day master
- 十神  
  ten gods
- 五行平衡  
  five-element balance
- 格局判断  
  chart structure
- 用神与喜忌  
  favorable and unfavorable energies
- 系统映射  
  system mapping
- 边界  
  boundaries

不要为了文化感而强行堆砌象征。  
Do not force decorative symbolism for its own sake.

### 4. 填写模板 / Fill The Template

默认使用 `assets/bazi-template.md` 作为输出骨架；如果目标项目已有更好的本地 `BAZI.md`，则在其基础上迭代。  
Use `assets/bazi-template.md` as the default skeleton unless the target project already has a stronger local `BAZI.md`.

如果存在创建时间输入，优先填写 `created_at`、`timezone`、`creation_source` 与 `pillar_derivation`。  
If creation-time inputs exist, populate `created_at`, `timezone`, `creation_source`, and `pillar_derivation` first.

要求：  
Requirements:

- 保持中文优先，并提供英文辅助  
  keep Chinese first with English support
- 用简洁、可判断的语言  
  use concise, deterministic language
- 保持 framework agnostic  
  preserve framework agnosticism
- 明确边界  
  make boundaries explicit
- 生命周期部分只有在项目信号明确时才展开  
  keep lifecycle notes lightweight unless the project clearly implies them

### 5. 校验草稿 / Validate The Draft

完成前检查：  
Before finishing, check:

- `BAZI.md` 里没有仓库命令  
  no repo commands were placed in `BAZI.md`
- 系统语义是否明确  
  operational semantics are explicit
- 草稿是否匹配项目真实质量要求  
  the draft matches the project's actual quality bar
- profile 是否稳定，而不是只服务某个临时任务  
  the profile is stable rather than overfit to one temporary task
- 结构是否仍与 `schemas/bazi-profile.schema.json` 对齐  
  the structure still matches `schemas/bazi-profile.schema.json`

## 输出规则 / Output Rules

- 如果用户要求直接修改文件，就直接写或更新 `BAZI.md`。  
  If the user asked for a file change, write or update `BAZI.md` directly.
- 如果仓库已有 `BAZI.md`，优先精修，不要盲目重写。  
  If the repository already has `BAZI.md`, refine it instead of replacing good material blindly.
- 证据不足时，应显式写出假设。  
  When evidence is weak, state the assumption rather than pretending certainty.
- 宁可保守，也不要写成戏剧化 archetype。  
  Prefer a conservative baseline over a dramatic archetype.

## 常见失败方式 / Common Failure Modes

- 把 `BAZI.md` 写成另一个 `AGENTS.md`  
  turning `BAZI.md` into another `AGENTS.md`
- 把项目 slogan 复制到每一节，却没有行为含义  
  copying project slogans into every section without operational meaning
- 过度拟合当前任务，而不是稳定默认值  
  overfitting the profile to current tasks instead of stable defaults
- 只写象征，不写行为后果  
  choosing symbolic terms with no behavioral consequence
- 所有项目都写成泛化的 strategist  
  making every project a generic strategist profile

## 启发式捷径 / Heuristic Shortcuts

- 基础设施、安全、审计、合规项目通常偏强 `金` 与 `土`  
  infra, security, review, and compliance-heavy projects often bias toward stronger `metal` and `earth`
- 研究、探索、综合、自适应系统通常偏强 `水`  
  research, discovery, synthesis, and adaptive systems often bias toward stronger `water`
- 产品策略、增长、创意、路线图工作通常增加 `木`  
  product strategy, growth, ideation, and roadmap work often increase `wood`
- 沟通、布道、教学、展示类工作通常增加 `火`  
  communication-heavy, evangelism, teaching, and presentation work often increase `fire`
- 稳定交付、服务可靠性、运营支持通常增加 `土`  
  execution reliability, service stability, and operations work often increase `earth`

这些只是启发，不是规则，最终以项目证据为准。  
These are hints, not rules. Repository evidence wins.
