# ZCode 适配

仅由用户输入 `/daxue-zhidao` 时读取；流程与授权以 `SKILL.md` 为准。

## 提问

建图后、选路前用 `AskUserQuestion` 诊断已有知识；方向和课程选择也用该工具。问题和选项服务路线并对应地图。仅在学习者提出时评估路线、方向或深入范围；不评估具体知识内容。工具不可用/失败即停止。学习者活动留在主会话。

## 执行

用 `Read`/`Edit`/`Write` 管理文件；已知来源用 `WebFetch`，发现资料用实际搜索工具。开课按[课程地图格式](technology-map-format.md)生成详细 `TECHNOLOGY_MAP.md`，诊断已有知识后选路；每次选课按[课次地图格式](lesson-map-format.md)生成详细 `LESSON_MAP.md`，只提供介绍和学习规划。范围不足或未核实即停止。显式调用：`/daxue-zhidao`。
