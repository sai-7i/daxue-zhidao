# ZCode 适配

仅在当前宿主是 ZCode 时读取；流程与授权以 `SKILL.md` 为准。

## 提问

选择、确认、授权和诊断用 `AskUserQuestion`，只问影响教学的信息，给出不推荐的实质不同选项；工具不可用/失败即停止。权限提示不代替课程授权，学习者活动留在主会话。

## 执行

用 `Read`/`Edit`/`Write` 管理文件，`Bash` 练习、搜索、测试或经授权探测；已知来源用 `WebFetch`，发现资料用实际搜索工具。选路前用实际搜索/页面读取按[技术地图格式](technology-map-format.md)建图，缺能力或未核实即停止。`TodoWrite`、`Agent`、浏览器、MCP 等仅在可用且获授权时使用；显式调用：`/daxue-zhidao`。
