# OpenCode 适配

仅在当前宿主是 OpenCode 时读取；流程与授权以 `SKILL.md` 为准。

## 重要约束注入

- 开始或恢复课程前，确认当前系统上下文是否已包含以下标记块：

```markdown
<!-- daxue-zhidao:critical-constraint -->
## Critical OpenCode Constraint

- During guided teaching, every choice, confirmation, authorization, diagnosis, and checkpoint confirmation MUST use the `question` tool.
- If `question` is unavailable or fails, stop that decision. Never ask in plain text, infer a choice, or continue past it.
- Before every `COURSE_PLAN.md` write and at each course boundary, normalize it to the minimal execution snapshot; delete teaching content, explanations, dialogue summaries, duplicate facts, stale candidates, resolved issues, and useless history.
<!-- /daxue-zhidao:critical-constraint -->
```

- 上下文未包含正确标记块时，必须先用 `question` 取得检查并按需更新当前项目 `AGENTS.md` 的授权；保留原内容，只新增或替换该标记块。
- 未授权、文件冲突、写入失败或 `question` 失败时停止课程。写入后停止本轮，要求学习者重新启动 OpenCode 会话，使约束进入系统上下文。

## 提问

- 选择、确认、授权、诊断和检查点确认必须用 `question`；尽可能详细覆盖会影响课程的所有问题。
- 提供尽可能多的有实质差异的选项，覆盖不同目标、基础、约束和路线；不标注推荐项，必须等待学习者明确选择。
- 工具未提供或调用失败时停止当前决策，不得改用文本提问或代为选择。

## 执行

- 项目事实用 `read`、`glob`、`grep`；符号、引用或诊断需要且 `lsp` 可用时使用 `lsp`。
- 库和工具当前用法优先查 Context7；已知来源用 `webfetch`。MCP、浏览器、图片等仅在实际提供时使用。
- 文件修改用专用编辑工具；`bash` 用于练习、测试、编译及经授权的只读探测。
- 三步以上执行可用 `todowrite`。复杂代码库探索可委派 `explore`，独立研究可委派合适的子代理；
  独立只读工作可并行，交互教学留在主会话。
