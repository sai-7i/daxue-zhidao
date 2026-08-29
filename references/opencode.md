# OpenCode 适配

仅由用户输入 `/daxue-zhidao` 时读取；流程与授权以 `SKILL.md` 为准。为避免 agent 发现该 Skill，在 OpenCode 配置中拒绝它：

```json
{
  "permission": {
    "skill": {
      "daxue-zhidao": "deny"
    }
  }
}
```

该配置仅从 agent 的可用 Skill 列表移除它，不影响用户的斜杠命令。

## 重要约束注入

- 开始/恢复前确认系统上下文包含此标记块：

```markdown
<!-- daxue-zhidao:critical-constraint -->
## Critical OpenCode Constraint

- During learning planning, every required diagnosis and direction or lesson choice MUST use the `question` tool; do not ask authorization questions or create unrelated confirmations.
- If `question` is unavailable or fails, stop that decision. Never ask in plain text, infer a choice, or continue past it.
- Before every `COURSE_PLAN.md` write and route or lesson boundary, normalize it to the minimal route snapshot; delete teaching content, detailed lesson content, duplicate facts, stale candidates, resolved issues, and history. Never delete, condense, or rewrite confirmed constraints unless the learner explicitly modifies or revokes them. Except when the learner cancels the entire course, update `COURSE_PLAN.md` in place.
<!-- /daxue-zhidao:critical-constraint -->
```

- 缺失时直接在实际学习任务项目根的 `AGENTS.md` 新增/替换该块，保留其余内容；不得修改 Skill 安装目录或本仓库的 `AGENTS.md`。不得先询问是否授权这项流程必需的写入；写入后在当前会话继续流程。
- 课程文件缺失时按其格式直接创建，并在当前会话继续；不得要求学习者重启会话。提问内容必须直接服务于学习起点、路线、诊断或约束；工具或权限不可用时停止并说明限制，不将限制转换为授权问题。

## 提问

建图后、选路前用 `question` 诊断已有知识；方向和课程选择也用该工具。问题和选项服务路线并对应地图。仅在学习者提出时评估路线、方向或深入范围；不评估具体知识内容。工具不可用/失败即停止。直接回答用户问题，不制造无关确认。

## 执行

项目事实用 `read`/`glob`/`grep`，库/工具用法优先 Context7，已知来源用 `webfetch`。开课生成详细 `TECHNOLOGY_MAP.md`，诊断已有知识后选路；每次选课按[课次地图格式](lesson-map-format.md)生成详细 `LESSON_MAP.md`，只提供介绍和学习规划。缺能力、范围不足或未核实即停止。专用工具修改文件；独立只读可并行，流程留在主会话。
