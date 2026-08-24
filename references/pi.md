# Pi 适配

仅在当前宿主是 Pi coding agent 时读取；流程与授权以 `SKILL.md` 为准。

## 提问

技术地图生成后，选择、确认和诊断用当前会话的 `question` 扩展；失败即停止决策。问题和选项必须参考技术地图中的方向、前置、边界和成本，只问直接影响学习的信息，提供不推荐的实质不同选项并等待选择；不调用 `ctx.ui.*`。

## 执行

按实际暴露使用 `read`、`bash`、`edit`、`write`、`grep`、`find`、`ls`；`bash` 仅用于练习和探测。Pi 没有核心沙箱，Web/MCP/LSP/todo/subagent 只在扩展注册时存在，不自动安装。先依据初始请求和可用的外部访问用实际 Web/页面读取扩展按[技术地图格式](technology-map-format.md)建图，再提问和选路；范围不足或未核实即停止。显式调用：`/skill:daxue-zhidao`；修改后 `/reload`。
