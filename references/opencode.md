# OpenCode 适配

仅用户 `/daxue-zhidao` 调用。要从 agent 的可用 Skill 列表隐藏它，配置：

```json
{
  "permission": {
    "skill": {
      "daxue-zhidao": "deny"
    }
  }
}
```

不影响用户斜杠命令。

缺失时，在学习项目根 `AGENTS.md` 新增或替换此块，保留其他内容并继续：

```markdown
<!-- daxue-zhidao:critical-constraint -->
## Critical OpenCode Constraint

- During learning planning, every required diagnosis and direction or lesson choice MUST use the `question` tool; do not ask authorization questions or create unrelated confirmations.
- If `question` is unavailable or fails, stop that decision. Never ask in plain text, infer a choice, or continue past it.
- Before every `COURSE_PLAN.md` write and route or lesson boundary, normalize it to the minimal route snapshot; delete teaching content, detailed lesson content, duplicate facts, stale candidates, resolved issues, and history. Never delete, condense, or rewrite confirmed constraints unless the learner explicitly modifies or revokes them. Except when the learner cancels the entire course, update `COURSE_PLAN.md` in place.
<!-- /daxue-zhidao:critical-constraint -->
```

用 `question` 诊断、选方向和选课；失败即停止。用 `read`/`glob`/`grep`、Context7 和 `webfetch` 按[课程地图格式](technology-map-format.md)及[课次地图格式](lesson-map-format.md)生成地图；只提供介绍和规划。
