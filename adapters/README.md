# 适配层 / Adapter Layer

适配层负责把核心 `BAZI.md` 规范映射到不同 framework 的运行时约定。  
The adapter layer maps the core `BAZI.md` standard into framework-specific runtime conventions.

每个 adapter 文档应回答：  
Each adapter document should explain:

- `BAZI.md` 如何映射到稳定 system instructions 或 role definitions  
  how `BAZI.md` maps to stable system instructions or role definitions
- `AGENTS.md` 如何作为仓库桥接层保留  
  how `AGENTS.md` remains the repository bridge layer
- 哪些能力可以强约束，哪些只是建议性映射  
  which behaviors can be enforced directly and which remain advisory
- 未来动态层加入后，应如何扩展  
  how future dynamic layers could extend the mapping

规则：  
Rules:

- framework 细节不要写进核心 spec  
  keep framework-specific details out of the core spec
- 映射时尽量保留原始语义  
  preserve normalized semantics when mapping
- 优先做增量映射，不做破坏性重写  
  prefer additive mappings over destructive rewrites
