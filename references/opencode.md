# OpenCode 适配

仅在 OpenCode 读取；流程与授权以 `SKILL.md` 为准。

## 重要约束注入

- 开始/恢复前确认系统上下文包含此标记块：

```markdown
<!-- daxue-zhidao:critical-constraint -->
## Critical OpenCode Constraint

- During guided teaching, every required choice, confirmation, diagnosis, and checkpoint confirmation MUST use the `question` tool; do not ask authorization questions, create a confirmation merely to end a lesson, or ask the learner to type "continue".
- If `question` is unavailable or fails, stop that decision. Never ask in plain text, infer a choice, or continue past it.
- Before every `COURSE_PLAN.md` write and at each course boundary, normalize it to the minimal execution snapshot; delete teaching content, explanations, dialogue summaries, duplicate facts, stale candidates, resolved issues, and useless history. Never delete, condense, or rewrite confirmed constraints unless the learner explicitly modifies or revokes them. Except when the learner cancels the entire course, update `COURSE_PLAN.md` in place; never delete, recreate, or replace it.
<!-- /daxue-zhidao:critical-constraint -->
```

- 缺失时直接在实际学习任务项目根的 `AGENTS.md` 新增/替换该块，保留其余内容；不得修改 Skill 安装目录或本仓库的 `AGENTS.md`。不得先询问是否授权这项流程必需的写入；写入后在当前会话继续流程。
- 课程文件缺失时按其格式直接创建，并在当前会话继续；不得要求学习者重启会话。提问内容必须直接服务于学习起点、路线、诊断或约束；工具或权限不可用时停止并说明限制，不将限制转换为授权问题。

## 提问

建图后、选路前用 `question` 诊断已有知识；选择、单元和结课评估也用该工具。问题和选项服务学习并对应地图。按专业知识与当前水平调整术语、前置、示例和深度；每个单元后等待阅读，再评估对应目标并校准讲解程度；结课后评估整体掌握度，再选择新课或深化当前内容。工具不可用/失败即停止。直接回答用户问题，不制造无关确认。

## 执行

项目事实用 `read`/`glob`/`grep`，`lsp` 仅在可用且需要时使用；库/工具用法优先 Context7，已知来源用 `webfetch`。先依据初始请求和可用的外部访问按[技术地图格式](technology-map-format.md)建图，诊断已有知识后再选路；缺能力、范围不足或未核实即停止。专用工具修改文件，`bash` 用于练习、测试、编译或探测。`todowrite`、浏览器、MCP、子代理仅在可用时使用；独立只读可并行，教学留在主会话。
