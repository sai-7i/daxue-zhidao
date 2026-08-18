# Claude Code 适配

仅在当前宿主是 Claude Code 时读取；流程与授权以 `SKILL.md` 为准。

## 提问

- 选择、确认、授权、诊断和检查点确认必须用 `AskUserQuestion`；尽可能详细覆盖会影响课程的所有问题。
- 提供尽可能多的有实质差异的选项，覆盖不同目标、基础、约束和路线；不标注推荐项，必须等待学习者明确选择。
- 工具未提供、被权限禁止或调用失败时停止当前决策，不得改用文本提问或代为选择。
- 子代理通常不能使用 `AskUserQuestion`，需要学习者回答的步骤留在主会话。

## 执行

- 用 `Read`、`Glob`、`Grep` 检查文件，`Edit`/`Write` 修改，`Bash` 执行练习和经授权的探测。
- 已知来源用 `WebFetch`，发现资料用可用的 `WebSearch`。LSP 插件与服务器均可用时才用 `LSP`；
  `NotebookEdit` 仅用于 Notebook 课程。
- 可用 `Agent` 并行委派有界的只读研究；不依赖旧称 `Task`、agent teams、任务工具、MCP 或插件必定存在。
- 权限提示不代替课程授权，也不声称 `Bash` 必然运行在沙箱中。
