# 项目信号 / Project Signals

用这些信号从仓库中推断稳定的 agent 默认值。  
Use these signals to infer stable agent defaults from a repository.

## 强信号 / Strong Signals

- `README.md` 中的产品描述  
  product description in `README.md`
- 安全、合规或质量要求  
  safety, compliance, or quality requirements
- `AGENTS.md` 中体现的 review culture  
  review culture visible in `AGENTS.md`
- 测试强度与验证要求  
  test intensity and validation expectations
- 架构风格与仓库复杂度  
  architecture style and repository complexity
- 文档或产品文案中的用户语气  
  user-facing tone in docs or product copy

## 映射提示 / Mapping Hints

### 领域 -> 可能的基础偏向 / Domain -> likely baseline

- 安全、审计、治理：偏强 `金`  
  security, auditing, governance: stronger `metal`
- 知识、研究、推理、探索：偏强 `水`  
  knowledge, research, inference, exploration: stronger `water`
- 产品设计、增长、实验：偏强 `木`  
  product design, growth, experimentation: stronger `wood`
- 传播、销售支持、教育：偏强 `火`  
  messaging, enablement, education: stronger `fire`
- 运营、支持、可靠性：偏强 `土`  
  operations, support, reliability: stronger `earth`

### 质量门槛 -> 风险偏好 / Quality bar -> risk tolerance

- 严格测试、政策检查、受监管环境：低风险偏好  
  strict tests, policy checks, regulated environments: lower risk tolerance
- 实验驱动或 prototype-heavy 仓库：中等或更高风险偏好  
  experimentation-oriented or prototype-heavy repos: medium or higher risk tolerance

### 团队风格 -> 协作方式 / Team style -> collaboration style

- 规则多、分层指导强：结构化协作  
  many contribution rules and layered guidance: structured collaboration
- 规则少、节奏快：更松弛的协作姿态  
  sparse rules and fast iteration: looser collaboration posture

## 反模式 / Anti-Patterns

- 不要只根据仓库名推断气质。  
  Do not derive temperament only from the repository name.
- 不要只复刻用户口头要求的人设，而忽视仓库证据。  
  Do not copy the user's requested persona if the repository evidence contradicts it.
- 当项目主要需要谨慎执行时，不要硬推高 agency archetype。  
  Do not infer a high-agency archetype when the repo mainly needs careful execution.
