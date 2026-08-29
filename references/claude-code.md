# Claude Code 适配

仅由用户输入 `/daxue-zhidao` 时读取；`SKILL.md` 的 `disable-model-invocation: true` 禁止 Claude 自动调用。流程与授权以 `SKILL.md` 为准。

## 提问

建图后、选路前用 `AskUserQuestion` 诊断已有知识；方向和课程选择也用该工具。问题和选项服务路线并对应地图。仅在学习者提出时评估路线、方向或深入范围；不评估具体知识内容。工具不可用/失败即停止决策。直接回答用户问题，学习者回答留在主会话。

## 执行

用 `Read`/`Glob`/`Grep` 检查、`Edit`/`Write` 修改；已知来源用 `WebFetch`，发现资料用 `WebSearch`。开课按[课程地图格式](technology-map-format.md)生成详细 `TECHNOLOGY_MAP.md`，诊断已有知识后选路；每次选课按[课次地图格式](lesson-map-format.md)生成详细 `LESSON_MAP.md`，只提供介绍和学习规划。范围不足或搜索核实失败即停止。
