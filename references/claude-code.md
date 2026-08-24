# Claude Code 适配

仅在当前宿主是 Claude Code 时读取；流程与授权以 `SKILL.md` 为准。

## 提问

技术地图生成后，选择、诊断和单元掌握评估用 `AskUserQuestion`，只问直接影响学习的信息；问题和选项必须参考技术地图中的方向、前置、边界和成本。每个单元讲解后先等待学习者阅读，再用与该单元目标直接相关的问题评估掌握程度；工具不可用/失败即停止决策。用户问题直接回答，学习者回答留在主会话。

## 执行

用 `Read`/`Glob`/`Grep` 检查、`Edit`/`Write` 修改、`Bash` 练习或探测；已知来源用 `WebFetch`，发现资料用 `WebSearch`。先依据初始请求和可用的外部访问按[技术地图格式](technology-map-format.md)研究，再提问和选路；范围不足或搜索核实失败即停止。`LSP`、`NotebookEdit`、`Agent` 仅在可用且适用时使用。
