# OpenCode 适配

仅在 OpenCode 读取；流程与授权以 `SKILL.md` 为准。

## 重要约束注入

- 开始/恢复前确认系统上下文包含此标记块：

```markdown
<!-- daxue-zhidao:critical-constraint -->
## Critical OpenCode Constraint

- During guided teaching, every required choice, confirmation, authorization, diagnosis, and checkpoint confirmation MUST use the `question` tool; do not create a confirmation merely to end a lesson or ask the learner to type "continue".
- If `question` is unavailable or fails, stop that decision. Never ask in plain text, infer a choice, or continue past it.
- Before every `COURSE_PLAN.md` write and at each course boundary, normalize it to the minimal execution snapshot; delete teaching content, explanations, dialogue summaries, duplicate facts, stale candidates, resolved issues, and useless history. Never delete, condense, or rewrite confirmed constraints unless the learner explicitly modifies or revokes them. Except when the learner cancels the entire course, update `COURSE_PLAN.md` in place; never delete, recreate, or replace it.
<!-- /daxue-zhidao:critical-constraint -->
```

- 缺失时先用 `question` 授权，再仅在实际学习任务项目根的 `AGENTS.md` 新增/替换该块，保留其余内容；不得修改 Skill 安装目录或本仓库的 `AGENTS.md`。
- 未授权、冲突、写入或提问失败即停止；写入后结束本轮，待学习者重启会话。

## 提问

技术地图生成后，选择、确认、授权和诊断用 `question`，只问影响教学的信息；问题和选项必须参考技术地图中的方向、前置、边界和成本，给出不推荐的实质不同选项。工具不可用/失败即停止。用户问题直接回答，不能为每节课制造检查或继续确认。

## 执行

项目事实用 `read`/`glob`/`grep`，`lsp` 仅在可用且需要时使用；库/工具用法优先 Context7，已知来源用 `webfetch`。先依据初始请求和已获授权的外部访问按[技术地图格式](technology-map-format.md)建图，再提问和选路；缺能力、范围不足或未核实即停止。专用工具修改文件，`bash` 用于练习、测试、编译或经授权探测。`todowrite`、浏览器、MCP、子代理仅在可用时使用；独立只读可并行，教学留在主会话。
