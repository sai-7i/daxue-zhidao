# Pi 适配

仅在当前宿主是 Pi coding agent 时读取；流程与授权以 `SKILL.md` 为准。

## 提问

选择、确认、授权和诊断用当前会话的 `question` 扩展；失败即停止决策。只问影响教学的信息，提供不推荐的实质不同选项并等待选择；不调用 `ctx.ui.*`。

## 执行

按实际暴露使用 `read`、`bash`、`edit`、`write`、`grep`、`find`、`ls`；`bash` 仅用于练习和经授权探测。Pi 没有核心沙箱，Web/MCP/LSP/todo/subagent 只在扩展注册时存在，不自动安装。选路前须用实际 Web/页面读取扩展按[技术地图格式](technology-map-format.md)建图，缺能力或未核实即停止。显式调用：`/skill:daxue-zhidao`；修改后 `/reload`。
