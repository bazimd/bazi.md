# 面向 Claude 的对接草案 / Claude Mapping Draft

## 目标 / Goal

将 `BAZI.md` 规范映射到 Claude 风格的指令栈，同时保留双层语义。  
Map the `BAZI.md` standard into a Claude-style instruction stack while preserving the two-layer meaning.

## 建议映射 / Suggested Mapping

- `BAZI.md` 作为稳定 constitutional profile。  
  `BAZI.md` becomes the stable constitutional profile.
- `AGENTS.md` 保留为仓库级编写与执行桥接层。  
  `AGENTS.md` remains the project-level authoring and execution bridge.

## 操作说明 / Operational Notes

- 将系统映射转换为简洁行为指令，而不是装饰性文案。  
  Convert system mappings into concise behavioral directives, not decorative prose.
- 保持解析优先级，确保 runtime 或 scenario override 仍然生效。  
  Preserve resolution order so runtime or scenario overrides still win.
- 文化术语可以保留，但必须搭配可操作的系统语义。  
  Keep cultural terms visible when useful, but always pair them with operational wording.

未来扩展：  
Future extension:

- 若未来加入 `bagua.md`，可把它作为位于 `BAZI.md` 之上的条件行为叠层。  
  If `bagua.md` is added later, treat it as a conditional behavior overlay above `BAZI.md`.
