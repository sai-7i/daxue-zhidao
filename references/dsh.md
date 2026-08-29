# DSH 适配

仅由用户输入 `/daxue-zhidao` 时读取；流程与授权以 `SKILL.md` 为准。

## 提问

建图后、选路前用 `ask_user_question` 诊断已有知识；方向和课程选择也用该工具。问题和选项服务路线并对应地图。仅在学习者提出时评估路线、方向或深入范围；不评估具体知识内容。工具/界面缺失或失败即停止。学习者回答留在主会话。

## 执行

能力皆为已加载插件。用 `read`/`edit`/`write` 管理文件、`glob`/`grep` 搜索；已知来源用 `web_fetch`，发现资料用 `web_search`。开课按[课程地图格式](technology-map-format.md)生成详细 `TECHNOLOGY_MAP.md`，诊断已有知识后选路；每次选课按[课次地图格式](lesson-map-format.md)生成详细 `LESSON_MAP.md`，只提供介绍和学习规划。范围不足或未核实即停止；显式调用：`/daxue-zhidao`。
