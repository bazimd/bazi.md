# 面向 Codex 的对接草案 / Codex Mapping Draft

## 目标 / Goal

将 `BAZI.md` 规范映射到兼容 Codex 的分层指令结构。  
Map the `BAZI.md` standard into a Codex-compatible layered setup.

## 建议映射 / Suggested Mapping

- `BAZI.md` 映射到稳定的 agent 身份、工作风格、边界条件与决策姿态。  
  `BAZI.md` maps to stable agent identity, working style, boundary conditions, and decision posture.
- `AGENTS.md` 继续作为仓库级桥接文件。  
  `AGENTS.md` remains the repository bridge file for project-level instructions.

## 操作说明 / Operational Notes

- 将稳定体质写入 repository instructions 或生成后的 system / developer guidance。  
  Put stable constitution into repository instructions or generated system/developer guidance.
- 把 `requires_confirmation` 视为强确认边界。  
  Preserve explicit `requires_confirmation` rules as hard confirmation boundaries.
- 除非 framework 必须合并输出，否则不要把 tool policy 混入 Bazi spec。  
  Keep tool-use policy outside the Bazi spec unless the framework requires merged output.

未来扩展：  
Future extension:

- 若未来加入 `bagua.md`，可将其映射为场景选择器或任务类别路由规则。  
  If `bagua.md` is added later, map it into scenario selectors or task-class routing rules.

## 示例 / Example

- 强 `金` + reviewer 原型 -> 更严格的 review 姿态、更低的模糊容忍度、更紧的边界检查。  
  Strong `metal` + reviewer archetype -> stricter review posture, lower ambiguity tolerance, tighter boundary checks.
- 若未来存在 `震` 模式 -> 更快探索、更大发散、更适合早期草稿。  
  If a future `zhen` mode exists -> faster exploration, broader divergence, early draft output.
- 若未来存在 `艮` 模式 -> 暂停、验证、收缩范围、偏向保守行动。  
  If a future `gen` mode exists -> pause, verify, constrain scope, prefer conservative action.
