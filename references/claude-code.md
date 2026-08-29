# Claude Code 适配

仅由用户输入 `/daxue-zhidao` 时读取；`SKILL.md` 的 `disable-model-invocation: true` 禁止 Claude 自动调用。流程与授权以 `SKILL.md` 为准。

## 提问

建图后、选路前用 `AskUserQuestion` 诊断已有知识；选择、单元和结课评估也用该工具。问题和选项服务学习并对应地图。按专业知识与当前水平调整术语、前置、示例和深度；每个单元后等待阅读，再评估对应目标并校准讲解程度；结课后评估整体掌握度，再选择新课或深化当前内容。工具不可用/失败即停止决策。直接回答用户问题，学习者回答留在主会话。

## 执行

用 `Read`/`Glob`/`Grep` 检查、`Edit`/`Write` 修改、`Bash` 练习或探测；已知来源用 `WebFetch`，发现资料用 `WebSearch`。先依据初始请求和可用的外部访问按[技术地图格式](technology-map-format.md)研究，诊断已有知识后再选路；范围不足或搜索核实失败即停止。`LSP`、`NotebookEdit`、`Agent` 仅在可用且适用时使用。
