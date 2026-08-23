# DSH 适配

仅在当前宿主是 DeepSeek Harness（dsh）时读取；流程与授权以 `SKILL.md` 为准。

## 提问

选择、确认、授权和诊断用 `ask_user_question`，只问影响教学的信息，给出不推荐的实质不同选项；工具/界面缺失或失败即停止。学习者回答留在主会话。

## 执行

能力皆为已加载插件。用 `read`/`edit`/`write` 管理文件、`glob`/`grep` 搜索、`bash` 练习/测试或经授权探测；已知来源用 `web_fetch`，发现资料用 `web_search`。选路前用实际 `web_search`/`web_fetch` 按[技术地图格式](technology-map-format.md)建图，缺能力或未核实即停止。`lsp`、`todo_write`、`subagent` 仅在可用时使用，子代理只做有界只读工作；显式调用：`/daxue-zhidao`。
