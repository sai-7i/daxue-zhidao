# Claude Code 适配

仅在当前宿主是 Claude Code 时读取；流程与授权以 `SKILL.md` 为准。

## 提问

- 选择、确认、授权、诊断和检查点确认必须用 `AskUserQuestion`；默认每次合并最多 4 个相关问题，尽量覆盖当前需要的信息，每题 2–4 个选项。信息已足够或学习者明确不确定时可以少问，不为凑数询问无关内容。
- 仅在工具未提供、被权限禁止或调用失败时用同等内容的文本，并说明降级。
- 子代理通常不能使用 `AskUserQuestion`，需要学习者回答的步骤留在主会话。

## 执行

- 用 `Read`、`Glob`、`Grep` 检查文件，`Edit`/`Write` 修改，`Bash` 执行练习和经授权的探测。
- 已知来源用 `WebFetch`，发现资料用可用的 `WebSearch`。LSP 插件与服务器均可用时才用 `LSP`；
  `NotebookEdit` 仅用于 Notebook 课程。
- 可用 `Agent` 并行委派有界的只读研究；不依赖旧称 `Task`、agent teams、任务工具、MCP 或插件必定存在。
- 权限提示不代替课程授权，也不声称 `Bash` 必然运行在沙箱中。
