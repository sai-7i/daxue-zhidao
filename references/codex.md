# Codex 适配

仅用户 `$daxue-zhidao` 调用；[策略](../agents/openai.yaml)禁用隐式调用。

用 `request_user_input` 诊断、选方向和选课；失败依次用 MCP 表单、文本。按实际能力用 Web 搜索/页面读取生成两类地图；只提供介绍和规划，遵守沙箱与审批。
