# Codex 适配

仅由用户输入 `$daxue-zhidao` 时读取；[Codex 策略](../agents/openai.yaml)禁用隐式调用。流程与授权以 `SKILL.md` 为准。

## 提问

建图后、选路前诊断已有知识；方向和课程选择优先 `request_user_input`，失败用 MCP `mcpServer/elicitation/request` 表单，再失败才文本提问。问题和选项服务路线并对应地图。仅在学习者提出时评估路线、方向或深入范围；不评估具体知识内容；不代选或改用命令审批。

## 执行

按实际能力读取、搜索和最小修改；遵守沙箱、可写根、网络与审批。开课用真实 Web 搜索/页面读取按[课程地图格式](technology-map-format.md)生成详细 `TECHNOLOGY_MAP.md`，诊断已有知识后选路；每次选课按[课次地图格式](lesson-map-format.md)生成详细 `LESSON_MAP.md`，只提供介绍和学习规划。范围不足、搜索或核实失败即停止；显式调用：`$daxue-zhidao`。
