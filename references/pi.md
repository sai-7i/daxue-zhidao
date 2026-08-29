# Pi 适配

仅由用户输入 `/skill:daxue-zhidao` 时读取；流程与授权以 `SKILL.md` 为准。

## 提问

建图后、选路前用当前会话的 `question` 扩展诊断已有知识；方向和课程选择也用该扩展，失败即停止决策。问题和选项服务路线并对应地图。仅在学习者提出时评估路线、方向或深入范围；不评估具体知识内容；不调用 `ctx.ui.*`。

## 执行

按实际暴露使用 `read`、`edit`、`write`、`grep`、`find`、`ls`。Pi 没有核心沙箱，Web/MCP/LSP/todo/subagent 只在扩展注册时存在。开课用实际 Web/页面读取扩展按[课程地图格式](technology-map-format.md)生成详细 `TECHNOLOGY_MAP.md`，诊断已有知识后选路；每次选课按[课次地图格式](lesson-map-format.md)生成详细 `LESSON_MAP.md`，只提供介绍和学习规划。范围不足或未核实即停止。显式调用：`/skill:daxue-zhidao`；修改后 `/reload`。
