# Pi 适配

仅在当前宿主是 Pi coding agent 时读取；流程与授权以 `SKILL.md` 为准。

## 提问

- Pi 核心没有结构化提问工具，默认用简短文本；当前会话明确提供 `question` 扩展工具时使用它。
- 每次集中 1–3 个问题并给出 2–4 个选项。不调用 `ctx.ui.*`，它是扩展 API。

## 执行

- 内置工具为 `read`、`bash`、`edit`、`write`、`grep`、`find`、`ls`，默认通常只启用前四个；按实际暴露
  情况使用。`read` 可读取常见图像，但还需当前模型支持视觉。
- `bash` 用于练习和经授权的探测。Pi 核心没有文件、进程或网络沙箱，项目信任也不是隔离措施。
- 独立只读调用可并行；核心没有 subagent、Web、MCP、LSP、todo 或 plan mode，只有扩展实际注册为模型
  工具时才使用，不自动安装扩展或 package。
- 显式调用：`/skill:daxue-zhidao`；修改后用 `/reload`。
