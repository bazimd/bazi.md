# BAZI.md 规范 / BAZI.md Specification

版本 / Version: `v0.1-draft`

## 1. 概述 / Overview

`BAZI.md` 是一个受八字文化启发、但保持 framework-agnostic 的 AI agent 开放规范。  
`BAZI.md` is a culture-inspired, framework-agnostic open standard for AI agents.

当前草案聚焦一个核心文件：`BAZI.md`，用于定义 agent 的稳定底盘。  
The current draft focuses on one core file: `BAZI.md`, which defines the agent's stable constitution.

推荐生成方式是：先基于 agent 创建时间自动提取年、月、日、时，再生成四柱骨架，最后由项目语义补全行为解释。  
The recommended generation mode is: first extract year, month, day, and hour from the agent creation time, generate the four-pillar skeleton, and then complete the behavioral interpretation through project semantics.

未来可能补充 `bagua.md` 作为动态模式层，但它不属于当前 `v0.1-draft` 的正式范围。  
A future `bagua.md` extension may define dynamic modes, but it is outside the active `v0.1-draft`.

本规范的目标不是保留象征本身，而是要求每个文化语义都具备可操作的系统语义。  
The purpose of the spec is not symbolism alone, but an operational interpretation for every cultural concept.

## 2. 设计目标 / Design Goals

- 文件位置可预测  
  predictable file locations
- 职责分层清晰  
  clear separation of responsibilities
- 支持 layered loading 与 override  
  layered loading and overrides
- 可被机器校验  
  machine-readable validation
- 可跨 agent framework 迁移  
  portability across agent frameworks

## 3. 核心文件 / Core Files

### 3.1 `BAZI.md`

定义 agent 的稳定基础 profile，包括：  
Defines the stable base profile of an agent, including:

- 身份与定位  
  identity and positioning
- 四柱结构  
  four-pillar architecture
- 日主原型  
  day-master archetype
- 十神关系  
  ten-gods composition
- 五行权重  
  elemental weighting
- 格局判断  
  chart structure
- 用神喜忌  
  favorable and unfavorable energies
- 生命周期  
  lifecycle markers
- 系统映射  
  operational system mapping
- 边界与确认规则  
  boundaries and confirmation rules

该文件应低频变化。  
This file should change infrequently.

建议包含生成输入元信息，例如：  
Suggested generation metadata includes:

- `created_at`
- `timezone`
- `creation_source`
- `pillar_derivation`

### 3.2 `AGENTS.md`

定义仓库层面的操作说明，是 bridge file，而不是 `BAZI.md` 的替代品。  
Defines repository-level operational guidance. It is a bridge file, not a replacement for `BAZI.md`.

### 3.3 未来扩展：`bagua.md` / Future Extension: `bagua.md`

`bagua.md` 预留给动态行为层。当前尚未完成研究，因此不纳入正式模板或 schema。  
`bagua.md` is reserved for a future dynamic behavior layer and is not yet part of the formal template or schema.

## 4. 语义模型 / Semantic Model

每个 profile 字段都应同时具备两层语义：  
Each profile field should expose two parallel meanings:

### 4.1 文化语义 / Cultural Semantics

- 四柱  
  four pillars
- 五行  
  five elements
- 阴阳  
  yin and yang
- 日主  
  day master
- 十神  
  ten gods

### 4.2 系统语义 / Operational Semantics

- 决策风格  
  decision style
- 沟通风格  
  communication style
- 协作偏向  
  collaboration bias
- 风险偏好  
  risk tolerance
- 规划深度  
  planning depth
- 上下文敏感度  
  context sensitivity

只有两层语义同时存在时，这个规范才真正可用。  
The spec is only useful when both layers are present.

## 5. 标准化数据形态 / Normalized Data Shape

Markdown 是编写表面，JSON 是校验与集成表面。  
Markdown is the authoring surface; JSON is the validation and integration surface.

实现应能将 `BAZI.md` 归一化为与下列 schema 兼容的结构：  
Implementations should be able to normalize `BAZI.md` into objects compatible with:

- `schemas/bazi-profile.schema.json`

标准化输出至少应保留：  
The normalized form should preserve:

- 标识信息  
  identifiers
- 生成输入  
  generation inputs
- 版本  
  version
- 默认语言  
  language defaults
- 四柱结构  
  four pillars
- 文化字段  
  cultural fields
- 系统映射  
  operational mappings
- 用神喜忌信号  
  favorable and unfavorable signals
- 生命周期信息  
  lifecycle metadata
- 边界  
  boundaries

## 6. 解析优先级 / Resolution Order

建议优先级，从高到低：  
Recommended precedence, from highest to lowest:

1. 运行时指令 / Runtime override
2. 场景级覆盖 / Scenario override
3. `AGENTS.md`
4. `BAZI.md`
5. Framework 默认值 / Framework default

含义：  
Implications:

- `AGENTS.md` 管仓库内执行方式。  
  `AGENTS.md` governs repository execution.
- `BAZI.md` 管稳定体质基线。  
  `BAZI.md` defines the stable constitutional baseline.
- 场景级说明可以进一步细化具体任务。  
  scenario-level instructions may specialize a given task.
- 运行时覆盖拥有最高优先级。  
  runtime overrides have the highest priority.

未来若加入 `bagua.md`，建议放在 `AGENTS.md` 与 `BAZI.md` 之间。  
If `bagua.md` is introduced later, it should sit between `AGENTS.md` and `BAZI.md`.

## 7. 兼容性规则 / Compatibility Rules

- 核心规范必须保持 framework agnostic。  
  The core spec must remain framework-agnostic.
- adapter 可以扩展行为，但不应重写核心语义。  
  Framework adapters may extend behavior but should not rewrite the core semantics.
- 未知字段应尽量保留，除非运行时明确拒绝。  
  Unknown fields should be preserved when possible unless the runtime explicitly rejects them.
- 破坏性变更应提升 spec version。  
  Breaking changes should increment the spec version.

## 8. 校验规则 / Validation Rules

一个最小有效 profile 至少应包含：  
A minimum valid profile should include:

- spec version
- profile name
- agent type
- 创建时间或可等价推导四柱的输入  
  creation time or equivalent inputs that can derive the four pillars
- 四柱章节  
  a four-pillar section
- 稳定体质章节  
  a stable constitution section
- 系统映射章节  
  an operational mapping section
- 明确的边界章节  
  an explicit boundaries section

## 9. 编写约定 / Authoring Conventions

- 使用简洁、可判断的语言。  
  Use concise, deterministic language.
- 不要只写象征，要写行为含义。  
  Prefer operational meaning over symbolism alone.
- 示例应兼顾人类可读与程序可解析。  
  Keep examples readable for humans and parsable for tools.
- 如果文化解释不影响行为，就保持简短。  
  Keep cultural explanation short when it does not affect runtime behavior.

## 10. 示例类型 / Example Profile Types

- strategy planner
- project manager
- product designer
- developer
- growth operations

## 11. 非目标 / Non-Goals

本规范不试图：  
This spec does not attempt to:

- 强制一种信仰体系  
  enforce one belief system
- 用真实命理推导 agent 行为  
  derive behavior from real-world astrology
- 彻底替代 framework-native system prompt  
  replace framework-native system prompts entirely
- 自行定义 tools、memory、planning API  
  define tools, memory, or planning APIs by itself

当前版本只定义稳定 agent constitution 的可移植 profile 层。  
The current version defines only a portable layer for stable agent constitution.

动态模式切换留待未来的 `bagua.md` 扩展。  
Dynamic mode switching is deferred to a future `bagua.md` extension.
