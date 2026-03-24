# BAZI.md

一个面向 AI Agent 的开源标准：用 `BAZI.md` 定义稳定体质，用 `AGENTS.md` 定义仓库执行规则。  
An open-source standard for AI agents: use `BAZI.md` for stable constitution, and `AGENTS.md` for repository execution rules.

`BAZI.md` 以八字语言为灵感，但输出的是可执行、可迁移、可校验的 agent profile。  
`BAZI.md` is inspired by Bazi language, but the output is an operational, portable, and validatable agent profile.

![BAZI.md web demo](https://bazimd.github.io/bazi.md/assets/readme-hero2.png)

- Demo: [bazimd.github.io/bazi.md](https://bazimd.github.io/bazi.md/)
- Spec: [SPEC.md](SPEC.md)
- Template: [templates/BAZI.md](templates/BAZI.md)
- Schema: [schemas/bazi-profile.schema.json](schemas/bazi-profile.schema.json)

## Overview

`BAZI.md` 是一个 framework-agnostic 的 profile layer，用来描述 agent 的默认身份、决策偏好、协作方式和边界。  
`BAZI.md` is a framework-agnostic profile layer for describing an agent's default identity, decision bias, collaboration style, and boundaries.

这个项目把文化语义和系统语义并排组织，让 profile 既能被人读懂，也能被工具使用。  
This project keeps cultural semantics and operational semantics side by side, so profiles stay readable for humans and usable for tools.

它不是某个单一框架的 prompt 模板，而是一个可以跨仓库、跨团队、跨 agent runtime 复用的开放规范。  
It is not a prompt template for one framework, but an open standard that can move across repositories, teams, and agent runtimes.

## Core Idea

- `AGENTS.md` 描述 agent 该如何工作。  
  `AGENTS.md` tells an agent how to work.
- `BAZI.md` 向 framework 或 runtime 说明：这个 agent 默认是什么样的。  
  `BAZI.md` tells a framework or runtime what kind of agent this is by default.

## Demo

在线 Demo 可以输入时间和时区，自动推导四柱并生成一个可复制、可下载的基础 `BAZI.md`。  
The live demo lets you enter a timestamp and timezone, derive the Four Pillars, and generate a base `BAZI.md` you can copy or download.

地址： [https://bazimd.github.io/bazi.md/](https://bazimd.github.io/bazi.md/)  
Live URL: [https://bazimd.github.io/bazi.md/](https://bazimd.github.io/bazi.md/)

![BAZI.md web demo](https://bazimd.github.io/bazi.md/assets/readme-hero.png)

## Use Cases

- 为新 agent 生成统一的底层 profile。  
  Create a consistent base profile for new agents.
- 给团队里的不同 agent 角色建立可复用 archetype。  
  Define reusable archetypes for different agent roles across a team.
- 把同一个 agent profile 映射到不同 framework。  
  Map the same agent profile into different frameworks.
- 在项目内清晰区分“仓库怎么做事”与“agent 默认是什么样”。  
  Clearly separate "how this repo works" from "what this agent is by default."

## Repository Structure

```text
.
├── AGENTS.md
├── BAZI.md
├── LICENSE
├── README.md
├── SPEC.md
├── adapters/
├── assets/
├── examples/
├── index.html
├── schemas/
├── skills/
└── templates/
```

## Status

当前版本是 `v0.1-draft`。  
The current version is `v0.1-draft`.

当前重点是把核心标准骨架确定下来：  
The current focus is locking down the minimum standard shape:

下一步计划进行 `BAGUA.md` 扩展。  
Next step will continue developing `BAGUA.md`.

## Contributing

欢迎 issue、discussion 和 PR。  
Issues, discussions, and PRs are welcome.

提交前请遵守这几个原则：  
Before contributing, keep these rules in mind:

- 核心规范保持 framework agnostic。  
  Keep the core spec framework-agnostic.
- 文化术语和系统语义并行出现。  
  Keep cultural terms paired with operational semantics.
- 新增字段时同步更新 spec 和 schema。  
  Update the spec and schema together when adding fields.
- adapter 行为放进 `adapters/`，不要塞进核心模板。  
  Put adapter behavior in `adapters/`, not in the core template.

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

## Note

This is a fun project made to laugh with the moment we're in: an era where AI agents are supposedly reshaping human work. Or maybe just reshaping the way we talk about it.