# 仓库操作契约 / AGENTS.md

## 目的 / Purpose

本仓库定义一个以 `BAZI.md` 为核心的、framework-agnostic 的开放规范。  
This repository defines a framework-agnostic open standard centered on `BAZI.md`.

`AGENTS.md` 是本仓库的操作契约。`BAZI.md` 是 agent 自身的稳定体质档案。  
`AGENTS.md` is the repository's operational contract. `BAZI.md` is the agent's stable constitutional profile.

当仓库执行规则与 `BAZI.md` 的默认气质冲突时，以本文件为准。  
When repository workflow rules conflict with defaults in `BAZI.md`, follow this file.

## 事实来源 / Source Of Truth

- `SPEC.md` 定义正式语义。  
  `SPEC.md` defines the formal semantics.
- `templates/BAZI.md` 定义稳定底盘模板。  
  `templates/BAZI.md` defines the stable constitution template.
- `schemas/` 存放机器可读校验规则。  
  `schemas/` contains machine-readable validation rules.
- `adapters/` 存放 framework 映射说明。  
  `adapters/` contains framework mapping notes.
- `examples/` 存放参考 profile。  
  `examples/` contains reference profiles.

`bagua.md` 是未来扩展，不属于当前活动草案。  
`bagua.md` is a future extension and is not part of the active draft.

## 贡献规则 / Contribution Rules

- 不要把 framework-specific 假设写进核心规范。  
  Do not add framework-specific assumptions to the core spec.
- 文化术语与系统语义必须并行出现。  
  Keep cultural terms and operational semantics in parallel.
- 新增字段时，规范与 schema 必须同步更新。  
  Update the spec and schema together when adding fields.
- adapter 行为应放在 `adapters/`，不要塞进核心模板。  
  Adapter-specific behavior belongs in `adapters/`, not in the core template.
- 示例保持简洁，并体现明确行为差异。  
  Keep examples concise and behaviorally clear.

## 编写原则 / Authoring Guidance

- 优先使用可判断、可执行的默认值，不要写空泛抒情句。  
  Prefer deterministic defaults over vague poetic language.
- 每个文化概念都要翻译成可操作的系统语义。  
  Translate every cultural concept into operational semantics.
- 边界要明确：应该做什么、不该做什么、何时需要确认。  
  Make boundaries explicit: what to do, what not to do, and when confirmation is required.
- 保持“稳定体质”和“仓库执行规则”的分离。  
  Preserve the separation between stable constitution and repository execution rules.

## 检查清单 / Review Checklist

- 是否仍保持 framework agnostic。  
  Does the change remain framework-agnostic?
- 是否让解析顺序更清晰，而不是更混乱。  
  Does it make resolution order clearer rather than blurrier?
- schema 与 spec 是否同步。  
  Are the schema and spec updated together?
- 示例是否仍与当前草案一致。  
  Do the examples still align with the current draft?
