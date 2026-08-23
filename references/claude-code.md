# Claude Code 适配

仅在当前宿主是 Claude Code 时读取；流程与授权以 `SKILL.md` 为准。

## 提问

选择、确认、授权和诊断用 `AskUserQuestion`，只问影响教学的信息，给出不推荐的实质不同选项；工具不可用/失败即停止决策。用户问题直接回答，学习者回答留在主会话。

## 执行

用 `Read`/`Glob`/`Grep` 检查、`Edit`/`Write` 修改、`Bash` 练习或经授权探测；已知来源用 `WebFetch`，发现资料用 `WebSearch`。选路前用实际可用的 `WebSearch`/`WebFetch` 按[技术地图格式](technology-map-format.md)研究，搜索或核实失败即停止。`LSP`、`NotebookEdit`、`Agent` 仅在可用且适用时使用；权限提示不代替课程授权。
